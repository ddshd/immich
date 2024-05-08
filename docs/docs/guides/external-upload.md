Here is a sample nginx config for supporting external upload endpoints

```
add_header Access-Control-Allow-Origin "EXTERNAL_DOMAIN" always;
#add_header Access-Control-Allow-Credentials 'true' always;
add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS' always;
add_header Access-Control-Allow-Headers 'Accept' always;

if ($request_method = 'OPTIONS') {
add_header Access-Control-Allow-Origin "EXTERNAL_DOMAIN" always;
add_header Access-Control-Allow-Credentials 'true' always;
add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS' always;
            add_header 'Access-Control-Allow-Headers' 'content-type';
            return 200;
}
```