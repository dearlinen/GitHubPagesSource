# 使用wakatime插件时遇到的一些问题

## 第一次debug

### wakatime在webstorm中不生效

* 开启wakatime的debug模式,查看idea.log文件  
  发现有报错,为
  `Cannot run program:"C:\Users\xxx\AppData\Roaming\WakaTime\wakatime-cli\wakatime-cli.exe"没有此文件`
* 尝试在github搜索issue,未发现相同问题,发现vscode中的插件运行正常,尝试将vscode插件目录中的wakatime-cli复制到wbstorm插件目录,问题解决

## 第二次debug

### vscode和webstorm插件全部未生效

* 检查~/目录未发现`.wakatime.db`文件
* 启动wakatime debug模式后查看wbstorm日志并未发现报错,但是wakatime在每次启动的时候都会下载安装wakatime-cli
* 查看vscode插件目录,未发现`wakatime-cli`文件夹,发现`wakatime-cli.zip`压缩包,文件体积国小,且一直被占用,猜测插件一直未下载完成
* 后猜测为网络问题,打开系统代理后用vscode重新安装wakatime插件,恢复正常,沿用上次webstorm解决方案同时解决了webstorm的问题

> * 经历的两次问题都是网络原因, 难以下载wakatime-cli导致无法正常使用.
>* 解决方案均为科学上网, 在vscode中可正常下载wakatime-cli后vscode即可正常使用
>* 如需在其他编辑器中启用, 将wakatime-cli复制到其插件目录中即可解决