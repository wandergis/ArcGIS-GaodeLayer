# gaodeLayer
ESRI的ArcGIS JavaScript API加载高德在线地图的扩展
#可以加载高德在线地图的扩展
##使用方法
1. 在api引入之前配置dojoConfig
```
<script type="text/javascript">
    var dojoConfig = {
        async: true,
        parseOnLoad: true,
        packages: [{
            name: "extLayers",
            location: location.pathname.replace(/\/[^/]*$/, '') + '/extLayers'
        }]
    };
</script>
```
2.然后在代码中可以如下方式构造layer
```
 require(["esri/map", "extLayers/gaodeLayer", "dojo/domReady!"], function (Map, gaodeLayer) {
        var map = new Map("map", {
            center: [116, 28],
            zoom: 5
        });
        var baselayer = new gaodeLayer();//默认加载矢量 new gaodeLayer({layertype:"road"});也可以
        //var baselayer = new gaodeLayer({layertype: "st"});//加载卫星图
        //var baselayer = new gaodeLayer({layertype: "label"});//加载标注图
        map.addLayer(baselayer);//添加高德地图到map容器
    });
```
