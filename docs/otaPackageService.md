# OTA PACKAGE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **OTA PACKAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackages(pageLink).subscribe(otapackages => {
  console.log('Get Ota Packages: otapackages');
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, 'your-device-profile-id', 'type').subscribe(otaPackagesInfoByDeviceProfileId => {
  console.log('Get Ota Packages Info By Device Profile Id:otaPackagesInfoByDeviceProfileId');
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage('your-ota-package-id').subscribe(otaPackage => {
  console.log('Get Ota Package: otaPackage');
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo('your-ota-package-id').subscribe(otaPackageInfo => {
  console.log('Get Ota Package Info: otaPackageInfo');
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage('your-ota-package-id').subscribe(result => {
  console.log('Download Ota Package: result');
});
```

**6. saveOtaPackage**

```javascript
const otaPackage = otaPackage;
otaPackageService.saveOtaPackage(otaPackage).subscribe(savedOtaPackage => {
  console.log('Save Ota Package: savedOtaPackage');
});
```

**7. saveOtaPackageInfo**

```javascript
const otaPackageInfo = otaPackageInfo;
otaPackageService.saveOtaPackageInfo(otaPackageInfo).subscribe(savedOtaPackageInfo => {
  console.log('Save Ota Package Info: savedOtaPackageInfo');
});
```

**8. uploadOtaPackageFile**

```javascript
const file = file;
otaPackageService.uploadOtaPackageFile('your-ota-package-id', file, 'SHA256', 'checksum').subscribe(result => {
  console.log('Upload Ota Package File: result');
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage('type', 'your-entity-id').subscribe(count => {
  console.log('Count Update Device After Change Package:count');
});
```

**10. confirmDialogUpdatePackage**

```javascript
const entity = entity;
const originEntity = originEntity;
otaPackageService.confirmDialogUpdatePackage(entity, originEntity).subscribe(result => {
  console.log('Confirm Dialog Update Package: result');
});
```
