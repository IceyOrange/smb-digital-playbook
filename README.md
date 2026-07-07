# Small Business Digital Playbook

> 40 个真实小生意的数字化方案 —— 每条都附带可直接复制到 [whacka](https://whacka.app) 的 Prompt 和真实 App 示例。

**在线预览**：https://smb-digital-playbook.vercel.app（绑定自定义域名后替换为你的域名）

---

## 这是什么

一个专门面向 SMB（小型商家）的数字化方案展示站：

- 覆盖咖啡、零售、健身、美容、教育、医疗、宠物、家政、本地服务等 10 个行业
- 每个方案包含：**场景描述**、**核心痛点**、**Prompt**、**可打开的真实 App**
- 不需要写代码，复制 Prompt 到 whacka 即可生成自己的版本

## 仓库内容

```
.
├── index.html          # 站点入口（由 smb-cases.html 生成）
├── assets/             # App 截图
└── README.md           # 本文件
```

## 本地预览

```bash
cd smb-digital-playbook
python3 -m http.server 8000
# 访问 http://localhost:8000
```

## 部署到 Vercel + 自定义域名

1. 把本仓库推送到 GitHub（已完成）。
2. 在 [Vercel](https://vercel.com/new) 导入该仓库。
3. Framework Preset 选 **Other**，Build Command 和 Output Directory 留空。
4. 进入项目 **Settings → Domains**，添加你的域名。
5. 在域名服务商处按 Vercel 提示添加 DNS 记录：
   - `@` → A 记录 `76.76.21.21`
   - `www` → CNAME `cname.vercel-dns.com`
6. 等待 DNS 生效，Vercel 会自动签发 HTTPS。

## 内容更新

本站内容由 Notion 数据库 `ideas_for_SMB` 同步生成。更新流程：

1. 在 Notion 中修改或新增 SMB 方案。
2. 运行同步脚本（位于主项目 `app_prompt_lib`）：
   ```bash
   python3 .agents/skills/sync-pages/scripts/sync_pages.py smb
   ```
3. 将更新后的 `smb-cases.html` 复制到本仓库并改名为 `index.html`：
   ```bash
   cp /Users/Lovegood/Desktop/app_prompt_lib/smb-cases.html \
      /Users/Lovegood/Desktop/app_prompt_lib/smb-digital-playbook/index.html
   ```
4. 提交并推送，Vercel 会自动重新部署。

---

Small Business Playbook · Digital setups grown from real shop floors
