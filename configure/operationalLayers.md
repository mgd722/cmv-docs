# Operational Layers Section of viewer.js

Layers to load on top of the basemap. See [Class: Layer](https://developers.arcgis.com/javascript/jsapi/layer-amd.html) for more information on types of layers and [Layer options](https://developers.arcgis.com/javascript/jsapi/layer-amd.html#layer1).

Each layer object may consist of the following properties:

| Property name         | Type      | Description                              |
|-----------------------|-----------|------------------------------------------|
| type                  | string    | CMV friendly [Layer type](#layer-types)  |
| url                   | string    | Url to layer resource                    |
| title                 | string    | Layer title used by widgets              |
| options               | object    | Layer constructor options                |
| editorLayerInfos      | object    | [Editor widget options](#editor)         |
| legendLayerInfos      | object    | [Legend widget options](#legend)         |
| identifyLayerInfos    | object    | [Identify widget options](#identify)     |
| layerControlLayerInfos| object    | [Layer control options](#layer-control)  |

## Layer types
The following list indicates tested and untested layers that can be used in CMV

| Layer Type  | ArcGIS Layer Type       | Tested |
|-------------|-------------------------|--------|
| csv         | CSV                     | x      |
| dynamic     | ArcGISDynamicMapService | x      |
| georss      | GeoRSS                  | x      |
| image       | ArcGISImageService      | x      |
| kml         | KML                     | x      |
| label       | Label                   |        |
| mapimage    | MapImage                |        |
| osm         | OpenStreetMap           | x      |
| tiled       | ArcGISTiledMapService   | x      |
| wms         | WMS                     | x      |
| wmts        | WMTS                    |        |

## Editor
Setting `exclude: true` in the `editorLayerInfos` property allows you to exclude the feature layer from the editor widget. Additional options that are found under the `layerInfo` portion of the [editor api docs](https://developers.arcgis.com/javascript/jsapi/editor-amd.html) may be provided in this object

## Legend
Setting `exclude: true` in the `legendLayerInfos` property allows you to exclude the feature layer from the editor widget. (Available in 1.4.0)

## Identify
Setting `exclude: true` in the `identifyLayerInfos` property allows you to exclude the feature layer from the editor widget.

## Layer Control
See the [layer control documentation](../widgets/LayerControl) for details on configuring the layer in this widget.


## Example
See [operational layers section in viewer.js](https://github.com/cmv/cmv-app/blob/master/viewer/js/config/viewer.js#L63) for examples.

## Feature Layer Modes
Feature layers have a default mode of `ON_DEMAND` so a value is not required. But if you would like to change the mode, you don't have to import `esri/layers/FeatureLayer`, instead you can use the integer value of the mode instead.

Mode           | Integer value
---------------|--------------
MODE_SNAPSHOT  | 0
MODE_ONDEMAND  | 1
MODE_SELECTION | 2
