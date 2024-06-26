# Japanese Building Footprint Data (a.k.a Flateau :wink:)

Original PLATEAU (National Government 3D project) building data are provided as the CityGML 3D format. We extracted LOD0 geometries (footprint 2D polygon) and their attributes and exported as GeoParquet and GeoPackage files. We used FME for this process and internally called Project **Flateau**. We kept attributes as much as possible, however, we omitted some of them based on our judgements. We addes several attributes such as heights and areas from the original 3D geometris. Japanese national and local government keep expanding data coverage, however, PLATEAU data don't cover the all cities in Japan (211 cites out of about 1720 cities). I hope the coverage will expand and cover the entire nation sometime. 

There are lots of attributes in this dataset. We separated ancillary data from the main data, 2D polygon and centroid point data. 

You can download and use our data freely under CC-BY 4.0 license. We used PLATEAU data so you also need to follow [their term of use](https://www.mlit.go.jp/plateau/site-policy/). 

- (c) [Pacific Spatial Solutions, inc.](https://pacificspatial.com) 2023 CC-BY. This data is made available under a Creative Commons Attribution 4.0 International license. Original building data are from PROJECT PLATEAU (https://www.mlit.go.jp/plateau/)

Polygon and Centroid data have gml_id columns which you can use to join attributes from other tables. 

Directories are organized by data types.
```
root/
|─ gpkg/
|  |─ geopackage files for each city
|─ merged/
|  |─ merged_building_centroid_lod0.parquet
|  |─ merged_building_lod0.parquet
|─ parquet/
|  |─ parquet files for each city
|─ README.md
```

データは自由にお使いいただけますが、[CC BY 4.0ライセンス]（https://creativecommons.org/licenses/by/4.0/legalcode.ja） に従います。

- 出典：国土交通省PLATEAU (https://www.mlit.go.jp/plateau/)
「3D都市モデル（Project PLATEAU）」（国土交通省）(https://www.geospatial.jp/ckan/dataset/plateau） をもとにジオメトリから各種統計データを算出しオンラインまたはGISソフトウェアで利用しやすいフォーマットに変換。 [Pacific Spatial Solutions株式会社](https://pacificspatial.com) 作成

各種属性ファイルのデータは、gml_idを使ってポリゴンとセントロイドのデータに紐づけすることができます。

## 2023 building data

### Prepared data (整備したデータ)
We prepared data for each city where Plateau data are available on 2024/05. Plateau project keeps adding more cities every year. So, hopefully we can keep adding more cities in the future.

2023年度のPlateauの建物データの変換を行いました。毎年整備対象都市が増えているのでできれば毎年追加していきたいと考えています。

### Prepaed data fromat（整備したデータのフォーマット）
We prepared our data in two data formats and host at [Source Cooperative](https://beta.source.coop/). If you click the following download page links, you will open the data download pages.
- GeoParquet/Parquet ([download page](https://beta.source.coop/pacificspatial/flateau/parquet/))
  - Footprint polygons and their centroid data as well as other ancillary data which don't have geometry information. You can join these data to GeoParquet data using gml_id column.
- GeoPackage ([download page](https://beta.source.coop/pacificspatial/flateau/gpkg/))
  - All with or without geometry data are in this file.

### File naming convention (ファイルの命名規則)
- GeoParquet and Parquet files
  - citycode_cityname_year_filename.parquet
  - example: 01100_sapporo-shi_2020_building_centroid_lod0.parquet
- GeoPackage files
  - citycode_cityname_year.gpkg
  - example: 01100_sapporo-shi_2020.gpkg

### File names（今回整備したファイル名一覧）

We prepared the following files/layers for each city. Available data files/layers vary depend on its availability. We prepared polygon and centroid data are in GeoParquet format and other data are in Parquet. GeoPackage files include all data as one file.

|filename                        |type   |description                                 |description_ja                           |
|--------------------------------|-------|--------------------------------------------|-----------------------------------------|
|building_lod0                   |polygon|Building footprint 2D polygons.             |建物フットプリント2Dポリゴンとその属性                     |
|building_centroid_lod0          |point  |Centroid points of 2D footprint polygons.   |建物フットプリントポリゴンのセントロイドとその属性                |
|building_detail                 |table  |Basic information of buildings.             |建築物に関する基礎的な情報                            |
|building_large_customer_facility|table  |Basic information of large size buildings.  |大規模小売店舗や大規模集客施設に関する基礎的な情報                |
|building_data_quality           |table  |Data quality of each building data.         |地物インスタンスごとのデータの作成情報                      |
|building_risk_flooding          |table  |Flooding zone attributes.                   |洪水浸水想定区域内に存在する建築物に付与された浸水想定区域がもつ属性       |
|building_risk_tsunami           |table  |Tsunami zone attributes.                    |津波洪水浸水想定の区域内に存在する建築物付与した津波浸水想定の区域の属性     |
|building_risk_high_tide         |table  |High tide zone attributes.                  |高潮浸水想定区域に存在する建築物に付与した高潮浸水想定区域の属性を        |
|building_risk_internal_overflow |table  |Inland water inundation zone attributes.    |内水浸水想定区域に存在する建築物に付与した内水浸水想定区域の属性         |
|building_risk_land_slide        |table  |Land slide zone attributes.                 |土砂災害警戒区域及び土砂災害特別警戒区域に存在する建築物に付与した区域に関する属性|

### Data Schema for each file (各データのスキーマ)

#### building_lod0 and building_centroid_lod0（建物ポリゴンとそのセントロイドデータのスキーマ）

|attribute_name                 |type     |sample data                                 |Definition                                                           |
|-------------------------------|---------|--------------------------------------------|---------------------------------------------------------------------|
|source_filename                |char(32) |53392546_bldg_6697_2_op.gml                 |Original data source file name                                       |
|gml_id                         |char(64) |bldg_fc50c7d9-76ac-4576-bfbd-f37c74410928   |Unique ID                                                            |
|building_id                    |char(32) |13111-bldg-524                              |Unique building ID in the municipality                               |
|branch_id                      |smallint |NULL                                        |Branch ID for Warehouses and sheds associated with the main building.|
|part_id                        |smallint |NULL                                        |Building area of a footprint polygon.                                |
|prefecture                     |char(5)  |東京都                                         |Prefecture name of the building location.                            |
|prefecture_code                |char(2)  |13                                          |Prefecture code number                                               |
|city                           |char(32) |東京都大田区                                      |City name of the building location.                                  |
|city_code                      |char(5)  |13111                                       |City code number                                                     |
|gml_description                    |char(64) |NULL                                        |                                                                     |
|gml_name                           |char(64) |六郷土手郵便局                                     |building name                                                        |
|address                        |char(64) |東京都大田区東六郷三丁目                                |building address                                                     |
|creation_date                  |date     |20230322                                    |                                                                     |
|termination_date               |date     |NULL                                        |                                                                     |
|class                          |char(32) |普通建物             |                                              |
|class_code                     |smallint |3001                                        |                                                                     |
|usage                     |char(128)|工場      |      |
|usage_code                     |smallint |441                                        |                                                                     |
|year_of_construction           |smallint |1985                                        |                                                                     |
|year_of_demolition             |smallint |NULL                                        |                                                                     |
|roof_type                      |char(32) |NULL                                        |                                                                     |
|roof_type_code                 |smallint |NULL                                        |                                                                     |
|measured_height                |double   |8.3                                         |measured building height in meter                                    |
|measured_height_uom            |char(8)  |m                                           |unit of height measurement                                           |
|storeys_above_ground           |smallint |3                                        |                                                                     |
|storeys_below_ground           |smallint |1                                        |                                                                     |
|address    |text|NULL                                        |                                                                     |
|real_estate_id_of_building|text  |4307000240386-000B  | |
|number_of_building_unit_ownership    |text |1                                        |  |
|real_estate_id_of_building_unit_ownership|text |1                                        |                                                                     |
|number_of_real_estate_id_of_land     |text|4313000119863-0000                                        | |
|matching_score                  |text     |97  |
|cal_area_m2                    |double   |40.445643597318096                          |polygon areas in square meters                                       |
|cal_xmin                       |double   |139.71218932484814                          |minimum longitude of footprint polygons                              |
|cal_xmax                       |double   |139.71218932484814                          |maximum longitude of footprint polygons                              |
|cal_ymin                       |double   |35.54154939251641                           |minimum latitude of footprint polygons                               |
|cal_ymax                       |double   |35.54160749301028                           |maximum latitude of footprint polygons                               |
|cal_zmin_m                     |double   |2.406                                       |minimum height value from 3D geometries                              |
|cal_zmax_m                     |double   |9.141                                       |maximum height value from 3D geometries                              |
|cal_height_m                   |double   |6.734999999999999                           |building height based on the min and max height                      |

## building_detail
|attribute_name                         |type     |sample data                              |Definition                                                                         |
|---------------------------------------|---------|-----------------------------------------|-----------------------------------------------------------------------------------|
|source_filename                        |text     |53392546_bldg_6697_2_op.gml              |                                                                                   |
|gml_id                                 |text     |bldg_fc50c7d9-76ac-4576-bfbd-f37c74410928|                                                                                   |
|building_id                            |text(200)|13111-bldg-524                           |Unique building ID in the municipality                                             |
|branch_id                              |text(200)|NULL                                     |Branch ID for Warehouses and sheds associated with the main building.              |
|prefecture|text|北海道|Prefecture name|
|prefecture_code|text|01|Prefecture code|
|city|text|北海道札幌市南区|City name|
|city_code|text|01106|City code|
|serial_number_of_building_certification|text(200)|NULL                                     |Serial number of the building certification.                                       |
|site_area                              |text(200)|NULL                                     |Site area of a building.                                                           |
|site_area_uom                          |text(200)|NULL                                     |                                                                                   |
|total_floor_area                       |text(200)|NULL                                     |Total floor area.                                                                  |
|total_floor_area_uom                   |text(200)|NULL                                     |                                                                                   |
|building_footprint_area                |text(200)|NULL                                     |Area of the wall outline of the building.                                          |
|building_footprint_area_uom            |text(200)|NULL                                     |                                                                                   |
|building_roof_edge_area                |text(200)|40.43768                                 |Area of the roof outline of the building.                                          |
|building_roof_edge_area_uom            |text(200)|m2                                       |                                                                                   |
|development_area                       |text(200)|NULL                                     |Area of development.                                                               |
|development_area_uom                   |text(200)|NULL                                     |                                                                                   |
|building_structure_type                |text(200)|NULL                                     |Building stcutture type based on standard codes.                                   |
|building_structure_type_code           |text(200)|NULL                                     |                                                                                   |
|building_structure_org_type            |text(200)|NULL                                     |Building stcutture type based on the code set by the municipality                  |
|building_structure_org_type_code       |text(200)|NULL                                     |                                                                                   |
|fireproof_structure_type               |text(200)|NULL                                     |Fireproof structure type of the building.                                          |
|fireproof_structure_type_code          |text(200)|NULL                                     |                                                                                   |
|implementing_body                      |text(200)|NULL                                     |Implement body of the building.                                                    |
|urban_plan_type                        |text(200)|NULL                                     |Type of the building location designated by Urban Plan                             |
|urban_plan_type_code                   |text(200)|NULL                                     |                                                                                   |
|area_classification_type               |text(200)|NULL                                     |Type of the building location designated by Area classification.                   |
|area_classification_type_code          |text(200)|NULL                                     |                                                                                   |
|districts_and_zones_type               |text(200)|NULL                                     |Type of the building location designated by Districts and Zones.                   |
|districts_and_zones_type_code          |text(200)|NULL                                     |                                                                                   |
|land_use_type                          |text(200)|NULL                                     |Type of the building location designated by Land Use Plan.                         |
|land_use_type_code                     |text(200)|NULL                                     |                                                                                   |
|major_usage                            |text(200)|NULL                                     |Major classification of building usage based on the code set by the municipality.  |
|major_usage_code                       |text(200)|NULL                                     |                                                                                   |
|major_usage2                           |text(200)|NULL                                     |Major classification of building usage 2 based on the code set by the municipality.|
|major_usage2_code                      |text(200)|NULL                                     |                                                                                   |
|org_usage                              |text(200)|NULL                                     |Building usage based on the code set by the municipality.                          |
|org_usage_code                         |text(200)|NULL                                     |                                                                                   |
|org_usage2                             |text(200)|NULL                                     |Building usage 2 based on the code set by the municipality.                        |
|org_usage2_code                        |text(200)|NULL                                     |                                                                                   |
|detailed_usage                         |text(200)|NULL                                     |Building detailed usage based on the code set by the municipality.                 |
|detailed_usage_code                    |text(200)|NULL                                     |                                                                                   |
|detailed_usage2                        |text(200)|NULL                                     |Building detailed usage 2 based on the code set by the municipality.               |
|detailed_usage2_code                   |text(200)|NULL                                     |                                                                                   |
|detailed_usage3                        |text(200)|NULL                                     |Building detailed usage 3 based on the code set by the municipality.               |
|detailed_usage3_code                   |text(200)|NULL                                     |                                                                                   |
|ground_floor_usage                     |text(200)|NULL                                     |Usage of the ground floor of the building                                          |
|ground_floor_usage_code                |text(200)|NULL                                     |                                                                                   |
|second_floor_usage                     |text(200)|NULL                                     |                                                                                   |
|second_floor_usage_code                |text(200)|NULL                                     |                                                                                   |
|third_floor_usage                      |text(200)|NULL                                     |                                                                                   |
|third_floor_usage_code                 |text(200)|NULL                                     |                                                                                   |
|basement_usage                         |text(200)|NULL                                     |                                                                                   |
|basement_usage_code                    |text(200)|NULL                                     |                                                                                   |
|basement_first_usage                   |text(200)|NULL                                     |                                                                                   |
|basement_first_usage_code              |text(200)|NULL                                     |                                                                                   |
|basement_second_usage                  |text(200)|NULL                                     |                                                                                   |
|basement_second_usage_code             |text(200)|NULL                                     |                                                                                   |
|vacancy                                |text(200)|NULL                                     |                                                                                   |
|vacancy_code                           |text(200)|NULL                                     |                                                                                   |
|building_coverage_rate                 |text(200)|NULL                                     |                                                                                   |
|floor_area_rate                        |text(200)|NULL                                     |                                                                                   |
|specified_building_coverage_rate       |text(200)|NULL                                     |                                                                                   |
|specified_floor_area_rate              |text(200)|NULL                                     |                                                                                   |
|standard_floor_area_rate               |text(200)|NULL                                     |                                                                                   |
|building_height                        |text(200)|NULL                                     |                                                                                   |
|building_height_uom                    |text(200)|NULL                                     |                                                                                   |
|eave_height                            |text(200)|NULL                                     |                                                                                   |
|eave_height_uom                        |text(200)|NULL                                     |                                                                                   |
|note                                   |text(200)|NULL                                     |                                                                                   |
|survey_year                            |text(200)|2016                                     |                                                                                   |

## building_large_customer_facility
|attribute_name                         |type     |sample data                              |Definition                                                                         |
|---------------------------------------|---------|-----------------------------------------|-----------------------------------------------------------------------------------|
|source_filename                        |text     |49300574_bldg_6697_op.gml                |                                                                                   |
|gml_id                                 |text     |bldg_154b30dc-1a6b-4af0-a9d8-5c99d8bba147|                                                                                   |
|building_id                            |text(200)|43100-bldg-3478                          |                                                                                   |
|branch_id                              |text(200)|NULL                                     |                                                                                   |
|prefecture|text|北海道|Prefecture name|
|prefecture_code|text|01|Prefecture code|
|city|text|北海道札幌市南区|City name|
|city_code|text|01106|City code|
|class                                  |text(200)|大規模小売店舗（その他）|                                                                                   |
|class_code                             |text(200)|4                                        |                                                                                   |
|name                                   |text(200)|TSUTAYA　むつ店|                                                                                   |
|capacity                               |text(200)|NULL                                     |                                                                                   |
|owner                                  |text(200)|NULL                                     |                                                                                   |
|total_floor_area                       |text(200)|2750                                     |                                                                                   |
|total_floor_area_uom                   |text(200)|m2                                     |                                                                                   |
|total_store_floor_area                 |text(200)|NULL                                     |                                                                                   |
|total_store_floor_area_uom             |text(200)|NULL                                     |                                                                                   |
|inaugural_date                         |text(200)|NULL                                     |                                                                                   |
|year_opened                            |text(200)|NULL                                     |                                                                                   |
|year_closed                            |text(200)|NULL                                     |                                                                                   |
|key_tenants                            |text(200)|NULL                                     |                                                                                   |
|availability                           |text(200)|NULL                                     |                                                                                   |
|urban_plan_type                        |text(200)|都市計画区域                              |                                                                                   |
|urban_plan_type_code                   |text(200)|21                                     |                                                                                   |
|area_classification_type               |text(200)|NULL                                     |                                                                                   |
|area_classification_type_code          |text(200)|NULL                                     |                                                                                   |
|districts_and_zones_type               |text(200)|NULL                                     |                                                                                   |
|districts_and_zones_type_code          |text(200)|NULL                                     |                                                                                   |
|land_use_type                          |text(200)|NULL                                     |                                                                                   |
|land_use_type_code                     |text(200)|NULL                                     |                                                                                   |
|reference                              |text(200)|NULL                                     |                                                                                   |
|note                                   |text(200)|NULL                                     |                                                                                   |
|survey_year                            |text(200)|2017                                     |                                                                                   |

## building_data_quality
|attribute_name                         |type     |sample data                              |Definition                                                                         |
|---------------------------------------|---------|-----------------------------------------|-----------------------------------------------------------------------------------|
|source_filename                        |text     |53392546_bldg_6697_2_op.gml              |                                                                                   |
|gml_id                                 |text     |bldg_fc50c7d9-76ac-4576-bfbd-f37c74410928|                                                                                   |
|building_id                            |text(200)|13111-bldg-524                           |                                                                                   |
|branch_id                              |text(200)|NULL                                     |                                                                                   |
|prefecture|text|北海道|Prefecture name|
|prefecture_code|text|01|Prefecture code|
|city|text|北海道札幌市南区|City name|
|city_code|text|01106|City code|
|src_scale                              |text     |地図情報レベル2500                              |                                                                                   |
|src_scale_code                         |text     |1                                        |                                                                                   |
|geometry_src_desc                      |text     |空中写真測量                                   |                                                                                   |
|geometry_src_desc_code                 |text     |5                                        |                                                                                   |
|thematic_src_desc                      |text     |都市計画基礎調査                                 |                                                                                   |
|thematic_src_desc_code                 |text     |1                                        |                                                                                   |
|appearance_src_desc                    |text     |空中写真                                     |                                                                                   |
|appearance_src_desc_code               |text     |1                                        |                                                                                   |
|lod_type                               |text     |2.0                                      |                                                                                   |
|lod1_height_type                       |text(200)|点群から取得_中央値                               |                                                                                   |
|lod1_height_type_code                  |text(200)|2                                        |                                                                                   |

## building_risk_flooding
|attribute_name                         |type     |sample data                              |Definition                                                                         |
|---------------------------------------|---------|-----------------------------------------|-----------------------------------------------------------------------------------|
|source_filename                        |text     |53392546_bldg_6697_2_op.gml              |                                                                                   |
|gml_id                                 |text     |bldg_fc50c7d9-76ac-4576-bfbd-f37c74410928|                                                                                   |
|building_id                            |text(200)|13111-bldg-524                           |                                                                                   |
|branch_id                              |text(200)|NULL                                     |                                                                                   |
|prefecture|text|北海道|Prefecture name|
|prefecture_code|text|01|Prefecture code|
|city|text|北海道札幌市南区|City name|
|city_code|text|01106|City code|
|description                            |text(200)|城南地区河川流域                                 |                                                                                   |
|description_code                       |text(200)|3                                        |                                                                                   |
|rank                                   |text(200)|0.5m未満                                   |                                                                                   |
|rank_code                              |text(200)|1                                        |                                                                                   |
|rank_org                               |text(200)|NULL                                     |                                                                                   |
|rank_org_code                          |text(200)|NULL                                     |                                                                                   |
|depth                                  |text(200)|0.092                                    |                                                                                   |
|depth_uom                              |text(200)|m                                        |                                                                                   |
|admin_type                             |text(200)|都道府県                                     |                                                                                   |
|admin_type_code                        |text(200)|2                                        |                                                                                   |
|scale                                  |text(200)|L2（想定最大規模）                               |                                                                                   |
|scale_code                             |text(200)|2                                        |                                                                                   |
|duration                               |text(200)|14.55                                    |                                                                                   |
|duration_uom                           |text(200)|hour                                     |                                                                                   |

## building_risk_tsunami
|attribute_name                         |type     |sample data                              |Definition                                                                         |
|---------------------------------------|---------|-----------------------------------------|-----------------------------------------------------------------------------------|
|source_filename                        |text     |52362499_bldg_6697_op.gml                |                                                                                   |
|gml_id                                 |text     |bldg_92f5c8b4-2e54-4c21-b93b-2119ca62c846|                                                                                   |
|building_id                            |text(200)|24202-bldg-169103                        |                                                                                   |
|branch_id                              |text(200)|NULL                                     |                                                                                   |
|prefecture|text|北海道|Prefecture name|
|prefecture_code|text|01|Prefecture code|
|city|text|北海道札幌市南区|City name|
|city_code|text|01106|City code|
|description                            |text(200)|1                                        |                                                                                   |
|description_code                       |text(200)|1                                        |                                                                                   |
|rank                                   |text(200)|3                                        |                                                                                   |
|rank_code                              |text(200)|3                                        |                                                                                   |
|rank_org                               |text(200)|NULL                                     |                                                                                   |
|rank_org_code                          |text(200)|NULL                                     |                                                                                   |
|depth                                  |text(200)|0.13                                     |                                                                                   |
|depth_uom                              |text(200)|m                                        |                                                                                   |

## building_risk_high_tide


| column           | data_type | details            | example                                   |
|------------------|-----------|--------------------|-------------------------------------------|
| source_filename  | String    | source file name   | 53394539_bldg_6697_2_op.gml               |
| gml_id           | String    | building unique ID | bldg_d36d2972-098d-4be1-b595-7fe8cd79994b |
| building_id      | String    | building ID        | 13101-bldg-9339                           |
| branch_id        | String    |                    |                                           |
|prefecture|text|北海道|Prefecture name|
|prefecture_code|text|01|Prefecture code|
|city|text|北海道札幌市南区|City name|
|city_code|text|01106|City code|
| description      | String    | description        | 高潮浸水想定区域図                                 |
| description_code | String    | 1                  |                                           |
| rank             | String    | tide rank          | 0.5m未満                                    |
| rank_code        | String    | tide rank code     | 1                                         |
| rank_org         | String    |                    |                                           |
| rank_org_code    | String    |                    |                                           |
| depth            | String    | tide depth         | 0.43                                      |
| depth_uom        | String    | unit               | m                                         |
| id               | Integer64 | sequential number  | 1                                         |

## building_risk_internal_overflow
|attribute_name                         |type     |sample data                              |Definition                                                                         |
|---------------------------------------|---------|-----------------------------------------|-----------------------------------------------------------------------------------|
|source_filename                        |text     |52362487_bldg_6697_op.gml                |                                                                                   |
|gml_id                                 |text     |bldg_7a69ff2f-a672-45e8-b743-b0323014ed46|                                                                                   |
|building_id                            |text(200)|24202-bldg-175892                        |                                                                                   |
|branch_id                              |text(200)|NULL                                     |                                                                                   |
|prefecture|text|北海道|Prefecture name|
|prefecture_code|text|01|Prefecture code|
|city|text|北海道札幌市南区|City name|
|city_code|text|01106|City code|
|description                            |text(200)|1                                        |                                                                                   |
|description_code                       |text(200)|1                                        |                                                                                   |
|rank                                   |text(200)|3                                        |                                                                                   |
|rank_code                              |text(200)|3                                        |                                                                                   |
|rank_org                               |text(200)|NULL                                     |                                                                                   |
|rank_org_code                          |text(200)|NULL                                     |                                                                                   |
|depth                                  |text(200)|0.076                                    |                                                                                   |
|depth_uom                              |text(200)|m                                        |                                                                                   |

## building_risk_land_slide
|attribute_name                         |type     |sample data                              |Definition                                                                         |
|---------------------------------------|---------|-----------------------------------------|-----------------------------------------------------------------------------------|
|source_filename                        |text     |53392584_bldg_6697_2_op.gml              |                                                                                   |
|gml_id                                 |text     |bldg_ad10f991-e3ca-4cbb-87f4-161e7065943b|                                                                                   |
|building_id                            |text(200)|13111-bldg-67878                         |                                                                                   |
|branch_id                              |text(200)|NULL                                     |                                                                                   |
|prefecture|text|北海道|Prefecture name|
|prefecture_code|text|01|Prefecture code|
|city|text|北海道札幌市南区|City name|
|city_code|text|01106|City code|
|description                            |text(200)|急傾斜地の崩落                                  |                                                                                   |
|description_code                       |text(200)|1                                        |                                                                                   |
|area_type                              |text(200)|土砂災害警戒区域（指定済）                            |                                                                                   |
|area_type_code                         |text(200)|1                                        |                                                                                   |

