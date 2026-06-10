---
title: "03.生成式 AI 應用技能"
type: "docs"
weight: 3
tags: ["Tech", "AI", "GenAI", "資策會"]
---

# 03.生成式 AI 應用技能

這部分依認證簡章附錄A分為八大應用類別，考各類生成式 AI 工具與應用場景。

---

## 3.1 文字生成

**主流文字生成工具：**

| 工具 | 開發商 | 特點 |
|------|------|------|
| **ChatGPT** | OpenAI | 最廣泛使用的對話式 AI；支援圖像輸入（GPT-4o）、記憶功能、Plugin |
| **Gemini** | Google | 深度整合 Google 服務（Gmail、Docs、Drive）；支援多模態輸入 |
| **Claude** | Anthropic | 長上下文視窗（200K token）；注重安全性與 Responsible AI |
| **Microsoft Copilot** | Microsoft | 整合 Office 365 套件；基於 GPT-4 |

**主要應用場景：** 文章撰寫、摘要生成、翻譯、Email 草稿、會議紀錄、客服回覆

**Prompt 工程四大維度（文字生成關鍵）：**

| 維度 | 說明 |
|------|------|
| **明確性** | 指令具體清楚，避免模糊 |
| **結構化** | 提供角色（Role）、任務（Task）、輸出格式（Format）|
| **控制範圍** | 限定字數、語言、主題 |
| **迭代優化** | 觀察結果後持續修改 Prompt |

---

## 3.2 圖片生成

**主流圖片生成工具：**

| 工具 | 開發商 | 技術基礎 |
|------|------|---------|
| **DALL-E 3** | OpenAI | Diffusion Model；整合於 ChatGPT |
| **Midjourney** | Midjourney | Diffusion Model；高藝術風格品質 |
| **Stable Diffusion** | Stability AI | 開源 Diffusion Model；可本地部署 |
| **Adobe Firefly** | Adobe | 訓練於商業授權素材；適合設計用途 |
| **ChatGPT Image 2** | OpenAI | 進階圖像生成，支援精細編輯與修改 |

**核心技術：**

| 模型 | 核心機制 | 說明 |
|------|---------|------|
| **GAN（生成對抗網路）** | 生成器 vs 判別器對抗 | 圖像合成、DeepFake、風格轉換 |
| **Diffusion Model（擴散模型）** | 逐步加噪→去噪重建 | 現代文生圖主流（DALL-E、Stable Diffusion）|
| **CNN（卷積神經網路）** | 特徵提取 | 圖像分類、物件偵測、風格融合（NST）|

**文生圖 Prompt 技巧：**
- 加入材質、光影、背景等細節描述，縮小 AI 猜測範圍
- 指定視覺風格（賽博朋克、寫實攝影、吉卜力動漫風）
- 換同義詞或調整句型結構解決 AI 誤解

---

## 3.3 簡報生成

**主流簡報生成工具：**

| 工具 | 說明 | 特點 |
|------|------|------|
| **Gamma** | AI 簡報生成平台 | 輸入大綱或文字，自動生成完整簡報；支援多種設計主題 |
| **Gemini Canvas** | Google Gemini 的創作模式 | 在 Gemini 內直接生成並編輯簡報、文件 |
| **Google Slides + Gemini** | Google 辦公套件 | 在 Slides 中使用 AI 輔助生成投影片內容 |
| **Microsoft Copilot + PowerPoint** | Microsoft | 以 Prompt 描述即可生成 PPT 投影片 |

**三種主要創作模式：**
1. **從大綱生成**：提供章節架構，AI 自動填入內容
2. **從文件生成**：上傳 PDF/Word，AI 自動萃取重點製成簡報
3. **從 Prompt 生成**：描述主題與需求，AI 端對端生成完整簡報

---

## 3.4 聲音生成

**語音技術兩大方向：**

| 方向 | 縮寫 | 說明 |
|------|------|------|
| **語音轉文字** | ASR / STT | 將語音訊號轉為文字；代表：OpenAI Whisper、Google Speech-to-Text |
| **文字轉語音** | TTS | 將文字合成為自然語音；代表：ElevenLabs、OpenAI TTS |

**TTS 相關技術：**
- **SSML（語音合成標記語言）**：XML 格式，精準控制停頓 `<break>`、語速 `rate`、音高 `pitch`
- **語音克隆（Voice Cloning）**：只需少量樣本即可複製特定人聲（ElevenLabs）
- **SpeechSynthesis API**：瀏覽器原生 Web API，可在網頁端直接使用 TTS

**AI 音樂生成：**

| 工具 | 說明 |
|------|------|
| **Suno AI** | 輸入文字描述即可生成完整歌曲（含詞、曲、演唱）|
| **Udio** | AI 音樂創作工具，支援多種音樂風格 |
| **MusicGen（Meta）** | 開源 AI 音樂生成模型 |

> **陷阱：** 企業 BYOG（Build Your Own GPT）是指自建語言模型，與聲音生成無關。

---

## 3.5 影片生成

**主流影片生成工具比較：**

| 工具 | 開發商 | 特點 |
|------|------|------|
| **Sora** | OpenAI | 高品質文生影片；可生成複雜物理效果與長達 1 分鐘影片；加入 C2PA 版權標記 |
| **Veo** | Google DeepMind | Google 的文生影片模型；整合 SynthID 隱形浮水印；高品質 4K 輸出 |
| **Vrew** | Vrew（韓國）| AI 影片剪輯工具；自動字幕、腳本生成、語音合成；適合 Youtuber |
| **HeyGen** | HeyGen | AI 虛擬人物影片；數位人克隆、多語言配音翻譯 |
| **Runway Gen-3** | Runway | 專業 AI 影片創作平台 |

