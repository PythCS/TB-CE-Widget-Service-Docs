# ASSET SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ASSET SERVICE**

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
assetService.getTenantAssetInfos(pageLink, 'type').subscribe(tenantassetinfos => {
  console.log('Get Tenant Asset Infos: tenantassetinfos');
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetService.getTenantAssetInfosByAssetProfileId(pageLink, 'your-asset-profile-id').subscribe(tenantAssetInfosByAssetProfileId => {
  console.log('Get Tenant Asset Infos By Asset Profile Id:tenantAssetInfosByAssetProfileId');
});
```

**3. getCustomerAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetService.getCustomerAssetInfos('your-customer-id', pageLink, 'type').subscribe(customerassetinfos => {
  console.log('Get Customer Asset Infos: customerassetinfos');
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetService.getCustomerAssetInfosByAssetProfileId('your-customer-id', pageLink, 'your-asset-profile-id').subscribe(customerAssetInfosByAssetProfileId => {
  console.log('Get Customer Asset Infos By Asset Profile Id:customerAssetInfosByAssetProfileId');
});
```

**5. getAsset**

```javascript
assetService.getAsset('your-asset-id').subscribe(asset => {
  console.log('Get Asset: asset');
});
```

**6. getAssets**

```javascript
assetService.getAssets('your-id').subscribe(assets => {
  console.log('Get Assets: assets');
});
```

**7. getAssetInfo**

```javascript
assetService.getAssetInfo('your-asset-id').subscribe(assetInfo => {
  console.log('Get Asset Info: assetInfo');
});
```

**8. saveAsset**

```javascript
const asset = asset;
assetService.saveAsset(asset).subscribe(savedAsset => {
  console.log('Save Asset: savedAsset');
});
```

**9. getAssetTypes**

```javascript
assetService.getAssetTypes().subscribe(assettypes => {
  console.log('Get Asset Types: assettypes');
});
```

**10. makeAssetPublic**

```javascript
assetService.makeAssetPublic('your-asset-id').subscribe(result => {
  console.log('Make Asset Public: result');
});
```

**11. assignAssetToCustomer**

```javascript
assetService.assignAssetToCustomer('your-customer-id', 'your-asset-id').subscribe(result => {
  console.log('Assign Asset To Customer: result');
});
```

**12. findByQuery**

```javascript
const query = query;
assetService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**13. findByName**

```javascript
const assetName = assetName;
assetService.findByName(assetName).subscribe(entity => {
  console.log('Find By Name: entity');
});
```

**14. assignAssetToEdge**

```javascript
assetService.assignAssetToEdge('your-edge-id', 'your-asset-id').subscribe(result => {
  console.log('Assign Asset To Edge: result');
});
```

**15. getEdgeAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetService.getEdgeAssets('your-edge-id', pageLink, 'type').subscribe(edgeassets => {
  console.log('Get Edge Assets: edgeassets');
});
```

**16. bulkImportAssets**

```javascript
const entitiesData = entitiesData;
assetService.bulkImportAssets(entitiesData).subscribe(result => {
  console.log('Bulk Import Assets: result');
});
```
