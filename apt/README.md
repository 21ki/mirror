```shell
install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://mirrors.bfsu.edu.cn/docker-ce/linux/debian \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  tee /etc/apt/sources.list.d/docker.list > /dev/null

# 切换北京外国语
sed -i.bak "s|mirrors.bfsu.edu.cn|mirrors.tuna.tsinghua.edu.cn|g" /etc/apt/sources.list.d/docker.list
# 切换debian版本
sed -i.bak "s|bookworm|$(lsb_release -sc)|g" /etc/apt/sources.list.d/docker.list
```
