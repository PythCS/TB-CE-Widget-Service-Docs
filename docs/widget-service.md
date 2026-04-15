# WidgetService

**Source:** `widget.service.ts`  
**Direct context access:** `none`

---

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```
**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(widScopeVariables => {
  console.log('Widget ScopeVariables:', widScopeVariables);
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(allWidsBundles => {
  console.log('AllWidget sBundles:', allWidsBundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(systemWidsBundles => {
  console.log('SystemWidget sBundles:', systemWidsBundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(tenantWidsBundles => {
  console.log('TenantWidget sBundles:', tenantWidsBundles);
});
```

**5. getWidgetBundles**

```javascript
widgetService.getWidgetBundles(self.ctx.pageLink(10, 0, null, null, null)).subscribe(widBundles => {
  console.log('Widget Bundles:', widBundles);
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle(/* widgetsBundleId */ null).subscribe(widsBundle => {
  console.log('Widget sBundle:', widsBundle);
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle(/* widgetsBundleId */ null).subscribe(exportWidsBundle => {
  console.log('exportWidget sBundle:', exportWidsBundle);
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle(/* widgetsBundle */ null).subscribe(widsBundle => {
  console.log('Widget sBundle:', widsBundle);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes(/* widgetsBundleId */ null, ['id1', 'id2']).subscribe(widsBundleWidTypes => {
  console.log('updateWidget sBundleWidget Types:', widsBundleWidTypes);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns(/* widgetsBundleId */ null, ['id1', 'id2']).subscribe(widsBundleWidFqns => {
  console.log('updateWidget sBundleWidget Fqns:', widsBundleWidFqns);
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes(/* widgetsBundleId */ null).subscribe(bundleWidTypes => {
  console.log('BundleWidget Types:', bundleWidTypes);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails(/* widgetsBundleId */ null).subscribe(exportBundleWidTypesDetails => {
  console.log('exportBundleWidget TypesDetails:', exportBundleWidTypesDetails);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns(/* widgetsBundleId */ null).subscribe(bundleWidTypeFqns => {
  console.log('BundleWidget TypeFqns:', bundleWidTypeFqns);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList(/* widgetsBundleId */ null).subscribe(bundleWidTypeInfosList => {
  console.log('BundleWidget Type infosList:', bundleWidTypeInfosList);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
widgetService.getBundleWidgetTypeInfos(self.ctx.pageLink(10, 0, null, null, null), /* widgetsBundleId */ null, null).subscribe(bundleWidTypeInfos => {
  console.log('BundleWidget Type infos:', bundleWidTypeInfos);
});
```

**16. getWidgetType**

```javascript
widgetService.getWidgetType(/* fullFqn */ null).subscribe(widType => {
  console.log('Widget Type:', widType);
});
```

**17. saveWidgetTypeDetails**

```javascript
widgetService.saveWidgetTypeDetails(/* widgetInfo */ null, /* id */ null, 0, 0).subscribe(widTypeDetails => {
  console.log('Widget TypeDetails:', widTypeDetails);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails(/* widgetTypeDetails */ null).subscribe(importedWidTypeDetails => {
  console.log('ImportedWidget TypeDetails:', importedWidTypeDetails);
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById(/* widgetTypeId */ null).subscribe(widTypeById => {
  console.log('Widget TypeById:', widTypeById);
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType(/* widgetTypeId */ null).subscribe(exportWidType => {
  console.log('exportWidget Type:', exportWidType);
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById(/* widgetTypeId */ null).subscribe(widTypeInfoById => {
  console.log('Widget Type infoById:', widTypeInfoById);
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType(/* widgetTypeDetails */ null).subscribe(widType => {
  console.log('Widget Type:', widType);
});
```

**23. getWidgetTypes**

```javascript
widgetService.getWidgetTypes(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(widTypes => {
  console.log('Widget Types:', widTypes);
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate(/* widgetTypeParam */ null).subscribe(widTemplate => {
  console.log('Widget Template:', widTemplate);
});
```

**25. getWidgetInfoFromCache**

```javascript
widgetService.getWidgetInfoFromCache(/* fullFqn */ null).subscribe(widInfoFromCache => {
  console.log('Widget infoFromCache:', widInfoFromCache);
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
widgetService.getBasicWidgetSettingsComponentBySelector(/* selector */ null).subscribe(basicWidSettingsComponentBySelector => {
  console.log('BasicWidget SettingsComponentBySelector:', basicWidSettingsComponentBySelector);
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
widgetService.getWidgetSettingsComponentTypeBySelector(/* selector */ null).subscribe(widSettingsComponentTypeBySelector => {
  console.log('Widget SettingsComponentTypeBySelector:', widSettingsComponentTypeBySelector);
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated(/* updatedWidgetType */ null).subscribe(widTypeUpdated => {
  console.log('widget TypeUpdated:', widTypeUpdated);
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds(['id1', 'id2']).subscribe(widsBundlesByIds => {
  console.log('Widget sBundlesByIds:', widsBundlesByIds);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(widsBundleCache => {
  console.log('loadWidget sBundleCache:', widsBundleCache);
});
```

---

*Auto-generated by ThingsBoardDocUpdater*