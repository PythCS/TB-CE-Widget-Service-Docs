# ASSET SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('assetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

**1. getTenantAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getTenantAssetInfos(pageLink, 'your-type-value').subscribe(tenantAssetInfos => {
  console.log('Get Tenant Asset Infos:', tenantAssetInfos);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getTenantAssetInfosByAssetProfileId(pageLink, 'your-assetprofile-id').subscribe(tenantAssetInfosByAssetProfileId => {
  console.log('Get Tenant Asset Infos By Asset Profile Id:', tenantAssetInfosByAssetProfileId);
});
```

**3. getCustomerAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getCustomerAssetInfos('your-customer-id', pageLink, 'your-type-value').subscribe(customerAssetInfos => {
  console.log('Get Customer Asset Infos:', customerAssetInfos);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getCustomerAssetInfosByAssetProfileId('your-customer-id', pageLink, 'your-assetprofile-id').subscribe(customerAssetInfosByAssetProfileId => {
  console.log('Get Customer Asset Infos By Asset Profile Id:', customerAssetInfosByAssetProfileId);
});
```

**5. getAsset**

```javascript
self.ctx.assetService.getAsset('your-asset-id').subscribe(asset => {
  console.log('Get Asset:', asset);
});
```

**6. getAssets**

```javascript
self.ctx.assetService.getAssets('your-assetids-value').subscribe(assets => {
  console.log('Get Assets:', assets);
});
```

**7. getAssetInfo**

```javascript
self.ctx.assetService.getAssetInfo('your-asset-id').subscribe(assetInfo => {
  console.log('Get Asset Info:', assetInfo);
});
```

**8. saveAsset**

```javascript
self.ctx.assetService.saveAsset('your-asset-value').subscribe(asset => {
  console.log('Save Asset:', asset);
});
```

**9. getAssetTypes**

```javascript
self.ctx.assetService.getAssetTypes().subscribe(assetTypes => {
  console.log('Get Asset Types:', assetTypes);
});
```

**10. makeAssetPublic**

```javascript
self.ctx.assetService.makeAssetPublic('your-asset-id').subscribe(makeAssetPublic => {
  console.log('Make Asset Public:', makeAssetPublic);
});
```

**11. assignAssetToCustomer**

```javascript
self.ctx.assetService.assignAssetToCustomer('your-customer-id', 'your-asset-id').subscribe(assetToCustomer => {
  console.log('Assign Asset To Customer:', assetToCustomer);
});
```

**12. findByQuery**

```javascript
self.ctx.assetService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**13. findByName**

```javascript
self.ctx.assetService.findByName('your-assetname-value').subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**14. assignAssetToEdge**

```javascript
self.ctx.assetService.assignAssetToEdge('your-edge-id', 'your-asset-id').subscribe(assetToEdge => {
  console.log('Assign Asset To Edge:', assetToEdge);
});
```

**15. getEdgeAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getEdgeAssets('your-edge-id', pageLink, 'your-type-value').subscribe(edgeAssets => {
  console.log('Get Edge Assets:', edgeAssets);
});
```

**16. bulkImportAssets**

```javascript
self.ctx.assetService.bulkImportAssets('your-entitiesdata-value').subscribe(bulkImportAssets => {
  console.log('Bulk Import Assets:', bulkImportAssets);
});
```
