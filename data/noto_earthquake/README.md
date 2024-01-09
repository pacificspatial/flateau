# 202401 能登半島地震関連地理情報データダウンロード

## Geospatail PDF
現在準備中 (2024/1/9)

## 3Dビューア Terria Map用カタログJsonファイル
#### [PSSの公開している3Dビューア](https://pss-terria.com/)や[東京都デジタルツイン実現プロジェクトの3Dビューア](https://3dview.tokyo-digitaltwin.metro.tokyo.lg.jp/)にドラッグアンドドロップすると、地震関連のデータが3Dで見れます。主なデータは、国土地理院のサイトから提供されているデータです。
[Avenza Maps](https://avenzamaps.jp/)用の地形図も直接Avenza Mapsにインポートできるレイヤも追加しました。Avenza Mapsのレイヤを読み込んで、目的の場所をクリックしてQRコードを表示させたら、Avenza Mapsのインポート機能を使って、直接地形図をインポートしてください。電波の届かないところでも自分の位置を確認しながらデータの収集、写真撮影などができます。
* [2024/1/9時点で集めたデータのカタログJSONダウンロード](https://flateau.s3.ap-northeast-1.amazonaws.com/data/noto_earthquake/catalog/noto_earthquake_20240109.json)
  * [PSS Terria Mapを開く](https://pss-terria.com/#https://flateau.s3.ap-northeast-1.amazonaws.com/data/noto_earthquake/catalog/noto_earthquake_20240109.json) (カタログの一番下にデータがリストされます)

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