# WIDGET

Widget and dashboard component management.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

## Methods

### getWidgetScopeVariables

```javascript
const result = widgetService.getWidgetScopeVariables();
console.log('Result:', result);
```

### getAllWidgetsBundles

```javascript
widgetService.getAllWidgetsBundles().subscribe(result => {
  console.log('AllWidsBundles:', result);
});
```

### getSystemWidgetsBundles

```javascript
widgetService.getSystemWidgetsBundles().subscribe(result => {
  console.log('SystemWidsBundles:', result);
});
```

### getTenantWidgetsBundles

```javascript
widgetService.getTenantWidgetsBundles().subscribe(result => {
  console.log('TenantWidsBundles:', result);
});
```

### getWidgetBundles

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

widgetService.getWidgetBundles(pageLink).subscribe(result => {
  console.log('WidBundles:', result);
});
```

### getWidgetsBundle

```javascript
const widgetsBundleId = 'your-wgetsbundle-id';

widgetService.getWidgetsBundle(widgetsBundleId).subscribe(result => {
  console.log('WidsBundle:', result);
});
```

### exportWidgetsBundle

```javascript
const widgetsBundleId = 'your-wgetsbundle-id';

widgetService.exportWidgetsBundle(widgetsBundleId).subscribe(result => {
  console.log('exportWidsBundle:', result);
});
```

### saveWidgetsBundle

```javascript
const widgetsBundle = {
  // your widgetsBundle object
};

widgetService.saveWidgetsBundle(widgetsBundle).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### updateWidgetsBundleWidgetTypes

```javascript
const widgetsBundleId = 'your-wgetsbundle-id';
const widgetTypeIds = 'your-wgettypes-id';

widgetService.updateWidgetsBundleWidgetTypes(widgetsBundleId, widgetTypeIds).subscribe(result => {
  console.log('Result:', result);
});
```

### updateWidgetsBundleWidgetFqns

```javascript
const widgetsBundleId = 'your-wgetsbundle-id';
const widgetTypeFqns = 'your-wgettypefqns-id';

widgetService.updateWidgetsBundleWidgetFqns(widgetsBundleId, widgetTypeFqns).subscribe(result => {
  console.log('Result:', result);
});
```

### getBundleWidgetTypes

```javascript
const widgetsBundleId = 'your-wgetsbundle-id';

widgetService.getBundleWidgetTypes(widgetsBundleId).subscribe(result => {
  console.log('BundleWidTypes:', result);
});
```

### exportBundleWidgetTypesDetails

```javascript
const widgetsBundleId = 'your-wgetsbundle-id';

widgetService.exportBundleWidgetTypesDetails(widgetsBundleId).subscribe(result => {
  console.log('exportBundleWidTypesDetails:', result);
});
```

### getBundleWidgetTypeFqns

```javascript
const widgetsBundleId = 'your-wgetsbundle-id';

widgetService.getBundleWidgetTypeFqns(widgetsBundleId).subscribe(result => {
  console.log('Result:', result);
});
```

### getBundleWidgetTypeInfosList

```javascript
const widgetsBundleId = 'your-wgetsbundle-id';

widgetService.getBundleWidgetTypeInfosList(widgetsBundleId).subscribe(info => {
  console.log('Info:', info);
});
```

### getBundleWidgetTypeInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const widgetsBundleId = 'your-wgetsbundle-id';
const widgetTypes = {
  // your widgetTypes object
};

widgetService.getBundleWidgetTypeInfos(pageLink, widgetsBundleId, widgetTypes).subscribe(info => {
  console.log('Info:', info);
});
```

### getWidgetType

```javascript
const fullFqn = 'your-fullfqn';

widgetService.getWidgetType(fullFqn).subscribe(result => {
  console.log('WidType:', result);
});
```

### saveWidgetTypeDetails

```javascript
const widgetInfo = {
  // your widgetInfo object
};
const id = {
  // your id object
};
const createdTime = Date.now();
const version = 100;

widgetService.saveWidgetTypeDetails(widgetInfo, id, createdTime, version).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### saveImportedWidgetTypeDetails

```javascript
const widgetTypeDetails = {
  // your widgetTypeDetails object
};

widgetService.saveImportedWidgetTypeDetails(widgetTypeDetails).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getWidgetTypeById

```javascript
const widgetTypeId = 'your-wgettype-id';

widgetService.getWidgetTypeById(widgetTypeId).subscribe(result => {
  console.log('WidTypeById:', result);
});
```

### exportWidgetType

```javascript
const widgetTypeId = 'your-wgettype-id';

widgetService.exportWidgetType(widgetTypeId).subscribe(result => {
  console.log('exportWidType:', result);
});
```

### getWidgetTypeInfoById

```javascript
const widgetTypeId = 'your-wgettype-id';

widgetService.getWidgetTypeInfoById(widgetTypeId).subscribe(info => {
  console.log('Info:', info);
});
```

### saveWidgetType

```javascript
const widgetTypeDetails = {
  // your widgetTypeDetails object
};

widgetService.saveWidgetType(widgetTypeDetails).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getWidgetTypes

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const widgetTypes = {
  // your widgetTypes object
};

widgetService.getWidgetTypes(pageLink, widgetTypes).subscribe(info => {
  console.log('Info:', info);
});
```

### getWidgetTemplate

```javascript
const widgetTypeParam = {
  // your widgetTypeParam object
};

widgetService.getWidgetTemplate(widgetTypeParam).subscribe(info => {
  console.log('Info:', info);
});
```

### getWidgetInfoFromCache

```javascript
const fullFqn = 'your-fullfqn';

const info = widgetService.getWidgetInfoFromCache(fullFqn);
console.log('Info:', info);
```

### getBasicWidgetSettingsComponentBySelector

```javascript
const selector = 'your-selector';

const result = widgetService.getBasicWidgetSettingsComponentBySelector(selector);
console.log('BasicWidSettingsComponentBySelector:', result);
```

### getWidgetSettingsComponentTypeBySelector

```javascript
const selector = 'your-selector';

const settings = widgetService.getWidgetSettingsComponentTypeBySelector(selector);
console.log('Settings:', settings);
```

### widgetTypeUpdated

```javascript
const updatedWidgetType = {
  // your updatedWidgetType object
};

const result = widgetService.widgetTypeUpdated(updatedWidgetType);
console.log('Result:', result);
```

### getWidgetsBundlesByIds

```javascript
const widgetsBundleIds = 'your-wgetsbundles-id';

widgetService.getWidgetsBundlesByIds(widgetsBundleIds).subscribe(result => {
  console.log('WidsBundlesByIds:', result);
});
```

### loadWidgetsBundleCache

```javascript
widgetService.loadWidgetsBundleCache().subscribe(result => {
  console.log('loadWidsBundleCache:', result);
});
```

