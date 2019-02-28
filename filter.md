# Filtering Vector Features

```python
# Just the selected features
layer = iface.activeLayer()
for feature in layer.selectedFeatures():
    print(feature['name'])

# Filter by current extent of the map
extent = iface.mapCanvas().extent()
request = QgsFeatureRequest()
request.setFilterRect(extent)
layer = iface.activeLayer()
for feature in layer.getFeatures(request):
    print(feature['name'])

# Filter by fixed extent
extent = QgsRectangle(-2.15, 52.20, 1.20, 52.60)
request = QgsFeatureRequest()
request.setFilterRect(extent)
layer = iface.activeLayer()
for feature in layer.getFeatures(request):
    print(feature['name'])

# Filter by attribute
exp = QgsExpression('name ILIKE \'%London%\'')
request = QgsFeatureRequest(exp)
layer = iface.activeLayer()
for feature in layer.getFeatures(request):
    print(feature['name'])

```
