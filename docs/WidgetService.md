# WidgetService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('WidgetService'));
```

**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(result => {
  console.log('Fetched  Wid Fetched  Scope Variables result:', result);
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(result => {
  console.log('Fetched  All Wid Fetched s Bundles result:', result);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(result => {
  console.log('Fetched  System Wid Fetched s Bundles result:', result);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(tenant => {
  console.log('Fetched  Tenant Wid Fetched s Bundles tenant:', tenant);
});
```

**5. getWidgetBundles**

```javascript
widgetService.getWidgetBundles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Wid Fetched  Bundles result:', result);
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle('your-w-idgetsbundle-id').subscribe(result => {
  console.log('Fetched  Wid Fetched s Bundle result:', result);
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle('your-w-idgetsbundle-id').subscribe(result => {
  console.log('export Wid Fetched s Bundle result:', result);
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle('your-widgetsbundle-value').subscribe(result => {
  console.log('Saved  Wid Fetched s Bundle result:', result);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes('your-w-idgetsbundle-id', 'your-widgettypeids-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns('your-w-idgetsbundle-id', 'your-widgettypefqns-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes('your-w-idgetsbundle-id').subscribe(result => {
  console.log('Fetched  Bundle Wid Fetched  Types result:', result);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails('your-w-idgetsbundle-id').subscribe(result => {
  console.log('export Bundle Wid Fetched  Types Details result:', result);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns('your-w-idgetsbundle-id').subscribe(result => {
  console.log('Fetched  Bundle Wid Fetched  Type Fqns result:', result);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList('your-w-idgetsbundle-id').subscribe(info => {
  console.log('Fetched  Bundle Wid Fetched  Type Infos List info:', info);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
widgetService.getBundleWidgetTypeInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-w-idgetsbundle-id', 'your-widgettypes-value').subscribe(info => {
  console.log('Fetched  Bundle Wid Fetched  Type Infos info:', info);
});
```

**16. getWidgetType**

```javascript
widgetService.getWidgetType('your-fullfqn-value').subscribe(result => {
  console.log('Fetched  Wid Fetched  Type result:', result);
});
```

**17. saveWidgetTypeDetails**

```javascript
widgetService.saveWidgetTypeDetails('your-widgetinfo-value', 'your--id', 0, 0).subscribe(result => {
  console.log('Saved  Wid Fetched  Type Details result:', result);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails('your-widgettypedetails-value').subscribe(result => {
  console.log('Saved  Imported Wid Fetched  Type Details result:', result);
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById('your-w-idgettype-id').subscribe(result => {
  console.log('Fetched  Wid Fetched  Type By Id result:', result);
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType('your-w-idgettype-id').subscribe(result => {
  console.log('export Wid Fetched  Type result:', result);
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById('your-w-idgettype-id').subscribe(info => {
  console.log('Fetched  Wid Fetched  Type Info By Id info:', info);
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType('your-widgettypedetails-value').subscribe(result => {
  console.log('Saved  Wid Fetched  Type result:', result);
});
```

**23. getWidgetTypes**

```javascript
widgetService.getWidgetTypes(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-widgettypes-value').subscribe(result => {
  console.log('Fetched  Wid Fetched  Types result:', result);
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate('your-widgettypeparam-value').subscribe(result => {
  console.log('Fetched  Wid Fetched  Template result:', result);
});
```

**25. getWidgetInfoFromCache**

```javascript
widgetService.getWidgetInfoFromCache('your-fullfqn-value').subscribe(info => {
  console.log('Fetched  Wid Fetched  Info From Cache info:', info);
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
widgetService.getBasicWidgetSettingsComponentBySelector('your-selector-value').subscribe(settings => {
  console.log('Fetched  Basic Wid Fetched  Settings Component By Selector settings:', settings);
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
widgetService.getWidgetSettingsComponentTypeBySelector('your-selector-value').subscribe(settings => {
  console.log('Fetched  Wid Fetched  Settings Component Type By Selector settings:', settings);
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated('your-updatedwidgettype-value').subscribe(result => {
  console.log('wid Fetched  Type Updated result:', result);
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds('your-widgetsbundleids-value').subscribe(result => {
  console.log('Fetched  Wid Fetched s Bundles By Ids result:', result);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(result => {
  console.log('load Wid Fetched s Bundle Cache result:', result);
});
```
