# OTA PACKAGE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackages(pageLink).subscribe(otaPackages => {
  console.log('Get Ota Packages:', otaPackages);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, 'your-deviceprofile-id', 'your-type-value').subscribe(otaPackagesInfoByDeviceProfileId => {
  console.log('Get Ota Packages Info By Device Profile Id:', otaPackagesInfoByDeviceProfileId);
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage('your-otapackage-id').subscribe(otaPackage => {
  console.log('Get Ota Package:', otaPackage);
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo('your-otapackage-id').subscribe(otaPackageInfo => {
  console.log('Get Ota Package Info:', otaPackageInfo);
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage('your-otapackage-id').subscribe(downloadOtaPackage => {
  console.log('Download Ota Package:', downloadOtaPackage);
});
```

**6. saveOtaPackage**

```javascript
otaPackageService.saveOtaPackage('your-otapackage-value').subscribe(otaPackage => {
  console.log('Save Ota Package:', otaPackage);
});
```

**7. saveOtaPackageInfo**

```javascript
otaPackageService.saveOtaPackageInfo('your-otapackageinfo-value').subscribe(otaPackageInfo => {
  console.log('Save Ota Package Info:', otaPackageInfo);
});
```

**8. uploadOtaPackageFile**

```javascript
otaPackageService.uploadOtaPackageFile('your-otapackage-id', 'your-file-value', 'your-checksumalgorithm-value', 'your-checksum-value').subscribe(uploadOtaPackageFile => {
  console.log('Upload Ota Package File:', uploadOtaPackageFile);
});
```

**9. getOtaPackageInfoByDeviceGroupId**

```javascript
otaPackageService.getOtaPackageInfoByDeviceGroupId('your-devicegroup-id', 'your-type-value').subscribe(otaPackageInfoByDeviceGroupId => {
  console.log('Get Ota Package Info By Device Group Id:', otaPackageInfoByDeviceGroupId);
});
```

**10. getOtaPackagesInfoByDeviceGroupId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackagesInfoByDeviceGroupId(pageLink, 'your-devicegroup-id', 'your-type-value').subscribe(otaPackagesInfoByDeviceGroupId => {
  console.log('Get Ota Packages Info By Device Group Id:', otaPackagesInfoByDeviceGroupId);
});
```

**11. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage('your-type-value', 'your-entity-id', 'your-package-id').subscribe(countUpdateDeviceAfterChangePackage => {
  console.log('Count Update Device After Change Package:', countUpdateDeviceAfterChangePackage);
});
```

**12. confirmDialogUpdatePackage**

```javascript
otaPackageService.confirmDialogUpdatePackage('your-entity-value', 'your-originentity-value').subscribe(confirmDialogUpdatePackage => {
  console.log('Confirm Dialog Update Package:', confirmDialogUpdatePackage);
});
```
