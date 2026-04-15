# Widget

```javascript
// Service name: widget
// File: widget.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widget = $injector.get(self.ctx.servicesMap.get('widget'));
```

### **1. getWidgetScopeVariables**

```javascript
widget.getWidgetScopeVariables().subscribe(widgetScopeVariable => {
  console.log('Widget Scope Variable:', widgetScopeVariable);
});
```

### **2. getAllWidgetsBundles**

```javascript
widget.getAllWidgetsBundles().subscribe(widgetsBundles => {
  console.log('Widgets Bundles:', widgetsBundles);
});
```

### **3. getSystemWidgetsBundles**

```javascript
widget.getSystemWidgetsBundles().subscribe(systemWidgetsBundles => {
  console.log('System Widgets Bundles:', systemWidgetsBundles);
});
```

### **4. getTenantWidgetsBundles**

```javascript
widget.getTenantWidgetsBundles().subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **5. getWidgetBundles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widget.getWidgetBundles(pageLink).subscribe(widgetBundles => {
  console.log('Widget Bundles:', widgetBundles);
});
```

### **6. getWidgetsBundle**

```javascript
widget.getWidgetsBundle(widgetsBundleId).subscribe(widgetsBundle => {
  console.log('Widgets Bundle:', widgetsBundle);
});
```

### **7. exportWidgetsBundle**

```javascript
widget.exportWidgetsBundle(widgetsBundleId).subscribe(exportWidgetsBundle => {
  console.log('Export Widgets Bundle:', exportWidgetsBundle);
});
```

### **8. saveWidgetsBundle**

```javascript
widget.saveWidgetsBundle(widgetsBundle).subscribe(saveWidgetsBundle => {
  console.log('Save Widgets Bundle:', saveWidgetsBundle);
});
```

### **9. updateWidgetsBundleWidgetTypes**

```javascript
widget.updateWidgetsBundleWidgetTypes(widgetsBundleId, widgetTypeIds).subscribe(updateWidgetsBundleWidgetType => {
  console.log('Update Widgets Bundle Widget Type:', updateWidgetsBundleWidgetType);
});
```

### **10. updateWidgetsBundleWidgetFqns**

```javascript
widget.updateWidgetsBundleWidgetFqns(widgetsBundleId, widgetTypeFqns).subscribe(updateWidgetsBundleWidgetFqn => {
  console.log('Update Widgets Bundle Widget Fqn:', updateWidgetsBundleWidgetFqn);
});
```

### **11. getBundleWidgetTypes**

```javascript
widget.getBundleWidgetTypes(widgetsBundleId).subscribe(bundleWidgetTypes => {
  console.log('Bundle Widget Types:', bundleWidgetTypes);
});
```

### **12. exportBundleWidgetTypesDetails**

```javascript
widget.exportBundleWidgetTypesDetails(widgetsBundleId).subscribe(exportBundleWidgetTypesDetails => {
  console.log('Export Bundle Widget Types Details:', exportBundleWidgetTypesDetails);
});
```

### **13. getBundleWidgetTypeFqns**

```javascript
widget.getBundleWidgetTypeFqns(widgetsBundleId).subscribe(bundleWidgetTypeFqns => {
  console.log('Bundle Widget Type Fqns:', bundleWidgetTypeFqns);
});
```

### **14. getBundleWidgetTypeInfosList**

```javascript
widget.getBundleWidgetTypeInfosList(widgetsBundleId).subscribe(bundleWidgetTypeInfosList => {
  console.log('Bundle Widget Type Infos List:', bundleWidgetTypeInfosList);
});
```

### **15. getBundleWidgetTypeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widget.getBundleWidgetTypeInfos(pageLink).subscribe(bundleWidgetTypeInfos => {
  console.log('Bundle Widget Type Infos:', bundleWidgetTypeInfos);
});
```

### **16. getWidgetType**

```javascript
widget.getWidgetType(fullFqn).subscribe(widgetType => {
  console.log('Widget Type:', widgetType);
});
```

### **17. saveWidgetTypeDetails**

```javascript
widget.saveWidgetTypeDetails(widgetInfo, id, createdTime, version).subscribe(saveWidgetTypeDetail => {
  console.log('Save Widget Type Detail:', saveWidgetTypeDetail);
});
```

### **18. saveImportedWidgetTypeDetails**

```javascript
widget.saveImportedWidgetTypeDetails(widgetTypeDetails).subscribe(saveImportedWidgetTypeDetail => {
  console.log('Save Imported Widget Type Detail:', saveImportedWidgetTypeDetail);
});
```

### **19. getWidgetTypeById**

```javascript
widget.getWidgetTypeById(widgetTypeId).subscribe(widgetType => {
  console.log('Widget Type:', widgetType);
});
```

### **20. exportWidgetType**

```javascript
widget.exportWidgetType(widgetTypeId).subscribe(exportWidgetType => {
  console.log('Export Widget Type:', exportWidgetType);
});
```

### **21. getWidgetTypeInfoById**

```javascript
widget.getWidgetTypeInfoById(widgetTypeId).subscribe(widgetType => {
  console.log('Widget Type:', widgetType);
});
```

### **22. saveWidgetType**

```javascript
widget.saveWidgetType(widgetTypeDetails).subscribe(saveWidgetType => {
  console.log('Save Widget Type:', saveWidgetType);
});
```

### **23. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widget.getWidgetTypes(pageLink).subscribe(widgetTypes => {
  console.log('Widget Types:', widgetTypes);
});
```

### **24. getWidgetTemplate**

```javascript
widget.getWidgetTemplate(widgetTypeParam).subscribe(widgetTemplate => {
  console.log('Widget Template:', widgetTemplate);
});
```

### **25. getWidgetInfoFromCache**

```javascript
widget.getWidgetInfoFromCache(fullFqn).subscribe(widgetInfoFromCache => {
  console.log('Widget Info From Cache:', widgetInfoFromCache);
});
```

### **26. getBasicWidgetSettingsComponentBySelector**

```javascript
widget.getBasicWidgetSettingsComponentBySelector(selector).subscribe(basicWidgetSettingsComponentBySelector => {
  console.log('Basic Widget Settings Component By Selector:', basicWidgetSettingsComponentBySelector);
});
```

### **27. getWidgetSettingsComponentTypeBySelector**

```javascript
widget.getWidgetSettingsComponentTypeBySelector(selector).subscribe(widgetSettingsComponentTypeBySelector => {
  console.log('Widget Settings Component Type By Selector:', widgetSettingsComponentTypeBySelector);
});
```

### **28. widgetTypeUpdated**

```javascript
widget.widgetTypeUpdated(updatedWidgetType).subscribe(widgetTypeUpdated => {
  console.log('Widget Type Updated:', widgetTypeUpdated);
});
```

### **29. getWidgetsBundlesByIds**

```javascript
widget.getWidgetsBundlesByIds(widgetsBundleIds).subscribe(widgetsBundless => {
  console.log('Widgets Bundless:', widgetsBundless);
});
```

### **30. loadWidgetsBundleCache**

```javascript
widget.loadWidgetsBundleCache().subscribe(loadWidgetsBundleCache => {
  console.log('Load Widgets Bundle Cache:', loadWidgetsBundleCache);
});
```
