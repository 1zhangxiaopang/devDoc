
nvm 管理 nodejs 和 npm 的版本，npm 可以管理 nodejs 的第三方插件。

参照：https://juejin.cn/post/7093787595951308836

* 安装前注意事项： 
  首先最重要的是：一定要卸载已安装的 NodeJS，否则会发生冲突。
  卸载node：确保在 Node.js 没有在后台运行的情况下，进行卸载。可以先打开软件，关闭后到控制面板中找到node.js进行卸载。
  删除相关文件: 卸载后，到文件夹中进行进一步的删除。node默认安装的文件夹，具体文件位置请查看自己安装时的位置！！

  C:\Program Files (x86)\Nodejs
  C:\Program Files\Nodejs
  C:\Users\admin\AppData\Roaming\npm
  C:\Users\admin\AppData\Roaming\npm-cache

* 下载nvm-windows

  url:https://github.com/coreybutler/nvm-windows/releases

  nvm-noinstall.zip： 这个是绿色免安装版本，但是使用之前需要配置。
  nvm-setup.zip：这是一个安装包，下载之后点击安装，无需配置就可以使用，方便。
  Source code(zip)：zip压缩的源码。
  Sourc code(tar.gz)：tar.gz的源码，一般用于Linux系统。

* 安装nvm

  参考：https://www.php.cn/js-tutorial-487496.html

  * nvm安装路径：D:\Program Files\nvm
  * 存放nodejs各版本的目录: D:\Program Files\nodejs
  * 添加镜像

  ![image-20220728192324168](..\assets\image-20220728192324168.png)

  查看安装是否正常 nvm -v  注意一定要在管理员 powerShell

* 安装14.18.0版本

  nvm install 14.18.0 

* 反安装

  nvm uninstall xx.xx.x

* 查看已安装的node版本

  nvm ls 

  ![image-20220728191230109](..\assets\image-20220728191230109.png)

  
