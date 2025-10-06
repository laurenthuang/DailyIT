# Q: 如何解决Python脚本Linux环境执行下载任务报自签署证书的问题？

---
tags:
  - python
  - troubleshooting
  - linux
  - shell
---


## 解决方法
先确认是不是`requests`模块执行时报错
```shell
export REQUESTS_CA_BUNDLE=/path/to/your/certificate.pem
python script.py

```
