<div align="center">

# ✨ 𝕐𝕊𝕓𝕣𝕠𝕨𝕤𝕖𝕣 ✨  

</div>

## 参数

| 参数名                              | 描述                         |
|----------------------------------|----------------------------|
| `--timezone=Asia/Tokyo`          | 时区                         |
| `--fpseed=12lfisffwfaTYa`        | 指纹种子数                      |
| `--chrome-version=130.0.7151.70` | 版本号                        |
| `--noimage`                      | 不加载图片                      |
| `--nocrash`                      | 解决playwright,puppeteer崩溃bug |
| `--lang=zh-CN`                   | 本地语言                       |
| `--accept-lang=zh-CN`            | 请求语言                       |
---


## 参数详细说明
- **`timezone`**  
  - 时区建议和ip所在地区的时区保持一致。
---
- **`fpseed`**  
  - 指纹的种子，用来固定生成的指纹，以便下次使用一致的指纹，会影响canvas,webgl,audio,speech,domrect,font等等指纹。
---
- **`chrome-version`**  
  - 浏览器版本号，不建议随便添加，因为版本和许多api绑定，api没做修改，严格情况下会被检测出来，增加这个的目的为了应付一些不检测api但封控版本的网站。
  - 注意，修改版本号会自动修改tls指纹，但由于我目前没有全部版本的chrome指纹，所有可能会存在问题。
  - 如果需要添加版本号，建议用chrome发布的版本号，随便伪造可能存在问题。
---
- **`noimage`**  
  - 不加载图片
---
- **`nocrash`**  
  - 解决playwright和puppeteer存在iframe的contentWindow.open导致崩溃的bug。
---
- **`lang`** 和 **`accept-lang`**
  - 官方的参数，建议加上，会影响speech指纹 


## 自动化工具的建议
- 干掉了一部分的自动化工具检测，但是仍然不建议使用selenium，由于chromedriver依赖Function.prototype.apply致命的特征。
---
- playwright过不了cloudflare的cdp检测，如果一定要使用建议用补丁完的[patchright](https://github.com/Kaliiiiiiiiii-Vinyzu/patchright)，它完全禁用了runtime.enable。
---
- 建议使用[DrissionPage](https://github.com/g1879/DrissionPage),特征比较少。
--- 
- 修复了cdp的鼠标事件bug，该bug影响所有使用Input.dispatchMouseEvent的自动化工具。

## 调试
- 原本的debugger被修改为debugging
----
- 过掉了console检测

## 支持的PC
- 由于目前手上只有2019款mac book pro,暂时只有mac_intel版本，后续会新增window和linux

