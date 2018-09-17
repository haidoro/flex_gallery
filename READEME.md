# FlexBoxを使ったイメージギャラリー

divタグで画像をタグ付けします。もちろん、liタグでもOKです。

CSSでは「img」要素に対して「display: block」と「width: 100%」を設定しておきます。
これでフルードイメージが出来上がります。

それぞれの画像はdivかliで囲みます。これはクラス名「.gallery-img」として、その親要素には
クラス名「.gallery-imgs」とします。

「.gallery-imgs」がflexコンテナで「.gallery-img」がflexアイテムになります。

「.gallery-imgs」がflexコンテナに「display: flex」としてFlexBoxを作成します。基本レイアウトはこれだけです。

次に、各flexアイテム「.gallery-img」にサイズを決めます。これは「flex-basis」で決めます。  
nth-child(4n+1)〜nth-child(4n+4) を使うことで１番目から4番目まで個別のサイズを決めます。あとは、また最初から4番目のサイズが繰り返されます。

また、「.gallery-img」に対して「flex-grow: 1」を指定することで、横幅が不足する場合に適度な拡大が行われます。これによりレイアウトは単純なサイズの繰り返しだけではなく状態に応じてフレキシブルなサイズとなります。

「.gallery-img」には左にマージンを8px入れています。けれども、この場合左端と右端はマージン0の状態にしたいので「.gallery-imgs」に「margin-left: -8px」を設定することで左端のマージンを相殺しています。

img要素に「object-fit: cover」をつけたのは画像をトリミングするためです。「cover」を指定するとちょうど「background-size:cover」のような挙動をしてくれます。