<div align="center">

# ✨ 𝕐𝕊𝕓𝕣𝕠𝕨𝕤𝕖𝕣 ✨  
**下一代隐私浏览器解决方案**

</div>

[English](README-en.md) | [中文](README.md)

## 🔍 检测通过列表
| 检测平台                                                             | 状态            | 备注     |
|--------------------------------------------------------------------|---------------|--------|
| [browserscan](https://browserscan.net)                             | ✅ 完美通过        | -      |
| [creepjs](https://abrahamjuliot.github.io/creepjs/)                | ✅ 62.5%+      | 持续优化中  |
| [iphey](https://iphey.com)                                         | ✅ 完美通过        | -      |
| [pixelscan](https://pixelscan.net)                                 | ✅ 完美通过        | -      |
| [cloudflare](https://www.cloudflare.com/zh-cn/)                    | ✅ 完美通过        | 需启用图片加载 |
| [datadome](https://datadome.co/products/bot-protection/)           | ✅ 完美通过        | -      |
| [brotector](https://kaliiiiiiiiii.github.io/brotector/)            | ✅ 完美通过        | -      |
| [sannysoft](https://bot.sannysoft.com/)                            | ✅ 完美通过        | -      |
| [fingerprint](https://fingerprint.com/products/bot-detection/)     | ✅ 完美通过        | -      |

---

## ⚙️ 核心参数配置
| 参数名                                  | 值                   | 功能描述         |
|--------------------------------------|---------------------|--------------|
| `--timezone`                         | `Asia/Tokyo`        | 设置浏览器时区      |
| `--fpseed`                           | `12lfisffwfaTYa`    | 指纹生成种子       |
| `--chrome-version`                   | `130.0.7151.70`     | Chrome 浏览器版本 |
| `--noimage`                          | -                   | 禁用图片加载       |
| `--nocrash`                          | -                   | 修复自动化工具崩溃问题  |
| `--lang`                             | `zh-CN`             | 设置浏览器语言      |
| `--accept-lang`                      | `zh-CN`             | 设置 HTTP 请求语言 |
| `--proxy-server`                     | `socks5://ip:port`  | 设置代理服务器      |
| `--proxy-auth`                       | `username:password` | 设置代理认证       |
| `--cpucores`                         | `6`                 | cpu核心数       |
| `--platformversion`                  | `15.4.1`            | 系统版本         |
| `--custom-screen`                    | `1792x1120,1792x1039` | 屏幕宽高         |
| `--force-device-scale-factor`        | `1`                 | 物理像素和css像素比值 |
| `--custom-geolocation`               | `110,220`           | 设置纬度和经度      |
| `--use-fake-device-for-media-stream` | -                   | 设置虚拟媒体设备     |
| `--custom-brand`                     | `"Microsoft Edge"`  | 浏览器品牌        |
| `--close-portscan`                   | -                   | 屏蔽端口扫描       |

---

## 📝 参数详解
### **`timezone`**  
- **功能**：设置浏览器时区
- **建议**：与代理 IP 所在地区时区保持一致
- **示例**：`--timezone=America/New_York`

### **`fpseed`**  
- **功能**：指纹生成种子
- **影响范围**：canvas, webgl, audio, speech, DOMRect, 字体等指纹
- **重要性**：保持相同种子可确保生成一致的浏览器指纹

### **`chrome-version`**  
- **功能**：指定 Chrome 浏览器版本
- **注意**：
  - 版本号与浏览器 API 紧密相关，随意修改可能导致检测风险
  - 自动适配 TLS 指纹（支持版本有限）
  - 仅建议在目标网站有严格版本控制时使用
- **推荐**：使用官方发布的 Chrome 版本号

### **`noimage`**  
- **功能**：禁用所有图片加载
- **使用场景**：提高页面加载速度
- **警告**：可能触发 Cloudflare 等安全检测（不推荐常规使用）

### **`nocrash`**  
- **功能**：修复 Playwright/Puppeteer 中 iframe 相关的崩溃问题
- **修复问题**：`contentWindow.open` 导致的崩溃

### **`lang` 与 `accept-lang`**
- **功能**：控制浏览器语言和 HTTP 请求头
- **影响**：语音识别(speech)、本地化相关指纹
- **建议**：保持两者一致

### **`proxy-server`**  
- **功能**：设置网络代理服务器
- **格式**：`--proxy-server=[协议]://[地址]:[端口]`
- **协议支持**：
  - `http`：HTTP/HTTPS 代理
  - `socks4`：SOCKS4 代理
  - `socks5`：SOCKS5 代理
- **示例**：
  - `--proxy-server=http://127.0.0.1:8080`

### **`proxy-auth`**  
- **功能**：设置网络代理认证
- **示例**：
  - `--proxy-auth=username:password`

### **`cpucores`**  
- **功能**：cpu的核心数（比如i7是6核，对应navigator.hardwareConcurrency）
- **建议**：使用常见的cpu核心数（6，8，10，12）

### **`platformversion`**  
- **功能**：系统的版本
- **建议**：
  - `macOS`：使用版本像15.4.1，15.5等
  - `Windows`：使用版本像10.0.0等

### **`custom-screen`**  
- **功能**：屏幕的宽高和可用宽高，对应javascript里的screen中width,height,availwidth,availheight。
- **建议**：如果设置它，width和height是必须的，availwidth和availheight如果不知道怎么设置可不加，浏览器会自动更改，尽量使用真实的分辨率。
- **示例**：
  - `1792x1120,1792x1039`
  - `1792x1120`

### **`force-device-scale-factor`**  
- **功能**：物理像素和css像素比值，也就是devicePixelRatio
- **示例**：
  - `1`
  - `2`

### **`custom-geolocation`** 
- **功能**：设置经纬度（navigator.geolocation.getCurrentPosition）
- **示例**：
  - `110,220`(纬度,经度)

### **`use-fake-device-for-media-stream`**
- **功能**：伪造媒体设备（navigator.mediaDevices.enumerateDevices）

### **`custom-brand`**
- **功能**：伪装浏览器品牌
- **建议**：如果伪装成真实的浏览器品牌，请携带user-agent这个参数，如果虚构不存在的品牌就不用携带user-agent。
- **示例**：
  - `--custom-brand="Microsoft Edge"
--user-agent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/137.0.0.0 Safari/537.36 Edg/137.0.0.0"`
  - `--custom-brand="fake brand"`

### **`close-portscan`**
- **功能**：屏蔽端口扫描

---

## 基本用法
- **警告**：由于没签名，mac上要执行xattr -cr YSbrowser.app才能使用。
```bash
chrome --timezone=Asia/Hong_Kong --lang=zh-CN --accept-lang=zh-CN,en --fpseed=121e0opwlltx --cpucores=12 --platformversion=10.0.0 --custom-screen=1920x1080 --chrome-version=137.0.3296.93 --force-device-scale-factor=1 --custom-geolocation=110,220 --user-data-dir=./my_user_data --custom-brand="Microsoft Edge" --user-agent="Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/137.0.0.0 Safari/537.36 Edg/137.0.0.0" --close-portscan
```

## 🤖 自动化工具支持
### 已消除的自动化特征
- ✅ CDP 检测
- ✅ Selenium 特征
- ✅ Playwright 特征
- ✅ DrissionPage 特征

### 推荐工具
**[DrissionPage](https://github.com/g1879/DrissionPage)** - 低特征、高性能的自动化解决方案  
**优势**：
- 极简的浏览器指纹特征
- 完美的鼠标事件模拟
- 无崩溃风险的内容交互

### 关键技术改进
1. **鼠标事件修复**：彻底解决 CDP 的 `Input.dispatchMouseEvent` 缺陷
2. **Shadow DOM 访问**：通过 `opshadowRoot` 访问封闭式 shadow DOM
3. **自动化检测绕过**：消除常见自动化工具特征标记

---

## 🐞 调试支持
- **重命名调试器**：`debugger` → `debugging`（绕过检测）
- **控制台检查**：绕过常见的控制台属性检查

---

## 🚧 开发路线图
| 功能                     | 状态   | 说明                                                                 |
|--------------------------|--------|----------------------------------------------------------------------|
| Linux 支持               | ❌ 待实现 | 正在适配 Linux 平台                                                  |
| GPU 指纹伪造             | ⚙️ 开发中 | 增强图形指纹的伪装能力                                               |
| 多版本 TLS 指纹支持      | ⚙️ 开发中 | 增加更多 Chrome 版本的 TLS 指纹库                                    |
> **提示**：项目持续更新中，欢迎提交 Issue！如果想帮助我收集更多指纹，请点击[网址](https://www.hanyiting.com)

### 交流群
<img src="QQ20250723-104659.png" alt="Q群1043047569" width="400" height="400">
