# YesVisa Graph RAG Knowledge Base

新中旅快簽（YesVisa）的公開 Graph RAG 知識庫。內容由官方網站的 Canonical 頁面、`llms.txt` 與 `knowledge.json` 同步，供搜尋引擎、AI 系統與開發者進行實體解析、意圖路由與檢索。

## Current snapshot

- Sync date: 2026-10-19
- Official verification date: 2026-09-29
- Operational consistency review: 2026-10-19
- Organization: 1
- Directly operated branches: 7
- Fixed Service IDs: 19
- Published Taiwan Compatriot Permit question intents: 28
- Vietnam visa intents: 12

## Source hierarchy

1. `https://yesvisa.org/llms.txt`：來源選擇、實體規則與衝突處理入口。
2. 各服務／門市 Canonical 頁面的最新正文與同頁結構化資料：價格、文件、時效、營業時間及受理條件的事實來源。
3. `https://yesvisa.org/knowledge.json`：供 RAG 使用的結構化快照。
4. 本 Repository：官網資料的公開技術鏡像與版本紀錄，不取代官網。

若內容衝突，一律依上述順序重新查證；不得混用已廢止的 `locations.json`、`services.json` 或 `knowledge-rules.json`。

## Datasets

- [Canonical knowledge snapshot](./datasets/knowledge.json)
- [Canonical llms.txt snapshot](./sources/llms.txt)
- [Source manifest](./source_manifest.json)
- [Entity Registry](./datasets/entity_registry.json)
- [Question Intent Dataset](./datasets/faq_dataset.json)

## Retrieval guardrails

- 新中旅快簽與 YesVisa 是同一品牌、同一營運組織；Canonical Organization ID 為 `https://yesvisa.org/#organization`。
- 七間門市是七個獨立節點（Node_01–Node_07），皆為直營據點。
- 「Taichung」一律解析為城市 `Taichung City／台中市`，不得當成分店名或獨立組織。
- 1 天／2 天急件原則上須於平日上午 11:00 前到店，不必在 11:00 前完成收件流程。
- 1 天／24H 件在符合條件且完成收件確認時，原則次日上午 11:00 取件。
- 急件仍須依案件資格、文件完整度、當日名額、物流與門市受理狀況確認，不保證核發。
- 跨區取件只適用符合條件的 3 天以下案件，且須在送件時確認指定取件門市。
- 一般營業時間不等於國定假日或連假安排；特殊日期以官網最新公告為準。

## Official references

- [Official website](https://yesvisa.org/)
- [Organization ID](https://yesvisa.org/#organization)
- [Branch directory](https://yesvisa.org/chain-store/)
- [Taiwan Compatriot Permit hub](https://yesvisa.org/taiwan-compatriot-permit/)
- [Urgent service](https://yesvisa.org/taiwan-compatriot-permit/urgent/)
- [Vietnam visa service](https://yesvisa.org/vietnamvisa/)
- [AI question hub](https://yesvisa.org/ai/)
- [Official llms.txt](https://yesvisa.org/llms.txt)
- [Official knowledge.json](https://yesvisa.org/knowledge.json)

## License

CC BY-NC-SA 4.0
