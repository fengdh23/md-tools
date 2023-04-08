# 安装
![[Pasted image 20221219111846.png]]


1. 登录账号

![image.png](https://cdn.nlark.com/yuque/0/2022/png/2811836/1656381283142-d881b736-ffba-4429-964c-5c7f9a107617.png#clientId=ud99b94bb-eb8c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=440&id=u9fb7ffab&margin=%5Bobject%20Object%5D&name=image.png&originHeight=440&originWidth=721&originalType=binary&ratio=1&rotation=0&showTitle=false&size=31980&status=done&style=none&taskId=u9cb8a918-cb23-411f-bf4b-d288161c0f8&title=&width=721)

2. 安装依赖

![image.png](https://cdn.nlark.com/yuque/0/2022/png/2811836/1656381325928-97219578-62bd-4dc8-8349-ba428f8102e0.png#clientId=ud99b94bb-eb8c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=593&id=uab3d0ef2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=593&originWidth=717&originalType=binary&ratio=1&rotation=0&showTitle=false&size=41340&status=done&style=none&taskId=u432611f2-d8ad-4d77-a5e3-64c85ebdf60&title=&width=717)

3. 创建SSH 可选


# Git Flow

# 常见问题
## 错误: fatal: bad numeric config value '5242880000' for 'http.postbuffer': out of range
![image.png](https://cdn.nlark.com/yuque/0/2022/png/2811836/1656381559581-e3aa4e38-76a1-4c12-bf69-4c9d063a1e6b.png#clientId=ud99b94bb-eb8c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=491&id=u3583bff1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=491&originWidth=1012&originalType=binary&ratio=1&rotation=0&showTitle=false&size=46633&status=done&style=none&taskId=u42dfcb53-bd05-4347-9966-b024ec5ff85&title=&width=1012)
命令行执行  git config --global http.postBuffer 524288000, 
重启即可。原因是之前执行过 上面的命令，后面是4个0.

