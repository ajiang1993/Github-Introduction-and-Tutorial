# Github-Introduction-and-Tutorial

当我知道Github时，我完全不知道怎么用。  
Github有网页版（https://github.com/ ） 和客户端（下载地址：https://desktop.github.com/ ）。
## 步骤
1. 首先你需要注册一个账号。
2. 然后你点击 New repository。这个的意思相当于你新建了一个文件夹或者说一个项目。
3. 学习markdown的语法


...
function [ output_args ] = Untitled( input_args )
%UNTITLED Summary of this function goes here
%   Detailed explanation goes here

x0=unifrnd(1,500);
n0=randi([0 30]);
v0=unifrnd(0,16);
a0=0;
%随机生成一列车队的车辆数 头车位置 头车速度 
fprintf(' %f %f %f \n',n0,v0,x0);

%道路限制
vmax=16;
amax=2.5;
amin=-2.5;
l=4;%单车长度
s=2;%安全车距
B=zeros(60,n0);

t0=0;%设置红灯时长40s，绿灯时长60s
v=v0;
x=x0;
a=a0;
    A=x0:6:(n0-1)*6+x0;
%红灯情况下
for t=1:60
    vh=16;
    vl=A/(100-t);
    m=max(vl)
    n=min(vh)
%判断能否通过
  if v<=n&v>=m
      a=0;
      v=v;
      A=A-v;
  elseif v<m
      if v+2.5<16
          a=2.5;
      else
          a=16-v
      end
      v=v+a;
      A=A-v;

  end
  fprintf('%f %f %f  \n',t,a,v);
   B(t,:)=A;
    
  
  xlswrite('F:\result6.xls',B,'sheet1','A1');
end




end

...


