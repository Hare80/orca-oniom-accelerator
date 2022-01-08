# orca-oniom-accelerator

计算化学程序ORCA从5.0.0开始支持QM/XTB ONIOM计算，但是直到目前版本(5.0.2)为止，仍然有很多BUG，通过使用该脚本可以优化这个计算过程。  
#### 部分代码参考ORCA论坛  
@arrowyz https://orcaforum.kofo.mpg.de/viewtopic.php?f=8&t=6857&p=29519  
#  功能
*  通过备份xtbrestart文件加速ORCA的ONIOM计算过程
*  给xtb联用提供更多参数
*  备份xtb输出文件，方便出错时查找问题
  


#  作者的话
在使用本脚本之前能给嘉然点个关注吗  
### [嘉然今天吃什么](https://space.bilibili.com/672328094?from=search&seid=1096288322192370152)   
![嘉然](https://i2.hdslb.com/bfs/face/d399d6f5cf7943a996ae96999ba3e6ae2a2988de.jpg@240w_240h_1c_1s.webp)

#  警告  
**[1]该程序可能会对原来文件进行修改，请注意备份**  
**[2]本程序目前支持GFN2-xTB（即含有下列关键词），其他方法可能会有bug**
```
! QM/XTB

%qmmm
  AutoFF_QM2_Method XTB  # XTB (default)
end
```  

**[3]计算中减少时间大约为两次全体系采用GFN2-xTB方法计算单点时间，对于小体系加速效果并不明显（甚至可能降低效率）**  
**[4]最好不要用ORCA算 QM / XTB**  

#  安装方法
* 下载并解压源代码  
* 用文本编辑器打开otool_xtb，将第10行```PATH_TO_XTB="/path/to/xtb"```中的/path/to/xtb 修改成xtb可执行程序路径
* 将otool_xtb文件复制到orca目录下面
* 给otool_xtb添加可执行权限```chmod +x otool_xtb ```  

#  如何给xtb调用时添加额外参数  
* 在orca工作目录下新建xtb_parameter.txt文件，将需要增加的参数加入到文件当中，如  
``` --iterations 1000 ```   
* 更多参数写法请参考[xtb文档](https://xtb-docs.readthedocs.io/en/latest/contents.html)  

