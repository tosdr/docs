# Browser Extension Privacy

## Below is our extension privacy policy <a href="#browserextensionprivacy-belowisourextensionprivacypolicy" id="browserextensionprivacy-belowisourextensionprivacypolicy"></a>

Upon loading the extension, we retrieve a single json file containing all services and their respective urls from our API.

Additionally, when opening a popup the service data gets retrieved with all points and documents in it.

We also check for extension updates by calling the same service DB API which is hosted on the same API server.

The extension also displays hyperlinks to our website, but that will not affect your privacy if you don't actively click on them.

Other than that, installing this extensions does not expose information to us or to any of the websites you visit.

Your IP address will temporarily be visible in to Netcup who provide infrastructure.

We employ anonymized IP logging, this means nginx collects web requests but anonymizes IPs in the process

(Private IP used in the example below)

```
192.115.194.0 - - [01/May/2021:08:21:12 +0200] "GET /api/1/all.json HTTP/2.0" 200 753375 "-" "Mozilla/5.0 (Windows NT 6.1; Win64; x64; rv:88.0) Gecko/20100101 Firefox/88.0" "-"
```

Your IP may be stored temporarily in our Redis Cache in order to enforce rate limits.

For our assets such as logos, branding images we use a selfhosted S3: Minio.

#### Nginx IP logging configuration <a href="#browserextensionprivacy-nginxiploggingconfiguration" id="browserextensionprivacy-nginxiploggingconfiguration"></a>

```
map $remote_addr $ip_anonym1 {
    default 0.0.0;
    "~(?P<ip>(\d+)\.(\d+)\.(\d+))\.\d+" $ip;
    "~(?P<ip>[^:]+:[^:]+):" $ip;
}

map $remote_addr $ip_anonym2 {
    default .0;
    "~(?P<ip>(\d+)\.(\d+)\.(\d+))\.\d+" .0;
    "~(?P<ip>[^:]+:[^:]+):" ::;
}

map $ip_anonym1$ip_anonym2 $ip_anonymized {
    default 0.0.0.0;
    "~(?P<ip>.*)" $ip;
}

log_format anonymized '$ip_anonymized - $remote_user [$time_local] ' 
                      '"$request" $status $body_bytes_sent ' 
                      '"$http_referer" "$http_user_agent"';
access_log  /var/log/nginx/access.log  anonymized;
```
