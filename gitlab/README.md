gitlab.rb config file:

```rb
# --- SSH port ---
gitlab_rails['gitlab_shell_ssh_port'] = 2424

# --- Main URL ---
external_url 'https://git.gerardgascon.com'

# --- Disable Let's Encrypt ---
letsencrypt['enable'] = false

# --- Nginx Proxy Manager Settings ---
nginx['listen_port'] = 8888
nginx['listen_https'] = false

nginx['proxy_set_headers'] = {
    "Host" => "$http_host_with_default",
    "X-Forwarded-For" => "$proxy_add_x_forwarded_for",
    "X-Forwarded-Proto" => "https",
    "X-Forwarded-Ssl" => "on",
}

nginx['real_ip_header'] = 'X-Real-IP'
nginx['real_ip_recursive'] = 'on'

# --- GitLab SMTP ---
gitlab_rails['smtp_enable'] = true
gitlab_rails['smtp_address'] = "smtp.gmail.com"
gitlab_rails['smtp_port'] = 587
gitlab_rails['smtp_user_name'] = ""
gitlab_rails['smtp_password'] = ""
gitlab_rails['smtp_domain'] = "smtp.gmail.com"
gitlab_rails['smtp_authentication'] = "login"
gitlab_rails['smtp_enable_starttls_auto'] = true
gitlab_rails['smtp_tls'] = false
gitlab_rails['smtp_openssl_verify_mode'] = 'peer'
```