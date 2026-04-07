# AssetService

### **ASSETSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('assetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

**1. getTenantAssetInfos**

```javascript
assetService.getTenantAssetInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(tenantaetinfo => {
  console.log('Tenant Asset Infos:', tenantaetinfo);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
assetService.getTenantAssetInfosByAssetProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-assetprofile-id', { /* your config */ }).subscribe(tenantaetinfobyaetprofileid => {
  console.log('Tenant Asset Infos By Asset Profile Id:', tenantaetinfobyaetprofileid);
});
```

**3. getCustomerAssetInfos**

```javascript
assetService.getCustomerAssetInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(cutomeraetinfo => {
  console.log('Customer Asset Infos:', cutomeraetinfo);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
assetService.getCustomerAssetInfosByAssetProfileId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-assetprofile-id', { /* your config */ }).subscribe(cutomeraetinfobyaetprofileid => {
  console.log('Customer Asset Infos By Asset Profile Id:', cutomeraetinfobyaetprofileid);
});
```

**5. getAsset**

```javascript
assetService.getAsset('your-asset-id', { /* your config */ }).subscribe(asset => {
  console.log('Asset:', asset);
});
```

**6. getAssets**

```javascript
assetService.getAssets(['id1', 'id2'], { /* your config */ }).subscribe(aet => {
  console.log('Assets:', aet);
});
```

**7. getAssetInfo**

```javascript
assetService.getAssetInfo('your-asset-id', { /* your config */ }).subscribe(assetinfo => {
  console.log('Asset Info:', assetinfo);
});
```

**8. saveAsset**

```javascript
assetService.saveAsset({ /* your asset object */ }, { /* your config */ }).subscribe(savedAsset => {
  console.log('Saved Asset:', savedAsset);
});
```

**9. getAssetTypes**

```javascript
assetService.getAssetTypes({ /* your config */ }).subscribe(aettype => {
  console.log('Asset Types:', aettype);
});
```

**10. makeAssetPublic**

```javascript
assetService.makeAssetPublic('your-asset-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. assignAssetToCustomer**

```javascript
assetService.assignAssetToCustomer('your-customer-id', 'your-asset-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. findByQuery**

```javascript
assetService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. findByName**

```javascript
assetService.findByName('your-assetName', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**14. assignAssetToEdge**

```javascript
assetService.assignAssetToEdge('your-edge-id', 'your-asset-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getEdgeAssets**

```javascript
assetService.getEdgeAssets('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(edgeaet => {
  console.log('Edge Assets:', edgeaet);
});
```

**16. bulkImportAssets**

```javascript
assetService.bulkImportAssets({ /* your entitiesData */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
