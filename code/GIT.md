#git #版本管理

# 学习资料
官方
视频
其他
# 介绍
是什么
优点
缺点

# GIT安装
linux环境

docker 方式

## Git GUI使用方法 不推荐
**前言**
之前一直想一篇这样的东西，因为最初接触时，我也认真看了廖雪峰的教程，但是似乎我觉得讲得有点多，而且还是会给我带来很多多余且重复的操作负担，所以我希望能压缩一下它在我工作中的成本，但是搜索了一下并没有找到满意的教程，新的一年自己梳理一下自己的经验。
可能男生们大神比较多，觉得Git是如此简单，便已觉得命令行操作就是SO EASY，甚至或许有看不起可视化这样面对低端用户的心理，好的，那您就当我是水货可以右上角了。
我一直觉得类似GIT这样的东西，他对于我而言只是个不完全必须的工具，我并不想成为使用他的专家，类似的东西，今天有GIT，明天可能有GAT，或者GAY？所以快速地掌握它我需要的重要日常操作，最好是10分钟，那就好了，如果你有类似的想法，好吧，那不要废话了，咱们赶紧开始。
**（全文限windows系统。）**
**何为GIT？**
[安装GIT](http://git-scm.com/download/)，大致了解下[GIT是做某子的](http://baike.baidu.com/link?url=_aNWZrVpQm9L89S4CYR66kVd6MZhQWXY5mO8zJfoTCEvQ7rkZdZOYOOyzA5IGO6kL2hw34M7r2wXixw6GNTTmk9kRAXHuIav23kej67ITc7)。
**权限校验**
首先,您的数据保存在远端服务器一份，服务器需要对您的身份识别。一段RSA加密字符串。
启动GUI，菜单-帮助，【Step1-**创建密钥】**Generate SSH KEY
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858853695-ea88807b-2b20-4f19-afdf-de2349f874c2.png#averageHue=%23cf5946&clientId=u6748753d-b83d-4&from=paste&id=u65cba849&name=image.png&originHeight=260&originWidth=506&originalType=url&ratio=1&rotation=0&showTitle=false&size=23207&status=done&style=none&taskId=uf6605e78-1993-4cb1-83d8-2879340526d&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271102462211960.png)
【Step2-**添加密钥】**去你的代码托管服务器，你的账号设置中，添加它。
比如在Github中的地址，title随意，比如你可以用Home,company等作为标识来区别。
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858853944-fd11343f-9b10-48d9-ae01-1623e95b0aa0.png#averageHue=%23fbfaf9&clientId=u6748753d-b83d-4&from=paste&id=u64b9d992&name=image.png&originHeight=568&originWidth=1031&originalType=url&ratio=1&rotation=0&showTitle=false&size=58410&status=done&style=none&taskId=u143c5378-c314-4bab-b21b-4496c2d295d&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271104566587275.png)
Gitlab中的演示
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858853712-45e58c40-29a9-4277-b6b2-18674703957d.png#averageHue=%23fafaf9&clientId=u6748753d-b83d-4&from=paste&id=uebf1ebd8&name=image.png&originHeight=389&originWidth=1918&originalType=url&ratio=1&rotation=0&showTitle=false&size=49386&status=done&style=none&taskId=u5d680c25-52b9-4090-ab20-3f0e0f6b79e&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271108115808959.png)
**账号保存**
如果不做设置的话，每次提交的时候，都会询问你填写密码。于是我们先来把这个设置好。
【Step3.1-添加环境变量**】**
**我的电脑 - 属性 - 高级系统设置 - 环境变量 - 新建变量**
**变量名HOME，变量值%USERPROFILE%**
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858853771-d17ef54c-3728-4fa6-9ac8-759feb7b43cb.png#averageHue=%23d7daad&clientId=u6748753d-b83d-4&from=paste&id=u0bac41e5&name=image.png&originHeight=279&originWidth=262&originalType=url&ratio=1&rotation=0&showTitle=false&size=31483&status=done&style=none&taskId=u06151cf5-85ec-454a-86e0-5a9713c0018&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271117100641718.png)

[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858853731-4c765b91-8b3d-460e-80eb-29be7e59a55e.png#averageHue=%23baeeeb&clientId=u6748753d-b83d-4&from=paste&id=u0415b0cf&name=image.png&originHeight=239&originWidth=356&originalType=url&ratio=1&rotation=0&showTitle=false&size=36528&status=done&style=none&taskId=uea04fdb1-e28b-4031-813e-9e8fea80ef3&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271117191748667.png)

[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858854556-90e3bb87-bd5d-447d-8c07-5edfb6cf70bf.png#averageHue=%23efeded&clientId=u6748753d-b83d-4&from=paste&id=uda55adb4&name=image.png&originHeight=433&originWidth=406&originalType=url&ratio=1&rotation=0&showTitle=false&size=22467&status=done&style=none&taskId=u6264884f-60d5-40be-9901-9497bc50c4c&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271117300493045.png)

[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858854623-fdf9ce6c-80fa-4ec9-a9be-e8f9832adfe1.png#averageHue=%23e6e5e2&clientId=u6748753d-b83d-4&from=paste&id=uc8e92aff&name=image.png&originHeight=396&originWidth=388&originalType=url&ratio=1&rotation=0&showTitle=false&size=24884&status=done&style=none&taskId=ucebd5fa0-5a74-41e3-b32b-be96907f165&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271117384245853.png)
**【Step3.2-创建账号文件】**
**开始 - 运行 中打开%Home%，即windows的管理员账号文件夹。**
**新建一个名为"_netrc"的文件，填写你要保存的服务器地址及账号密码，保存。**
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858854801-7e257080-c0b0-4d0b-ada9-974b266aa3e5.png#averageHue=%23e4d598&clientId=u6748753d-b83d-4&from=paste&id=u90e3a225&name=image.png&originHeight=344&originWidth=946&originalType=url&ratio=1&rotation=0&showTitle=false&size=65089&status=done&style=none&taskId=u9196da04-2e55-4aed-bbc0-e85ba22023d&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271123307214691.png)

[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858855057-ce830db1-4b81-4ae1-801f-5329f0fc2b21.png#averageHue=%23292a24&clientId=u6748753d-b83d-4&from=paste&id=u48ded2ef&name=image.png&originHeight=215&originWidth=255&originalType=url&ratio=1&rotation=0&showTitle=false&size=6850&status=done&style=none&taskId=u1e0044b7-91d4-40a5-9fd5-0a90bd5a76b&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271123401437312.png)
**操作流程**
如果你用过SVN的话就会大致了解操作流程，如果没有也没关系。
**初始化**（Git init）
顾名思义，就是新建一个项目，跟你用PS新建一张画布一样。在你新建好的文件夹中右键创建即可，若点击Git bash则以此目录作为当前目录进入命令行状态。
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858855860-089b4003-477b-4c71-b6c7-eb8ce800833b.png#averageHue=%23d9c67b&clientId=u6748753d-b83d-4&from=paste&id=uc0708624&name=image.png&originHeight=607&originWidth=1024&originalType=url&ratio=1&rotation=0&showTitle=false&size=81258&status=done&style=none&taskId=uec7e8461-1f22-42e0-b0b7-07e3ce61ebf&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271234025648572.png)
**添加**（Git add）
添加并不是提交代码到远程Git库，Git也并不会你修改了代码它自动帮你保存你修改的每一个过程。你修改了很多文件，但未必所有的修改，最终打算提交上去，那么哪些是你打算提交的，你可以添加进来待会提交，叫做缓存改动。很简单，比如本地电脑上我有整个项目完整的东东，甚至包含了账号密码的一些文件，但是我只是ADD除账号密码之外的文件，并不缓存账号密码文件的改动。不被ADD它就不会参与后续的操作。通常我都会直接全部缓存，它会自动寻找所有有改动的文件，而不需要提交的文件放在忽略的文件夹中。（关于忽略下面我们就会说到）
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858855894-e264c387-be85-4b24-a7e4-6a584d73df05.png#averageHue=%23dac57e&clientId=u6748753d-b83d-4&from=paste&id=u94d52857&name=image.png&originHeight=607&originWidth=1024&originalType=url&ratio=1&rotation=0&showTitle=false&size=86768&status=done&style=none&taskId=u17f5517d-ff6b-40cb-8263-0e9759d35a6&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271238259396476.png)
**忽略**（.gitignore）
但实际上大部分我们的文件都是一起提交的，并不会逐一去甄选，又或者类似PSD这样的大源文件以及并不作为产品最终展示的过渡文件，我们可以统一放在临时文件夹中，并忽略此文件夹。
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858855947-1500969e-7838-4b65-9ee0-8b963c2bf84f.png#averageHue=%23f5f4f1&clientId=u6748753d-b83d-4&from=paste&id=ue821d7af&name=image.png&originHeight=462&originWidth=344&originalType=url&ratio=1&rotation=0&showTitle=false&size=23021&status=done&style=none&taskId=ub9ad70b7-c435-46aa-b2cc-f789805c37e&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271134259394618.png)
**提交**（Git commit）
提交则代表此前被添加ADD的文件已确认被提交到Git库了。需要注意的是，如果你改变代码的缩进（尽管没有修改内容），默认状态下会被识别为整个代码全部变更。**提交的时候是要求必须要写备注的**。
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858856248-7c1dc556-03d3-43d9-9ad1-8fe6a163a3b3.png#averageHue=%23f2f2f1&clientId=u6748753d-b83d-4&from=paste&id=uedc18dde&name=image.png&originHeight=184&originWidth=584&originalType=url&ratio=1&rotation=0&showTitle=false&size=10464&status=done&style=none&taskId=ud86dadba-355a-4242-a9cf-8a944378c8b&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271240398302205.png)
**上传**（Git push）
顾名思义，上传则是上至远端服务器了，小伙伴们可以看到咱们的渣渣代码了（好羞涩。
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858856715-89e91ba8-d5ed-4a02-bfe8-53d08dd08a85.png#averageHue=%23f4f3f3&clientId=u6748753d-b83d-4&from=paste&id=ucc3411d5&name=image.png&originHeight=494&originWidth=536&originalType=url&ratio=1&rotation=0&showTitle=false&size=29934&status=done&style=none&taskId=u1ac5144e-5bed-41ff-9af1-f12f5529777&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271241402522046.png)
**获取远程代码**（Git remote/fetch）
比如你在公司做好的东东，今夜难眠十分亢奋，回家准备继续搬砖，那咱们就在家里的电脑上，同上进行好各种安装配置账号，先把公司做好的东东嫩下来（不过公司是内网不可以，但是假如是Github上是可以的）。又或者和小伙伴一起开发个啥，你也要先fetch他的下来。至于怎么操作，下面上图。现在你只要知道，大大们下齿全露刷牙表情对你口口念念的fetch是个啥子～
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858856888-b74f57d8-5c06-4dcd-a2e9-537af2b8f112.png#averageHue=%23535964&clientId=u6748753d-b83d-4&from=paste&id=ue2096557&name=image.png&originHeight=76&originWidth=75&originalType=url&ratio=1&rotation=0&showTitle=false&size=10874&status=done&style=none&taskId=ud925a2c3-b958-42bb-b783-7497bebf85a&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271145255335341.png)
来，跟我念，fetch~~（我怕你们脑补不出来……）
**先来设置与远程地址的关联，Git remote：**
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858856995-ecff5d5c-d784-46fc-89e2-ae73209235fd.png#averageHue=%23f6f3eb&clientId=u6748753d-b83d-4&from=paste&id=ue0224e0a&name=image.png&originHeight=533&originWidth=815&originalType=url&ratio=1&rotation=0&showTitle=false&size=50914&status=done&style=none&taskId=u64367947-7718-47f9-88a1-4314e5c033a&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271242561118002.png)

[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858856971-d20f2f90-eaf3-4abb-bd67-8ae5f90fab34.png#averageHue=%23edebe9&clientId=u6748753d-b83d-4&from=paste&id=u734c2525&name=image.png&originHeight=277&originWidth=375&originalType=url&ratio=1&rotation=0&showTitle=false&size=16832&status=done&style=none&taskId=ueb3e6f4a-db78-4373-87ff-af946ce778d&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271244220336453.png)
填写SSH地址与项目名。下面有3个选项：
第一个：立刻获取最新改动（所以如果是本地克隆远程一个项目，也可以这样操作）。
第二个：本地新建的项目，初始化远程仓库并发布过去。
第三个：什么也不做。
**在项目的进行过程中，获取仓库的最新改动Git fetch**
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858857196-51042b40-a978-4158-9245-6897675142e5.png#averageHue=%23f8f6ef&clientId=u6748753d-b83d-4&from=paste&id=u06e647d3&name=image.png&originHeight=673&originWidth=1176&originalType=url&ratio=1&rotation=0&showTitle=false&size=48761&status=done&style=none&taskId=ue4f66825-3e84-4bf5-8898-a75b3af9680&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271259025495085.png)
选择从远程仓库哪个分支中获取更新，如果没有则只有主支。
提示成功则改动的已经被存放到临时区了，你一会还需要进行合并操作，如果没有任何改动，则列表中是空的，比如：
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858857506-f4e11208-121f-46c6-bb33-6f3cdfb86372.png#averageHue=%23f5f5f4&clientId=u6748753d-b83d-4&from=paste&id=uc5aa2414&name=image.png&originHeight=280&originWidth=604&originalType=url&ratio=1&rotation=0&showTitle=false&size=15813&status=done&style=none&taskId=u51b2e522-d04a-4615-b902-16942c437fa&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271300329558531.png)
**合并**（Git merge）
请注意啦，不管你本地有没有代码，fetch之后呢，是都要merge的，也就是说，fetch下来后，大大的代码还在一个小黑屋里，我们需要把它装到自己兜里。
选择合并 - 本地合并，然后选择本地的分支（如果你没有创建分支，则只有1个主支master）
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858857547-11db3e0e-348a-40ff-b928-a9259c1020a0.png#averageHue=%23f2eee4&clientId=u6748753d-b83d-4&from=paste&id=u70000f05&name=image.png&originHeight=528&originWidth=813&originalType=url&ratio=1&rotation=0&showTitle=false&size=55646&status=done&style=none&taskId=uc5c15c7c-fa4f-48f2-8f07-fbf7dff8b2b&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271254126278757.png)
**冲突处理**（Conflict）
合并的过程中可能会出现一些红色的文件与一堆叹号，这时候慌慌张张的点啥它都不管用，不用担心，不是程序坏了，只是有冲突的文件，例如A童鞋写了width:1180px，你写了width:auto。那到底用你们谁的呢。
在GUI界面正文区，**正文区右键**可以选择，Use local version（使用本地版本）或Use remote version（使用远程版本），到底用你的还是小伙伴的？或者你也可以自己再整合。
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858857892-8a098b0b-5950-4f3b-a65e-abe110856e66.png#averageHue=%23ddba3c&clientId=u6748753d-b83d-4&from=paste&id=u9ccbf2d4&name=image.png&originHeight=825&originWidth=824&originalType=url&ratio=1&rotation=0&showTitle=false&size=161219&status=done&style=none&taskId=u24717782-2bea-45e7-b8a5-5a6feaecea2&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271257485644055.png)
其他还有分支和一些高级功能，如果需要了解可以自己再摸索摸索，以上的操作已经可以满足简单的开发需求了。
**总结**
1.先进行安装，密钥添加，账号等一次性操作。
2.操作流程：
[![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858858057-acb93a72-86b1-402a-bdbd-709194023b71.png#averageHue=%23f9f9f8&clientId=u6748753d-b83d-4&from=paste&id=uab59223a&name=image.png&originHeight=209&originWidth=830&originalType=url&ratio=1&rotation=0&showTitle=false&size=29679&status=done&style=none&taskId=ua3dee7af-f444-419b-b3c9-0c6b588ff39&title=)](https://www.runoob.com/wp-content/uploads/2015/03/271314500648180.png)
是不是觉得so easy了呢，赶紧have a try!
## Sourcetree gitlow 推荐
# 
# GitLab
GitLab是一款使用MIT许可证的基于网络的Git仓库管理工具，我们可以使用它来搭建自己的Git仓库
## 安装-docker
**下载Gitlab的Docker镜像**
docker pull gitlab/gitlab-ce
**运行如下命令来启动Gitlab**
需要注意的是我们的Gitlab的http服务运行在宿主机的1080端口上，这里我们将Gitlab的配置，日志以及数据目录映射到了宿主机的指定文件夹下，防止我们在重新创建容器后丢失数据。
docker run --detach \
--publish 10443:443 --publish 1080:80 --publish 1022:22 \
--name gitlab \
--restart always \
--volume /mydata/gitlab/config:/etc/gitlab \
--volume /mydata/gitlab/logs:/var/log/gitlab \
--volume /mydata/gitlab/data:/var/opt/gitlab \
gitlab/gitlab-ce:latest
**开启防火墙的指定端口**
由于Gitlab运行在1080端口上，所以我们需要开放该端口，注意千万不要直接关闭防火墙，否则Gitlab会无法启动。
_# 开启1080端口_
firewall-cmd --zone=public --add-port=1080/tcp --permanent
_# 重启防火墙才能生效_
systemctl restart firewalld
_# 查看已经开放的端口_
firewall-cmd --list-ports
**访问Gitlab**

- 访问地址：http://192.168.3.101:1080/
- 由于Gitlab启动比较慢，需要耐心等待10分钟左右，如果Gitlab没有启动完成访问，会出现如下错误。
- 可以通过docker命令动态查看容器启动日志来知道gitlab是否已经启动完成。

docker logs gitlab -f
**Gitlab的使用**
**Gitlab启动完成后第一次访问，会让你重置root帐号的密码**
![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858680589-bf32c407-8420-4fe1-b941-7a71ebb44c75.png#averageHue=%23fcfcfb&clientId=u6748753d-b83d-4&from=paste&id=u247ce574&name=image.png&originHeight=479&originWidth=999&originalType=url&ratio=1&rotation=0&showTitle=false&size=43813&status=done&style=none&taskId=ubd78be05-8f70-464f-886a-06da38ff708&title=)
**重置完成后输入帐号密码登录**
**选择创建项目、创建组织、创建帐号**
**创建组织**
首先我们需要创建一个组织，然后在这个组织下分别创建用户和项目，这样同组织的用户就可以使用该组织下的项目了。
**创建用户并修改密码**
**找到添加用户的按钮**
**输入用户名密码添加用户**
**在编辑界面中修改用户密码**

**创建项目并添加README文件**

![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858680568-6c79ed20-d1af-4cfa-ac29-51dacce844a8.png#averageHue=%23fcfbfa&clientId=u6748753d-b83d-4&from=paste&id=ue713f4b1&name=image.png&originHeight=308&originWidth=998&originalType=url&ratio=1&rotation=0&showTitle=false&size=29153&status=done&style=none&taskId=u8fcaf2db-4910-4d81-92da-57a95d42462&title=)
**将用户分配到组织**

# 常用命令
一般使用图形化工具，比如ide里面的插件、**Sourcetree**。
一、 Git 常用命令速查

git branch 查看本地所有分支
git status 查看当前状态 
git commit 提交 
git branch -a 查看所有的分支
git branch -r 查看远程所有分支
git commit -am "init" 提交并且加注释 
git remote add origin git@192.168.1.119:ndshow
git push origin master 将文件给推到服务器上 
git remote show origin 显示远程库origin里的资源 
git push origin master:develop
git push origin master:hb-dev 将本地库与服务器上的库进行关联 

### checkout 切换
git checkout --track origin/dev 切换到远程dev分支
git branch -D master develop 删除本地库develop
git checkout -b dev 建立一个新的本地分支dev
git merge origin/dev 将分支dev与当前分支进行合并
git checkout dev 切换到本地dev分支
git remote show 查看远程库
git add .
git rm 文件名(包括路径) 从git中删除指定文件
git clone git://github.com/schacon/grit.git 从服务器上将代码给拉下来
git config --list 看所有用户
git ls-files 看已经被提交的
git rm [file name] 删除一个文件
git commit -a 提交当前repos的所有的改变
git add [file name] 添加一个文件到git index
git commit -v 当你用－v参数的时候可以看commit的差异
git commit -m "This is the message describing the commit" 添加commit信息
git commit -a -a是代表add，把所有的change加到git index里然后再commit
git commit -a -v 一般提交命令
git log 看你commit的日志
git diff 查看尚未暂存的更新
git rm a.a 移除文件(从暂存区和工作区中删除)
git rm --cached a.a 移除文件(只从暂存区中删除)
git commit -m "remove" 移除文件(从Git中删除)
git rm -f a.a 强行移除修改后文件(从暂存区和工作区中删除)
git diff --cached 或 $ git diff --staged 查看尚未提交的更新
git stash push 将文件给push到一个临时空间中
git stash pop 将文件从临时空间pop下来
---------------------------------------------------------
git remote add origin git@github.com:username/Hello-World.git
git push origin master 将本地项目给提交到服务器中
-----------------------------------------------------------
git pull 本地与服务器端同步
-----------------------------------------------------------------
git push (远程仓库名) (分支名) 将本地分支推送到服务器上去。
git push origin serverfix:awesomebranch
------------------------------------------------------------------
git fetch 相当于是从远程获取最新版本到本地，不会自动merge
git commit -a -m "log_message" (-a是提交所有改动，-m是加入log信息) 本地修改同步至服务器端 ：
git branch branch_0.1 master 从主分支master创建branch_0.1分支
git branch -m branch_0.1 branch_1.0 将branch_0.1重命名为branch_1.0
git checkout branch_1.0/master 切换到branch_1.0/master分支
du -hs

git branch 删除远程branch
git push origin :branch_remote_name
git branch -r -d branch_remote_name
-----------------------------------------------------------

初始化版本库，并提交到远程服务器端
mkdir WebApp
cd WebApp
git init 本地初始化
touch README
git add README 添加文件
git commit -m 'first commit'
git remote add origin git@github.com:daixu/WebApp.git

增加一个远程服务器端

上面的命令会增加URL地址为'git@github.com:daixu/WebApp.git'，名称为origin的远程服务器库，以后提交代码的时候只需要使用 origin别名即可

二、 Git 命令速查表

1、常用的Git命令
命令
简要说明
git add  添加至暂存区
git add–interactive 交互式添加
git apply 应用补丁
git am 应用邮件格式补丁
git annotate

同义词，等同于 git blame

git archive

文件归档打包

git bisect

二分查找

git blame

文件逐行追溯

git branch

分支管理

git cat-file

版本库对象研究工具

git checkout

检出到工作区、切换或创建分支

git cherry-pick

提交拣选

git citool

图形化提交，相当于 git gui 命令

git clean 清除工作区未跟踪文件

**git clone 克隆版本库**

**git commit 提交**

git config

查询和修改配置

git describe

通过里程碑直观地显示提交ID

git diff  差异比较

git difftool 调用图形化差异比较工具

**git fetch 获取远程版本库的提交**

git format-patch

创建邮件格式的补丁文件。参见 git am 命令

git grep

文件内容搜索定位工具

git gui

基于Tcl/Tk的图形化工具，侧重提交等操作

git help

帮助

git init  版本库初始化

git init-db*

同义词，等同于 git init

git log  显示提交日志

git merge 分支合并
git mergetool 图形化冲突解决

git mv 重命名

**git pull 拉回远程版本库的提交**

**git push 推送至远程版本库**

**git rebase 分支变基**

**git rebase–interactive 交互式分支变基**

git reflog

分支等引用变更记录管理

git remote

远程版本库管理

git repo-config*

同义词，等同于 git config

git reset

重置改变分支“游标”指向

git rev-parse

将各种引用表示法转换为哈希值等

git revert

反转提交

git rm

删除文件

git show

显示各种类型的对象

git stage*

同义词，等同于 git add

git stash

保存和恢复进度

git status

显示工作区文件状态

git tag

里程碑管理


2、对象库操作相关命令

命令

简要说明

git commit-tree

从树对象创建提交

git hash-object

从标准输入或文件计算哈希值或创建对象

git ls-files

显示工作区和暂存区文件

git ls-tree

显示树对象包含的文件

git mktag

读取标准输入创建一个里程碑对象

git mktree

读取标准输入创建一个树对象

git read-tree

读取树对象到暂存区

git update-index

工作区内容注册到暂存区及暂存区管理

git unpack-file

创建临时文件包含指定 blob 的内容

git write-tree

从暂存区创建一个树对象


3、引用操作相关命令

命令

简要说明

git check-ref-format

检查引用名称是否符合规范

git for-each-ref

引用迭代器，用于shell编程

git ls-remote

显示远程版本库的引用

git name-rev

将提交ID显示为友好名称

git peek-remote*

过时命令，请使用 git ls-remote

git rev-list

显示版本范围

git show-branch

显示分支列表及拓扑关系

git show-ref

显示本地引用

git symbolic-ref

显示或者设置符号引用

git update-ref

更新引用的指向

git verify-tag

校验 GPG 签名的Tag


4、版本库管理相关命令

命令

简要说明

git count-objects

显示松散对象的数量和磁盘占用

git filter-branch

版本库重构

git fsck

对象库完整性检查

git fsck-objects*

同义词，等同于 git fsck

git gc

版本库存储优化

git index-pack

从打包文件创建对应的索引文件

git lost-found*

过时，请使用 git fsck –lost-found 命令

git pack-objects

从标准输入读入对象ID，打包到文件

git pack-redundant

查找多余的 pack 文件

git pack-refs

将引用打包到 .git/packed-refs 文件中

git prune

从对象库删除过期对象

git prune-packed

将已经打包的松散对象删除

git relink

为本地版本库中相同的对象建立硬连接

git repack

将版本库未打包的松散对象打包

git show-index

读取包的索引文件，显示打包文件中的内容

git unpack-objects

从打包文件释放文件

git verify-pack

校验对象库打包文件


5、数据传输相关命令

命令

简要说明

git fetch-pack

执行 git fetch 或 git pull 命令时在本地执行此命令，用于从其他版本库获取缺失的对象

git receive-pack

执行 git push 命令时在远程执行的命令，用于接受推送的数据

git send-pack

执行 git push 命令时在本地执行的命令，用于向其他版本库推送数据

git upload-archive

执行 git archive –remote 命令基于远程版本库创建归档时，远程版本库执行此命令传送归档

git upload-pack

执行 git fetch 或 git pull 命令时在远程执行此命令，将对象打包、上传


6、邮件相关命令

命令

简要说明

git imap-send

将补丁通过 IMAP 发送

git mailinfo

从邮件导出提交说明和补丁

git mailsplit

将 mbox 或 Maildir 格式邮箱中邮件逐一提取为文件

git request-pull

创建包含提交间差异和执行PULL操作地址的信息

git send-email

发送邮件


7、协议相关命令

命令

简要说明

git daemon

实现Git协议

git http-backend

实现HTTP协议的CGI程序，支持智能HTTP协议

git instaweb

即时启动浏览器通过 gitweb 浏览当前版本库

git shell

受限制的shell，提供仅执行Git命令的SSH访问

git update-server-info

更新哑协议需要的辅助文件

git http-fetch

通过HTTP协议获取版本库

git http-push

通过HTTP/DAV协议推送

git remote-ext

由Git命令调用，通过外部命令提供扩展协议支持

git remote-fd

由Git命令调用，使用文件描述符作为协议接口

git remote-ftp

由Git命令调用，提供对FTP协议的支持

git remote-ftps

由Git命令调用，提供对FTPS协议的支持

git remote-http

由Git命令调用，提供对HTTP协议的支持

git remote-https

由Git命令调用，提供对HTTPS协议的支持

git remote-testgit

协议扩展示例脚本


8、版本库转换和交互相关命令

命令

简要说明

git archimport

导入Arch版本库到Git

git bundle

提交打包和解包，以便在不同版本库间传递

git cvsexportcommit

将Git的一个提交作为一个CVS检出

git cvsimport

导入CVS版本库到Git。或者使用 cvs2git

git cvsserver

Git的CVS协议模拟器，可供CVS命令访问Git版本库

git fast-export

将提交导出为 git-fast-import 格式

git fast-import

其他版本库迁移至Git的通用工具

git svn

Git 作为前端操作 Subversion


9、合并相关的辅助命令

命令

简要说明

git merge-base

供其他脚本调用，找到两个或多个提交最近的共同祖先

git merge-file

针对文件的两个不同版本执行三向文件合并

git merge-index

对index中的冲突文件调用指定的冲突解决工具

git merge-octopus

合并两个以上分支。参见 git merge 的octopus合并策略

git merge-one-file

由 git merge-index 调用的标准辅助程序

git merge-ours

合并使用本地版本，抛弃他人版本。参见 git merge 的ours合并策略

git merge-recursive

针对两个分支的三向合并。参见 git merge 的recursive合并策略

git merge-resolve

针对两个分支的三向合并。参见 git merge 的resolve合并策略

git merge-subtree

子树合并。参见 git merge 的 subtree 合并策略

git merge-tree

显式三向合并结果，不改变暂存区

git fmt-merge-msg

供执行合并操作的脚本调用，用于创建一个合并提交说明

git rerere

重用所记录的冲突解决方案


10、 杂项

命令

简要说明

git bisect–helper

由 git bisect 命令调用，确认二分查找进度

git check-attr

显示某个文件是否设置了某个属性

git checkout-index

从暂存区拷贝文件至工作区

git cherry

查找没有合并到上游的提交

git diff-files

比较暂存区和工作区，相当于 git diff –raw

git diff-index

比较暂存区和版本库，相当于 git diff –cached –raw

git diff-tree

比较两个树对象，相当于 git diff –raw A B

git difftool–helper

由 git difftool 命令调用，默认要使用的差异比较工具

git get-tar-commit-id

从 git archive 创建的 tar 包中提取提交ID

git gui–askpass

命令 git gui 的获取用户口令输入界面

git notes

提交评论管理

git patch-id

补丁过滤行号和空白字符后生成补丁唯一ID

git quiltimport

将Quilt补丁列表应用到当前分支

git replace

提交替换

git shortlog

对 git log 的汇总输出，适合于产品发布说明

git stripspace

删除空行，供其他脚本调用

git submodule

子模组管理

git tar-tree

过时命令，请使用 git archive

git var

显示 Git 环境变量

git web–browse

启动浏览器以查看目录或文件

git whatchanged

显示提交历史及每次提交的改动

git-mergetool–lib

包含于其他脚本中，提供合并/差异比较工具的选择和执行

git-parse-remote

包含于其他脚本中，提供操作远程版本库的函数

git-sh-setup

包含于其他脚本中，提供 shell 编程的函数库


# 特性
主干master、branch 分支、tag(不可修改一般是上线成功的版本)
# 最佳实践
## 提交规范
taskID:{} 
desc:{}
bugID:{}
desc{}
最简单直接，关联业务、bug。
## 分支合到主干master
1.首先将idea中的代码分支切换到master分支，可以看到我们在dev上提交的代码 在master上是没有的
![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858947278-f60a5d0b-b3bf-4a8c-84a5-1af61c6633f6.png#averageHue=%23f6f4f1&clientId=u6748753d-b83d-4&from=paste&id=u1492b374&name=image.png&originHeight=423&originWidth=715&originalType=url&ratio=1&rotation=0&showTitle=false&size=39190&status=done&style=none&taskId=u3837654f-3aaa-48a8-87ff-d9c9a547915&title=)


2.如图所示，在remote branch 上选择分支，点击后面的三角图标，展开之后选择Merge into current
![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858947248-e60cac7b-86e8-44a3-8ab5-75b3311ca869.png#averageHue=%23f6f5f3&clientId=u6748753d-b83d-4&from=paste&id=u9c66c3a0&name=image.png&originHeight=426&originWidth=668&originalType=url&ratio=1&rotation=0&showTitle=false&size=33912&status=done&style=none&taskId=udfb7d568-734b-4a09-9b2d-683cbe32437&title=)


3.合并过程中可能会出现主干代码和自己分支代码冲突，需要手动解决冲突，合并完成之后会如图提示信息
![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858947567-4f643981-ebfb-43cd-9e71-e4ce02519540.png#averageHue=%23494e50&clientId=u6748753d-b83d-4&from=paste&id=u34692fdf&name=image.png&originHeight=182&originWidth=631&originalType=url&ratio=1&rotation=0&showTitle=false&size=78788&status=done&style=none&taskId=u189558e2-6ffd-4a07-9894-4652af2c46b&title=)


4.此时合并完成只是在自己电脑本地，还没有提交到远程服务器，最后将合并好的代码push到远程即可大功告成
注意：
版本合并完成之后还没有提交到远程服务器，此时可以检查是否合并有问题，合并错了可以选择revert然后重新合并
在点击revert后 发现再进行之前的合并步骤会报一下错误
You have not concluded your merge (MERGE_HEAD exists). Please, commit your changes before you merge.
此时你可以先保留本地的修改
点击idea的命令行窗口Terminal
![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858947108-31bbf67a-e153-43cc-99ef-46f43e8f807c.png#averageHue=%23f8f6f4&clientId=u6748753d-b83d-4&from=paste&id=ud115890f&name=image.png&originHeight=473&originWidth=866&originalType=url&ratio=1&rotation=0&showTitle=false&size=32401&status=done&style=none&taskId=u6a761532-777d-48d6-a269-b9ebbad5c03&title=)

然后输入以下命令 保留你本地的修改
git merge --abort
git reset --merge
然后再执行以上的合并master步骤，进行重新合并。合并后 将代码推送到远端即可

来自 <[https://www.cnblogs.com/chcha1/p/12588711.html](https://www.cnblogs.com/chcha1/p/12588711.html)> 
## 主干合到分支
正常来说，而且现在网上的教程都在说，分支同步到主干的办法，今天因为项目需求，需要将主干的项目全部合并到分支上，正常的都会，反过来就不会了，这个问题，我也是找了很久才知道解决办法，当然如果有人能知道其他的更好的办法，希望能够留言交流。
首先，我们要打开我们的分支项目，在右下角找到如下的内容
![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858951107-023d08b1-a618-4d74-829d-a81f232beaa6.png#averageHue=%23ded9d9&clientId=u6748753d-b83d-4&from=paste&id=u60ceb783&name=image.png&originHeight=380&originWidth=603&originalType=url&ratio=1&rotation=0&showTitle=false&size=47380&status=done&style=none&taskId=u2651cff1-d790-4326-9670-ba3f7bce827&title=)
（19-02-21 下午）最新更改：以测试过，我第二次需要同步主干上的项目的时候同样是这样点击以拉取到最新的主干的程序
（19-2-25 上午）根据项目需求，又进行一次合并，测试功能正常，合并完成。
我们要选中主干的内容，然后单击“Merge into Current”,即可。
注：
1.在合并的时候如果出现了你代码之外的任何文件，及有可能是自动生成的文件，直接删除该文件即可（要再三确认是无用的并且是自动生成的文件）。
2.如果出现文件冲突，他会让你选择是接受你的（就是自己的意思）还是接受主干的版本，然后你需要将分支的版本文件都粘贴出来，然后再返回点击接受主干的文件，到后续了再针对这些冲突的慢慢修改。（这一步我也没有想到太好的解决办法）
3.如果中间出现了什么冲突，比如鄙人遇到的“You have not concluded your merge (MERGE_HEAD exists).”这个问题，对不起，我解决不了，你只能回滚项目了（尴尬。。。）问题原因我也不是很清楚，至于造成这个问题的过程我可以和你们说一下，是在我有冲突文件的时候，我选择了。。。我忘了。。。（尴尬。。。）反正就是出现这个问题了。我弄了半天也解决不了，就回滚了项目，回滚项目的博客我也写了，大家要用的直接去找就可以了。感谢。。。
直到你看见了这个
![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858951086-61a0c832-503b-431c-8ae0-96a40b620383.png#averageHue=%23e7e6e4&clientId=u6748753d-b83d-4&from=paste&id=ud7415961&name=image.png&originHeight=76&originWidth=187&originalType=url&ratio=1&rotation=0&showTitle=false&size=1550&status=done&style=none&taskId=ud252085a-e7a8-4dec-8457-cfb91e8c146&title=)
你就算是大功告成了，等你去翻Git日志记录的时候你会发现它会显示的就这俩文件
![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631858951081-99f4a51d-7c61-4057-870e-4076c5acf8fb.png#averageHue=%23fcfaf7&clientId=u6748753d-b83d-4&from=paste&id=udea9937a&name=image.png&originHeight=45&originWidth=159&originalType=url&ratio=1&rotation=0&showTitle=false&size=1317&status=done&style=none&taskId=uf6f8c6f3-b063-4a70-b241-b9cde42e3dc&title=)
这个文件可能每个人遇见的不同(详细的我也不是很清楚)，这个不要紧，你需要去检查一下代码是否都过来了，如果都过来了那就没问题了，反正idea自带的这个日志记录里是不详细的。
注：在自己的项目里，你也找不到蓝色的文件（修改过的文件）和绿色文件（新的文件），他们会统一变成黑色文件。

来自 <[https://blog.csdn.net/weixin_40836179/article/details/87003899](https://blog.csdn.net/weixin_40836179/article/details/87003899)> 
## 删除提交历史
devà master 
dev修改了太多，很多无效的提交。
**还未提交的**
由于还没有 commit 到线上，还在本地，只需要一条命令就可以

| git reset --hard HEAD~1 //--hard表示不保留当前更改，强制回滚 |
| --- |

**已经提交**

| git reset --hard <commit_id> //回滚到你想回滚的commit |
| --- |
| git push origin HEAD --force //重新push到你的远程仓库 |

![image.png](https://cdn.nlark.com/yuque/0/2021/png/2811836/1631857856625-4f730131-3323-4ac8-9958-678e13a49b88.png#averageHue=%233c4347&clientId=u6748753d-b83d-4&from=paste&id=ub4fa4e32&name=image.png&originHeight=510&originWidth=1096&originalType=url&ratio=1&rotation=0&showTitle=false&size=118662&status=done&style=none&taskId=u7c5ecfe9-d86b-47f6-b553-314471720f8&title=)
##### 查看git 远程的url. 是github 还是gitee

```shell
git remote -v
git remote show origin
```

# FAQ

## 1 OpenSSL SSL_read: Connection was reset, errno 10054  
```shell
git config --global http.sslVerify "false"
# 还不行的话 比如我这边拉取 prometheus
git config --global http.postBuffer 5242880000
```
## 2 Filename too long

git有可以创建4096长度的文件名，然而在windows最多是260，因为git用了旧版本的windows api，为此踩了个坑。
解决打开git命令行：

```shell
git config --global core.longpaths true
```
##  Failed to connect to github.com port 443
