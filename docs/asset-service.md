# ASSET SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('assetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

**1. getTenantAssets**

```javascript
const assetService = self.ctx.assetService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
assetService.getTenantAssets(pageLink, type).subscribe(tenantAssets => {
  console.log('List of Tenant Assets:', tenantAssets);
});
```

**2. getCustomerAssets**

```javascript
const assetService = self.ctx.assetService;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
assetService.getCustomerAssets(customerId, pageLink, type).subscribe(customerAssets => {
  console.log('List of Customer Assets:', customerAssets);
});
```

**3. getAsset**

```javascript
const assetService = self.ctx.assetService;
const assetId = 'your-asset-id';
assetService.getAsset(assetId).subscribe(asset => {
  console.log('Get Asset:', asset);
});
```

**4. getAssets**

```javascript
const assetService = self.ctx.assetService;
const assetIds = ['your-asset-i-1', 'your-asset-i-2'];
assetService.getAssets(assetIds).subscribe(assets => {
  console.log('List of Assets:', assets);
});
```

**5. getUserAssets**

```javascript
const assetService = self.ctx.assetService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
assetService.getUserAssets(pageLink, type).subscribe(userAssets => {
  console.log('List of User Assets:', userAssets);
});
```

**6. getAllAssetInfos**

```javascript
const assetService = self.ctx.assetService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const assetProfileId = 'value';
assetService.getAllAssetInfos(includeCustomers, pageLink, assetProfileId).subscribe(allAssetInfos => {
  console.log('List of All Asset Infos:', allAssetInfos);
});
```

**7. getCustomerAssetInfos**

```javascript
const assetService = self.ctx.assetService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const assetProfileId = 'value';
assetService.getCustomerAssetInfos(includeCustomers, customerId, pageLink, assetProfileId).subscribe(customerAssetInfos => {
  console.log('List of Customer Asset Infos:', customerAssetInfos);
});
```

**8. getAssetInfo**

```javascript
const assetService = self.ctx.assetService;
const assetId = 'your-asset-id';
assetService.getAssetInfo(assetId).subscribe(assetInfo => {
  console.log('Get Asset Info:', assetInfo);
});
```

**9. saveAsset**

```javascript
const assetService = self.ctx.assetService;
const asset = {  // Asset object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = assetService.saveAsset(asset, entityGroupIds);
console.log('Result:', result);
```

**10. getAssetTypes**

```javascript
const assetService = self.ctx.assetService;
assetService.getAssetTypes().subscribe(assetTypes => {
  console.log('List of Asset Types:', assetTypes);
});
```

**11. findByQuery**

```javascript
const assetService = self.ctx.assetService;
const query = {  // AssetSearchQuery object
  // ... set the fields you need
};
assetService.findByQuery(query).subscribe(byQuerys => {
  console.log('List of By Querys:', byQuerys);
});
```

**12. findByName**

```javascript
const assetService = self.ctx.assetService;
const assetName = 'your-asset-name';
assetService.findByName(assetName).subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**13. bulkImportAssets**

```javascript
const assetService = self.ctx.assetService;
const entitiesData = {  // BulkImportRequest object
  // ... set the fields you need
};
assetService.bulkImportAssets(entitiesData).subscribe(bulkImportAssets => {
  console.log('Bulk Import Assets:', bulkImportAssets);
});
```
