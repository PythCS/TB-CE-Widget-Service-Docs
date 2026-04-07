# OtaPackageService

### **OTAPACKAGESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
otaPackageService.getOtaPackages(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(otapackage => {
  console.log('Ota Packages:', otapackage);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
otaPackageService.getOtaPackagesInfoByDeviceProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id', 'your-type', { /* your config */ }).subscribe(otapackagesinfobydeviceprofileid => {
  console.log('Ota Packages Info By Device Profile Id:', otapackagesinfobydeviceprofileid);
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage('your-otapackage-id', { /* your config */ }).subscribe(otapackage => {
  console.log('Ota Package:', otapackage);
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo('your-otapackage-id', { /* your config */ }).subscribe(otapackageinfo => {
  console.log('Ota Package Info:', otapackageinfo);
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage('your-otapackage-id').subscribe(result => {
  console.log('Result:', result);
});
```

**6. saveOtaPackage**

```javascript
otaPackageService.saveOtaPackage({ /* your otaPackage */ }, { /* your config */ }).subscribe(savedOtaPackage => {
  console.log('Saved OtaPackage:', savedOtaPackage);
});
```

**7. saveOtaPackageInfo**

```javascript
otaPackageService.saveOtaPackageInfo({ /* your otaPackageInfo */ }, { /* your config */ }).subscribe(savedOtaPackageInfo => {
  console.log('Saved OtaPackageInfo:', savedOtaPackageInfo);
});
```

**8. uploadOtaPackageFile**

```javascript
otaPackageService.uploadOtaPackageFile('your-otapackage-id', { /* your file */ }, { /* your checksumAlgorithm */ }, 'your-checksum', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage('your-type', 'your-entity-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. confirmDialogUpdatePackage**

```javascript
otaPackageService.confirmDialogUpdatePackage({ /* your entity */ }, { /* your originEntity */ }).subscribe(result => {
  console.log('Result:', result);
});
```
