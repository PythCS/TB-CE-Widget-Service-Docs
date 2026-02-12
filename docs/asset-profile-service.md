# ASSET PROFILE

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

## Methods

### getAssetProfiles

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

assetProfileService.getAssetProfiles(pageLink).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### getAssetProfilesByIds

```javascript
const assetProfileIds = 'your-assetprofiles-id';

assetProfileService.getAssetProfilesByIds(assetProfileIds).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### getAssetProfile

```javascript
const assetProfileId = 'your-assetprofile-id';

assetProfileService.getAssetProfile(assetProfileId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### exportAssetProfile

```javascript
const assetProfileId = 'your-assetprofile-id';

assetProfileService.exportAssetProfile(assetProfileId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### saveAssetProfile

```javascript
const assetProfile = {
  // your assetProfile object
};

assetProfileService.saveAssetProfile(assetProfile).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### setDefaultAssetProfile

```javascript
const assetProfileId = 'your-assetprofile-id';

assetProfileService.setDefaultAssetProfile(assetProfileId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### getDefaultAssetProfileInfo

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(asset => {
  console.log('Asset:', asset);
});
```

### getAssetProfileInfo

```javascript
const assetProfileId = 'your-assetprofile-id';

assetProfileService.getAssetProfileInfo(assetProfileId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

### getAssetProfileInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

assetProfileService.getAssetProfileInfos(pageLink).subscribe(assets => {
  console.log('Assets:', assets);
});
```

### getAssetProfileNames

```javascript
const activeOnly = {
  // your activeOnly object
};

assetProfileService.getAssetProfileNames(activeOnly).subscribe(info => {
  console.log('Info:', info);
});
```

