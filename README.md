# yomi-dictionary-data

日文字典資料(給 Yomi 日文學習 App 使用):JMdict 常用詞、繁體中文意思與簡單例句,以及合併後的字典資料檔。

## 檔案

| 檔案 | 內容 |
|---|---|
| `dictionary.dict` | 合併後的字典資料檔(JSON Lines,第一行是標頭 `YOMIDICT1<TAB>筆數<TAB>日期`)。24,535 筆:8,032 個 JLPT 單字 + 16,503 個 JMdict 常用詞。每筆欄位:`i` 編號、`k` 漢字寫法、`r` 讀音、`s` 義項(`p` 詞性、`e` 英文、`z` 中文、`zs` 中文來源 `jlpt`/`subagent`)、`f` 常用度、`l` JLPT 等級、`u` 通常以假名書寫、`x` 例句 `[句子, 帶振假名, 中文, 來源 t/a]` |
| `entries.json` | JMdict 常用詞中、不在 JLPT 單字表內的 16,503 個詞條(JMdict 資料的子集與重新整理) |
| `translations.json` | 為上述詞條產生的繁體中文意思與一句例句(`i` 為 JMdict 編號,`z` 各義項中文,`s`/`r`/`t` 例句、帶振假名的例句、中文翻譯) |

## 品質說明(請先讀)

中文意思與例句是以自動化流程離線產生,再經過自動驗證(義項數、簡體與大陸用語、例句用到該詞、振假名與原句一致、與系統分詞器交叉檢查)與獨立審查(全檢,約 4% 被回報問題並已修正或剔除)。**仍可能有誤**,不保證正確,使用前請自行判斷。45 個詞條沒有中文意思。

## 授權

本儲存庫的資料依 **Creative Commons Attribution-ShareAlike 4.0 International(CC BY-SA 4.0)** 授權:<https://creativecommons.org/licenses/by-sa/4.0/>。你可以分享與改作(含商業用途),但必須標示來源、標示是否有修改,並以相同授權分享衍生作品。

## 來源與標示

- **JMdict**:Copyright © Electronic Dictionary Research and Development Group (EDRDG),CC BY-SA 4.0。授權說明 <https://www.edrdg.org/edrdg/licence.html>,專案 <https://www.edrdg.org/>。取得自 jmdict-simplified(<https://github.com/scriptin/jmdict-simplified>),使用 `jmdict-eng-common-3.6.2+20261102210542`。本資料對 JMdict 的修改:篩選常用詞、整理格式、加上繁體中文意思與例句。
- **JLPT 單字表**(單字與英文意思):Jonathan Waller,<https://www.tanos.co.uk/jlpt/>,CC BY。本資料加上了繁體中文意思、將讀音統一為平假名並重新排序、移除重複項目;這些修改不是原作者所為。JLPT 官方沒有公布單字表,此為坊間通用分級。
- **例句**:部分例句來自 Tatoeba(<https://tatoeba.org>)貢獻者,CC BY 2.0 FR;已做篩選並將中文翻譯轉為繁體;其餘例句為本專案撰寫並經審查(例句來源欄位為 `a`)。

資料版本:建置日期見 `dictionary.dict` 第一行。JMdict 會持續更新,本資料會定期更新。
