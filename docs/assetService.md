# ASSET SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('assetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

**1. getTenantAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getTenantAssets(pageLink, 'your-type-value').subscribe(tenantAssets => {
  console.log('Get Tenant Assets:', tenantAssets);
});
```

**2. getCustomerAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getCustomerAssets('your-customer-id', pageLink, 'your-type-value').subscribe(customerAssets => {
  console.log('Get Customer Assets:', customerAssets);
});
```

**3. getAsset**

```javascript
self.ctx.assetService.getAsset('your-asset-id').subscribe(asset => {
  console.log('Get Asset:', asset);
});
```

**4. getAssets**

```javascript
self.ctx.assetService.getAssets('your-assetids-value').subscribe(assets => {
  console.log('Get Assets:', assets);
});
```

**5. getUserAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getUserAssets(pageLink, 'your-type-value').subscribe(userAssets => {
  console.log('Get User Assets:', userAssets);
});
```

**6. getAllAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getAllAssetInfos(true, pageLink, 'your-assetprofile-id').subscribe(allAssetInfos => {
  console.log('Get All Asset Infos:', allAssetInfos);
});
```

**7. getCustomerAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getCustomerAssetInfos(true, 'your-customer-id', pageLink, 'your-assetprofile-id').subscribe(customerAssetInfos => {
  console.log('Get Customer Asset Infos:', customerAssetInfos);
});
```

**8. getAssetInfo**

```javascript
self.ctx.assetService.getAssetInfo('your-asset-id').subscribe(assetInfo => {
  console.log('Get Asset Info:', assetInfo);
});
```

**9. saveAsset**

```javascript
self.ctx.assetService.saveAsset('your-asset-value', 'your-entitygroupids-value').subscribe(asset => {
  console.log('Save Asset:', asset);
});
```

**10. getAssetTypes**

```javascript
self.ctx.assetService.getAssetTypes().subscribe(assetTypes => {
  console.log('Get Asset Types:', assetTypes);
});
```

**11. findByQuery**

```javascript
self.ctx.assetService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**12. findByName**

```javascript
self.ctx.assetService.findByName('your-assetname-value').subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**13. bulkImportAssets**

```javascript
self.ctx.assetService.bulkImportAssets('your-entitiesdata-value').subscribe(bulkImportAssets => {
  console.log('Bulk Import Assets:', bulkImportAssets);
});
```
