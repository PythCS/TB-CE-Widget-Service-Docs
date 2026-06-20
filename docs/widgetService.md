# WIDGET SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **WIDGET SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(widgetscopevariables => {
  console.log('Get Widget Scope Variables: widgetscopevariables');
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(allwidgetsbundles => {
  console.log('Get All Widgets Bundles: allwidgetsbundles');
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(systemwidgetsbundles => {
  console.log('Get System Widgets Bundles: systemwidgetsbundles');
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(tenantwidgetsbundles => {
  console.log('Get Tenant Widgets Bundles: tenantwidgetsbundles');
});
```

**5. getWidgetBundles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetBundles(pageLink).subscribe(widgetbundles => {
  console.log('Get Widget Bundles: widgetbundles');
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle('your-widgets-bundle-id').subscribe(widgetsBundle => {
  console.log('Get Widgets Bundle: widgetsBundle');
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle('your-widgets-bundle-id').subscribe(exported => {
  console.log('Export Widgets Bundle: exported');
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle('your-id').subscribe(savedWidgetsBundle => {
  console.log('Save Widgets Bundle: savedWidgetsBundle');
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes('your-widgets-bundle-id', 'your-id').subscribe(result => {
  console.log('Update Widgets Bundle Widget Types:result');
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns('your-widgets-bundle-id', 'your-id').subscribe(result => {
  console.log('Update Widgets Bundle Widget Fqns:result');
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes('your-widgets-bundle-id').subscribe(bundlewidgettypes => {
  console.log('Get Bundle Widget Types: bundlewidgettypes');
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails('your-widgets-bundle-id').subscribe(exported => {
  console.log('Export Bundle Widget Types Details:exported');
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns('your-widgets-bundle-id').subscribe(bundlewidgettypefqns => {
  console.log('Get Bundle Widget Type Fqns: bundlewidgettypefqns');
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList('your-widgets-bundle-id').subscribe(bundleWidgetTypeInfosList => {
  console.log('Get Bundle Widget Type Infos List:bundleWidgetTypeInfosList');
});
```

**15. getBundleWidgetTypeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getBundleWidgetTypeInfos(pageLink, 'your-widgets-bundle-id', 'your-id').subscribe(bundlewidgettypeinfos => {
  console.log('Get Bundle Widget Type Infos: bundlewidgettypeinfos');
});
```

**16. getWidgetType**

```javascript
const fullFqn = fullFqn;
widgetService.getWidgetType(fullFqn).subscribe(widgetType => {
  console.log('Get Widget Type: widgetType');
});
```

**17. saveWidgetTypeDetails**

```javascript
const createdTime = createdTime;
const version = version;
widgetService.saveWidgetTypeDetails('your-id', 'your-id', createdTime, version).subscribe(savedWidgetTypeDetails => {
  console.log('Save Widget Type Details: savedWidgetTypeDetails');
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails('your-id').subscribe(savedImportedWidgetTypeDetails => {
  console.log('Save Imported Widget Type Details:savedImportedWidgetTypeDetails');
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById('your-widget-type-id').subscribe(widgetTypeById => {
  console.log('Get Widget Type By Id: widgetTypeById');
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType('your-widget-type-id').subscribe(exported => {
  console.log('Export Widget Type: exported');
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById('your-widget-type-id').subscribe(widgetTypeInfoById => {
  console.log('Get Widget Type Info By Id: widgetTypeInfoById');
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType('your-id').subscribe(savedWidgetType => {
  console.log('Save Widget Type: savedWidgetType');
});
```

**23. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetTypes(pageLink, 'your-id').subscribe(widgettypes => {
  console.log('Get Widget Types: widgettypes');
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate('your-id').subscribe(widgetTemplate => {
  console.log('Get Widget Template: widgetTemplate');
});
```

**25. getWidgetInfoFromCache**

```javascript
const fullFqn = fullFqn;
widgetService.getWidgetInfoFromCache(fullFqn).subscribe(widgetInfoFromCache => {
  console.log('Get Widget Info From Cache: widgetInfoFromCache');
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
const selector = selector;
widgetService.getBasicWidgetSettingsComponentBySelector(selector).subscribe(basicWidgetSettingsComponentBySelector => {
  console.log('Get Basic Widget Settings Component By Selector:basicWidgetSettingsComponentBySelector');
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
const selector = selector;
widgetService.getWidgetSettingsComponentTypeBySelector(selector).subscribe(widgetSettingsComponentTypeBySelector => {
  console.log('Get Widget Settings Component Type By Selector:widgetSettingsComponentTypeBySelector');
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated('your-id').subscribe(result => {
  console.log('Widget Type Updated: result');
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds('your-id').subscribe(widgetsbundlesbyids => {
  console.log('Get Widgets Bundles By Ids: widgetsbundlesbyids');
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(result => {
  console.log('Load Widgets Bundle Cache: result');
});
```
