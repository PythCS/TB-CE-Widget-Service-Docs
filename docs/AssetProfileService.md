# AssetProfileService

### **ASSETPROFILESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
assetProfileService.getAssetProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(aetprofile => {
  console.log('Asset Profiles:', aetprofile);
});
```

**2. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds(['id1', 'id2'], { /* your config */ }).subscribe(aetprofilebyid => {
  console.log('Asset Profiles By Ids:', aetprofilebyid);
});
```

**3. getAssetProfile**

```javascript
assetProfileService.getAssetProfile('your-assetprofile-id', { /* your config */ }).subscribe(assetprofile => {
  console.log('Asset Profile:', assetprofile);
});
```

**4. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile('your-assetprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. saveAssetProfile**

```javascript
assetProfileService.saveAssetProfile({ /* your assetProfile */ }, { /* your config */ }).subscribe(savedAssetProfile => {
  console.log('Saved AssetProfile:', savedAssetProfile);
});
```

**6. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile('your-assetprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo({ /* your config */ }).subscribe(defaultassetprofileinfo => {
  console.log('Default Asset Profile Info:', defaultassetprofileinfo);
});
```

**8. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo('your-assetprofile-id', { /* your config */ }).subscribe(assetprofileinfo => {
  console.log('Asset Profile Info:', assetprofileinfo);
});
```

**9. getAssetProfileInfos**

```javascript
assetProfileService.getAssetProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(aetprofileinfo => {
  console.log('Asset Profile Infos:', aetprofileinfo);
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames({ /* your activeOnly */ }, { /* your config */ }).subscribe(aetprofilename => {
  console.log('Asset Profile Names:', aetprofilename);
});
```
