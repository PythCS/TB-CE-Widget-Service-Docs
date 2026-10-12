# ASSET PROFILE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfiles(pageLink).subscribe(assetProfiles => {
  console.log('Get Asset Profiles:', assetProfiles);
});
```

**2. getAssetProfile**

```javascript
assetProfileService.getAssetProfile('your-assetprofile-id').subscribe(assetProfile => {
  console.log('Get Asset Profile:', assetProfile);
});
```

**3. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile('your-assetprofile-id').subscribe(assetProfile => {
  console.log('Export Asset Profile:', assetProfile);
});
```

**4. saveAssetProfile**

```javascript
assetProfileService.saveAssetProfile('your-assetprofile-value').subscribe(assetProfile => {
  console.log('Save Asset Profile:', assetProfile);
});
```

**5. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile('your-assetprofile-id').subscribe(defaultAssetProfile => {
  console.log('Set Default Asset Profile:', defaultAssetProfile);
});
```

**6. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(defaultAssetProfileInfo => {
  console.log('Get Default Asset Profile Info:', defaultAssetProfileInfo);
});
```

**7. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo('your-assetprofile-id').subscribe(assetProfileInfo => {
  console.log('Get Asset Profile Info:', assetProfileInfo);
});
```

**8. getAssetProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(assetProfileInfos => {
  console.log('Get Asset Profile Infos:', assetProfileInfos);
});
```

**9. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds('your-assetprofileids-value').subscribe(assetProfilesByIds => {
  console.log('Get Asset Profiles By Ids:', assetProfilesByIds);
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames('your-activeonly-value').subscribe(assetProfileNames => {
  console.log('Get Asset Profile Names:', assetProfileNames);
});
```
