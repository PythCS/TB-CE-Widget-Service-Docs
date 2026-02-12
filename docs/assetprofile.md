### **ASSET PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetprofileservice = $injector.get(self.ctx.servicesMap.get('assetprofileservice'));

```

**1. getAssetProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetprofileservice.getAssetProfiles(pageLink).subscribe(assetprofiles => {
  console.log('Assetprofiles:', assetprofiles);
});
```

**2. getAssetProfilesByIds**

```javascript
assetprofileservice.getAssetProfilesByIds('your-asset-id').subscribe(assetprofilesbyids => {
  console.log('Assetprofilesbyids:', assetprofilesbyids);
});
```

**3. getAssetProfile**

```javascript
assetprofileservice.getAssetProfile('your-asset-id').subscribe(assetprofile => {
  console.log('Assetprofile:', assetprofile);
});
```

**4. exportAssetProfile**

```javascript
assetprofileservice.exportAssetProfile('your-asset-id').subscribe(exportassetprofile => {
  console.log('Exportassetprofile:', exportassetprofile);
});
```

**5. saveAssetProfile**

```javascript
assetprofileservice.saveAssetProfile(assetProfile).subscribe(saveassetprofile => {
  console.log('Saveassetprofile:', saveassetprofile);
});
```

**6. setDefaultAssetProfile**

```javascript
assetprofileservice.setDefaultAssetProfile('your-asset-id').subscribe(setdefaultassetprofile => {
  console.log('Setdefaultassetprofile:', setdefaultassetprofile);
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetprofileservice.getDefaultAssetProfileInfo().subscribe(defaultassetprofileinfo => {
  console.log('Defaultassetprofileinfo:', defaultassetprofileinfo);
});
```

**8. getAssetProfileInfo**

```javascript
assetprofileservice.getAssetProfileInfo('your-asset-id').subscribe(assetprofileinfo => {
  console.log('Assetprofileinfo:', assetprofileinfo);
});
```

**9. getAssetProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetprofileservice.getAssetProfileInfos(pageLink).subscribe(assetprofileinfos => {
  console.log('Assetprofileinfos:', assetprofileinfos);
});
```

**10. getAssetProfileNames**

```javascript
assetprofileservice.getAssetProfileNames(true).subscribe(assetprofilenames => {
  console.log('Assetprofilenames:', assetprofilenames);
});
```

