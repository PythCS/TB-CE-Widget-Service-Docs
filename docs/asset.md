# Asset

```javascript
// Service name: asset
// File: asset.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const asset = self.ctx.assetService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const asset = $injector.get(self.ctx.servicesMap.get('asset'));
```

### **1. getTenantAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
asset.getTenantAssetInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **2. getTenantAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
asset.getTenantAssetInfosByAssetProfileId(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **3. getCustomerAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
asset.getCustomerAssetInfos(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **4. getCustomerAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
asset.getCustomerAssetInfosByAssetProfileId(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **5. getAsset**

```javascript
asset.getAsset(assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **6. getAssets**

```javascript
asset.getAssets(assetIds).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### **7. getAssetInfo**

```javascript
asset.getAssetInfo(assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **8. saveAsset**

```javascript
asset.saveAsset(asset).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **9. getAssetTypes**

```javascript
asset.getAssetTypes().subscribe(assets => {
  console.log('Assets:', assets);
});
```

### **10. makeAssetPublic**

```javascript
asset.makeAssetPublic(assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **11. assignAssetToCustomer**

```javascript
asset.assignAssetToCustomer(customerId, assetId).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### **12. findByQuery**

```javascript
asset.findByQuery(query).subscribe(findByQuerys => {
  console.log('Find By Querys:', findByQuerys);
});
```

### **13. findByName**

```javascript
asset.findByName(assetName).subscribe(find => {
  console.log('Find:', find);
});
```

### **14. assignAssetToEdge**

```javascript
asset.assignAssetToEdge(edgeId, assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **15. getEdgeAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
asset.getEdgeAssets(pageLink).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### **16. bulkImportAssets**

```javascript
asset.bulkImportAssets(entitiesData).subscribe(asset => {
  console.log('Asset:', asset);
});
```
