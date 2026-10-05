# ASSET PROFILE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfiles(pageLink).subscribe(assetProfiles => {
  console.log('List of Asset Profiles:', assetProfiles);
});
```

**2. getAssetProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileId = 'your-asset-profile-id';
assetProfileService.getAssetProfile(assetProfileId).subscribe(assetProfile => {
  console.log('Get Asset Profile:', assetProfile);
});
```

**3. exportAssetProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileId = 'your-asset-profile-id';
assetProfileService.exportAssetProfile(assetProfileId).subscribe(exportAssetProfile => {
  console.log('Export Asset Profile:', exportAssetProfile);
});
```

**4. saveAssetProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfile = {  // AssetProfile object
  // ... set the fields you need
};
assetProfileService.saveAssetProfile(assetProfile).subscribe(savedAssetProfile => {
  console.log('Saved Asset Profile:', savedAssetProfile);
});
```

**5. setDefaultAssetProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileId = 'your-asset-profile-id';
assetProfileService.setDefaultAssetProfile(assetProfileId).subscribe(setDefaultAssetProfile => {
  console.log('Set Default Asset Profile:', setDefaultAssetProfile);
});
```

**6. getDefaultAssetProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
assetProfileService.getDefaultAssetProfileInfo().subscribe(defaultAssetProfileInfo => {
  console.log('Get Default Asset Profile Info:', defaultAssetProfileInfo);
});
```

**7. getAssetProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileId = 'your-asset-profile-id';
assetProfileService.getAssetProfileInfo(assetProfileId).subscribe(assetProfileInfo => {
  console.log('Get Asset Profile Info:', assetProfileInfo);
});
```

**8. getAssetProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(assetProfileInfos => {
  console.log('List of Asset Profile Infos:', assetProfileInfos);
});
```

**9. getAssetProfilesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const assetProfileIds = ['your-asset-profile-i-1', 'your-asset-profile-i-2'];
assetProfileService.getAssetProfilesByIds(assetProfileIds).subscribe(assetProfilesBys => {
  console.log('List of Asset Profiles By Ids:', assetProfilesBys);
});
```

**10. getAssetProfileNames**

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
const activeOnly = 'value';
assetProfileService.getAssetProfileNames(activeOnly).subscribe(assetProfileNames => {
  console.log('List of Asset Profile Names:', assetProfileNames);
});
```
