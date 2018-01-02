# HBuilder打包iOS APP发布App Store上架流程
上架iOS需要一个苹果开发者账号，还没有的话申请一个或者借用。

*** 上架过程分七个步骤，按步骤一步步来。

1. 创建APP身份证（App IDs）

2. 申请发布证书

3. 申请发布描述文件

4. HBuilder在线打包iOS APP

5. 在iTunes Connect创建App

6. Windows下上传IPA到App Store

7. 上传好IPA回到iTunes Connect填写APP信息并提交审核

## 一、创建唯一标示符App IDs
1.1 首先打开 [开发者中心](https://developer.apple.com/cn/)，进入证书页面。

1.2 点击证书、ID及配件文件，进入设置。
![alt 证书](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/1.1-1.png)

1.3 选择App IDs –>点击+创建一个新的App ID

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/1.2-1.png)
其中有两项需要你自己填：

第一项Name，用来描述你的App ID，这个随便填，没有什么限制，最好是项目名称，这样方便自己辨识（不允许中文）

第二项Bundle ID (App ID Suffix)，这是你App ID的后缀，需要仔细填写。用来标示我们的 app，使它有一个固定的身份，和你的程序直接相关。填写 Explicit App ID 的格式为：com.company.appName，照着格式写，写个方便记的，后面很多地方要用到。

第三项App Services，默认会选择2项，不能修改，其它根据自己需要的服务选择上，然后点击Continue确认，下一步。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/1.3-1.png)

检查下没有错的话直接点击Register后点击Done完成App ID的创建

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/1.4.png)

## 二、申请发布证书
申请iOS证书这里要用到工具Appuploader、直接在Windows系统中申请iOS证书、和后面上传IPA到App Store

工具需要Java运行环境，安装好才能启动使用。免费使用一个月、足够时间上架了。[Appuploader安装介绍](http://www.applicationloader.net/blog/zh/72.html)

2.1打开程序，输入苹果开发者中心账号，登录。
![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/2.1.png)

2.2选择证书

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/2.2-1.png)

2.3点击+ADD，这里有开发证书等等创建选项，这里选第三项发布证书。
如果你之前有了发布证书也可以不用创建，用之前的也行，苹果规定个人只能创建3个发布证书

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/2.3-1.png)

2.4输入，证书名称（随意） 邮箱（任何邮箱都行） 密码（后面打包编译时用到）然后点击ok

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/2.4.png)

2.5此时生成了好了一个发布证书，点击p12 File,下载证书文件，保存到电脑,这样发布证书就创建好了。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/2.5.png)

## 三、申请发布描述文件

3.1 回到软件点击Profiles

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/3.1.png)

3.2 点击+ADD，这里有开发描述文件等等选项，这里选发布描述文件。
![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/3.2.png)

3.3选择APP IDs，之前在开发者中心创建的，这里会自动出现。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/3.3.png)

3.4 勾选刚创建的发布证书关联好，输入name，点击ok
注意：如果你之前创建了多个发布证书，下面发布证书框显示多个发布证书，
可以全选，默认最新创建的发布证书，打包时输入最新创建的发布证书密码。
ps：发布证书不同的app可以通用的，描述文件不同就行了。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/3.4.png)

3.5此时生成了发布描述文件，点击 Download下载到电脑保存

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/3.5.png)

## 四、HBuilder在线打包iOS
4.1 打开HBuilder工具，选择完工的项目，点击发行，选择发行为原生安装包。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/1-2.png)

4.2 选择iOS打包，支持的设备类型，填写AppID（苹果开发者中心申请的那个），选择之前创建的iOS发布证书及配置文件并输入创建证书时设置的密码，点击打包。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/2-1.png)

4.3打包成功后，下载保存ipa，这个ipa包就能进行测试或上传App Store了。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/3-1.png)



## 五、在iTunes Connect创建App

5.1 回到软件，点击ItunerConnect，进入iTunes Connect进入创建APP。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/4.1.png)

5.2选择我的APP点击左上角+号选择新建APP，输入你的应用名称，语言，套装ID，之前在开发者中心创建的对应APP IDs ,（与创建iOS证书所选的appid要一致，这样用iOS证书打包的IPA，上传就能关联到了）
sku不能写中文，点击创建

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/4.2.png)

5.3 这里提示要用到Xcode或者Application loader提交IPA，等下用Appuploader直接在Windows环境下上传ipa，不用Mac了。
现在APP各项信息都没填写，等下把IPA上传成功了再填写。
这里构建版本旁边还没有出现+号，后面上传了IPA就会出现，等下会用到。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/4.5.png)


## 六、Windows环境下上传IPA到App Store
6.1打开Appuploader程序，点击Upload.

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/6.1.png)

6.2选择刚生成的iap包

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/6.2.png)

6.3 Appuploader将自动上传你的IPA，当出现以下提示时，说明上传成功，点击deail可以查看APP信息。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/6.3.png)

## 七、回到iTunes Connect提交审核

7.1上传好了IPA，然后回到iTunes Connect，进入填写信息的页面，下边有一个构建版本的选项，之前这旁边没有+号的，如果上传成功了，过几分钟旁边会出现一个加号按钮，点击一下+然后会出现你刚上传的APP，有上传多个版本会出现多个，点选、点击完成即可。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/1-5.png)

添加了构建版本，如果要修改添加，打包时改下版本号，如果跟之前的相同那上传不了。
点击删除又会出现+号，可选择其他上传的版本去提交审核。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/2-4.png)

7.2然后设置好APP相关的信息、类别，价格、销售服务等。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/4-3.png)

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/4-4.png)


截图的话、如果你的应用只支持 iPhone，你只需提供 5.5 英寸的显示屏截图
像素-纵向：1242 x 2208，横向：2208 x 1242
72 dpi、RGB、平展、不透明
高品质 JPEG 或 PNG 图像文件格式）即可。
其他尺寸的勾选引用5.5寸的就行，最多上传5张。
如果你的应用支持iPad，一套 12.9 英寸的屏幕截图就可以满足要求。
APP图标的规格则为1024*1024


7.3设置好相应的APP信息后，点击提交以供审核。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/7.2.png)

7.4 提交审核回到我的APP查看会提示正在等待审核，审核有时很快一两天，或要几天时间，常登陆看看审核情况，或看邮件提示。

如果变成可供销售，恭喜你~上架成功了，如果显示被拒绝，点击查看问题，根据反馈修改再重新上传。

![alt ID](http://www.applicationloader.net/blog/wp-content/uploads/2017/05/7.3.png)