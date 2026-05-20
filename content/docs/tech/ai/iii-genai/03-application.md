---
title: "三、生成式 AI 應用技能"
type: "docs"
weight: 3
tags: ["Tech", "AI", "GenAI", "資策會"]
---

# 三、生成式 AI 應用技能

這部分考不同媒介（文字、聲音、影像）的工具定義與 Prompt 技巧。

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

## 參考資料
