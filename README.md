# Flateau
## Data for the people

So this is our internal project to make Japanese open geospatial data available for online visualization and analysis. We are going to start with Project Plateau data and expand our efforts gradually to other data sources. What we want to do is convert geospatial data to cloud-native data formats such as GeoParquet, COG, and COPC, as well as open standard formats such as GeoPackage and GeoJSON. We have been creating FME pipelines to convert geospatial data to cloud-native formats.

Thanks to MLIT (Ministry of Land, Infrastructure, Transport and Tourism), we now have access to high-quality 3D building data. We want to contribute a bit to making their and local governments' data accessible to everyone. At least that is our hope!

We are going to start distributing our latest data for your use, so please use it freely and give us some feedback.

For the Plateau data, we converted their CityGML building data to GeoPackage as well as GeoParquet. During our conversion process, we calculated various height measurements, such as the maximum and minimum heights of buildings. Here are the Plateau data's terms of use:

[PLATEAU Terms of Use](https://www.mlit.go.jp/plateau/site-policy/)

We are following the CC BY 4.0（https://creativecommons.org/licenses/by/4.0/legalcode.ja）license as the same as the PLATEAU license.

出典：国土交通省[PLATEAU](https://www.mlit.go.jp/plateau/)
「3D都市モデル（Project PLATEAU）」（国土交通省）(https://www.geospatial.jp/ckan/dataset/plateau） をもとにジオメトリから各種統計データを算出しオンラインまたはGISソフトウェアで利用しやすいフォーマットに変換。 [Pacific Spatial Solutions株式会社](https://pacificspatial.com) 作成

Let's see how far we can go.


## みんなのためのデータ

このプロジェクトFlateauは、ライセンス上問題のない日本のあらゆるデータをクラウドネイティブ化して配ってしまうことを目的としています。まず手始めに、国交省の進めるPLATEAUの3D建物データを2DフットプリントポリゴンにしてGeoParquet形式にします。関連データはParquetファイルとして作成し、gml_idで紐づけできるようにしていますので、属性による解析やフィルタリングもできます。前回のバージョンはお試しだったので余計な属性値が入っていたり、必要な属性が入っていませんでしたが、今回が頑張ってきれいなデータを作りました。

国交省のPLATEAUは、高品質の3D建物データをオープンソースで配布するという画期的なプロジェクトです。このプロジェクトのおかげで日本のGeospatialデータの充実度はかなり上がったと思います。私達の思いとしては、少しでも日本のそして世界の方が日本のデータにアクセスして面白いことをできるようにしたいということですので、是非色々お使いください。

データは自由にお使いいただけますが、CC BY 4.0ライセンス（https://creativecommons.org/licenses/by/4.0/legalcode.ja）に従います。
(c) Pacific Spatial Solutions, inc. 2023 CC-BY. This data is made available under a Creative Commons Attribution 4.0 International license.

出典：国土交通省[PLATEAU](https://www.mlit.go.jp/plateau/)
「3D都市モデル（Project PLATEAU）」（国土交通省）(https://www.geospatial.jp/ckan/dataset/plateau） をもとにジオメトリから各種統計データを算出しオンラインまたはGISソフトウェアで利用しやすいフォーマットに変換。 [Pacific Spatial Solutions株式会社](https://pacificspatial.com) 作成