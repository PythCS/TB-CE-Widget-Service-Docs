# WIDGET SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(widgetScopeVariables => {
  console.log('Get Widget Scope Variables:', widgetScopeVariables);
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(allWidgetsBundles => {
  console.log('Get All Widgets Bundles:', allWidgetsBundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(systemWidgetsBundles => {
  console.log('Get System Widgets Bundles:', systemWidgetsBundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(tenantWidgetsBundles => {
  console.log('Get Tenant Widgets Bundles:', tenantWidgetsBundles);
});
```

**5. getWidgetBundles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetBundles(pageLink).subscribe(widgetBundles => {
  console.log('Get Widget Bundles:', widgetBundles);
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle('your-widgetsbundle-id').subscribe(widgetsBundle => {
  console.log('Get Widgets Bundle:', widgetsBundle);
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle('your-widgetsbundle-id').subscribe(widgetsBundle => {
  console.log('Export Widgets Bundle:', widgetsBundle);
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle('your-widgetsbundle-value').subscribe(widgetsBundle => {
  console.log('Save Widgets Bundle:', widgetsBundle);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes('your-widgetsbundle-id', 'your-widgettypeids-value').subscribe(result => {
  console.log('Update Widgets Bundle Widget Types:', result);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns('your-widgetsbundle-id', 'your-widgettypefqns-value').subscribe(result => {
  console.log('Update Widgets Bundle Widget Fqns:', result);
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes('your-widgetsbundle-id').subscribe(bundleWidgetTypes => {
  console.log('Get Bundle Widget Types:', bundleWidgetTypes);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails('your-widgetsbundle-id').subscribe(bundleWidgetTypesDetails => {
  console.log('Export Bundle Widget Types Details:', bundleWidgetTypesDetails);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns('your-widgetsbundle-id').subscribe(bundleWidgetTypeFqns => {
  console.log('Get Bundle Widget Type Fqns:', bundleWidgetTypeFqns);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList('your-widgetsbundle-id').subscribe(bundleWidgetTypeInfosList => {
  console.log('Get Bundle Widget Type Infos List:', bundleWidgetTypeInfosList);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getBundleWidgetTypeInfos(pageLink, 'your-widgetsbundle-id', 'your-widgettypes-value').subscribe(bundleWidgetTypeInfos => {
  console.log('Get Bundle Widget Type Infos:', bundleWidgetTypeInfos);
});
```

**16. getWidgetType**

```javascript
widgetService.getWidgetType('your-fullfqn-value').subscribe(widgetType => {
  console.log('Get Widget Type:', widgetType);
});
```

**17. saveWidgetTypeDetails**

```javascript
widgetService.saveWidgetTypeDetails('your-widgetinfo-value', 'your--id', 0, 0).subscribe(widgetTypeDetails => {
  console.log('Save Widget Type Details:', widgetTypeDetails);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails('your-widgettypedetails-value').subscribe(importedWidgetTypeDetails => {
  console.log('Save Imported Widget Type Details:', importedWidgetTypeDetails);
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById('your-widgettype-id').subscribe(widgetTypeById => {
  console.log('Get Widget Type By Id:', widgetTypeById);
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType('your-widgettype-id').subscribe(widgetType => {
  console.log('Export Widget Type:', widgetType);
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById('your-widgettype-id').subscribe(widgetTypeInfoById => {
  console.log('Get Widget Type Info By Id:', widgetTypeInfoById);
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType('your-widgettypedetails-value').subscribe(widgetType => {
  console.log('Save Widget Type:', widgetType);
});
```

**23. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetTypes(pageLink, 'your-widgettypes-value').subscribe(widgetTypes => {
  console.log('Get Widget Types:', widgetTypes);
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate('your-widgettypeparam-value').subscribe(widgetTemplate => {
  console.log('Get Widget Template:', widgetTemplate);
});
```

**25. getWidgetInfoFromCache**

```javascript
widgetService.getWidgetInfoFromCache('your-fullfqn-value').subscribe(widgetInfoFromCache => {
  console.log('Get Widget Info From Cache:', widgetInfoFromCache);
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
widgetService.getBasicWidgetSettingsComponentBySelector('your-selector-value').subscribe(basicWidgetSettingsComponentBySelector => {
  console.log('Get Basic Widget Settings Component By Selector:', basicWidgetSettingsComponentBySelector);
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
widgetService.getWidgetSettingsComponentTypeBySelector('your-selector-value').subscribe(widgetSettingsComponentTypeBySelector => {
  console.log('Get Widget Settings Component Type By Selector:', widgetSettingsComponentTypeBySelector);
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated('your-updatedwidgettype-value').subscribe(widgetTypeUpdated => {
  console.log('Widget Type Updated:', widgetTypeUpdated);
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds('your-widgetsbundleids-value').subscribe(widgetsBundlesByIds => {
  console.log('Get Widgets Bundles By Ids:', widgetsBundlesByIds);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(loadWidgetsBundleCache => {
  console.log('Load Widgets Bundle Cache:', loadWidgetsBundleCache);
});
```