**AI 影片內容標示技術：**
- **SynthID（Google）**：在每一幀嵌入**不可見**數位浮水印，肉眼不可見但可機器偵測
- **C2PA（Content Credentials）**：嵌入元數據記錄創作者、工具、修改歷程，提供來源可追溯性
- **可見浮水印**：Sora 預設在生成影片中加入動態浮水印

---

## 3.6 程式生成

**主流程式輔助工具：**

| 工具 | 說明 |
|------|------|
| **GitHub Copilot** | 整合於 VS Code 等 IDE；即時補全程式碼、生成函數、解釋錯誤 |
| **Cursor** | AI 原生程式碼編輯器；支援整個專案的上下文理解與修改 |
| **ChatGPT / Claude** | 透過對話生成、解釋、除錯程式碼 |
| **Microsoft Copilot** | 整合於 Azure、Office，支援 Power Automate 自動化腳本 |

**No-Code / Low-Code 開發：**

| 類型 | 工具 | 適用對象 |
|------|------|---------|
| **No-Code** | Bubble、AppSheet、Glide | 完全無需寫程式，拖拉介面建立應用 |
| **Low-Code** | Power Platform、Retool | 少量程式碼配合視覺化介面 |
| **GenAI 輔助** | ChatGPT、Gemini、Copilot | 以自然語言描述需求，AI 生成程式碼 |

> **考試重點：** No-Code/Low-Code 降低技術門檻，讓非工程師也能建立 AI 自動化工作流程。

---

## 3.7 數據分析

**AI 輔助數據分析工具：**

| 工具 | 說明 |
|------|------|
| **NotebookLM** | Google 的 AI 知識助理；上傳 PDF/文件後可對話問答、摘要、生成播客音頻 |
| **Napkin AI** | 將文字描述自動生成資料視覺化圖表（流程圖、比較圖、時間軸）|
| **ChatGPT Data Analysis** | 上傳 CSV/Excel，AI 自動分析、生成圖表、解釋數據趨勢 |
| **Microsoft Copilot for Excel** | 在 Excel 中使用自然語言進行資料分析、公式生成、視覺化 |

**探索式資料分析（EDA）：**
- **EDA（Exploratory Data Analysis）**：在正式建模前，透過統計與視覺化方式探索資料特徵、分布、相關性與異常值

**Context Engineering（上下文工程）：**
- Excel 匯出的原始表格（`.csv`、`.xls`）LLM 解析效果不穩定
- **最佳做法**：將表格轉換為 **Markdown table** 或 **JSON** 格式再輸入

---

## 3.8 聊天機器人

**主流聊天機器人平台：**

| 工具 | 說明 | 應用場景 |
|------|------|---------|
| **Gemini Gems** | Google Gemini 的個人化 AI 助理，可自訂角色、指令與知識範圍 | 備考助理、語言教學、客服機器人 |
| **ChatGPT GPTs** | OpenAI 的自訂 GPT，可配置人格、知識庫與工具 | 企業內部助理、產品問答機器人 |
| **LINE Bot + ChatGPT API** | 透過 API 串接 LLM 的即時通訊機器人 | 客服自動化、提醒通知 |
| **Microsoft Copilot Studio** | 低程式碼聊天機器人建置平台 | 企業客服、IT 幫助台 |

**Gemini Gems 四大使用情境：**
1. **學習輔助**：上傳教材，以對話方式深化理解
2. **語言練習**：設定外語對話情境，進行口語或寫作練習
3. **創意寫作**：設定角色與風格，協助劇本或文案創作
4. **工作助理**：設定職務背景與 SOP，協助日常工作任務

---

## 進階 Prompt 策略

### 推理策略比較

| 策略 | 核心概念 | 適用場景 |
|------|---------|---------|
| **Zero-shot** | 不提供任何範例，直接給指令 | 簡單任務、快速測試 |
| **Few-shot** | 提供 1–N 個範例引導模型 | 新情境分類、格式固定任務 |
| **Chain-of-Thought（CoT）** | 要求模型「逐步展開推理過程」 | 數學、邏輯推理、多步驟問題 |
| **Tree of Thoughts（ToT）** | 探索多條推理路徑，從中選最優 | 複雜決策、多可能性問題 |
| **Graph Prompting** | 以結構化方式呈現條件與關聯，明確說明多個因素間的依存關係 | 多條件相互影響的規劃問題（如補貨策略）|

> **CoT vs Graph Prompting 差異：** CoT 適合「單一邏輯鏈」的問題；Graph Prompting 適合「多因素互相影響」的複雜場景。

---

### AIGC 商業應用四大挑戰

| 挑戰 | 說明 |
|------|------|
| **幻覺問題（Hallucination）** | LLM 生成看似合理但錯誤的內容，需 RAG 或人工審核 |
| **著作權與版權** | AI 生成內容的所有權歸屬不明，訓練資料的版權爭議 |
| **深偽（Deepfake）** | AI 生成的假影片/音訊可被用於詐騙與輿論操控 |
| **資料隱私** | 用戶輸入的資料可能被用於模型訓練，涉及 GDPR/個資法 |

---
## 參考資料
