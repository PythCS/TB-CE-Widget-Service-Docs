# WidgetService

### **WIDGETSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(widgetcopevariable => {
  console.log('Widget Scope Variables:', widgetcopevariable);
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles({ /* your config */ }).subscribe(allwidgetbundle => {
  console.log('All Widgets Bundles:', allwidgetbundle);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles({ /* your config */ }).subscribe(ytemwidgetbundle => {
  console.log('System Widgets Bundles:', ytemwidgetbundle);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles({ /* your config */ }).subscribe(tenantwidgetbundle => {
  console.log('Tenant Widgets Bundles:', tenantwidgetbundle);
});
```

**5. getWidgetBundles**

```javascript
widgetService.getWidgetBundles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(widgetbundle => {
  console.log('Widget Bundles:', widgetbundle);
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle('your-widgetsbundle-id', { /* your config */ }).subscribe(widgetsbundle => {
  console.log('Widgets Bundle:', widgetsbundle);
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle('your-widgetsbundle-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle({ /* your widgetsBundle */ }, { /* your config */ }).subscribe(savedWidgetsBundle => {
  console.log('Saved WidgetsBundle:', savedWidgetsBundle);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes('your-widgetsbundle-id', 'your-widgettypeids', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns('your-widgetsbundle-id', 'your-widgettypefqns', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes('your-widgetsbundle-id', { /* your config */ }).subscribe(bundlewidgettype => {
  console.log('Bundle Widget Types:', bundlewidgettype);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails('your-widgetsbundle-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns('your-widgetsbundle-id', { /* your config */ }).subscribe(bundlewidgettypefqn => {
  console.log('Bundle Widget Type Fqns:', bundlewidgettypefqn);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList('your-widgetsbundle-id', { /* your config */ }).subscribe(bundlewidgettypeinfolit => {
  console.log('Bundle Widget Type Infos List:', bundlewidgettypeinfolit);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
widgetService.getBundleWidgetTypeInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-widgetsbundle-id', 'your-widgettypes', { /* your config */ }).subscribe(bundlewidgettypeinfo => {
  console.log('Bundle Widget Type Infos:', bundlewidgettypeinfo);
});
```

**16. getWidgetType**

```javascript
widgetService.getWidgetType('your-fullFqn', { /* your config */ }).subscribe(widgettype => {
  console.log('Widget Type:', widgettype);
});
```

**17. saveWidgetTypeDetails**

```javascript
widgetService.saveWidgetTypeDetails({ /* your widgetInfo */ }, { /* your id */ }, 100, 100, { /* your config */ }).subscribe(savedWidgetTypeDetails => {
  console.log('Saved WidgetTypeDetails:', savedWidgetTypeDetails);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails('your-widgettypedetails', { /* your config */ }).subscribe(savedImportedWidgetTypeDetails => {
  console.log('Saved ImportedWidgetTypeDetails:', savedImportedWidgetTypeDetails);
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById('your-widgettype-id', { /* your config */ }).subscribe(widgettypebyid => {
  console.log('Widget Type By Id:', widgettypebyid);
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType('your-widgettype-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById('your-widgettype-id', { /* your config */ }).subscribe(widgettypeinfobyid => {
  console.log('Widget Type Info By Id:', widgettypeinfobyid);
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType('your-widgettypedetails', { /* your config */ }).subscribe(savedWidgetType => {
  console.log('Saved WidgetType:', savedWidgetType);
});
```

**23. getWidgetTypes**

```javascript
widgetService.getWidgetTypes(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-widgettypes', { /* your config */ }).subscribe(widgettype => {
  console.log('Widget Types:', widgettype);
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate('your-widgettypeparam', { /* your config */ }).subscribe(widgettemplate => {
  console.log('Widget Template:', widgettemplate);
});
```

**25. getWidgetInfoFromCache**

```javascript
widgetService.getWidgetInfoFromCache('your-fullFqn').subscribe(widgetinfofromcache => {
  console.log('Widget Info From Cache:', widgetinfofromcache);
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
widgetService.getBasicWidgetSettingsComponentBySelector('your-selector').subscribe(basicwidgetsettingscomponentbyselector => {
  console.log('Basic Widget Settings Component By Selector:', basicwidgetsettingscomponentbyselector);
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
widgetService.getWidgetSettingsComponentTypeBySelector('your-selector').subscribe(widgetsettingscomponenttypebyselector => {
  console.log('Widget Settings Component Type By Selector:', widgetsettingscomponenttypebyselector);
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated('your-updatedwidgettype').subscribe(result => {
  console.log('Result:', result);
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds(['id1', 'id2'], { /* your config */ }).subscribe(widgetbundlebyid => {
  console.log('Widgets Bundles By Ids:', widgetbundlebyid);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
