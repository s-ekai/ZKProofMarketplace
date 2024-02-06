first week: memo

The concept of a zk proof market has intrigued me, especially after being inspired by the project at https://github.com/nulven/EthDataMarketplace. Zero-knowledge (zk) proofs represent a promising future in technology, potentially becoming more commonly utilized in various applications. For instance, imagine a mechanism within a contract that allows authentication to be executed just once, similar to how proofs are used in Tornado Cash. This paves the way for a future where operations could be managed in a manner akin to the concept 'aa.'

In this context, it becomes crucial to recognize and securely transfer or trade these proofs, much like how NFTs are currently handled. That's where the idea of a zk proof market comes into play.

Transfer of Proofs
Consider a scenario in the zk proof market where we have two individuals, Alice and Bob. Alice wants to transfer a proof, let's call it 'proofA', to Bob. Bob submits his public key 'B' to the zk proof market. Alice then sends the desired proof to Bob, encrypted with his public key B. Bob can decrypt it using his private key B.

This idea is inspired by the project https://github.com/nulven/EthDataMarketplace.

A question arises: Can we universally prove that a zero-knowledge proof is correct using zero-knowledge proof itself?

Regarding 'proofA' and the contract for 'proofA', is it possible to perform computations even in an encrypted state?

In /EthDataMarketplace, the concept revolves around transferring coordinates, but in this case, the entire content is based on the proof.

When transferring a 'dark forest' proof, certain aspects need to be considered, though they might not offer much convenience:

Input private proofA
Input private public key B
Input private coordinates x and y
Output public encryption (encrypting proofA with public key B)
Output public proofA2 (appears by default)
The process involves proving that proofA contains coordinates x and y. If proofA2 is publicly verified as correct, it's acceptable. For verification, external contracts need to be compatible. Alice would leave a record in the dark forest contract, indicating that proofA2 was correctly created. Bob can review this and decide if it's satisfactory. Can the encrypted output be made public for decryption and approval?

The process for verifying with zero-knowledge proof might have slipped my mind, but could this approach work?

It might be better to split the process into steps:

Input private proofA
Input private coordinates x and y
Output public proofA2 (appears by default)
Then, pass proofA2 to a contract for verification. After verification, proofA2 can be published on the zk proof market and checked against the dark forest contract. If it's approved, one can apply, deposit into the zk proof market, and then:

Input private proofA
Input private public key B
Input private coordinates x and y
Output public encryption (encrypting proofA with public key B)
Output public proofA2 (appears by default)
Submit this for verification. If it's approved, a claim can be made. Should there also be a way for the receiving party to detect this?

The concept of recursive zk might be a viable solution here. This idea is further explored in the article "Recursive Zero-Knowledge Proofs: Proof of a Proof of a Proof" at https://coingeek.com/recursive-zero-knowledge-proofs-proof-of-a-proof-of-a-proof/.



Japanese:

zk proof market


https://github.com/nulven/EthDataMarketplace
This project inspired me.

zk is the future.

zk proofはより一般的に使用される可能性があります。
例えばあるコントラクトで一度だけ実行できる認証の仕組みとして(トルネードキャッシュでproofを使用するイメージ)、aaのようなイメージで操作できる未来があると思いました。

その中でproofはより外部から正しいものだと認識し安全に渡したり、売買できる仕組みが必要になります。(NFTのように。)

そこで今回考えたのはzk proof marketです。

# proofの受け渡し
zk proofではAliceさん、Bobさんがいるとして、
AliceさんがproofAをBobさんに渡すとします。
Bobさんはzk proof marketに自分の公開鍵Bを渡します。Aliceさんは渡したいproofを公開鍵Bを使ってBobさんに送り、Bobさんは秘密鍵Bで復号して渡します。

こちらのアイデアは
https://github.com/nulven/EthDataMarketplace
にinspireを受けています。

ゼロ知識証明のproofが正しいことをゼロ知識証明で汎用的に持っていることを証明できますか？

proofA
contract for proofA
暗号化された状態でも計算できる、みたいなことが利用できないか？


/EthDataMarketplaceでは座標の内容を渡すが、今回はその内容が全てproofになっている。


dark forestのproofを渡す場合は考慮する場合(ただしこれは利便性はない)
input private proofA
input private 公開鍵B
input private x
input private y

output public 暗号化(proofAを公開鍵Bで暗号化)
output public proofA2 (デフォで出現)


proofAががx,yを持っていることの証明を行う。
proofA2を公開して外部でそれが正しいと検証できたらOK。
検証する時には外部のコントラクトが対応する必要がある。
Aliceがdark forestのコントラクトに対してproofA2が正しく作成された履歴を置いておく。
Bobはそれをみて大丈夫だと判断する。out 暗号化したものを公開できる？
それを復号化してOKにする。

ゼロ知識証明でverifyする時のプロセス忘れた。けど、これでいける？


これ、順番を分けた方が良い。


input private proofA
input private x
input private y

output public proofA2 (デフォで出現)
にして、

proofA2をコントラクトに渡してverfyしてもらう。
proofA2をzk proof marketで公開して、darkforestのコントラクトで確かめてOKだったら申請、zk proof marketにdepositして、あとは

input private proofA
input private 公開鍵B
input private x
input private y

output public 暗号化(proofAを公開鍵Bで暗号化)
output public proofA2 (デフォで出現)

を提出、これをverifyしてOKだったら、claimできるようにする。
これも相手側で検知できるようにする必要がある？


recursive zkの概念を使えばいける可能性がある。intmax

これ、
https://coingeek.com/recursive-zero-knowledge-proofs-proof-of-a-proof-of-a-proof/