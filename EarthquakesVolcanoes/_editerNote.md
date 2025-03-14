# 編集備考

## ヘッダが複数ある場合
そのままです。以下の対応表を確認してください。

### 24

<table>
	<tr>
		<td colspan="3">AreaForecastLocalE</td>
		<td colspan="3">AreaInformationCity</td>
		<td colspan="3">震度観測点</td>
	</tr>
	<tr>
		<td>Code</td>
		<td>Name</td>
		<td>ふりがな</td>
		<td>Code</td>
		<td>Name</td>
		<td>ふりがな</td>
		<td>Code</td>
		<td>Name</td>
		<td>ふりがな</td>
	</tr>
</table>

### 25

<table>
	<tr>
		<td colspan="3">AreaForecastLocalE</td>
		<td colspan="3">AreaInformationCity</td>
		<td colspan="3">リアルタイム震度観測点</td>
	</tr>
	<tr>
		<td>Code</td>
		<td>Name</td>
		<td>ふりがな</td>
		<td>Code</td>
		<td>Name</td>
		<td>ふりがな</td>
		<td>Code</td>
		<td>Name</td>
		<td>ふりがな</td>
	</tr>
</table>

### 26

<table>
	<tr>
		<td colspan="3">AreaForecastLocalE</td>
		<td colspan="3">長周期地震動観測点</td>
	</tr>
	<tr>
		<td>Code</td>
		<td>Name</td>
		<td>ふりがな</td>
		<td>Code</td>
		<td>Name</td>
		<td>ふりがな</td>
	</tr>
</table>

### 35

<table>
	<tr>
		<td>潮位観測点</td>
		<td></td>
		<td></td>
		<td colspan="2">津波情報（沖合の津波観測に関する情報）の内容部で使用する潮位観測点に対応し、同情報のヘッダ部で使用する「簡略化した観測点名」</td>
		<td rowspan="2">備考</td>
	</tr>
	<tr>
		<td>Code</td>
		<td>Name</td>
		<td>ふりがな</td>
		<td>Code</td>
		<td>Name</td>
	</tr>
</table>



## 備考に`"`や`,`、改行などが含まれる場合

`~~_edit.csv`として処理しやすいものも用意しています。編集内容は以下で`編集: `と記述しています。

### 21, 22 : `"`

`気象庁が発信する電文では"奄美"と記載する。`が`"気象庁が発信する電文では""奄美""と記載する。"`となっています。

編集: `"`を`”`に

### 31 : `,`

例: `領域表現（構成する津波予報区100,101,102）`が``"領域表現（構成する津波予報区100,101,102）"となっています。コンマ区切りなので特別な処理が必要になることがあります。

編集: `""`内の`,`を`，`にして、`"`を削除

### 52, 62 : 改行

例:
```csv
111,調査中,"監視領域内でマグニチュード6.8以上の地震が発生したことにより、臨時に「南海トラフ沿いの地震に関する評価検討会」を開催する場合
【このコードは、「南海トラフ地震臨時情報」で運用する】
"
```

編集: 52では改行、`"`を削除　62では改行を`\n`(生文字)で置き換え、`"`を削除

### 51 : `　`

空白が入っているようです。

編集: 空白を削除


## 【編集手順】「備考」が上下セル結合されているもの
分割、文字を下に複製/移動、上段の削除　対象は以下

### 31, 35
