### **ASSET SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetservice = $injector.get(self.ctx.servicesMap.get('assetservice'));

// Alternative: Direct context access
const assetservice = self.ctx.assetService;
```

**1. getTenantAssetInfos**

```javascript
const assetservice = self.ctx.assetService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetservice.getTenantAssetInfos(pageLink, 'your-type').subscribe(tenantassetinfos => {
  console.log('Tenantassetinfos:', tenantassetinfos);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
const assetservice = self.ctx.assetService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetservice.getTenantAssetInfosByAssetProfileId(pageLink, 'your-asset-id').subscribe(tenantassetinfosbyassetprofileid => {
  console.log('Tenantassetinfosbyassetprofileid:', tenantassetinfosbyassetprofileid);
});
```

**3. getCustomerAssetInfos**

```javascript
const assetservice = self.ctx.assetService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetservice.getCustomerAssetInfos(pageLink, 'your-customer-id', 'your-type').subscribe(customerassetinfos => {
  console.log('Customerassetinfos:', customerassetinfos);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
const assetservice = self.ctx.assetService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetservice.getCustomerAssetInfosByAssetProfileId(pageLink, 'your-customer-id', 'your-asset-id').subscribe(customerassetinfosbyassetprofileid => {
  console.log('Customerassetinfosbyassetprofileid:', customerassetinfosbyassetprofileid);
});
```

**5. getAsset**

```javascript
const assetservice = self.ctx.assetService;
assetservice.getAsset('your-asset-id').subscribe(asset => {
  console.log('Asset:', asset);
});
```

**6. getAssets**

```javascript
const assetservice = self.ctx.assetService;
assetservice.getAssets('your-asset-id').subscribe(assets => {
  console.log('Assets:', assets);
});
```

**7. getAssetInfo**

```javascript
const assetservice = self.ctx.assetService;
assetservice.getAssetInfo('your-asset-id').subscribe(assetinfo => {
  console.log('Assetinfo:', assetinfo);
});
```

**8. saveAsset**

```javascript
const assetservice = self.ctx.assetService;
assetservice.saveAsset(asset).subscribe(saveasset => {
  console.log('Saveasset:', saveasset);
});
```

**9. getAssetTypes**

```javascript
const assetservice = self.ctx.assetService;
assetservice.getAssetTypes().subscribe(assettypes => {
  console.log('Assettypes:', assettypes);
});
```

**10. makeAssetPublic**

```javascript
const assetservice = self.ctx.assetService;
assetservice.makeAssetPublic('your-asset-id').subscribe(makeassetpublic => {
  console.log('Makeassetpublic:', makeassetpublic);
});
```

**11. assignAssetToCustomer**

```javascript
const assetservice = self.ctx.assetService;
assetservice.assignAssetToCustomer('your-customer-id', 'your-asset-id').subscribe(assignassettocustomer => {
  console.log('Assignassettocustomer:', assignassettocustomer);
});
```

**12. findByQuery**

```javascript
const assetservice = self.ctx.assetService;
assetservice.findByQuery(query).subscribe(byquery => {
  console.log('Byquery:', byquery);
});
```

**13. findByName**

```javascript
const assetservice = self.ctx.assetService;
assetservice.findByName('Device Name').subscribe(byname => {
  console.log('Byname:', byname);
});
```

**14. assignAssetToEdge**

```javascript
const assetservice = self.ctx.assetService;
assetservice.assignAssetToEdge('your-edge-id', 'your-asset-id').subscribe(assignassettoedge => {
  console.log('Assignassettoedge:', assignassettoedge);
});
```

**15. getEdgeAssets**

```javascript
const assetservice = self.ctx.assetService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetservice.getEdgeAssets(pageLink, 'your-edge-id', 'your-type').subscribe(edgeassets => {
  console.log('Edgeassets:', edgeassets);
});
```

**16. bulkImportAssets**

```javascript
const assetservice = self.ctx.assetService;
assetservice.bulkImportAssets(entitiesData).subscribe(bulkimportassets => {
  console.log('Bulkimportassets:', bulkimportassets);
});
```

