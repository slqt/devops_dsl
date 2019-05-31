# devops_dsl
这是一款专为运维打造的dsl，使用python开发，为简化工作量而生
拿nginx安装过程举例

set :nginx /opt/nginx #路径变量。
set @nginx root #用户变量，若是root用户可以省略
set :dest /home/nginx/app

set down_path http://nginx.org/download/nginx-1.10.3.tar.gz #普通变量
set ;lang python shell #表示将生成python和shell两种脚本
set ;system Linux #表示使用预设系统变量
set ;log /tmp/log/install_nginx.log 
let yum=yum install -y #临时自定义语法，只在当前脚本和其他引用该脚本的脚本范围内有效

@nginx #表示使用该用户操作。若是root可以不写
:nginx #表示切换到该路径操作

yum pcre pcre-devel
wget down_path

tar_result=untar tar_path to path
echo tar_result.text tar_result.status

:dest
configure  prefix=/home/nginx/app/nginx
:/home/nginx/app/nginx
make && make install

另外还有其他语法
例如add ;aliyun ;tecent ./test
do tar_result
done
do
done tar_result
for i in a b :1
endfor
if
else
endif
尚未开发完毕，敬请期待

