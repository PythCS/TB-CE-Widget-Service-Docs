# WIDGET SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

**1. getWidgetScopeVariables**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const result = widgetService.getWidgetScopeVariables();
console.log('Result:', result);
```

**2. getAllWidgetsBundles**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
widgetService.getAllWidgetsBundles().subscribe(allWidgetsBundles => {
  console.log('List of All Widgets Bundles:', allWidgetsBundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
widgetService.getSystemWidgetsBundles().subscribe(systemWidgetsBundles => {
  console.log('List of System Widgets Bundles:', systemWidgetsBundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
widgetService.getTenantWidgetsBundles().subscribe(tenantWidgetsBundles => {
  console.log('List of Tenant Widgets Bundles:', tenantWidgetsBundles);
});
```

**5. getWidgetBundles**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetBundles(pageLink).subscribe(widgetBundles => {
  console.log('List of Widget Bundles:', widgetBundles);
});
```

**6. getWidgetsBundle**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getWidgetsBundle(widgetsBundleId).subscribe(widgetsBundle => {
  console.log('Get Widgets Bundle:', widgetsBundle);
});
```

**7. exportWidgetsBundle**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.exportWidgetsBundle(widgetsBundleId).subscribe(exportWidgetsBundle => {
  console.log('Export Widgets Bundle:', exportWidgetsBundle);
});
```

**8. getWidgetsBundlesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleIds = ['your-widgets-bundle-i-1', 'your-widgets-bundle-i-2'];
widgetService.getWidgetsBundlesByIds(widgetsBundleIds).subscribe(widgetsBundlesBys => {
  console.log('List of Widgets Bundles By Ids:', widgetsBundlesBys);
});
```

**9. saveWidgetsBundle**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundle = {  // WidgetsBundle object
  // ... set the fields you need
};
widgetService.saveWidgetsBundle(widgetsBundle).subscribe(savedWidgetsBundle => {
  console.log('Saved Widgets Bundle:', savedWidgetsBundle);
});
```

**10. updateWidgetsBundleWidgetTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeIds = ['your-widget-type-i-1', 'your-widget-type-i-2'];
widgetService.updateWidgetsBundleWidgetTypes(widgetsBundleId, widgetTypeIds).subscribe(savedWidgetsBundleWidgetTypes => {
  console.log('Saved Widgets Bundle Widget Types:', savedWidgetsBundleWidgetTypes);
});
```

**11. updateWidgetsBundleWidgetFqns**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeFqns = [];  // e.g. array of widget-type-fqns values
widgetService.updateWidgetsBundleWidgetFqns(widgetsBundleId, widgetTypeFqns).subscribe(savedWidgetsBundleWidgetFqns => {
  console.log('Saved Widgets Bundle Widget Fqns:', savedWidgetsBundleWidgetFqns);
});
```

**12. getBundleWidgetTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getBundleWidgetTypes(widgetsBundleId).subscribe(bundleWidgetTypes => {
  console.log('List of Bundle Widget Types:', bundleWidgetTypes);
});
```

**13. exportBundleWidgetTypesDetails**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.exportBundleWidgetTypesDetails(widgetsBundleId).subscribe(exportBundleWidgetTypesDetails => {
  console.log('List of Export Bundle Widget Types Details:', exportBundleWidgetTypesDetails);
});
```

**14. getBundleWidgetTypeFqns**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getBundleWidgetTypeFqns(widgetsBundleId).subscribe(bundleWidgetTypeFqns => {
  console.log('List of Bundle Widget Type Fqns:', bundleWidgetTypeFqns);
});
```

**15. getBundleWidgetTypeInfosList**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getBundleWidgetTypeInfosList(widgetsBundleId).subscribe(bundleWidgetTypeInfosLists => {
  console.log('List of Bundle Widget Type Infos Lists:', bundleWidgetTypeInfosLists);
});
```

**16. getBundleWidgetTypeInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypes = 'value';
widgetService.getBundleWidgetTypeInfos(pageLink, widgetsBundleId, widgetTypes).subscribe(bundleWidgetTypeInfos => {
  console.log('List of Bundle Widget Type Infos:', bundleWidgetTypeInfos);
});
```

**17. getWidgetType**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const fullFqn = 'your-full-fqn';
widgetService.getWidgetType(fullFqn).subscribe(widgetType => {
  console.log('Get Widget Type:', widgetType);
});
```

**18. saveWidgetTypeDetails**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetInfo = {  // WidgetInfo object
  // ... set the fields you need
};
const id = {  // WidgetTypeId object
  // ... set the fields you need
};
const createdTime = 10;
const version = 10;
widgetService.saveWidgetTypeDetails(widgetInfo, id, createdTime, version).subscribe(savedWidgetTypeDetails => {
  console.log('Saved Widget Type Details:', savedWidgetTypeDetails);
});
```

**19. saveImportedWidgetTypeDetails**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeDetails = {  // WidgetTypeDetails object
  // ... set the fields you need
};
widgetService.saveImportedWidgetTypeDetails(widgetTypeDetails).subscribe(savedImportedWidgetTypeDetails => {
  console.log('Saved Imported Widget Type Details:', savedImportedWidgetTypeDetails);
});
```

**20. getWidgetTypeById**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeById(widgetTypeId).subscribe(widgetTypeBy => {
  console.log('Get Widget Type By Id:', widgetTypeBy);
});
```

**21. exportWidgetType**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeId = 'your-widget-type-id';
widgetService.exportWidgetType(widgetTypeId).subscribe(exportWidgetType => {
  console.log('Export Widget Type:', exportWidgetType);
});
```

**22. getWidgetTypeInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeInfoById(widgetTypeId).subscribe(widgetTypeInfoBy => {
  console.log('Get Widget Type Info By Id:', widgetTypeInfoBy);
});
```

**23. saveWidgetType**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeDetails = {  // WidgetTypeDetails object
  // ... set the fields you need
};
widgetService.saveWidgetType(widgetTypeDetails).subscribe(savedWidgetType => {
  console.log('Saved Widget Type:', savedWidgetType);
});
```

**24. getWidgetTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const widgetTypes = 'value';
widgetService.getWidgetTypes(pageLink, widgetTypes).subscribe(widgetTypes => {
  console.log('List of Widget Types:', widgetTypes);
});
```

**25. getWidgetTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const widgetTypeParam = {  // widgetType object
  // ... set the fields you need
};
widgetService.getWidgetTemplate(widgetTypeParam).subscribe(widgetTemplate => {
  console.log('Get Widget Template:', widgetTemplate);
});
```

**26. getWidgetInfoFromCache**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const fullFqn = 'your-full-fqn';
const result = widgetService.getWidgetInfoFromCache(fullFqn);
console.log('Result:', result);
```

**27. getBasicWidgetSettingsComponentBySelector**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const selector = 'your-selector';
const result = widgetService.getBasicWidgetSettingsComponentBySelector(selector);
console.log('Result:', result);
```

**28. getWidgetSettingsComponentTypeBySelector**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const selector = 'your-selector';
const result = widgetService.getWidgetSettingsComponentTypeBySelector(selector);
console.log('Result:', result);
```

**29. widgetTypeUpdated**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
const updatedWidgetType = {  // BaseWidgetType object
  // ... set the fields you need
};
const result = widgetService.widgetTypeUpdated(updatedWidgetType);
console.log('Result:', result);
```

**30. loadWidgetsBundleCache**

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
widgetService.loadWidgetsBundleCache().subscribe(widgetsBundleCache => {
  console.log('Load Widgets Bundle Cache:', widgetsBundleCache);
});
```
