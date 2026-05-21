# AssetProfileService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('AssetProfileService'));
```

**1. getAssetProfiles**

```javascript
assetProfileService.getAssetProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(profile => {
  console.log('Fetched  Asset Profiles profile:', profile);
});
```

**2. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds('your-assetprofileids-value').subscribe(profile => {
  console.log('Fetched  Asset Profiles By Ids profile:', profile);
});
```

**3. getAssetProfile**

```javascript
assetProfileService.getAssetProfile('your-assetprofile-id').subscribe(profile => {
  console.log('Fetched  Asset Profile profile:', profile);
});
```

**4. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile('your-assetprofile-id').subscribe(profile => {
  console.log('export Asset Profile profile:', profile);
});
```

**5. saveAssetProfile**

```javascript
assetProfileService.saveAssetProfile('your-assetprofile-value').subscribe(profile => {
  console.log('Saved  Asset Profile profile:', profile);
});
```

**6. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile('your-assetprofile-id').subscribe(profile => {
  console.log('set Default Asset Profile profile:', profile);
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(profile => {
  console.log('Fetched  Default Asset Profile Info profile:', profile);
});
```

**8. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo('your-assetprofile-id').subscribe(profile => {
  console.log('Fetched  Asset Profile Info profile:', profile);
});
```

**9. getAssetProfileInfos**

```javascript
assetProfileService.getAssetProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(profile => {
  console.log('Fetched  Asset Profile Infos profile:', profile);
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames('your-activeonly-value').subscribe(profile => {
  console.log('Fetched  Asset Profile Names profile:', profile);
});
```
