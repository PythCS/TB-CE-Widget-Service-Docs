# OtaPackageService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('OtaPackageService'));
```

**1. getOtaPackages**

```javascript
otaPackageService.getOtaPackages(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Ota Packages result:', result);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
otaPackageService.getOtaPackagesInfoByDeviceProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id', 'your-type-value').subscribe(device => {
  console.log('Fetched  Ota Packages Info By Device Profile Id device:', device);
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage('your-otapackage-id').subscribe(result => {
  console.log('Fetched  Ota Package result:', result);
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo('your-otapackage-id').subscribe(info => {
  console.log('Fetched  Ota Package Info info:', info);
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage('your-otapackage-id').subscribe(result => {
  console.log('download Ota Package result:', result);
});
```

**6. saveOtaPackage**

```javascript
otaPackageService.saveOtaPackage('your-otapackage-value').subscribe(result => {
  console.log('Saved  Ota Package result:', result);
});
```

**7. saveOtaPackageInfo**

```javascript
otaPackageService.saveOtaPackageInfo('your-otapackageinfo-value').subscribe(info => {
  console.log('Saved  Ota Package Info info:', info);
});
```

**8. uploadOtaPackageFile**

```javascript
otaPackageService.uploadOtaPackageFile('your-otapackage-id', 'your-file-value', 'your-checksumalgorithm-value', 'your-checksum-value').subscribe(result => {
  console.log('upload Ota Package File result:', result);
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage('your-type-value', 'your-entity-id').subscribe(device => {
  console.log('count Update Device After Change Package device:', device);
});
```

**10. confirmDialogUpdatePackage**

```javascript
otaPackageService.confirmDialogUpdatePackage('your-entity-value', 'your-originentity-value').subscribe(result => {
  console.log('confirm Dialog Update Package result:', result);
});
```
