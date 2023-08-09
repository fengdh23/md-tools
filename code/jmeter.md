#test 

```shell
## 修改环境变量 重新登录 每次执行先 sudo su , 再 source /etc/profile 
## 域名访问, https 端口是 443; http 默认端口是 80

-- 默认走网关 https

jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/dolphin-text.jmx" -l "/opt/apache-jmeter-5.4.1/result/dolphin-text.jtl" -e -o report/dolphin-text -JthreadNum=100 -JrampupTime=1 -JdurationTime=300

-- 走网关 https
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/dolphin-text.jmx" -l "/opt/apache-jmeter-5.4.1/result/dolphin-text-g1.jtl" -e -o report/dolphin-text-g1 -JthreadNum=100 -JrampupTime=1 -JdurationTime=300 -Jhttp=https -Jhostname=testnj.ucall.tech -Jport=443 -Jurl=/api/message/sendDolphinMsg

-- 网关 http
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/dolphin-text.jmx" -l "/opt/apache-jmeter-5.4.1/result/dolphin-ghttp2xs.jtl" -e -o report/dolphin-ghttp2x -JthreadNum=100 -JrampupTime=1 -JdurationTime=300 -Jhttp=http -Jhostname=testnj.ucall.tech -Jport=80 -Jtoken=ba3b2f11-5f7c-4c0d-9fa9-d002a33fcf33  -Jurl=/api/message/sendDolphinMsg


-- ip 是容器的ip http 不走网关不走域名解析 
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/dolphin-text.jmx" -l "/opt/apache-jmeter-5.4.1/result/dolphin-text91.jtl" -e -o report/dolphin-text91 -JthreadNum=1000 -JrampupTime=0 -JdurationTime=300 -Jhttp=http -Jhostname=192.168.17.186 -Jport=7200 -Jtoken=ba3b2f11-5f7c-4c0d-9fa9-d002a33fcf33 -Jurl=/message/sendDolphinMsg

# 进入到目录
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/dolphin-text.jmx" -l "/opt/apache-jmeter-5.4.1/result/dolphin-text.jtl"
查看占用cpu的线程


## html 报告
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/dolphin-text.jmx" -l "/opt/apache-jmeter-5.4.1/result/dolphin-text.jtl" –e –o report

## 动态参数 threadNum rampupTime durationTime 每次修改结果文件和report文件
## 1000并发 持续10分钟
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/dolphin-text.jmx" -l "/opt/apache-jmeter-5.4.1/result/dolphin-text.jtl" -e -o report/dolphin-text-1000 -JthreadNum=1000 -JrampupTime=1 -JdurationTime=600

## 文本 500并发 持续10分钟
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/dolphin-text.jmx" -l "/opt/apache-jmeter-5.4.1/result/dolphin-text.jtl" -e -o report/dolphin-text-500 -JthreadNum=500 -JrampupTime=1 -JdurationTime=600




## 图片
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/robot-image.jmx" -l "/opt/apache-jmeter-5.4.1/result/robot-image-1000-1.jtl" -e -o report/robot-image-1000-1 -JthreadNum=1000 -JrampupTime=10 -JdurationTime=600




## windows 环境 每次需要修改 jtl report 文件及文件夹名称
jmeter.bat -n -t ‪D:\toolDev\apache-jmeter-5.3\jmx\dolphin-text.jmx -l result\dolphin-text.jtl -e -o report\dolphin-text -JthreadNum=1000 -JrampupTime=5 -JdurationTime=60 -Jhttp=http -Jhostname=127.0.0.1 -Jport=7200

## 不需要要带盘符

jmeter.bat -n -t jmx\dolphin-text-local.jmx -l result\dolphin-text71.jtl -e -o report\dolphin-text71 -JthreadNum=500 -JrampupTime=0 -JdurationTime=60

jmeter.bat -n -t jmx\dolphin-text-local.jmx -l result\dolphin-text71.jtl -e -o report\dolphin-text71 -JthreadNum=500 -JrampupTime=0 -JdurationTime=60 -Jhttp=http -Jhostname=127.0.0.1 -Jport=7200 -Jurl=/message/sendDolphinMsg


### auth 需要修改脚本，body 入参的token的值每天会变化
## windows
jmeter.bat -n -t jmx\auth-checktoken.jmx  -l result\auth-checktoken11.jtl -e -o report\auth-checktoken11 -JthreadNum=500 -JrampupTime=0 -JdurationTime=60 -Jhttp=https -Jhostname=testnj.ucall.tech -Jport=443 -Jurl=/api/auth/checkToken

## 走网关 https
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/auth-checktoken.jmx" -l "/opt/apache-jmeter-5.4.1/result/auth-checktoken-g14.jtl" -e -o report/auth-checktoken-g14 -JthreadNum=100 -JrampupTime=1 -JdurationTime=300 -Jhttp=https -Jhostname=testnj.ucall.tech -Jport=443 -Jurl=/api/auth/checkToken

## 走网关 http
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/auth-checktoken.jmx" -l "/opt/apache-jmeter-5.4.1/result/auth-checktoken-g14.jtl" -e -o report/auth-checktoken-g14 -JthreadNum=100 -JrampupTime=1 -JdurationTime=300 -Jhttp=http -Jhostname=testnj.ucall.tech -Jport=80  -Jurl=/api/auth/checkToken

## 不走网关
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/auth-checktoken.jmx" -l "/opt/apache-jmeter-5.4.1/result/auth-checktoken-12.jtl" -e -o report/auth-checktoken-12 -JthreadNum=500 -JrampupTime=1 -JdurationTime=300 -Jhttp=http -Jhostname=192.168.17.173 -Jport=6999  -Jurl=/auth/checkToken

-- 18 29 
	
## 缓存 业务类型
-- 不走网关
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/business-getBusinessTypeById.jmx" -l "/opt/apache-jmeter-5.4.1/result/getBusinessTypeById-20.jtl" -e -o report/getBusinessTypeById-20 -JthreadNum=10 -JrampupTime=1 -JdurationTime=300 -Jhttp=http -Jhostname=192.168.17.139 -Jport=7004 -Jurl=/business/businessType/getBusinessTypeById?id=18

--  网关 http
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/business-getBusinessTypeById.jmx" -l "/opt/apache-jmeter-5.4.1/result/getBusinessTypeById-20.jtl" -e -o report/getBusinessTypeById-20 -JthreadNum=10 -JrampupTime=1 -JdurationTime=300 -Jhttp=http -Jhostname=testnj.ucall.tech -Jport=80 -Jurl=/api/business/businessType/getBusinessTypeById?id=18

--  网关 https
jmeter -n -t "/opt/apache-jmeter-5.4.1/jmx/business-getBusinessTypeById.jmx" -l "/opt/apache-jmeter-5.4.1/result/getBusinessTypeById-20.jtl" -e -o report/getBusinessTypeById-20 -JthreadNum=10 -JrampupTime=1 -JdurationTime=300 -Jhttp=https -Jhostname=testnj.ucall.tech -Jport=443 -Jurl=/api/business/businessType/getBusinessTypeById?id=18
```