

## 数学的方法

データの最も単純な形式が数値だとするならば、数値を関連づける最も簡単な方法は数学的方法を活用することです。割り算のような単純な演算子から、三角関数などの複雑な計算式まで、数学的方法は数値の関係とパターンを調べるための非常に便利な方法です。

### 算術演算子

演算子は、代数関数と 2 つの入力値を組み合わせて使用する一連のコンポーネントであり、1 つの出力値を生成します(加算、減産、乗算、除算など)。演算子は、[Operators] > [Actions]で使用できます。

|アイコン|名前|構文|入力|出力|
| -- | -- | -- | -- | -- |
|![](../images/icons/add-Large.png)|Add|+|var[]...[], var[]...[]|var[]...[]|
|![](../images/icons/sub-Large.png)|Subtract|-|var[]...[], var[]...[]|var[]...[]|
|![](../images/icons/mul-Large.png)|Multiply|*|var[]...[], var[]...[]|var[]...[]|
|![](../images/icons/div-Large.png)|Divide|/|var[]...[], var[]...[]|var[]...[]|

### パラメータを使用する計算式

> この演習に付属しているサンプル ファイルをダウンロードしてください(右クリックして[名前を付けてリンク先を保存...]を選択): [Building Blocks of Programs - Math.dyn](datasets/4-2/Building Blocks of Programs - Math.dyn)。 すべてのサンプルファイルの一覧については、付録を参照してください。

[Operators]で演算子と変数を組み合わせて**計算式**を作成することにより、複雑な関係を定義することができます。 ここでは、スライダなどの入力パラメータによってコントロールできる計算式を作成してみましょう。

![](images/4-2/4-2-5/01.png)

> 1. **Number Sequence** ノードで、*start、amount、**step* という 3 つの入力に基づいて数列を定義します。 この数列は、パラメータ式内の「t」を表しています。ここでは、サイズの大きなリストを使用して、らせん構造を定義します。

上記の手順により、パラメータ領域を定義するための数値のリストが作成されます。黄金螺旋は、![](images/4-2/4-2-5/x.gif)=![](images/4-2/4-2-5/goldenSpiral.gif) と ![](images/4-2/4-2-5/y.gif)=![](images/4-2/4-2-5/goldenSpiral2.gif) の等式として定義されます。 下図のノード グループは、この等式をビジュアル プログラミングの形式で表現しています。

![](images/4-2/4-2-5/02.png)

> ここからは、順を追ってノード グループを確認していきます。ビジュアル プログラムと記述形式の等式との相違点に注意してください。

> 1. **Number Slider** ノードを使用して、キャンバスに 2 つの数値スライダを追加します。 これらのスライダは、パラメータ式の変数である「*a*」と「*b*」を表します。 これらの変数は、柔軟に変化する定数や、必要な結果に合わせて調整可能なパラメータを表します。
2. 「*****」ノードは、乗算を表します。 このノードを繰り返し使用して、乗算変数を接続します。
3. **Math.RadiansToDegrees** ノードで「*t*」の値を角度に変換して、三角関数内でその角度を評価します。 Dynamo では、三角関数の評価には角度が既定で使用されます。
4. **Math.Pow** ノードは、「*t*」および数値「*e*」の関数として動作し、フィボナッチ数列を作成します。
5. **Math.Cos と Math.Sin** ノードは、三角関数です。パラメータ指定の各点の X 座標と Y 座標を識別します。
6. **Watch** ノードで、出力値として 2 つのリストが生成されたことを確認します。これらのリストが、らせんの生成に使用される点群の *x* 座標と *y* 座標になります。

### 計算式からジオメトリへ

上記の手順でも問題なく機能しますが、多数のノードを使用するため、手間がかかります。より効率的なワークフローを作成するには、セクション 3.3.2.3 の**コード ブロック**に関する説明で、Dynamo 表現の文字列を 1 つのノード内に定義する方法を参照してください。 次の手順では、パラメータ式を使用してフィボナッチ曲線を描画する方法について確認します。![](images/4-2/4-2-5/03.png)

> 1. **Point.ByCoordinates** ノードの *x* 入力に上部の乗算ノードを接続し、*y* 入力に下部の乗算ノードを接続します。 この操作により、パラメータで制御された点群のらせん構造が画面上に表示されます。

