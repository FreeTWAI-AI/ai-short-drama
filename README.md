# ai-short-drama

> 把「假廢物真強者、重生、系統、隱藏大佬、逆襲」從題材標籤，編譯成有起承轉合、角色一致性、每集爽點與追更鉤子的 AI 短劇系統。

`ai-short-drama` 是給 Codex、Claude Code 與相容 Skills 客戶端使用的開源 Skill。它負責故事與連載狀態，不把整部短劇塞進一條生成提示詞。

## 能做什麼

- Scout：研究當下題材、平台與案例。
- Greenlight：用八維評分選出值得測試的概念。
- Bible：建立角色、世界規則、能力代價、揭露與反派階梯。
- Season／Episode：規劃 micro-arc，寫出有 dominant turn、payoff、cliffhanger 與 state delta 的單集。
- Produce：輸出 schema-valid production pack、固定 entity ID、逐鏡生成 brief 與剪輯 handoff。
- Audit：分開診斷概念、單集、整季、生產與包裝問題。

## 安裝

```bash
# Codex
git clone https://github.com/Hao0321/ai-short-drama.git ~/.codex/skills/ai-short-drama

# Claude Code
git clone https://github.com/Hao0321/ai-short-drama.git ~/.claude/skills/ai-short-drama
```

安裝後可直接說：

```text
用 $ai-short-drama 把「被當成廢物的外送員其實能倒轉五秒，但每次會失去一段記憶」做成三集 pilot。
```

## 自動化邊界

核心 Skill 可獨立完成概念、劇本、production pack、schema／lint 驗證與下游 handoff。

- 媒體提示詞與生成建議：搭配 [ai-media-generator](https://github.com/Hao0321/ai-media-generator)。
- 自動組裝 `current.mp4`：需另外安裝 `video-autopilot/drama_autopilot.py` 或提供相容剪輯執行器。
- 登入、額外付費、模型能力不符、合規不確定與正式公開發布，必須停下確認。

這個公開版本不包含作者的私人系列 Bible、角色資產或未公開故事設定。

## 驗證

```bash
python -m py_compile scripts/drama_lint.py
python scripts/drama_lint.py --help
```

`scripts/production_pack.schema.json` 定義機器欄位；`scripts/drama_lint.py --production-ready <pack.json>` 檢查敘事與連載契約。

## License

MIT
