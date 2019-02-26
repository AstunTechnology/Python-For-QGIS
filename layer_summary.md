Filtering Vector Features
=========================

```python
import itertools
import qgis
from qgis.gui import QgsMessageBar
from qgis.core import QgsMapLayer,QgsWkbTypes


def layer_info(layer):
    print("Layer name: %s" % layer.name())
    print("CRS: %s" % layer.crs().authid())
    print("Extent: %s" % layer.extent().asWktCoordinates())
    print("Feature count: %s" % layer.featureCount())
    print("Geometry type: %s" % QgsWkbTypes.displayString(int(layer.wkbType())))
    field_names = [field.name() for field in layer.fields().toList()]
    print("Fields: %s" % field_names)

    num_features = min(2, layer.featureCount())
    print("First %d features..." % num_features)

    features = itertools.islice(layer.getFeatures(), num_features)
    for feature in features:
        print("Feature ID %d: " % feature.id())
        print("Attributes: ", list(zip(field_names, feature.attributes())))
        geom = feature.geometry()
        print("Geometry: ", geom.asJson())


layer = qgis.utils.iface.activeLayer()
if layer and layer.type() == QgsMapLayer.VectorLayer:
    layer_info(layer)
else:
    qgis.utils.iface.messageBar().pushMessage("Please select a vector layer in the layer panel", Qgis.Info, 4)
```