![](images/4-2/4-2-5/03aaa.png)

> 1. **Polycurve.ByPoints** ノードの *points* 入力に Point.ByCoordinates ノードの出力を接続します。 ここでは閉曲線は作成しないため、*connectLastToFirst* 入力には何も接続しなくてかまいません。 この操作により、前の手順で定義した各点を通過するらせん構造が作成されます。

これで、フィボナッチ曲線が作成されました。ここからは、2 つの演習で「オウムガイ」と「ヒマワリ」を作成してみましょう。これらは自然界にみられる形状を抽象的に表しているばかりではなく、フィボナッチ曲線の 2 つの異なる適用例を的確に表現しています。

### らせん構造からオウムガイへ

![](images/4-2/4-2-5/03.png)

> 1. 最初に、前の演習と同じ手順を実行します。**Point.ByCoordinates** ノードを使用して、点群をらせん状に並べた配列を作成します。

![](images/4-2/4-2-5/03aa.png)

> 1. 前の演習で使用した **Polycurve.ByPoints** ノードを、参照用ノードとして使用します。
2. 円弧を作成するための **Circle.ByCenterPointRadius** ノードの入力ポートに、前の手順と同じ値を接続します。 radius 入力の値は既定で *1.0* に設定されているため、出力として円弧が即座に表示されます。 点群が基準点から遠ざかっていく様子がよくわかります。

![](images/4-2/4-2-5/03a.png)

> 1. **Circle.ByCenterPointRadius** ノードの radius 入力に元の数値(「*t*」の数列)を接続し、より動的な円弧の配列を作成します。
2. **数列**のノード グループは「*t*」の元の配列です。 これを radius 入力に接続すると、円弧の中心は基準点から離れていきますが、円の半径は次第に長くなっていき、特長的な形状のらせん構造が作成されます。余裕があれば、これを 3D に変換してみてください。

### オウムガイから螺旋葉序パターンへ

ここまでの手順では、円弧を重ねたオウムガイのような形状を作成しました。次に、パラメータ制御のグリッドを使用してみましょう。ここでは、フィボナッチ曲線の基本的ならせんを使用して、フィボナッチ グリッドを作成していきます。結果として、[ヒマワリ](http://ms.unimelb.edu.au/~segerman/papers/sunflower_spiral_fibonacci_metric.pdf)のようならせん形状が作成されます。

![](images/4-2/4-2-5/03.png)

> 1. ここでも、前の演習と同じ手順から開始します。**Point.ByCoordinates** ノードを使用して、点群をらせん状に並べた配列を作成します。

![](images/4-2/4-2-5/04.png)

> 1. **Geometry.Rotate** ノードには、同じ名前のノードが複数存在します。*geometry*、*basePlane*、*degrees* という入力を持つ Geometry.Rotate ノードを選択してください。 geometry 入力に **Point.ByCoordinates** ノードを接続します。
2. **Plane.XY** ノードを *basePlane* 入力に接続します。 これにより、基準点に向かって回り込んでいくように点が描画されます。基準点の位置は、らせんの基準の位置と同じです。
3. **Number Range** ノードで角度を入力することにより、複数の巻き筋を作成します。 Number Range コンポーネントを使用すると、この操作をすばやく実行することができます。このコンポーネントを *degrees* 入力に接続します。
4. **Number** ノードをキャンバスに 3 つ追加して縦に並べ、数値の範囲を定義します。 上から下に、それぞれ *0.0、360.0、**120.0* の値を割り当てます。 これらの値により、らせんの巻き筋が制御されます。**Number Range** ノードに 3 つの Number ノードを接続すると、結果が出力されます。

出力結果が渦の流れのようになってきました。**Number Range** パラメータの一部を調整して、出力結果がどのように変わるか確認してみましょう。![](images/4-2/4-2-5/05.png)

> 1. **Number Range** ノードの step の入力値を *120.0* から *36.0* に変更します。 この操作により、巻き筋の数が増え、グリッドの密度が上がります

![](images/4-2/4-2-5/06.png)

> 1. **Range** ノードの step 入力の値を *36.0* から *3.6* に変更します。 この操作により、グリッドの密度が大幅に上がり、螺旋の方向が不明瞭になります。これで、ヒマワリが完成しました。

