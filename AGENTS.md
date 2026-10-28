# AGENTS.md

> 写给在本仓库工作的 AI 代理（如 DeepSeek Harness / DSH）。第 2 节人类协作者同样适用。

## 1. 仓库是什么

- 个人技术笔记库，主题集中在高速 SerDes / 光通信物理层与测试：码元、调制（NRZ / PAM4）、TDECQ、PRBS、眼图、均衡等。
- 纯 Markdown 笔记，没有代码、构建流程和测试套件。
- 远端：`git@github.com:FWanye/Knowledge-of-electronic-information-hardware.git`，主分支 `main`。

## 2. 提交与协作约定（最重要）

1. **作者身份**：AI 的提交以仓库主身份提交——作者为 `yaotng <yaotng5@qq.com>`，使贡献计入其账号；同时在提交信息末尾另起一段加共同作者标记：

   ```
   Co-authored-by: DeepSeek Harness <agent@dsh.local>
   ```

   不要修改全局或仓库本地的 `user.name` / `user.email`。
2. **先同步再推送**：提交/推送前先 `git fetch`；**禁止 force push、禁止改写历史、禁止删分支**。
3. **不动别人的工作**：只提交自己改动的文件；不 stash、不 reset 未提交的改动；发现工作区有未知改动时先停下来询问。
4. **改动粒度**：小改动（错字、补充、格式）可直接提交；大改动（新建笔记、结构调整）先给出 diff 摘要或改在 `agent/<主题>` 分支上，由仓库主合并。
5. **提交信息**：沿用现有风格，`note:` / `feat:` 前缀 + 中文短描述，例如 `note: 速率与编码基础（Rate_Coding）`。

## 3. 笔记写作风格

- 中文，面向工程实践，先结论后展开；开头用一句加粗的话点出主线。
- 用 `### 1. xxx` 编号小节；关键术语首次出现加粗，并补英文或缩写。
- 公式用 `$...$` / `$$...$$`；对比用 Markdown 表格。
- 相关笔记之间用相对链接互相引用，如 `[Serdes_PAM.md](Serdes_PAM.md)`。
- 引用外部资料时在文末注明来源（链接 + 日期）。

## 4. 文件命名

- 形如 `主题_子主题.md`，用英文或缩写、首字母大写：`Serdes_PAM.md`、`TDECQ_PAM4.md`、`Rate_Coding.md`。
- 一个主题一个文件，避免碎片化；内容相近时优先并入已有笔记而不是新建。

## 5. 隐私

- 不写入公司内部资料、未公开芯片/项目信息、个人联系方式等隐私内容。

## 6. 本机环境提示

- Windows + Git for Windows；仓库本地已设置 `core.sshCommand` 指向系统 OpenSSH（`C:/Windows/System32/OpenSSH/ssh.exe`），因为在受限沙箱里 Git 自带的 MSYS ssh 会报 signal pipe 错误。
- 访问 GitHub 偶发连接超时，遇到时重试 2–4 次即可，不必改配置。

## 7. 维护

- 协作约定或写作风格变化时，同步更新本文件，让它始终是"当前约定"而不是历史记录。
