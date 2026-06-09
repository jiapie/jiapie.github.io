---
title: "03.生成式 AI 應用技能"
type: "docs"
weight: 3
tags: ["Tech", "AI", "GenAI", "資策會"]
---

# 03.生成式 AI 應用技能

這部分考不同媒介（文字、聲音、影像）的工具定義與 Prompt 技巧。

---

## 語音識別技術與語音轉文字應用

**語音技術兩大方向：**

| 方向 | 英文縮寫 | 說明 |
|------|---------|------|
| **語音轉文字** | ASR（Automatic Speech Recognition）/ STT | 將語音訊號轉為文字，是語音輸入的基礎 |
| **文字轉語音** | TTS（Text-to-Speech） | 將文字合成為自然語音，用於播報、閱讀輔助 |

**ASR 語音識別流程：**
```
音訊輸入 → 特徵提取（MFCC 梅爾頻率倒譜係數）→ 聲學模型 → 語言模型 → 文字輸出
```

**關鍵技術：**
- **MFCC（Mel-Frequency Cepstral Coefficients）**：模仿人耳感知特性的音訊特徵，是語音辨識標準前處理
- **聲學模型**：將音訊特徵映射到音素（phoneme），早期用 HMM，現代用深度神經網路
- **語言模型**：決定詞序合理性，確保輸出符合語法（現代以 Transformer 為主）
- **端對端模型（End-to-End）**：直接從音訊輸出文字，代表：OpenAI Whisper、Google Speech-to-Text

**TTS 與 SSML：**
- **TTS**：文字轉語音，現代採用神經 TTS（如 WaveNet）生成自然語調
- **SSML（語音合成標記語言）**：XML 格式，精準控制 TTS 的停頓 `<break>`、語速 `rate`、音高 `pitch`
- **語音克隆（Voice Cloning）**：只需少量樣本即可複製特定人聲音色

**應用場景：** 語音助理（Siri/小愛）、會議記錄自動轉寫、客服語音機器人、語音翻譯

> **陷阱：** 企業 BYOG 工具（Build Your Own GPT）是指自建語言模型，與聲音生成無關。

---

## 生成模型與 AI 在創作領域的應用

**主要生成模型類型：**

| 模型 | 核心機制 | 創作應用 |
|------|---------|---------|
| **GAN** | 生成器 vs 判別器對抗 | 圖像生成、人臉合成、DeepFake、風格轉換 |
| **VAE** | 機率潛在空間取樣 | 影像重建、藥物分子設計 |
| **擴散模型（Diffusion）** | 逐步加噪→去噪重建 | 文生圖（Stable Diffusion、DALL-E、Midjourney） |
| **Transformer / LLM** | 自迴歸文字生成 | 小說、劇本、詩歌、程式碼生成（ChatGPT、Claude） |
| **神經風格轉換（NST）** | CNN 特徵融合內容＋風格 | 照片轉繪畫風格 |

**創作 AI 各領域代表工具：**

| 媒介 | 工具 / 技術 |
|------|-----------|
| 🖼 圖像生成 | Stable Diffusion、Midjourney、DALL-E 3 |
| 🎵 音樂生成 | Suno、Udio、MusicGen（Meta） |
| 🎬 影片生成 | Sora（OpenAI）、Runway Gen-3 |
| ✍️ 文字創作 | ChatGPT、Claude、Gemini |
| 🗣 語音合成 | ElevenLabs（語音克隆）、OpenAI TTS |

**文生圖 Prompt 技巧（考試重點）：**

- 聲音與影像生成專有名詞：
    - TTS（文字轉語音） 與 SSML（語音合成標記語言）：SSML 用於精準控制 TTS 的停頓、語速與音高。
    - 語音克隆（Voice Cloning）：複製特定人類的音色。
    - 陷阱：企業 BYOG 工具（Build Your Own GPT / Bring Your Own Generation）是指自建大腦或自備電廠，與聲音生成無關。

- Prompt 工程（提示詞技巧）：
    - Few-shot Prompting（少樣本提示）：在 Prompt 中提供1~2個範例給 AI 模仿。
    - CoT（Chain-of-Thought，思維鏈）：在 Prompt 加入「請一步一步思考」，能顯著提升 AI 在邏輯與數學推理上的準確度。

- Prompt 優化技巧：
    - **加入更多細節描述**：補充主體的材質、光影、背景或動作，能縮小 AI 瞎猜的範圍。
    - **輸入期待的產出風格**：指定如「賽博朋克(Cyberpunk)、寫實攝影(Photorealistic)、吉卜力動漫風」等風格關鍵字，能直接限定視覺調性。
    - **嘗試以不同方式、字詞描述**：當 AI 誤解某個詞彙時，換成同義詞或調整句型結構(例如將長句拆成權重標籤)，是調整 AI 理解偏差的有效方法。

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

### Context Engineering（上下文工程）

讓 LLM 能更準確理解和處理輸入資料的技術策略。

**表格資料處理：**
- Excel 匯出的原始表格（`.csv`、`.xls`）LLM 解析效果不穩定
- **最佳做法**：將表格轉換為 **Markdown table** 或 **JSON** 格式再輸入

```
❌ 直接貼上 CSV 格式（逗號分隔，不易解析）
✅ 轉換為 Markdown table 或 JSON（結構清晰，LLM 可準確理解）
```

**Few-shot 的局限性：**
- 少量範例難以涵蓋所有情境（尤其面對新市場或新類別資料）
- 若範例未覆蓋新情境的資料差異，分類結果會不穩定
- 解法：增加覆蓋度更廣的範例、或採用 Fine-tuning / RAG 補強知識

---
## 參考資料
