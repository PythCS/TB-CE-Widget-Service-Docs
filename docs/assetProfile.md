# Asset Profile

```javascript
// Service name: assetProfile
// File: asset-profile.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfile = $injector.get(self.ctx.servicesMap.get('assetProfile'));
```

### **1. getAssetProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfile.getAssetProfiles(pageLink).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### **2. getAssetProfilesByIds**

```javascript
assetProfile.getAssetProfilesByIds(assetProfileIds).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### **3. getAssetProfile**

```javascript
assetProfile.getAssetProfile(assetProfileId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **4. exportAssetProfile**

```javascript
assetProfile.exportAssetProfile(assetProfileId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **5. saveAssetProfile**

```javascript
assetProfile.saveAssetProfile(assetProfile).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **6. setDefaultAssetProfile**

```javascript
assetProfile.setDefaultAssetProfile(assetProfileId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **7. getDefaultAssetProfileInfo**

```javascript
assetProfile.getDefaultAssetProfileInfo().subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **8. getAssetProfileInfo**

```javascript
assetProfile.getAssetProfileInfo(assetProfileId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### **9. getAssetProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfile.getAssetProfileInfos(pageLink).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### **10. getAssetProfileNames**

```javascript
assetProfile.getAssetProfileNames(activeOnly).subscribe(assets => {
  console.log('Assets:', assets);
});
```
