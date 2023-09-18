# building data

Polygon and Centroid data have gml_id columns which you can use to join attributes from other tables.

## 2022 building data

## Tokyo23 
### Original Data: https://www.geospatial.jp/ckan/dataset/plateau-tokyo23ku-2022

## GeoParquet

- [Building 2D Polygons 427.3 MB](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/tokyo23/2022/buildings/tokyo23_2022_buildings_polygon.parquet)
- [Building Centroid 285.6 MB](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/tokyo23/2022/buildings/tokyo23_2022_buildings_centroid.parquet)
- [Building Data Quality 132.8 MB](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/tokyo23/2022/buildings/tokyo23_2022_buildings_data_quality.parquet)
- [Building Detail 156.5 MB](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/tokyo23/2022/buildings/tokyo23_2022_buildings_detail.parquet)
- [Building Extended Attributes 133.9 MB](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/tokyo23/2022/buildings/tokyo23_2022_buildings_extended_attributes.parquet)
- [Building Generic Attributes 126.2 MB](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/tokyo23/2022/buildings/tokyo23_2022_buildings_generic_attributes.parquet)
- [Building Risk Flooding 146.3 MB](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/tokyo23/2022/buildings/tokyo23_2022_buildings_risk_flooding.parquet)
- [Building Risk High Tide 2.9 MB](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/tokyo23/2022/buildings/tokyo23_2022_buildings_risk_high_tide.parquet)
- [Building Risk Land Slide 259.9 KB](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/tokyo23/2022/buildings/tokyo23_2022_buildings_risk_land_slide.parquet)

## GeoPackage

- [All data included](https://flateau.s3.ap-northeast-1.amazonaws.com/data/plateau/2022/buildings/tokyo23_2022_buildings.gpkg)

# Data Schema
## buildings (Building 2D Plygons and Building Centroid)

| column                      | data_type | details                                                                          | example                                   |
|-----------------------------|-----------|----------------------------------------------------------------------------------|-------------------------------------------|
| id                          | Integer64 | sequential number                                                                | 1                                         |
| _suffix                     | String    | lod0                                                                             |                                           |
| lod                         | String    | LOD level                                                                        | lod0                                      |
| _temp_id                    | String    | bldg_fc50c7d9-76ac-4576-bfbd-f37c74410928                                        |                                           |
| gml_parent_id               | String    | fme-gen-93d790fd-7696-45f6-a979-3b925fb6fc85                                     |                                           |
| _path_unix                  | String    | C:/tmp/13100_tokyo23-ku_2022_citygml_1_2_op/udx/bldg/53392546_bldg_6697_2_op.gml |                                           |
| gml_id                      | String    | building unique ID                                                               | bldg_fc50c7d9-76ac-4576-bfbd-f37c74410928 |
| citygml_geometry_name       | String    | lod0RoofEdge                                                                     |                                           |
| building_id                 | String    | 13111-bldg-524                                                                   |                                           |
| branch_id                   | String    |                                                                                  |                                           |
| part_id                     | String    |                                                                                  |                                           |
| prefecture                  | String    | prefecture name in Japanese                                                      | 東京都                                       |
| prefecture_code             | String    | prefecture code                                                                  | 13                                        |
| city                        | String    | prefecture and city name in Japanese                                             | 東京都大田区                                    |
| city_code                   | String    | city code                                                                        | 13111                                     |
| _max_lod                    | String    | 1                                                                                |                                           |
| _num_building_parts         | String    | 0                                                                                |                                           |
| _num_building_installations | String    | 0                                                                                |                                           |
| source_filename             | String    | source file name                                                                 | 53392546_bldg_6697_2_op.gml               |
| creation_date               | String    |                                                                                  |                                           |
| termination_date            | String    |                                                                                  |                                           |
| usage                       | String    |                                                                                  |                                           |
| usage_code                  | String    |                                                                                  |                                           |
| storey_heights_above_ground | String    |                                                                                  |                                           |
| storey_heights_below_ground | String    |                                                                                  |                                           |
| usage_desc                  | String    |                                                                                  |                                           |
| fme_rejection_code          | String    |                                                                                  |                                           |
| _count                      | Integer64 | 0                                                                                |                                           |
| cal_area_m2                 | Real      | building footprint area in meter                                                 | 40.44564364                               |
| cal_xmin                    | Real      | building x minimum in logitude                                                   | 139.7121893                               |
| cal_xmax                    | Real      | building x maximum in logitude                                                   | 139.7123071                               |
| cal_ymin                    | Real      | building y minimum in latitude                                                   | 35.54154939                               |
| cal_ymax                    | Real      | building y maximum in latitude                                                   | 35.54160749                               |
| cal_zmin_m                  | Real      | building z minimum in meter                                                      | 2.406                                     |
| cal_zmax_m                  | Real      | building z maximu in meter                                                       | 9.141                                     |
| cal_height_m                | Real      | building height in meter                                                         | 6.735                                     |
