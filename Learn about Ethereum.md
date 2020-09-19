# 學習 Ethereum

研究[官方學習區](https://ethereum.org/en/learn/)中的文章或影片的重點整理（或是自己覺得有趣的地方）。

## 不錯的起手式

### [Decentralizing Everything](https://www.youtube.com/watch?v=WSN5BaCzsbo&feature=youtu.be)

乙太坊創辦人Vitalik（V神）的演講

- 去中心化貨幣需要有個系統紀錄大家的錢。
- 交易會有經典雙花問題，集中式系統容易解決這個問題，但對於分散式系統很難。
- 可以想像ETH是一個去中心的共享（內存）系統。
- 加密經濟學：加密理論與經濟學誘因理論。
- 合約是可以操控自己資產的程式。
- 要考慮加密貨幣當資料庫時，每秒處理的峰值，目前每個都比集中式的系統差好幾個層級。
- 本身的基礎層級很安全，其他人可以在這之上疊加不同的layer擁有不同的屬性。

### [Why Decentralization Matters](https://onezero.medium.com/why-decentralization-matters-5e3f79f7638e)

網路歷史發展與未來走向

- 2000到現在，網路被大公司把持引發很多問題。
    - 大公司走到最後都是在處理個資。
    - 第三方在這些大公司底下開發最後都會變成競爭關係。
- 網際網路的第三世代，加密經濟網路，由簡單的核心層連接數以萬計的軟體。兩大好處：
    - 社群管理。
    - 分散式網路（可用性最後會大於任何一個集中式管理的網路）。
- 加密網路如何解決這些問題：
    - 利用共識機制維持或更新網路狀態。
    - 利用加密通貨去激勵參與者去讓系統更好（網路的增長及通貨的升值）。
- 目前大部分的能量放在基礎建設，等建得差不多了，這股能量會去開發應用
- 分散式網路最後會成功是因為他贏得了新創和開發者的心，就像網路開被發明一樣。
- 要把分散式網路產品當作一個動態流程，而不是一個最終不變的產品
- 好的誘因讓參與者自動自發地讓這個網路更好
- 通常分散式的平台都是半成品，要需**PMF**
    - 平台和開發者造就一個生態系
    - 平台和終端使用者
  
### [The Year in Ethereum 2019](https://medium.com/@jjmstark/the-year-in-ethereum-2019-242012e4276d)

2019年回顧，裡面有各項Ethereum應用的介紹和發展程度。

- Ethereum經濟持續增長，最主要的是Defi，遊戲和DAOs（decentralized autonomous organizations ）也有看到早期成長的跡象。
- DeFi元年：一個金融系統的另一個選擇，使用者可以透過網路直接控制自己的資產、負債、付款和投資。
    - 穩定幣價機制。
    - 群眾借款取得利息機制。
    - 公開審核、透明且永不關閉的金融體系。
- 乙太上的應用程式開始可以互動跟組合，把他們想成「錢的樂高」
- 去中心交易所：
    - Uniswap：使用者直接跟Uniswap protocol交易，全在鏈上完成。其他的DeFi protocol可以直接呼叫Uniswap protocol去進行交易，把Uniswap當作工具使用。
    - DEXs、Kyber、0x。
- 借貸服務：
    - Compond、MakerDAO。
- 穩定幣
    - Tether從比特幣轉移至ETH，史上最大的鍊鍊轉移。
- 基於乙太的資產
    - TokenSets：例如ETH漲就幫客戶多持有ETH，ETH跌就自動換成穩定幣保值。
    - Universal Market Access (UMA)：多種資產錨定現實資產，如股票。
- 遊戲： 
    - Gods Unchained，裡面用到一個技術NFT（非同質化代幣）。
    - PoolTogether：零損失的樂透遊戲。
    - 遊戲跟金融的邊界漸漸消失，金融應用程式像遊戲，遊戲應用程式裡面有金融系統。
- DAO（Decentralized Autonomous Organizations）
    - 一個藉由定義好的自治原則來管理資產的程式。
    - MolochDAO：會員可以決定要贊助哪一個專案。
    - Saint Fame：會員決定要哪種設計的T-shirt，決定要不要賣，價格交由市場決定。買家買到token可以去換T-shirt。
    - Aragon：一個開發DAO的框架和SDK。
- NBA球星將自己的合約token化，讓大家可以買token並得到將來合約的分潤。
- 明年ETH發行率會再減半。
- ETH2:
    - 從proof of work 轉成 proof of stake。
    - 更動太大，會分成不同階段推出。
- Layer 2 和鏈下技術
    - 利用昂貴的鏈下運算，達到高速交易但又有乙太坊原有的安全性特色，適合那些需要scale up的服務。
    - Connext：可以程式化的微支付應用，瀏覽器base。
    
## Ethereum 如何運作

### [How does Ethereum work, anyway?](https://medium.com/@preethikasireddy/how-does-ethereum-work-anyway-22d1df506369)

#### 區塊練

一個共享狀態，加密保護的單例機器。

- 共享狀態：狀態是公開且分享給所有人。
- 加密保護：藉由複雜的數學演算法讓加密貨幣難以破壞（創造假交易、抹除歷史交易...等）
- 單例機器：只有一種（所有人都認可的現實）符合規範的機器去處理所有的交易。（這裡機器應該是指某種狀態機的機器？）

#### Ethereum 區塊鏈的典範解釋
- Ethereum區塊鏈本質上是一個基於交易的狀態機（狀態機：基於input而改變本身狀態的機制）。
- 交易紀錄被分組成區塊，每個區塊被他們上一個區塊給綁住。
- 為了驗證交易合法，會有個驗證機制叫做挖礦。
- 挖礦是指一群節點（電腦們）消耗其運算資源去驗證一個區塊的合法性。
- 只要礦工提供一個驗證的區塊，新的ETH tokens就會被產生當作獎勵。
- 節點產生不同區塊路徑時，會產生多鏈情況，也就是多狀態。
    - 也就是分叉 fork。
    - 會逼大家去選擇哪一個區塊路徑是大家所相信的。
- 例用GHOST protocol（Greedy Heaviest Observed Subtree）來選擇大家接受的狀態（大家相信的合法）
    - 永遠挑已被運算最多（也就是最長）路徑。
#### 帳戶 Account

- 所謂Ethereum的共享狀態，即是由許多小小的物件（帳戶）所構成。
- 每一個帳戶都有一個與其關聯的狀態及一個20 bytes的address（一個 160 bits的識別碼去區分不同的帳戶）。
- 兩種帳戶：
    - 外部擁有的帳戶：藉由private key控制，無程式碼。
      - 藉由private key創造及簽署交易來發送訊息給其他帳戶（外部或合約）。
      - 訊息發給外部擁有帳戶：價值交換。
      - 訊息發給合約帳戶：啟動合約帳戶的程式來執行各種活動。
    - 合約帳戶：藉由其內的程式碼控制，有程式碼。
      - 合約帳戶無法自己發起一個交易。
      - 只能被動啟動。
- 所以只有外部擁有帳戶可以發動交易。
- 帳戶狀態包含四種東西：隨機數、餘額（多少Wei，1 wei = 10-18ETH）、storageRoot、codeHash。
- 世界狀態包含了一個帳戶address和帳戶狀態的映射。儲存這種映射關係的資料結構稱Merkle Patricia tree。
（Merkle Patricia tree的講解太複雜，大致就是為什麼Ethereum驗證可以快、也可以快速回滾，如果要研究什麼叫做輕節點，需要研究這段。但目前先跳過...）。

#### Gas 和支付
- 每一次由交易結果而產生的運算都需要費用。
- Gas是衡量費用的單位。
- Gas Price是指你願意用多少ETH買一個gas，單位gwei。
  - 1 gwei =  1,000,000,000 Wei
- Gas limit，一次交易你最多想付gas。
- 一次交易真正的費用：消耗多少gas x gas price。
- 交易完多的Gas會還你，不夠用交易會失敗，中間消耗的gas不會還你。
- 除了交易要費用，儲存資料也要費用。（儲存資料？？）
- 所有付的gas都會進礦工的address。
- 費用的機制是要防止濫用系統的使用者。


