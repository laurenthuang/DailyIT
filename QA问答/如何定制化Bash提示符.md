# Q: 如何定制化Bash提示符？

---
tags:
  - bash
  - prompt
  - tips
  - shell
  - linux
---
## PS1环境变量在线生成工具
https://bash-prompt-generator.org/


## 安装Statship
```bash
$ sudo apt install fonts-firacode
$ curl -sS https://starship.rs/install.sh | sh
$ echo 'eval "$(starship init bash)" >> ~/.bashrc

$ starship preset tokyo-night -o ~/.config/starship.toml

$ sed -i s/$'\ue711'/$'\ue712'/  ~/.config/starship.toml
$ sed -i 's/^\(truncation_length\) = 3/\1 = 10/' ~/.config/starship.toml
```
说明：第一个sed命令用来将apple logo替换成linux企鹅logo，第二个将directory中上级目录的显示个数增大到10
