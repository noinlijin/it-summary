#!/usr/bin/env bash
#xxx解释一下这个脚本的功能
x=`echo $0 | grep "^/"`
pwdp=`pwd`
if test "${x}"; then
        dir=`dirname $0`
else
        dir=`dirname $pwdp/$0`
fi
dir=$dir
cd $dir



# 第一行表示这个脚本直接运行要使用bash解释,有时候sh也可以,只是某些语法是不一样的.bash更容易使用一些
# 后面的代码是用来找到脚本所在的目录,然后根据脚本所在的目录切换为当前目录. 
  -> 不必关心具体执行这个脚本的时候的当前目录是什么 
  -> 调用者不必关心这些细节...
