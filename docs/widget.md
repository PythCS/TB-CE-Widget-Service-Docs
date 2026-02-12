### **WIDGET SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetservice = $injector.get(self.ctx.servicesMap.get('widgetservice'));

```

**1. getWidgetScopeVariables**

```javascript
const result = widgetservice.getWidgetScopeVariables();
console.log('Result:', result);
```

**2. getAllWidgetsBundles**

```javascript
widgetservice.getAllWidgetsBundles().subscribe(allwidsbundles => {
  console.log('Allwidsbundles:', allwidsbundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetservice.getSystemWidgetsBundles().subscribe(systemwidsbundles => {
  console.log('Systemwidsbundles:', systemwidsbundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetservice.getTenantWidgetsBundles().subscribe(tenantwidsbundles => {
  console.log('Tenantwidsbundles:', tenantwidsbundles);
});
```

**5. getWidgetBundles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetservice.getWidgetBundles(pageLink).subscribe(widbundles => {
  console.log('Widbundles:', widbundles);
});
```

**6. getWidgetsBundle**

```javascript
widgetservice.getWidgetsBundle('your-widgetsbundle-id').subscribe(widsbundle => {
  console.log('Widsbundle:', widsbundle);
});
```

**7. exportWidgetsBundle**

```javascript
widgetservice.exportWidgetsBundle('your-widgetsbundle-id').subscribe(exportwidsbundle => {
  console.log('Exportwidsbundle:', exportwidsbundle);
});
```

**8. saveWidgetsBundle**

```javascript
widgetservice.saveWidgetsBundle('your-widgetsbundle-id').subscribe(savewidsbundle => {
  console.log('Savewidsbundle:', savewidsbundle);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetservice.updateWidgetsBundleWidgetTypes('your-widgetsbundle-id', 'your-widgettypes-id').subscribe(updatewidsbundlewidtypes => {
  console.log('Updatewidsbundlewidtypes:', updatewidsbundlewidtypes);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetservice.updateWidgetsBundleWidgetFqns('your-widgetsbundle-id', 'your-widgettypefqns-id').subscribe(updatewidsbundlewidfqns => {
  console.log('Updatewidsbundlewidfqns:', updatewidsbundlewidfqns);
});
```

**11. getBundleWidgetTypes**

```javascript
widgetservice.getBundleWidgetTypes('your-widgetsbundle-id').subscribe(bundlewidtypes => {
  console.log('Bundlewidtypes:', bundlewidtypes);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetservice.exportBundleWidgetTypesDetails('your-widgetsbundle-id').subscribe(exportbundlewidtypesdetails => {
  console.log('Exportbundlewidtypesdetails:', exportbundlewidtypesdetails);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetservice.getBundleWidgetTypeFqns('your-widgetsbundle-id').subscribe(bundlewidtypefqns => {
  console.log('Bundlewidtypefqns:', bundlewidtypefqns);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetservice.getBundleWidgetTypeInfosList('your-widgetsbundle-id').subscribe(bundlewidtypeinfoslist => {
  console.log('Bundlewidtypeinfoslist:', bundlewidtypeinfoslist);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetservice.getBundleWidgetTypeInfos(pageLink, 'your-widgetsbundle-id', 'your-widgettypes-id').subscribe(bundlewidtypeinfos => {
  console.log('Bundlewidtypeinfos:', bundlewidtypeinfos);
});
```

**16. getWidgetType**

```javascript
widgetservice.getWidgetType('your-fullfqn').subscribe(widtype => {
  console.log('Widtype:', widtype);
});
```

**17. saveWidgetTypeDetails**

```javascript
widgetservice.saveWidgetTypeDetails('your-widgetinfo-id', 'your-id-id', 10, 10).subscribe(savewidtypedetails => {
  console.log('Savewidtypedetails:', savewidtypedetails);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetservice.saveImportedWidgetTypeDetails('your-widgettypedetails-id').subscribe(saveimportedwidtypedetails => {
  console.log('Saveimportedwidtypedetails:', saveimportedwidtypedetails);
});
```

**19. getWidgetTypeById**

```javascript
widgetservice.getWidgetTypeById('your-widgettype-id').subscribe(widtypebyid => {
  console.log('Widtypebyid:', widtypebyid);
});
```

**20. exportWidgetType**

```javascript
widgetservice.exportWidgetType('your-widgettype-id').subscribe(exportwidtype => {
  console.log('Exportwidtype:', exportwidtype);
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetservice.getWidgetTypeInfoById('your-widgettype-id').subscribe(widtypeinfobyid => {
  console.log('Widtypeinfobyid:', widtypeinfobyid);
});
```

**22. saveWidgetType**

```javascript
widgetservice.saveWidgetType('your-widgettypedetails-id').subscribe(savewidtype => {
  console.log('Savewidtype:', savewidtype);
});
```

**23. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetservice.getWidgetTypes(pageLink, 'your-widgettypes-id').subscribe(widtypes => {
  console.log('Widtypes:', widtypes);
});
```

**24. getWidgetTemplate**

```javascript
widgetservice.getWidgetTemplate('your-widgettypeparam-id').subscribe(widtemplate => {
  console.log('Widtemplate:', widtemplate);
});
```

**25. getWidgetInfoFromCache**

```javascript
const result = widgetservice.getWidgetInfoFromCache('your-fullfqn');
console.log('Result:', result);
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
const result = widgetservice.getBasicWidgetSettingsComponentBySelector('your-selector');
console.log('Result:', result);
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
const result = widgetservice.getWidgetSettingsComponentTypeBySelector('your-selector');
console.log('Result:', result);
```

**28. widgetTypeUpdated**

```javascript
const result = widgetservice.widgetTypeUpdated('your-updatedwidgettype-id');
console.log('Result:', result);
```

**29. getWidgetsBundlesByIds**

```javascript
widgetservice.getWidgetsBundlesByIds('your-widgetsbundles-id').subscribe(widsbundlesbyids => {
  console.log('Widsbundlesbyids:', widsbundlesbyids);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetservice.loadWidgetsBundleCache().subscribe(widsbundlecache => {
  console.log('Widsbundlecache:', widsbundlecache);
});
```

