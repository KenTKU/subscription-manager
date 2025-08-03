# SubsTracker - 訂閱管理與提醒系統

基於Cloudflare Workers的輕量級訂閱管理系統，幫助您輕鬆跟蹤各類訂閱服務的到期時間，並通過Telegram,企業微信等發送及時提醒。

![image](https://github.com/user-attachments/assets/22ff1592-7836-4f73-aa13-24e9d43d7064)

## ✨ 功能特色

### 🎯 核心功能
- **訂閱管理**：添加、編輯、刪除各類訂閱服務
- **智慧提醒**：自訂提前提醒天數，自動續訂計算
- **農曆顯示**：支持農曆日期顯示，可控制開關
- **狀態管理**：訂閱啟用/停用，過期狀態自動識別

### 📱 多渠道通知
- **Telegram**：支持 Telegram Bot 通知
- **NotifyX**：集成 NotifyX 推送服務
- **企業微信應用通知**：支持企業微信應用推送
- **企業微信機器人**：支持企業微信群機器人通知
- **郵件通知**：基於 Resend 的專業郵件服務
- **自訂 Webhook**：支持自訂請求格式和模板

### 🌙 農曆功能
- **農曆轉換**：支持 1900-2100 年農曆轉換
- **智慧顯示**：列表和編輯頁面可控制農曆顯示
- **通知集成**：通知消息中可包含農曆資訊

### 🎨 用戶體驗
- **響應式設計**：完美適配桌面端和行動端
- **備註最佳化**：長備註自動截斷，懸停顯示完整內容
- **即時預覽**：日期選擇時即時顯示對應農曆
- **用戶偏好**：記住用戶的顯示偏好設置

## 🚀 一鍵部署

### 點擊按鈕，一鍵部署到 CloudFlare Workers,

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/wangwangit/SubsTracker)


> 適用於新部署的,以前部署過的直接替換js中的內容即可!

## 📋 三步開始使用

### 1️⃣ 一鍵部署
Fork倉庫,然後點擊自己倉庫裡的部署按鈕，等待部署完成,**注意,KV名稱修改為 `SUBSCRIPTIONS_KV`**
![image.png](https://img.wangwangit.com/file/1751942578108_image.png)

### 2️⃣ 首次登錄
- 訪問部署後的域名
- 預設使用者名稱：`admin`
- 默認密碼：`password`

### 3️⃣ 開始使用
1. **修改默認密碼**（進入系統配置）
2. **配置通知渠道**（選擇一個或多個）
3. **添加訂閱**，設置提醒
4. **享受智慧提醒**！

## 🔧 通知渠道配置

### Telegram
- **Bot Token**: 從 [@BotFather](https://t.me/BotFather) 獲取
- **Chat ID**: 從 [@userinfobot](https://t.me/userinfobot) 獲取

### NotifyX
- **API Key**: 從 [NotifyX官網](https://www.notifyx.cn/) 獲取

### 郵件通知 (Resend)
- **API Key**: 從 [Resend官方教學](https://developers.cloudflare.com/workers/tutorials/send-emails-with-resend/) 獲取
- **發件人信箱**: 必須是已在Resend驗證的域名信箱
- **收件人信箱**: 接收通知的信箱地址
- 支持HTML格式的美觀郵件模板

### 企業微信應用通知
- **推送 URL**: 從 [企業微信應用通知平台](https://push.996007.icu) 獲取
- 支持自訂請求頭和消息模板

### 企業微信機器人
- **推送 URL**: 參考[官方文件](https://developer.work.weixin.qq.com/document/path/91770)獲取


> 💡 **提示**: 系統默認每天早上8點自動檢查即將到期的訂閱


**歡迎大家關注我的公眾號**

![39d8d5a902fa1eee6cbbbc8a0dcff4b](https://github.com/user-attachments/assets/96bae085-4299-4377-9958-9a3a11294efc)



## 🚀 手動部署指南

### 前提條件

- Cloudflare帳戶
- Telegram Bot (用於發送通知)
- 可以直接將代碼丟給AI,幫助查漏補缺

### 部署步驟

1.登陸cloudflare,創建worker,黏貼本項目中的js代碼,點擊部署

![image](https://github.com/user-attachments/assets/ff4ac794-01e1-4916-b226-1f4f604dcbd3)


2.創建KV鍵值 **SUBSCRIPTIONS_KV**

![image](https://github.com/user-attachments/assets/c9ebaf3e-6015-4400-bb0a-1a55fd5e14d2)


3.給worker綁定上鍵值對,以及設置定時執行時間!

![image](https://github.com/user-attachments/assets/25b663b3-8e8e-4386-a499-9b6bf12ead76)


4.打開worker提供的域名地址,輸入默認帳號密碼: admin  password (或者admin admin123),可以在代碼中查看默認帳號密碼!

![image](https://github.com/user-attachments/assets/5dac1ce0-43a3-4642-925c-d9cf21076454)


5.前往系統配置,修改帳號密碼,以及配置tg通知的資訊

![image](https://github.com/user-attachments/assets/f6db2089-28a1-439d-9de0-412ee4b2807f)


6.配置完成可以點擊測試通知,查看是否能夠正常通知,然後就可以正常添加訂閱使用了!

![image](https://github.com/user-attachments/assets/af530379-332c-4482-9e6e-229a9e24775e)


## 贊助
本項目的 CDN 加速和安全保護由騰訊 EdgeOne 贊助。
[Best Asian CDN, Edge, and Secure Solutions - Tencent EdgeOne](https://edgeone.ai/?from=github)
![image](https://edgeone.ai/media/34fe3a45-492d-4ea4-ae5d-ea1087ca7b4b.png)

## 🤝 貢獻

歡迎貢獻代碼、報告問題或提出新功能建議!

## 📜 許可證

MIT License

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=wangwangit/SubsTracker&type=Date)](https://www.star-history.com/#wangwangit/SubsTracker&Date)
