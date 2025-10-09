# Q: 如何用命令行更新Cloudflare的DNS记录？

---
tags:
  - shell
  - dns
  - cloudflare
---
## 使用Curl命令

### 模板
```shell
curl https://api.cloudflare.com/client/v4/zones/$ZONE_ID/dns_records/$DNS_RECORD_ID \
    -X PATCH \
    -H 'Content-Type: application/json' \
    -H "X-Auth-Email: $CLOUDFLARE_EMAIL" \
    -H "X-Auth-Key: $CLOUDFLARE_API_KEY" \
    -d '{
      "comment": "Domain verification record",
      "content": "$NEW_IP",
      "name": "example.com",
      "proxied": true,
      "ttl": 3600,
      "type": "A"
    }'
```

### backforce.ip-ddns.com

- Zone ID: 0e9935da9af28ad81f39ed29fa301a9b
- Record ID: ee80baef627e2e8336b634664137d05e
- Record Type: A


```shell
curl https://api.cloudflare.com/client/v4/zones/0e9935da9af28ad81f39ed29fa301a9b/dns_records/ee80baef627e2e8336b634664137d05e \
    -X PATCH \
    -H 'Content-Type: application/json' \
    -H "X-Auth-Email: <email address>" \
    -H "X-Auth-Key: $CLOUDFLARE_API_KEY" \
    -d '{
      "comment": "test update",
      "content": "$NEW_IP",
      "name": "backforce.ip-ddns.com",
      "proxied": true,
      "ttl": 1,
      "type": "A"
    }'
```
