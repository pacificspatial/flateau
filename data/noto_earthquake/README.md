# 202401 能登半島地震関連地理情報データ (202401 Noto Penninsula Eathquake Geospatial Data)

  * [PSS Terria Map 日本語版を開く](https://pss-terria.com/#clean&map=3d&https://flateau.s3.ap-northeast-1.amazonaws.com/data/noto_earthquake/catalog/noto_earthquake_20240109.json) (日本語のカタログ名です)
    * ３D表示するには、「日本全国地形データ」は必ず読み込んでください。その上で他のデータを読み込んで下さい。
  * [PSS Terria Map English version](https://pss-terria.com/#clean&map=3d&https://flateau.s3.ap-northeast-1.amazonaws.com/data/noto_earthquake/catalog/noto_earthquake_en_20240109.json) (I translated layer names in English, so it may be easier for no Japanese reading audience)
    * You need to load the "Japanese Terrain data" along with other layers to see 3D topography!

## Geospatail PDF
地図は現在準備中 (2024/1/9)

Geospataial PDFは、普通のPDFファイルですが、[Avenza Maps](https://avenzamaps.jp/)で読み込むと、GPSと連動した地図として使えます。インターネットが使えない場所でも自分の位置を地図上で確認しながら移動、調査、データ収集ができます。写真を撮影しておけば、場所と写真を紐づけしながらデータを収集できます。もちろん、PDFなので、紙に印刷したり、パソコンで普通に見ることもできます。

[地理院地図のインポートサイト](https://avenzamaps.jp/?page_id=2494)では、被災地を含む日本全国の地形図が無償でダウンロードできます。少し下の方に書いてあるとおり、3DビューアにAvenza Mapsダウンロード用のレイヤを読み込んで、地図をダウンロードすることもできます。

Avenza Mapsの使い方は、武揚堂様が作成した[このビデオをご覧ください](https://www.youtube.com/watch?v=YMHlxKw4YsQ)。

## 3Dビューア Terria Map用カタログJsonファイル
#### [PSSの公開している3Dビューア](https://pss-terria.com/)や[東京都デジタルツイン実現プロジェクトの3Dビューア](https://3dview.tokyo-digitaltwin.metro.tokyo.lg.jp/)にドラッグアンドドロップすると、地震関連のデータが3Dで見れます。主なデータは、国土地理院のサイトから提供されているデータです。
[Avenza Maps](https://avenzamaps.jp/)用の地形図も直接Avenza Mapsにインポートできるレイヤも追加しました。Avenza Mapsのレイヤを読み込んで、目的の場所をクリックしてQRコードを表示させたら、Avenza Mapsのインポート機能を使って、直接地形図をインポートしてください。電波の届かないところでも自分の位置を確認しながらデータの収集、写真撮影などができます。
* [2024/1/9時点で集めたデータのカタログJSONダウンロード](https://flateau.s3.ap-northeast-1.amazonaws.com/data/noto_earthquake/catalog/noto_earthquake_20240109.json)
  * [PSS Terria Mapを開く](https://pss-terria.com/#clean&map=3d&https://flateau.s3.ap-northeast-1.amazonaws.com/data/noto_earthquake/catalog/noto_earthquake_20240109.json) 
  * [PSS Terria Map English version](https://pss-terria.com/#clean&map=3d&https://flateau.s3.ap-northeast-1.amazonaws.com/data/noto_earthquake/catalog/noto_earthquake_en_20240109.json) (I translated layer names in English, so it may be easier for no Japanese reading audience)

![TerriaMap](https://flateau.s3.ap-northeast-1.amazonaws.com/data/noto_earthquake/images/2024-01-09_12-19-11.png)


## Plateu建物フットプリント関連データ
被災地周辺のデータは有りませんが、石川県内のデータをリストしました。
### GeoParquet
* [17201_kanazawa-shi_2020_building_centroid_lod0.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17201_kanazawa-shi_2020_building_centroid_lod0.parquet) 41.25MB
* [17201_kanazawa-shi_2020_building_data_quality.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17201_kanazawa-shi_2020_building_data_quality.parquet) 14.86MB
* [17201_kanazawa-shi_2020_building_detail.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17201_kanazawa-shi_2020_building_detail.parquet) 15.19MB
* [17201_kanazawa-shi_2020_building_lod0.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17201_kanazawa-shi_2020_building_lod0.parquet) 68.07MB
* [17201_kanazawa-shi_2020_building_risk_flooding.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17201_kanazawa-shi_2020_building_risk_flooding.parquet) 13.09MB
* [17201_kanazawa-shi_2020_building_risk_land_slide.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17201_kanazawa-shi_2020_building_risk_land_slide.parquet) 0.66MB
* [17201_kanazawa-shi_2020_building_risk_tsunami.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17201_kanazawa-shi_2020_building_risk_tsunami.parquet) 0.06MB
* [17206_kaga-shi_2022_building_centroid_lod0.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17206_kaga-shi_2022_building_centroid_lod0.parquet) 10.44MB
* [17206_kaga-shi_2022_building_data_quality.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17206_kaga-shi_2022_building_data_quality.parquet) 3.72MB
* [17206_kaga-shi_2022_building_detail.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17206_kaga-shi_2022_building_detail.parquet) 3.87MB
* [17206_kaga-shi_2022_building_extended_attributes.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17206_kaga-shi_2022_building_extended_attributes.parquet) 0.79MB
* [17206_kaga-shi_2022_building_generic_attributes.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17206_kaga-shi_2022_building_generic_attributes.parquet) 0.78MB
* [17206_kaga-shi_2022_building_lod0.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17206_kaga-shi_2022_building_lod0.parquet) 17.9MB
* [17206_kaga-shi_2022_building_risk_flooding.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17206_kaga-shi_2022_building_risk_flooding.parquet) 1.24MB
* [17206_kaga-shi_2022_building_risk_land_slide.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17206_kaga-shi_2022_building_risk_land_slide.parquet) 0.33MB
* [17206_kaga-shi_2022_building_risk_tsunami.parquet](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpqt/17206_kaga-shi_2022_building_risk_tsunami.parquet) 0.01MB

### GeoPackage
* [17201_kanazawa-shi_2020.gpkg](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpkg/17201_kanazawa-shi_2020.gpkg) 350.36MB
* [17206_kaga-shi_2022.gpkg](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings202312/gpkg/17206_kaga-shi_2022.gpkg) 93.34MB

## データの出典
[データの出典については岩崎様のサイトを参考にさせていただきました](https://wata909.github.io/R060101_Noto_Peninsula_EQ_QGIS/?fbclid=IwAR0EkrJixe8gO0xkGKlGR-v48zVRlIZlOI7Oqu4zzhrLp2RnpgLOmuHmc_Q)

### 国土地理院
* 斜面崩壊・堆積分布データ（2024年1月3日更新分）
  * 出典：https://www.gsi.go.jp/BOUSAI/20240101_noto_earthquake.html#2
  * 概要：国土地理院が1月2日に撮影した空中写真から、令和6年能登半島地震によって生じたと考えられる斜面崩壊箇所及び土砂堆積箇所の範囲について判読したものであり、道路や河川上の土砂は、一部撤去されている可能性あり。
  * オリジナルデータ閲覧：地理院地図
  * ライセンス：国土地理院コンテンツ利用規約に従い、出典明示により、転載も含め使用可
* 斜面崩壊・堆積分布データ（2024年1月6日更新分）
  * 出典：https://www.gsi.go.jp/BOUSAI/20240101_noto_earthquake.html#2
  * 概要：国土地理院が1月2日及び1月5日に撮影した空中写真（珠洲地区、輪島東地区、輪島中地区、穴水地区）から、令和6年能登半島地震によって生じたと考えられる斜面崩壊箇所及び土砂堆積箇所の範囲について判読したものであり、道路や河川上の土砂は、一部撤去されている可能性あり。
  * オリジナルデータ閲覧：地理院地図
  * ライセンス：国土地理院コンテンツ利用規約に従い、出典明示により、転載も含め使用可
* 被災地域空中写真（正射画像）：珠洲地区、輪島東地区、輪島中地区、20240102撮影
  * 出典：https://www.gsi.go.jp/BOUSAI/20240101_noto_earthquake.html#4
  * オリジナルデータ閲覧：地理院地図
  * ライセンス：国土地理院コンテンツ利用規約
* 被災地域空中写真（正射画像）：珠洲地区、輪島中地区、穴水地区、七尾地区、20240105撮影
  * 出典：https://www.gsi.go.jp/BOUSAI/20240101_noto_earthquake.html#4
  * オリジナルデータ閲覧：地理院地図
  * ライセンス：国土地理院コンテンツ利用規約
* 地理院タイル
  * 出典：https://maps.gsi.go.jp/development/ichiran.html
  * 概要：背景画像として空中写真と標準地図を使用
### 国立研究開発法人 森林研究・整備機構 森林総合研究所
* 森林土壌デジタルマップ・CS立体図（能登半島）
  * 出典：https://www2.ffpri.go.jp/soilmap/index1.html?page=3
  * 概要：デジタル標高データから計算される曲率（Curvature）、傾斜（Slope）の情報を色調を変えて重ね合わせることにより、視覚的・直感的に地形判読を可能としたCS立体図を閲覧できる。作成に利用した標高データは災害前(2020-2023)に取得されたものである。
  * オリジナルデータ閲覧：CS立体図（ズームレベル1～17）
  * ライセンス：森林土壌デジタルマップ・利用規約参照。