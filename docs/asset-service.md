# ASSET

Asset management and organization.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('assetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

## Methods

### getTenantAssetInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

assetService.getTenantAssetInfos(pageLink, type).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### getTenantAssetInfosByAssetProfileId

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const assetProfileId = 'your-assetprofile-id';

assetService.getTenantAssetInfosByAssetProfileId(pageLink, assetProfileId).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### getCustomerAssetInfos

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

assetService.getCustomerAssetInfos(customerId, pageLink, type).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### getCustomerAssetInfosByAssetProfileId

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const assetProfileId = 'your-assetprofile-id';

assetService.getCustomerAssetInfosByAssetProfileId(customerId, pageLink, assetProfileId).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### getAsset

```javascript
const assetId = 'your-asset-id';

assetService.getAsset(assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### getAssets

```javascript
const assetIds = 'your-assets-id';

assetService.getAssets(assetIds).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### getAssetInfo

```javascript
const assetId = 'your-asset-id';

assetService.getAssetInfo(assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### saveAsset

```javascript
const asset = {
  // your asset object
};

assetService.saveAsset(asset).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### getAssetTypes

```javascript
assetService.getAssetTypes().subscribe(result => {
  console.log('AssetTypes:', result);
});
```

### makeAssetPublic

```javascript
const assetId = 'your-asset-id';

assetService.makeAssetPublic(assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### assignAssetToCustomer

```javascript
const customerId = 'your-customer-id';
const assetId = 'your-asset-id';

assetService.assignAssetToCustomer(customerId, assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### findByQuery

```javascript
const query = {
  // your query object
};

assetService.findByQuery(query).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### findByName

```javascript
const assetName = 'your-assetname';

assetService.findByName(assetName).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### assignAssetToEdge

```javascript
const edgeId = 'your-edge-id';
const assetId = 'your-asset-id';

assetService.assignAssetToEdge(edgeId, assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### getEdgeAssets

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

assetService.getEdgeAssets(edgeId, pageLink, type).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### bulkImportAssets

```javascript
const entitiesData = {
  // your entitiesData object
};

assetService.bulkImportAssets(entitiesData).subscribe(result => {
  console.log('Result:', result);
});
```

