# MacOSX运行MylhGithub配置教程

### 1 解决 "XXX" cannot be opened because the developer cannot be verified
打开 Mac 的 **终端 (Terminal)**，进入 `MylhGithub` 可执行文件所在的路径，依次执行以下两条命令：

1. **赋予执行权限**：
```bash
   chmod +x ./MylhGithub
```
2. **解除苹果隔离锁定**：

```bash
   sudo xattr -d com.apple.quarantine *.*
```   
   
   
### 2 安装并信任安全证书   
MylhGithub 拦截并加速加密网络流需要本地证书支持。
1. 软件首次成功启动后，程序同级目录下会自动生成一个 cacert 文件夹。
2. 进入 cacert 目录，双击打开 Mylhgithub.cer 证书文件。
3. 系统会自动弹出 钥匙串访问 (Keychain Access) 窗口。
4. 在列表中找到 MylhGitHub 证书并双击它，展开弹窗中的 「信任」 (Trust) 选项。
5. 将“使用此证书时”改为：始终信任 (Always Trust)，随后关闭窗口并输入 Mac 锁屏密码确认。

<img src="http://p0.meituan.net/csc/882e62c7eb1cef0ab3c43c06ce1f15111902079.png"/>

<img src="http://p0.meituan.net/csc/255e536e2a5a213adb28997d195f0c2e1989262.png"/>

### 3 配置代理
#### 3.1 自动代理(PAC)
1. 打开 Mac 系统设置 -> 网络 -> 点击当前连接的网络（如Wi-Fi） -> 详细信息 -> 代理。
2. 勾选 自动代理配置 (Automatic Proxy Configuration)。
3. 在 URL/地址栏中填写 MylhGithub 窗口或日志中提示的 PAC 地址（通常为本地相关路径）。
4. 点击好，并点击 应用。

<img src="http://p0.meituan.net/csc/0a39853576a56b785e38eda4deb3417898001.png"/>

<img src="http://p1.meituan.net/csc/6fd4b7d082ee184241a72616ec943dc41534488.png"/>

#### 3.2 手动代理
1. 打开 Mac 系统设置 -> 网络 -> 点击当前连接的网络（如Wi-Fi） -> 详细信息 -> 代理。
2. 勾选 网页代理 (HTTP) 和 安全网页代理 (HTTPS)。
3. 服务器地址统一填写：127.0.0.1，端口统一填写：38457。
4. 点击好，并点击 应用。

<img src="http://p0.meituan.net/csc/6dc9f4351fb624b83ea6e8a1cc1ac61a98891.png"/>

<img src="http://p1.meituan.net/csc/6fd4b7d082ee184241a72616ec943dc41534488.png"/>

### 4 访问没有灵魂 Web 运行监控台
无需依赖 Windows 客户端，在 Mac 的 Safari 或 Chrome 浏览器中直接输入：
[http://127.0.0.1:38458](http://127.0.0.1:38458)

打开后即可完整展现专为 macOS 优化的单屏免滚动监控面板：

数据监控：实时跳动显示当前的上行/下行网络速率，不间断精准累加当前已消耗的总上传与总下载流量。

日志与跳转：下半部分实时滚动输出核心拦截事件日志。点击底部下划线文本可一键穿梭访问魔法世界。

---

**⚠️ 声明**: Mylhgithub不具备“翻墙”功能,也没有相关的计划。
