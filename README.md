# 深圳大学体育场馆预约助手 🚀

![版本](https://img.shields.io/badge/version-v9.0-blue)
![语言](https://img.shields.io/badge/language-JavaScript-yellow)
![平台](https://img.shields.io/badge/platform-Tampermonkey-brightgreen)
![协议](https://img.shields.io/badge/license-MIT-lightgrey)
![状态](https://img.shields.io/badge/status-active-success)

一款为深圳大学学生和教职工设计的油猴脚本，旨在全自动化体育场馆的预约流程，从繁琐的手动点击中解放出来，特别为 **12:30 定时抢场** 进行了深度优化。

---

## ✨ 主要功能

*   **一键启动**：配置好偏好后，只需点击一次，即可启动全自动预约流程。
*   **智能定时抢场**：自动判断当前时间，若早于 `12:30`，则进入倒计时模式，在指定时间准时发起请求，最大化抢场成功率。
*   **场地优先级策略**：独创的场地选择策略，可设置如 `A3 B5 any` 的优先级列表，脚本会按顺序尝试抢占你最心仪的场地。
*   **适配多校区/多项目**：完美适配粤海、丽湖两校区，并能智能处理不同校区羽毛球馆的命名差异。
*   **开发者调试模式**：内置调试开关，开启后可运行完整选择流程而不触发最终的“提交”操作，方便测试与排错。
*   **无缝持久化用户设置**：你的所有选择（包括校区、项目、时间、场地偏好、调试开关状态）都会被实时保存在本地，刷新页面后无缝恢复，无需重复配置。
*   **清晰的状态反馈**：从倒计时到每一步操作，脚本都会在面板上提供清晰、实时的状态更新。

## 🖼️ 效果预览

#### 操作面板
 <!-- 建议替换为你自己的截图链接 -->

#### 自动化流程 (GIF)
 <!-- 建议替换为你自己的GIF动图链接 -->

## 🚀 安装与使用

### 第一步：安装油猴 (Tampermonkey)

首先，你的浏览器需要安装油猴扩展。如果已经安装，请跳过此步。

*   **Chrome**: [Tampermonkey 网上应用店](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
*   **Firefox**: [Tampermonkey 火狐附加组件](https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/)
*   **Edge**: [Tampermonkey Edge 附加组件](https://microsoftedge.microsoft.com/addons/detail/tampermonkey/iikmkjmpaadaobahmlepeloendndfphd)

### 第二步：安装本脚本

提供两种安装方式：

#### 方式 A：从 Greasy Fork 安装 (推荐)

1.  点击下方链接，一键安装最新版本：
    *   [**点我安装**](https://greasyfork.org/zh-CN/scripts/YOUR-SCRIPT-ID) <!-- ⚠️ 注意：请将 YOUR-SCRIPT-ID 替换为你在 Greasy Fork 上发布脚本后得到的数字ID -->
2.  在打开的页面中，点击绿色的“安装此脚本”按钮。
3.  油猴扩展会弹出确认窗口，再次点击“安装”即可。

#### 方式 B：手动安装

1.  打开本项目中的 `szu_booking_helper.user.js` 文件。
2.  复制文件内的所有代码。
3.  点击浏览器右上角的油猴图标，选择“管理面板”。
4.  点击“+”号标签页，进入“添加新脚本”界面。
5.  清空编辑器里的默认代码，将你复制的代码粘贴进去。
6.  点击菜单栏的“文件” -> “保存”。

### 第三步：配置与使用

1.  安装并启用脚本后，打开 [深圳大学体育场馆预约网址](https://ehall.szu.edu.cn/qljfwapp/sys/lwSzuCgyy/index.do#/sportVenue)。
2.  页面右侧会出现脚本的操作面板。
3.  根据你的需求，配置校区、项目、日期、时间段和场地偏好。
4.  点击“**一键预约**”按钮，启动自动化流程。

## 📖 使用指南

### 常规预约 (12:30 之后)

-   在面板上配置好所有选项。
-   确保底部的“调试模式”开关是**关闭**的。
-   点击“一键预约”，脚本会立即执行所有步骤并提交。

### 定时抢场 (12:30 之前)

1.  在抢场当天的 `12:30` 之前打开页面。
2.  脚本会自动将日期设置为**第二天**。
3.  配置好所有你想要的选项（特别是时间段和场地优先级）。
4.  点击“一键预约”，按钮会变灰，状态栏开始**倒计时**。
5.  等待即可，脚本会在 `12:30:00` 准时自动执行所有流程。

### 场地优先级策略

场地选择功能仅在选择“羽毛球”项目时出现。你可以在输入框中定义抢场顺序：

-   **精确顺序**: 输入 `A3 B5 C1`，脚本会先抢A3，失败则抢B5，再失败则抢C1。
-   **带后备选项**: 输入 `A3 any`，脚本会先抢A3，如果A3不可用，则会抢任意一个其他可用的场地。
-   **佛系抢场**: 输入 `any` 或 `任意`，脚本会抢它找到的第一个可用场地。

### 调试模式

-   打开底部的“调试模式”开关。
-   此时运行脚本，它会完成所有选择，但**不会点击最后的“提交预约”按钮**。
-   这允许你安全地测试前面的所有步骤是否按预期工作。

## 🔧 技术栈

*   **JavaScript (ES6+)**: 脚本核心语言。
*   **Tampermonkey API**: 使用 `GM_addStyle`, `GM_setValue`, `GM_getValue` 等接口与浏览器和油猴环境交互。
*   **MutationObserver**: 实现高性能、事件驱动的DOM监控，以瞬时响应页面动态加载的内容，取代了传统的 `setInterval` 轮询。
*   **HTML5 / CSS3**: 用于构建和美化用户操作面板。

## 🤝 贡献与反馈

欢迎提出任何问题或改进建议！

*   **Bug 反馈**: 如果你发现了 Bug，请在本仓库的 [Issues](https://github.com/YOUR-USERNAME/YOUR-REPO/issues) 页面提交详细描述。
*   **功能建议**: 欢迎提出新的功能想法！
*   **代码贡献**: 如果你希望贡献代码，请 Fork 本仓库，创建新的分支，提交修改后发起 Pull Request。

## 📄 授权协议

本项目采用 [MIT](https://opensource.org/licenses/MIT) 授权协议。
