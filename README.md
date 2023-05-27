# ResNext
## ポイント
- Residualブロックに、Inceptionと同様のsplit-transform-merge（分割,変換,マージ)戦略を適用し、横にネットワークを拡張した
- Inceptionと大きく違うのは、横に拡張されたネットワークのトポロジー（convのパラメータ）は全て同じ値をもつ。これによって、パラメータ調整の手間が省ける
- **ネットワークを深く、広くするよりも、カーディナリティを増やす方が精度を上げるために効果的**
## NEW Residual Block
<img alt="new residual" src="./image/new_residual_block.png"></img>
- 残差ブロックの幅をInceptionのように拡張した
- チャンネルを分割し、1×1convで畳み込み、その出力マップに3×3convで畳み込む。最後に出力を結合したものに1×1convで畳み込みを行う
- 上記の考えはInceptionの Network in Newtowork とは対照的に, **Network in Nueron**と呼ばれる
- 
