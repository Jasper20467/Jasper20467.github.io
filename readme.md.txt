# 個人部落格 — 專案說明 (README)

此為個人履歷與技術 / 生活文章分享的靜態網站專案，透過 GitHub Actions 自動化建置與佈署到 Azure，並使用 AWS Route53 綁定 DNS。

## 主要目標
- 儲存並展示個人履歷與文章（技術、生活）
- 使用靜態站點以提升效能與簡化佈署
- CI/CD：GitHub Actions 自動建置與佈署到 Azure
- DNS：使用 Route53 綁定自訂網域、管理 TLS/證書

## 建議專案結構（範例）
- /content/        # 文章或 markdown 原始檔
- /public/         # 靜態輸出（建置後）
- /src/            # 前端程式（若使用框架）
- /static/         # 圖片、資源
- /.github/workflows/  # GitHub Actions workflow
- README.md.txt    # 本檔案
- package.json / hugo config / 等建置設定檔

## 開發與本地建置（範例）
1. 安裝相依（依專案技術選型，如 Hugo / Jekyll / Next / VuePress）
    - npm / yarn / brew / hugo 等
2. 本地啟動
    - npm install
    - npm run dev 或 hugo server
3. 本地檢視並撰寫文章（放到 /content 或對應資料夾），完成後 commit 至 repo

## CI/CD（GitHub Actions） — 範例流程
- 觸發條件：push 到 main 或發 PR
- 步驟：checkout -> install -> build -> deploy 到 Azure

範例（概念性）：
     name: CI - Build & Deploy
     on:
        push:
          branches: [ main ]
     jobs:
        build-deploy:
          runs-on: ubuntu-latest
          steps:
             - uses: actions/checkout@v3
             - name: Setup Node
                uses: actions/setup-node@v3
                with:
                  node-version: '18'
             - name: Install
                run: npm ci
             - name: Build
                run: npm run build
             - name: Deploy to Azure Static Web Apps (example)
                uses: Azure/static-web-apps-deploy@v1
                with:
                  azure_static_web_apps_api_token: ${{ secrets.AZURE_STATIC_WEB_APPS_API_TOKEN }}
                  repo_token: ${{ secrets.GITHUB_TOKEN }}
                  action: "upload"
                  app_location: "/" 
                  output_location: "public"

備註：若改用 Azure Storage / App Service，可改用 azure/login 與 Azure CLI 或使用 publish profile。

## Azure 佈署要點
- 推薦服務：Azure Static Web Apps（簡單、內建 GitHub Actions 支援）或 Azure Storage 靜態網站 + CDN（自訂化、成本效益）
- 建議在 GitHub Secrets 中儲存必要金鑰（AZURE_STATIC_WEB_APPS_API_TOKEN、AZURE_CREDENTIALS、AZURE_WEBAPP_PUBLISH_PROFILE）
- 若需自訂後端 API，可使用 Azure Functions（與 Static Web Apps 整合方便）

## Route53（DNS）綁定與 TLS
- 取得 Azure 給的自訂網域驗證資訊（CNAME、A record 或 TXT 驗證）
- 在 AWS Route53 建立對應的 Record：
  - 若 Azure 提供 A/AAAA 或 ALIAS，建立对应紀錄指向 Azure 資源
  - 若需 CNAME（例如 staticwebapps.net），建立 CNAME 指向 Azure 提供的主機名
- 重新產生/驗證 TLS：Azure 會處理自動憑證（Static Web Apps/Front Door），或自行在 Azure Key Vault / CDN 上管理
- 測試：完成後以 dig / nslookup 驗證 DNS 傳播與 https 連線

## 安全與運維建議（簡短）
- 不在 repo 放置憑證：使用 GitHub Secrets
- 啟用分支保護與 Pull Request 程式碼審查
- 定期更新相依套件與 CI runner 的版本
- 監控靜態站點可用性（簡單的 uptime check）

## 快速檢查清單（部署前）
- [ ] 本地建置成功且 public/ 輸出正確
- [ ] GitHub Actions workflow 已加入 repo 並在 main 有執行紀錄
- [ ] GitHub Secrets（API token / Azure credentials）已設定
- [ ] Azure 上的靜態站點或儲存帳戶已建立
- [ ] Route53 中的 DNS 紀錄已建立並生效
- [ ] HTTPS 可用並通過驗證

---

如需，我可以：
- 產生對應的 GitHub Actions workflow YAML（針對你的靜態產生器）
- 提供 Azure Static Web Apps 或 Azure Storage + CDN 的具體佈署步驟
- 提供 Route53 對應紀錄範例（需你的網域與目標 Azure 主機名）