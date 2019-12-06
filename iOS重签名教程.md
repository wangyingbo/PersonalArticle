# iOS 重签名教程

---

iOS 程序在导出包的时候可选择的发布方式有四种：

  ![distribution_method](https://raw.githubusercontent.com/wangyingbo/PrivateImages/master/2019/distribution_method.8hidp5wioaf.png)

如果是企业证书签名，发布方式选择`Enterprise`,则可直接把`xx.ipa`包放到本公司自己的服务器上，用户可通过链接直接安装。如果是通过个人开发证号生成的证书打包生成ipa文件，且不准备上架到App Store，且需要非本开发账号下的设备安装，则需使用重签名的方式，提供给客户使用。以下步骤以`易盘点`为例：

---

### 重签名步骤

* 易盘点公司通过自己公司的个人开发账号，对甲公司定制开发的的本地化程序打包，打包方式为`App Store Connect`，然后选择导出ipa包的方式，生成ipa文件；

 ![export](https://raw.githubusercontent.com/wangyingbo/PrivateImages/master/2019/export.x9rcqf55bv.png)
 

* 甲公司iOS开发人员在自己的个人开发证书下创建新的App，并生成provisioning profile 和 signing certificate文件，并安装到本地；

* 甲公司的iOS开发人员，首先下载重签名工具：[ios-app-signer](https://github.com/DanTheMan827/ios-app-signer)，在自己电脑上run起项目，成功后如下：
 ![run-signer-window](https://raw.githubusercontent.com/wangyingbo/PrivateImages/master/2019/run-ios-app-signer.hyk7aebft3.png)
 
* 在run起来的Mac窗口里，配置一下文件：
 ![signerProfile](https://raw.githubusercontent.com/wangyingbo/PrivateImages/master/2019/signerProfile.u8lbuuun6x.png)
 
 
 > + Input File:即ipa文件，导入即可；
 
 > + Signing Certificate:即证书文件，在下拉列表里选择生成的证书文件；
 
 > + Provisioning Profile:即provisioning profile文件；
 
 > + 余下选项任意配置即可；
 
 
 * 点击start，生成重签名后的ipa包；

---
 
### 安装重签名包
 
 * 重新生成的ipa包，可通过xcode直接装到手机上；
 
 ![deviceAppList](https://raw.githubusercontent.com/wangyingbo/PrivateImages/master/2019/deviceAppList.vkrklu6alac.png)
 
* 也可以通过fir或者蒲公英等第三方发布；