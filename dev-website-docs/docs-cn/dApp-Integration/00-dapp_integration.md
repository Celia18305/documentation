
# dApp接入说明

移动端dAPI规范文档包括唤醒、扫码、钱包中打开H5 DApp三种场景。已支持dAPI的钱包[麦子钱包](http://www.mathwallet.org/en/)、[Onion](http://onion.fun/),对接请参考对应的对接文档。协议详情请看[CEP1](https://github.com/ontio-cyano/CEPs/blob/master/CEPS/CEP1.mediawiki)。

参考钱包下载链接： http://101.132.193.149/files/app-debug.apk

钱包对接：


* [钱包对接-Cyano Bridge安装和使用](https://dev-docs.ont.io/#/docs-cn/Wallet-Integration/01-01-WalletDocking-Installation-&-use-of-Cyano-Bridge)
* [钱包对接-钱包打开DApp接入流程](https://dev-docs.ont.io/#/docs-cn/Wallet-Integration/02-WalletDocking-wallet-open-DApp)
* [钱包对接-扫码接入流程](https://dev-docs.ont.io/#/docs-cn/Wallet-Integration/03-WalletDocking-scan-qrcode)
* 钱包对接-唤醒接入流程(暂不支持)
* 钱包对接-ONTID认证授权(暂不支持)

DAPP对接：

* [DAPP对接-手机钱包打开DAPP](https://dev-docs.ont.io/#/docs-cn/dApp-Integration/01-DAppDocking-Wallet-Opens-DApp)
* [DAPP对接-手机钱包扫码](https://dev-docs.ont.io/#/docs-cn/dApp-Integration/02-DAppDocking-QRcode)
* [DAPP对接-chrome插件钱包](https://dev-docs.ont.io/#/docs-cn/dApp-Integration/03-DAppDocking-use-chrome-extension-wallet)
* DAPP对接-ONTID认证授权(暂不支持)

DAPP后台对接：
* [同步链上信息（可选）](http://dev-docs.ont.io/#/docs-cn/dApp-Integration/05-DAppDocking-Sync)


## 场景1和2： 唤醒、扫码场景


##### 登录、调用智能合约

![](https://raw.githubusercontent.com/ontio/documentation/master/dev-website-docs/assets/integration/split-login-invoke.png)

##### 未登录时调用智能合约

![](https://raw.githubusercontent.com/ontio/documentation/master/dev-website-docs/assets/integration/invoke-with-login.png)


## 场景3： 钱包中打开H5 DApp

1. Open DApp in Provider
2. Get account or get identity
3. Login DApp
4. DApp Invoke smart contract

![](https://raw.githubusercontent.com/ontio/documentation/master/dev-website-docs/assets/integration/scenario3.png)

## 钱包演示

移动版Cyano钱包源码链接地址[cyano-android](https://github.com/ontio-cyano/cyano-android),[cyano-ios](https://github.com/ontio-cyano/cyano-ios)。

H5 DApp例子源码: [mobile-dapp-demo](https://github.com/ontio-cyano/mobile-dapp-demo)

### 钱包中打开 DApp

钱包中打开DApp：http://101.132.193.149:5000/#/

<div align="center">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/01-dapps.jpg" height="350" width="200">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/01-private-dapp.jpg" height="350" width="200">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/01-open-dapp.png" height="350" width="200">
</div>

### Get account or get identity

DApp登录如果不需要验证用户身份，直接查询账号或身份信息：

<div align="center">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/01-open-dapp.png" height="350" width="200">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/02-getAccount.jpg" height="350" width="200">
</div>

### Login DApp

DApp登录如果需要验证用户身份: DApp发消息到给钱包签名，DApp验证签名。

<div align="center">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/01-open-dapp.png" height="350" width="200">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/03-login-pwd.png" height="350" width="200">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/04-logined.jpg" height="350" width="200">
</div>

### DApp Invoke smart contract

DApp调用合约，用户签名后预执行合约，用户确认并发送交易，返回交易hash给DAPP。

<div align="center">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/input-password.jpg" height="350" width="200">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/05-pre-exec-result.png" height="350" width="200">
  <img src="https://raw.githubusercontent.com/ontio-cyano/integration-docs/master/images/ios/06-dapp-recv-txhash.jpg" height="350" width="200">
</div>
