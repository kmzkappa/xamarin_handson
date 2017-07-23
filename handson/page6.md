## 暗号化処理の作成

ログインサービスへのアクセスは完成しましたが、実際のログインに失敗しました。  
これは、入力したパスワードを暗号化せずにサーバに送信しているからです。

NXのクライアントでは `NXCryptoProvider` で暗号化をしています。  
`NXCryptoProvider`では内部で `System.Security.Cryptography` を使用しています。
しかし、APIの制限によりPCLからは `System.Security.Cryptography` を呼ぶことはできません。

ここでは、Androidプロジェクト側に `NXCryptoProvider` を実装し、ViewModelから呼び出すようにします。

