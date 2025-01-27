

## パッケージ

簡単に説明すると、パッケージとはカスタム ノードの集合のことです。Dynamo Package Manager は、オンラインでパブリッシュされたパッケージをダウンロードするためのコミュニティ ポータルです。これらのツールセットは、Dynamo の基本機能を拡張するためにサード パーティによって開発されたもので、すべてのユーザがアクセスでき、ボタンをクリックするだけでダウンロードすることができます。

![](images/10-1/dpm.png)

Dynamo のようなオープンソース プロジェクトは、このようなコミュニティによって成長しています。サード パーティの専任開発者の取り組みにより、Dynamo はさまざまな業界のワークフローで採用されています。そのため、Dynamo チームは、パッケージの開発とパブリッシュの合理化を連携して進めています。これについては、以降のセクションで詳しく説明します。

### パッケージをインストールする

パッケージを最も簡単にインストールする方法は、Dynamo インタフェースの[パッケージ]ツールバーを使用する方法です。では、実際にインストールしてみましょう。ここでは、次に示す簡単な例を使用して、グリッド上に四角いパネルを作成するためのパッケージをインストールします。![](images/10-1/AddingToLibrary- 01.png)

> 1. Dynamo で、*[パッケージ] > [パッケージの検索]*に移動します。

![](images/10-1/AddingToLibrary- 00.png)

> [検索]バーで、「quads from rectangular grid」を検索してみましょう。しばらくすると、この検索クエリーに一致するパッケージがすべて表示されます。一致する名前を持つ最初のパッケージを選択します。

> 1. パッケージ名の左に表示されているダウンロード矢印アイコンをクリックします。

![](images/10-1/buildz.png)

> 1. Dynamo ライブラリに「*buildz*」という名前の新しいグループが表示されます。 この名前は、パッケージの[開発者](http://buildz.blogspot.com/)を参照して付けられます。また、カスタム ノードはこのグループ内に配置されます。 このグループは、すぐに使用することができます。

![](images/10-1/example.png)

> 矩形グリッドを定義するためのコード ブロック操作を実行することにより、矩形パネルのリストをすばやく作成できます。

### パッケージ フォルダ

上記の例では、1 つのカスタム ノードが含まれているパッケージを使用しましたが、複数のカスタム ノードやサポート データ ファイルが含まれているパッケージをダウンロードする場合も、同じプロセスを実行します。ここでは、より包括的な Dynamo Unfold パッケージを使用して手順を説明します。

![](images/10-1/unfold.png)

> 上記の例と同様に、*[パッケージ] > [パッケージの検索]*を選択します。 ここでは、「*DynamoUnfold*」という 1 つの単語を、大文字と小文字を区別して検索します。 パッケージが表示されたら、パッケージ名の左に表示されている矢印をクリックしてパッケージをダウンロードします。Dynamo Unfold が Dynamo ライブラリにインストールされます。

![](images/10-1/unfoldLibrary.png)

> Dynamo ライブラリに *DynamoUnfold* グループが表示されます。このグループに、複数のカテゴリとカスタム ノードが含まれているのがわかります。

![](images/10-1/manage.png)

> ここで、パッケージのファイル構造を確認しましょう。Dynamo で*[パッケージ] > [パッケージを管理]*を選択します。 上記のウィンドウに、インストールされている 2 つのライブラリが表示されます。*DynamoUnfold* の右に表示されているボタンをクリックし、[*ルート フォルダを表示*]を選択します。

![](images/10-1/rd1.png)

> この操作により、パッケージのルート フォルダが表示されます。このルート フォルダには、3 つのフォルダと 1 つのファイルが格納されています。

> 1. *bin* フォルダには .dll ファイルが格納されます。 この Dynamo パッケージは Zero-Touch を使用して開発されているため、カスタム ノードはこのフォルダに格納されます。
2. *dyf* フォルダにはカスタム ノードが格納されます。 このパッケージは Dynamo カスタム ノードを使用して開発されたものではないため、このフォルダには格納されません。
3. extra フォルダには、サンプル ファイルを含め、すべての追加ファイルが格納されます。
4. pkg ファイルは、パッケージの設定を定義する基本のテキスト ファイルです。ここでは、このファイルは無視してかまいません。

![](images/10-1/rd2.png)

> *extra* フォルダを開くと、インストール時にダウンロードされた多数のサンプル ファイルが格納されていることがわかります。 すべてのパッケージにサンプル ファイルが付属しているわけではありませんが、付属のサンプル ファイルはこのフォルダに格納されています。ここで、*SphereUnfold* ファイルを開いてみましょう。

![](images/10-1/sphereUnfold.png)

> ファイルを開いてからソルバで[*実行*]をクリックすると、展開された球形が表示されます。 これらのサンプル ファイルは、新しい Dynamo パッケージの使用方法を理解するのに役立ちます。

### Dynamo Package Manager

Dynamo パッケージの仕組みを理解する別の方法として、[Dynamo Package Manager](http://dynamopackages.com/) をオンラインで参照する方法もあります。 これは、パッケージを参照するのに便利な方法です。リポジトリにより、ダウンロード回数と人気度に応じて、パッケージが並べ替えられます。また、パッケージの最新の更新プログラムに関する情報を簡単に収集することもできます。一部の Dynamo パッケージは、Dynamo ビルドのバージョン管理と依存関係の影響を受けます。

![](images/10-1/dpm2.png)

> Dynamo Package Manager で[*Quads from Rectangular Grid*]をクリックすると、説明、バージョン、開発者、依存関係を確認することができます。

また、Dynamo Package Manager からパッケージ ファイルをダウンロードすることもできますが、Dynamo から直接ダウンロードした方が簡単です。

### ローカルでのファイルの保存場所

Dynamo Package Manager からファイルをダウンロードした場合や、すべてのパッケージ ファイルの保存場所を参照する場合は、*[設定] > [ノードとパッケージのパスを管理]*をクリックします。 フォルダ ディレクトリの横にある省略記号をクリックすると、ルート フォルダをコピーして、エクスプローラ ウィンドウでパッケージを詳細に調べることができます。既定では、パッケージは *C:¥Users¥[ユーザ名]¥AppData¥Roaming¥Dynamo¥[Dynamo バージョン]* というフォルダ パスにインストールされます。

### パッケージの拡張

Dynamo コミュニティは、常に成長と進化を続けています。Dynamo Package Manager を定期的に確認して、便利な新機能を発見してください。これ以降のセクションでは、エンドユーザの視点から見た独自の Dynamo パッケージの作成など、パッケージについてより詳しく確認していきます。

