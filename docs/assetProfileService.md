# ASSET PROFILE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ASSET PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfiles(pageLink).subscribe(assetprofiles => {
  console.log('Get Asset Profiles: assetprofiles');
});
```

**2. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds('your-id').subscribe(assetprofilesbyids => {
  console.log('Get Asset Profiles By Ids: assetprofilesbyids');
});
```

**3. getAssetProfile**

```javascript
assetProfileService.getAssetProfile('your-asset-profile-id').subscribe(assetProfile => {
  console.log('Get Asset Profile: assetProfile');
});
```

**4. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile('your-asset-profile-id').subscribe(exported => {
  console.log('Export Asset Profile: exported');
});
```

**5. saveAssetProfile**

```javascript
const assetProfile = assetProfile;
assetProfileService.saveAssetProfile(assetProfile).subscribe(savedAssetProfile => {
  console.log('Save Asset Profile: savedAssetProfile');
});
```

**6. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile('your-asset-profile-id').subscribe(result => {
  console.log('Set Default Asset Profile: result');
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(defaultAssetProfileInfo => {
  console.log('Get Default Asset Profile Info:defaultAssetProfileInfo');
});
```

**8. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo('your-asset-profile-id').subscribe(assetProfileInfo => {
  console.log('Get Asset Profile Info: assetProfileInfo');
});
```

**9. getAssetProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(assetprofileinfos => {
  console.log('Get Asset Profile Infos: assetprofileinfos');
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames(true).subscribe(assetprofilenames => {
  console.log('Get Asset Profile Names: assetprofilenames');
});
```
