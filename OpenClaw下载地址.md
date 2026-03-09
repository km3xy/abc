OpenClaw 没有官方原生手机 App，下面给你安卓手机可用的全部安全下载链接（小米通用）：
 
📱 一、官方远程控制入口（手机网页版）
 
- 手机浏览器直接打开（扫码配对电脑）：
https://openclaw.ai/mobile
 
📦 二、社区 APK 安装包（本地运行，无需电脑）
 
GitHub Releases（最新 v1.8.1）：
 
- 主流 64 位手机（推荐）：
https://github.com/mithun50/openclaw-termux/releases/download/v1.8.1/OpenClaw-v1.8.1-arm64-v8a.apk
​
- 通用兼容版（所有安卓）：
https://github.com/mithun50/openclaw-termux/releases/download/v1.8.1/OpenClaw-v1.8.1-universal.apk
​
- 32 位老手机：
https://github.com/mithun50/openclaw-termux/releases/download/v1.8.1/OpenClaw-v1.8.1-armeabi-v7a.apk
​
- 模拟器/x86：
https://github.com/mithun50/openclaw-termux/releases/download/v1.8.1/OpenClaw-v1.8.1-x86_64.apk
 
⚙️ 三、Termux 一键安装脚本（最稳，小米推荐）
 
打开 F‑Droid 版 Termux，复制运行：



图1：可选包与下一步配置
 
- 界面标题： Setup OpenClaw ，提示“正在设置环境，可能需要几分钟”。
​
- 可选安装包：
​
- Go (Golang)：Go语言编译器和工具（约150MB），用于编译部分插件。
​
- Homebrew：Linux包管理器（约500MB），用于安装更多依赖。
​
- OpenSSH：SSH客户端/服务端（约10MB），用于远程访问手机环境。
​
- 底部红色按钮： Configure API Keys ，这是下一步配置AI服务密钥的入口。
 
 
 
图2：安装进度界面
 
- 已完成步骤：
​
1. ✅  Download Ubuntu rootfs ：下载Ubuntu根文件系统
​
2. ✅  Extract rootfs ：解压根文件系统
​
- 当前步骤：
3.  Install Node.js ：安装Node.js
4. 🔴  Installing OpenClaw (this may take a few minutes)... ：正在安装OpenClaw核心程序
​
- 待完成步骤：
5.  Configure Bionic Bypass ：配置Bionic兼容层，解决安卓系统调用兼容问题
 
 
 
下一步操作建议
 
1. 等待安装完成：图2中的“Installing OpenClaw”步骤需要一定时间，请保持手机亮屏、网络稳定，避免后台被系统清理。
​
2. 配置API密钥：安装完成后，会跳转到图1的界面，点击  Configure API Keys ，按提示填入你使用的AI服务商（如OpenAI、DeepSeek等）的API密钥。
​
3. 可选包安装：如果需要编译插件或远程访问，可以安装Go、Homebrew或OpenSSH，普通使用场景可以跳过。
 
 
 
如果你在安装过程中卡住了，我可以帮你排查原因并提供解决方案。需要我帮你看看吗？



二、小米系统设置清单（手动必做）
 
1. 关闭电池优化
​
- 设置 → 应用设置 → 应用管理 → OpenClaw → 电池 → 省电策略 → 无限制
​
- 设置 → 电池与性能 → 电池优化 → 所有应用 → OpenClaw → 不优化
​
2. 开启自启动与后台活动
​
- 设置 → 应用设置 → 应用管理 → OpenClaw → 自启动 → 开启
​
- 设置 → 应用设置 → 应用管理 → OpenClaw → 后台活动 → 允许
​
3. 锁定后台
​
- 上滑进入最近任务 → 长按 OpenClaw 卡片 → 点击锁图标（加锁）
​
4. 开启存储权限
​
- 设置 → 应用设置 → 应用管理 → OpenClaw → 权限 → 存储 → 允许
 
 
 
三、开机自启（可选，更省心）



 
在 Termux 中运行以下命令，让 OpenCla

# 安装 Termux 服务管理
pkg install termux-services -y

# 创建 OpenClaw 自启服务
mkdir -p $PREFIX/var/service/openclaw
cat > $PREFIX/var/service/openclaw/run << 'EOF'
#!/bin/sh
termux-wake-lock
nohup openclaw gateway start &
EOF

chmod +x $PREFIX/var/service/openclaw/run
sv up openclaw
sv enable openclaw

四、验证是否正常运行
 
1. 打开手机浏览器，访问： http://localhost:18789 
​
2. 如果能看到 OpenClaw 控制台，说明网关已成功启动
​
3. 尝试发送一条指令（如“列出当前目录文件”），确认功能正常



这是 OpenClaw 手机版的 AI Providers（AI 服务提供商）配置界面，我帮你解读一下当前状态和后续操作：
 
 
 
一、当前状态
 
- Active Model： deepseek-chat ，说明 DeepSeek 模型已经被成功设置为当前活跃模型。
​
- DeepSeek：显示为 Active，表示 DeepSeek 服务已启用，你已经完成了 API Key 的配置。
​
- 其他可选提供商：Anthropic、OpenAI、Google Gemini、OpenRouter、NVIDIA NIM 等，你可以根据需要配置其他模型。
 
 
 
二、下一步操作建议
 
1. 验证配置是否生效
​
- 启动 OpenClaw 网关：

- 
 ./start_openclaw.sh

​
- 在手机浏览器中访问  http://localhost:18789 ，进入 Web 控制台。
​
- 发送一条测试指令，例如“你好，介绍一下自己”，确认 DeepSeek 模型能正常响应。
​
2. 切换其他模型（可选）

  
​
- 如果你想使用其他模型（如 OpenAI GPT-4o、Google Gemini 等），可以点击对应的提供商，输入 API Key 进行配置。
​
- 配置完成后，在模型选择列表中切换即可。
​
3. 优化性能（可选）
​
- 在 DeepSeek 配置页中，你可以调整模型参数，如  Max Tokens 、 Temperature  等，以获得更好的生成效果。
​
- 确保手机网络稳定，避免因网络问题导致 API 调用失败。
 
 
 
三、常见问题排查
 
- 如果测试指令没有响应：
​
1. 检查 DeepSeek API Key 是否正确。
​
2. 确认手机网络可以正常访问 DeepSeek 服务器（可能需要开启 VPN）。
​
3. 重启 OpenClaw 网关。






