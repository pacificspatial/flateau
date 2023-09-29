# flateau
data for the people

So this is an experimental project to make Japanese open geospatial data available for online visualization and analysis. We are going to start with Project Plateau data and expand our efforts gradually to other data sources. What we want to do is convert geospatial data to cloud-native data formats such as GeoParquet, COG, and COPC, as well as open standard formats such as GeoPackage and GeoJSON. Once we find out the best way to distribute data, we want to create FME pipelines to convert geospatial data to the appropriate formats and specifications.

Thanks to MLIT (Ministry of Land, Infrastructure, Transport and Tourism), we now have access to high-quality 3D building data. We want to contribute a bit to making their and local governments' data accessible to everyone. At least that is our hope!

We are going to start distributing experimental data for your use, so please use it freely and give us some feedback. We only included limited attributes at the beginning (2023/9/29), but for the next round, we will include all useful attributes.

For the Plateau data, we converted their CityGML building data to GeoPackage as well as GeoParquet. During our conversion process, we calculated various height measurements, such as the maximum and minimum heights of buildings. Here are the Plateau data's terms of use:

[PLATEAU Terms of Use](https://www.mlit.go.jp/plateau/site-policy/)

We are following the CC BY 4.0（https://creativecommons.org/licenses/by/4.0/legalcode.ja）license as the same as the PLATEAU license.

出典：国土交通省[PLATEAU](https://www.mlit.go.jp/plateau/)
「3D都市モデル（Project PLATEAU）」（国土交通省）(https://www.geospatial.jp/ckan/dataset/plateau） をもとにジオメトリから各種統計データを算出しオンラインまたはGISソフトウェアで利用しやすいフォーマットに変換。 [Pacific Spatial Solutions株式会社](https://pacificspatial.com) 作成

Let's see how far we can go.
