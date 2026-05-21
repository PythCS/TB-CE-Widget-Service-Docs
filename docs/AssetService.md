# AssetService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('AssetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

**1. getTenantAssetInfos**

```javascript
assetService.getTenantAssetInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(tenant => {
  console.log('Fetched  Tenant Asset Infos tenant:', tenant);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
assetService.getTenantAssetInfosByAssetProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-assetprofile-id').subscribe(tenant => {
  console.log('Fetched  Tenant Asset Infos By Asset Profile Id tenant:', tenant);
});
```

**3. getCustomerAssetInfos**

```javascript
assetService.getCustomerAssetInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(info => {
  console.log('Fetched  Customer Asset Infos info:', info);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
assetService.getCustomerAssetInfosByAssetProfileId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-assetprofile-id').subscribe(profile => {
  console.log('Fetched  Customer Asset Infos By Asset Profile Id profile:', profile);
});
```

**5. getAsset**

```javascript
assetService.getAsset('your-asset-id').subscribe(result => {
  console.log('Fetched  Asset result:', result);
});
```

**6. getAssets**

```javascript
assetService.getAssets('your-assetids-value').subscribe(result => {
  console.log('Fetched  Assets result:', result);
});
```

**7. getAssetInfo**

```javascript
assetService.getAssetInfo('your-asset-id').subscribe(info => {
  console.log('Fetched  Asset Info info:', info);
});
```

**8. saveAsset**

```javascript
assetService.saveAsset('your-asset-value').subscribe(result => {
  console.log('Saved  Asset result:', result);
});
```

**9. getAssetTypes**

```javascript
assetService.getAssetTypes().subscribe(result => {
  console.log('Fetched  Asset Types result:', result);
});
```

**10. makeAssetPublic**

```javascript
assetService.makeAssetPublic('your-asset-id').subscribe(result => {
  console.log('make Asset Public result:', result);
});
```

**11. assignAssetToCustomer**

```javascript
assetService.assignAssetToCustomer('your-customer-id', 'your-asset-id').subscribe(result => {
  console.log('assign Asset To Customer result:', result);
});
```

**12. findByQuery**

```javascript
assetService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**13. findByName**

```javascript
assetService.findByName('your-assetname-value').subscribe(result => {
  console.log('find By Name result:', result);
});
```

**14. assignAssetToEdge**

```javascript
assetService.assignAssetToEdge('your-edge-id', 'your-asset-id').subscribe(result => {
  console.log('assign Asset To Edge result:', result);
});
```

**15. getEdgeAssets**

```javascript
assetService.getEdgeAssets('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(result => {
  console.log('Fetched  Edge Assets result:', result);
});
```

**16. bulkImportAssets**

```javascript
assetService.bulkImportAssets('your-entitiesdata-value').subscribe(result => {
  console.log('bulk Import Assets result:', result);
});
```
