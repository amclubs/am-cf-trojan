# [am-cf-trojan](https://github.com/amclubs/am-cf-trojan)
这是基于CF平台的脚本，部署Trojan 配置信息转换为订阅内容。可以方便地将 Trojan 节点配置信息转换到 Clash 或 Singbox 或Quantumult X等工具中。

#
▶️ **新人[YouTube](https://youtube.com/@am_clubs?sub_confirmation=1)** 需要您的支持，请务必帮我**点赞**、**关注**、**打开小铃铛**，***十分感谢！！！*** ✅
</br>🎁请 **follow** 我的[GitHub](https://github.com/amclubs)、给我所有项目一个 **Star** 星星（拜托了）！你的支持是我不断前进的动力！ 💖
</br>✅**解锁更多技能** [加入TG群【am_clubs】](https://t.me/am_clubs)、[YouTube频道【@am_clubs】](https://youtube.com/@am_clubs?sub_confirmation=1)、[【博客(国内)】](https://amclubss.com)、[【博客(国际)】](https://amclubs.blogspot.com) 
</br>✅点击观看教程[CLoudflare免费节点](https://www.youtube.com/playlist?list=PLGVQi7TjHKXbrY0Pk8gm3T7m8MZ-InquF) | [VPS搭建节点](https://www.youtube.com/playlist?list=PLGVQi7TjHKXaVlrHP9Du61CaEThYCQaiY) | [获取免费域名](https://www.youtube.com/playlist?list=PLGVQi7TjHKXZGODTvB8DEervrmHANQ1AR) | [免费VPN](https://www.youtube.com/playlist?list=PLGVQi7TjHKXY7V2JF-ShRSVwGANlZULdk) | [IPTV源](https://www.youtube.com/playlist?list=PLGVQi7TjHKXbkozDYVsDRJhbnNaEOC76w) | [Mac和Win工具](https://www.youtube.com/playlist?list=PLGVQi7TjHKXYBWu65yP8E08HxAu9LbCWm) | [AI分享](https://www.youtube.com/playlist?list=PLGVQi7TjHKXaodkM-mS-2Nwggwc5wRjqY)

# 推荐视频教程
- [Error 1101 和 522 报错解决方案教程](https://youtu.be/4fcyJjstFdg) | [优选IP和优选反代IP视频教程](https://youtu.be/pKrlfRRB0gU) | [解决常见订阅测试-1问题教程](https://youtu.be/kYQxV1G-ePw)
- [trojan免费节点部署教程](https://youtu.be/dPH63nITA0M) | [Trojan免费节点部署教程](https://youtu.be/uh27CVVi6HA) | [从入门到精通免费部署教程](https://youtu.be/ag12Rpc9KP4) | [聚合节点订阅教程](https://youtu.be/YBO2hf96150)
- [GitHub私有库存储优选IP文教程](https://youtu.be/vX3U3FuuTT8) | [CF免费KV存储优选IP文件教程](https://youtu.be/dzxezRV1v-o) [获取免费域名教程](https://www.youtube.com/playlist?list=PLGVQi7TjHKXZGODTvB8DEervrmHANQ1AR) | [获取CF自家域名无限节点](https://youtu.be/novrPiMsK70)

## 
## Workers 部署方法 [视频教程](https://www.youtube.com/watch?v=uh27CVVi6HA&t=31s)
<details>
<summary>点击展开/收起</summary>
	
1. 部署 Cloudflare Worker：
   - 在 Cloudflare Worker 控制台中创建一个新的 Worker。
   - 将 [_worker.js](https://github.com/amclubs/am-cf-trojan/blob/main/_worker.js) 的内容粘贴到 Worker 编辑器中。
2. 给 workers绑定 自定义域： [免费域名申请教程](https://www.youtube.com/playlist?list=PLGVQi7TjHKXZGODTvB8DEervrmHANQ1AR)
   - 在 workers控制台的 `设置` 选项卡 -> 点击 `域和路由` -> 右方点击 -> `添加` -> 选择 `自定义域`。
   - 填入你已转入 CloudFlare 域名 (amclubss.com) 解析服务的次级域名，例如:`trojan.amclubss.com`后 点击 `添加域`，等待证书生效即可。
3. 给PASSWORD设置KV存储桶(可选项，推荐设置)： 
   - 在 CloudFlare主页的左边菜单的 ` 存储和数据库` 选项卡 -> 展开选择点击 `KV` -> 右方点击 -> `创建` -> 填入 `命名空间名称`(此名称自己命名) 后 -> 点击 `添加`。(此步已有可忽略)
   - 在 workers控制台的 `设置` 选项卡 -> 点击 `绑定` -> 右方点击 -> `添加` -> 选择 `KV 命名空间` -> 变量名称 填入 `amclubs`(此名称固定不能变) -> KV 命名空间 选择 在上面创建的 `命名空间名称`后 -> 右下方点击 `部署`。
4. 访问订阅内容：
   - 访问 `https://[YOUR-WORKERS-URL]/[PASSWORD]` 即可获取订阅内容（默认PASSWORD是：auto）。
   - 例如 `https://trojan.amclubss.com/auto?sub` 就是你的通用自适应订阅地址(Quantumult X、Clash、singbox、小火箭、v2rayN、v2rayU、surge、PassWall、SSR+、Karing等)。
   - 例如 `https://trojan.amclubss.com/auto?base64` Base64订阅格式，适用PassWall,SSR+等。
   - 例如 `https://trojan.amclubss.com/auto?clash` Clash订阅格式，适用OpenClash等。
   - 例如 `https://trojan.amclubss.com/auto?singbox` singbox订阅格式，适用singbox等。
   - 例如 `https://trojan.amclubss.com/auto?sub&IP_URL=https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/ipUrl.txt` 自动义变量等参数。
5. 修改默认PASSWORD变量，使用KV存储桶(可选项，推荐修改，防止别人用你节点)： 
   - 访问 `https://trojan.amclubss.com/auto/ui` 即可进入修改PASSWORD页面 
   - 在PASSWORD页面PASSWORD项 -> 填入 `新的PASSWORD` 后 -> 点击 `Save`。
   - 保存成功后，原PASSWORD已作废不能访问，用新PASSWORD访问  `https://trojan.amclubss.com/新的PASSWORD` 即可获取订阅内容。

</details>

## 
## Pages 上传 部署方法 [视频教程](https://www.youtube.com/watch?v=wgeM9XvZ5RA&t=1738s)
<details>
<summary>点击展开/收起</summary>
	
1. 部署 Cloudflare Pages：
   - 下载 [_worker.js.zip](https://raw.githubusercontent.com/amclubs/am-cf-trojan/main/_worker.js.zip) 文件，并点上 Star !!!
   - 在 Cloudflare Pages 控制台中选择 `上传资产`后，为你的项目取名后点击 `创建项目`，然后上传你下载好的 [_worker.js.zip](https://raw.githubusercontent.com/amclubs/am-cf-trojan/main/_worker.js.zip) 文件后点击 `部署站点`。
2. 给 Pages绑定 CNAME自定义域：[无域名绑定Cloudflare部署视频教程]->[免费域名教程1](https://youtu.be/wHJ6TJiCF0s) [免费域名教程2](https://youtu.be/yEF1YoLVmig)  [免费域名教程3](https://www.youtube.com/watch?v=XS0EgqckUKo&t=320s)
   - 在 Pages控制台的 `自定义域`选项卡，下方点击 `设置自定义域`。
   - 填入你的自定义次级域名，注意不要使用你的根域名，例如：
     您分配到的域名是 `amclubss.com`，则添加自定义域填入 `trojan.amclubss.com`即可，点击 `激活域`即可。    
3. 给PASSWORD设置KV存储桶(可选项，推荐设置)： 
   - 在 CloudFlare主页的左边菜单的 ` 存储和数据库` 选项卡 -> 展开选择点击 `KV` -> 右方点击 -> `创建` -> 填入 `命名空间名称`(此名称自己命名) 后 -> 点击 `添加`。(此步已有可忽略)
   - 在 workers控制台的 `设置` 选项卡 -> 点击 `绑定` -> 右方点击 -> `添加` -> 选择 `KV 命名空间` -> 变量名称 填入 `amclubs`(此名称固定不能变) -> KV 命名空间 选择 在上面创建的 `命名空间名称`后 -> 右下方点击 `部署`。
   - 在 `设置` 选项卡，在右上角点击 `创建部署` 后，重新上传 [_worker.js.zip](https://raw.githubusercontent.com/amclubs/am-cf-trojan/main/_worker.js.zip) 文件后点击 `保存并部署` 即可。
4. 访问订阅内容：
   - 访问 `https://[YOUR-WORKERS-URL]/[PASSWORD]` 即可获取订阅内容（默认PASSWORD是：auto）。
   - 例如 `https://trojan.amclubss.com/auto?sub` 就是你的通用自适应订阅地址(Quantumult X、Clash、singbox、小火箭、v2rayN、v2rayU、surge、PassWall、SSR+、Karing等)。
   - 例如 `https://trojan.amclubss.com/auto?base64` Base64订阅格式，适用PassWall,SSR+等。
   - 例如 `https://trojan.amclubss.com/auto?clash` Clash订阅格式，适用OpenClash等。
   - 例如 `https://trojan.amclubss.com/auto?singbox` singbox订阅格式，适用singbox等。
   - 例如 `https://trojan.amclubss.com/auto?sub&IP_URL=https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/ipUrl.txt` 自动义变量等参数。
5. 修改默认PASSWORD变量，使用KV存储桶(可选项，推荐修改，防止别人用你节点)： 
   - 访问 `https://trojan.amclubss.com/auto/ui` 即可进入修改PASSWORD页面 
   - 在PASSWORD页面PASSWORD项 -> 填入 `新的PASSWORD` 后-> 点击 `Save`。
   - 保存成功后，原PASSWORD已作废不能访问，用新PASSWORD访问  `https://trojan.amclubss.com/新的PASSWORD` 即可获取订阅内容。

</details>

## 
## Pages GitHub 部署方法 [视频教程](https://www.youtube.com/watch?v=uh27CVVi6HA&t=511s)
<details>
<summary>点击展开/收起</summary>
	
1. 部署 Cloudflare Pages：
   - 在 Github 上先 Fork 本项目，并点上 Star !!!
   - 在 Cloudflare Pages 控制台中选择 `连接到 Git`后，选中 `am-cf-tunnel`项目后点击 `开始设置`。
   - 在 `设置构建和部署`页面下方，后点击 `保存并部署`即可。
2. 给 Pages绑定 CNAME自定义域：[无域名绑定Cloudflare部署视频教程]->[免费域名教程1](https://youtu.be/wHJ6TJiCF0s) [免费域名教程2](https://youtu.be/yEF1YoLVmig)  [免费域名教程3](https://www.youtube.com/watch?v=XS0EgqckUKo&t=320s)
   - 在 Pages控制台的 `自定义域`选项卡，下方点击 `设置自定义域`。
   - 填入你的自定义次级域名，注意不要使用你的根域名，例如：
     您分配到的域名是 `amclubss.com`，则添加自定义域填入 `trojan.amclubss.com`即可，点击 `激活域`即可。    
3. 给PASSWORD设置KV存储桶(可选项，推荐设置)： 
   - 在 CloudFlare主页的左边菜单的 ` 存储和数据库` 选项卡 -> 展开选择点击 `KV` -> 右方点击 -> `创建` -> 填入 `命名空间名称`(此名称自己命名) 后 -> 点击 `添加`。(此步已有可忽略)
   - 在 workers控制台的 `设置` 选项卡 -> 点击 `绑定` -> 右方点击 -> `添加` -> 选择 `KV 命名空间` -> 变量名称 填入 `amclubs`(此名称固定不能变) -> KV 命名空间 选择 在上面创建的 `命名空间名称`后 -> 右下方点击 `部署`。
   - 在 `设置` 选项卡，在右上角点击 `创建部署` 后，重新选择 `部署` 即可。
4. 访问订阅内容：
   - 访问 `https://[YOUR-WORKERS-URL]/[PASSWORD]` 即可获取订阅内容（默认PASSWORD是：auto）。
   - 例如 `https://trojan.amclubss.com/auto?sub` 就是你的通用自适应订阅地址(Quantumult X、Clash、singbox、小火箭、v2rayN、v2rayU、surge、PassWall、SSR+、Karing等)。
   - 例如 `https://trojan.amclubss.com/auto?base64` Base64订阅格式，适用PassWall,SSR+等。
   - 例如 `https://trojan.amclubss.com/auto?clash` Clash订阅格式，适用OpenClash等。
   - 例如 `https://trojan.amclubss.com/auto?singbox` singbox订阅格式，适用singbox等。
   - 例如 `https://trojan.amclubss.com/auto?sub&IP_URL=https://raw.githubusercontent.com/amclubs/am-cf-tunnel/main/ipUrl.txt` 自动义变量等参数。
5. 修改默认PASSWORD变量，使用KV存储桶(可选项，推荐修改，防止别人用你节点)： 
   - 访问 `https://trojan.amclubss.com/auto/ui` 即可进入修改PASSWORD页面 
   - 在PASSWORD页面PASSWORD项 -> 填入 `新的PASSWORD` 后 -> 点击 `Save`。
   - 保存成功后，原PASSWORD已作废不能访问，用新PASSWORD访问  `https://trojan.amclubss.com/新的PASSWORD` 即可获取订阅内容。

</details>

## 
## 🔧五、变量说明 [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=468s)
| 变量名 | 示例 | 必填 | 备注 | YT |
|-----|-----|-----|-----|-----|
| ID   | ec872d8f-72b0-4a04-b612-0327d85e18ed（默认）|✅| 支持Cloudflare的KV存储桶设置 [在线获取UUID](https://1024tools.com/uuid) VLESS、Trojan节点共用 | |
| D_URL | https://cloudflare-dns.com/dns-query |❌| DNS解析获取作用，小白勿用                                                           |  |

## 
## ⚙️ Snippets 部署方法 [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=165s)
<details>
<summary>点击展开/收起</summary>

1. 进入 Cloudflare Snippets：
   - 在 CloudFlare主页的左边菜单的 `域` 选项卡 -> 点击 `域` 菜单 -> 进入到 `域管理` -> 找到已开通**Snippets**的域名点击进入 -> 进入后在左边菜单的 `规则` 选项卡 点击展开 -> 点击 `Snippets` 菜单 -> 进入 `Snippets`片段代码主页面。
2. 部署 Cloudflare Snippets代码：
   - 在 `Snippets`片段代码主页面的 右下角方点击 `+创建片段` 图标进入代码编辑页面 -> 在右上方创建片段 -> 填入 `片段名称`(此名称自己命名)。
   - 将 [_worker.js](https://github.com/amclubs/am-cf-trojan/blob/main/snippets.js) 的内容粘贴到 `Snippets` 编辑器中 -> 修改第一行代码`id`变量值(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed) 建议自己要修改 [在线获取UUID](https://1024tools.com/uuid)。
   - 点击右上方 `片段规则` 图标 -> 选择 `自定义筛选表达式` -> 字段 选择 `主机名` -> 运算符 选择 `运算符` -> 值 填入 `Snippets进入的域名名称，再前面加多一节子域名名称`(子域名名称自己命名) 后 -> 点击 `完成`。(此步已有可忽略)
   - 在 码编辑页面 右上角方点击 `部署`  即可。
3. 验证部署是否成功：
   - 访问 `https://[YOUR-Snippets-URL]` 即可进入登录页面,登录成功就是完成部署(默认登录密码(UUID)是：ec872d8f-72b0-4a04-b612-0327d85e18ed)。
   - 例如 `https://vless.amclubss.com` 然后进入登录页面 -> 输入密码 `ec872d8f-72b0-4a04-b612-0327d85e18ed` -> 点击登录 -> 成功登录。 
4. 订阅连接和节点生成使用方法：  [视频教程](https://www.youtube.com/watch?v=i-XnnP-MptY&t=596s)
   - 进入 [am-cf-tunnel-sub](https://github.com/amclubs/am-cf-tunnel-sub) 项目 -> 根据项目教程部署和使用。(此步已有可忽略)
   - 本频道订阅器转换地址：https://sub.amclubss.com
   
</details>

## 五、已适配订阅工具 [点击进入视频教程](https://youtu.be/xGOL57cmvaw) [点进进入karing视频教程](https://youtu.be/M3vLLBWfuFg)
- Mac（苹果电脑）
   - [v2rayU](https://github.com/yanue/V2rayU/releases) | [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases) | [Quantumult X](https://apps.apple.com/us/app/quantumult-x/id1443988620) |  [小火箭](https://apps.apple.com/us/app/shadowrocket/id932747118) | [surge](https://apps.apple.com/us/app/surge-5/id1442620678) | [karing](https://karing.app/download) | [sing-box](https://github.com/SagerNet/sing-box/releases)  | [Clash Nyanpasu](https://github.com/keiko233/clash-nyanpasu/releases) | [openclash](https://github.com/vernesong/OpenClash/releases) | [Hiddify](https://github.com/hiddify/hiddify-next/releases)

- Win（win系统电脑）
   - [v2rayN](https://github.com/2dust/v2rayN/releases) |  [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases) | [sing-box](https://github.com/SagerNet/sing-box/releases) |  [Clash Nyanpasu](https://github.com/keiko233/clash-nyanpasu/releases) | [openclash](https://github.com/vernesong/OpenClash/releases)  | [karing](https://karing.app/download) |  [Hiddify](https://github.com/hiddify/hiddify-next/releases)
     
- IOS（苹果手机）
   - [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases) |  [Quantumult X](https://apps.apple.com/us/app/quantumult-x/id1443988620)  |  [小火箭](https://apps.apple.com/us/app/shadowrocket/id932747118)  |  [surge](https://apps.apple.com/us/app/surge-5/id1442620678) |  [sing-box](https://github.com/SagerNet/sing-box/releases) | [Clash Nyanpasu](https://github.com/keiko233/clash-nyanpasu/releases) | [karing](https://karing.app/download) | [Hiddify](https://github.com/hiddify/hiddify-next/releases)
     
- Android（安卓手机）
   - [v2rayNG](https://github.com/2dust/v2rayNG/releases) |  [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases) | [sing-box](https://github.com/SagerNet/sing-box/releases) |  [Clash Nyanpasu](https://github.com/keiko233/clash-nyanpasu/releases) |  [karing](https://karing.app/download) | [Hiddify](https://github.com/hiddify/hiddify-next/releases)
  
 # 
<center>
<details><summary><strong> [点击展开] 赞赏支持 ~🧧</strong></summary>
*我非常感谢您的赞赏和支持，它们将极大地激励我继续创新，持续产生有价值的工作。*

- **USDT-TRC20:** `TWTxUyay6QJN3K4fs4kvJTT8Zfa2mWTwDD`
- **TRX-TRC20:** `TWTxUyay6QJN3K4fs4kvJTT8Zfa2mWTwDD`

<div align="center"> 
  <img src="https://github.com/user-attachments/assets/e6cdc42a-6374-4722-b833-601738f72196" width="200"></br> 
  TRC10/TRC20扫码支付 
</div> 
</details>
</center>

 #
 免责声明:
 - 1、该项目设计和开发仅供学习、研究和安全测试目的。请于下载后 24 小时内删除, 不得用作任何商业用途, 文字、数据及图片均有所属版权, 如转载须注明来源。
 - 2、使用本程序必循遵守部署服务器所在地区的法律、所在国家和用户所在国家的法律法规。对任何人或团体使用该项目时产生的任何后果由使用者承担。
 - 3、作者不对使用该项目可能引起的任何直接或间接损害负责。作者保留随时更新免责声明的权利，且不另行通知。
 
