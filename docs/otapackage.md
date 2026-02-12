### **OTA PACKAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otapackageservice = $injector.get(self.ctx.servicesMap.get('otapackageservice'));

```

**1. getOtaPackages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otapackageservice.getOtaPackages(pageLink).subscribe(otapackages => {
  console.log('Otapackages:', otapackages);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otapackageservice.getOtaPackagesInfoByDeviceProfileId(pageLink, 'your-device-id', type).subscribe(otapackagesinfobydeviceprofileid => {
  console.log('Otapackagesinfobydeviceprofileid:', otapackagesinfobydeviceprofileid);
});
```

**3. getOtaPackage**

```javascript
otapackageservice.getOtaPackage('your-otapackage-id').subscribe(otapackage => {
  console.log('Otapackage:', otapackage);
});
```

**4. getOtaPackageInfo**

```javascript
otapackageservice.getOtaPackageInfo('your-otapackage-id').subscribe(otapackageinfo => {
  console.log('Otapackageinfo:', otapackageinfo);
});
```

**5. downloadOtaPackage**

```javascript
otapackageservice.downloadOtaPackage('your-otapackage-id').subscribe(downotapackage => {
  console.log('Downotapackage:', downotapackage);
});
```

**6. saveOtaPackage**

```javascript
otapackageservice.saveOtaPackage(otaPackage).subscribe(saveotapackage => {
  console.log('Saveotapackage:', saveotapackage);
});
```

**7. saveOtaPackageInfo**

```javascript
otapackageservice.saveOtaPackageInfo(otaPackageInfo).subscribe(saveotapackageinfo => {
  console.log('Saveotapackageinfo:', saveotapackageinfo);
});
```

**8. uploadOtaPackageFile**

```javascript
otapackageservice.uploadOtaPackageFile('your-otapackage-id', file, checksumAlgorithm, 'your-checksum').subscribe(upotapackagefile => {
  console.log('Upotapackagefile:', upotapackagefile);
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
otapackageservice.countUpdateDeviceAfterChangePackage(type, 'your-entity-id').subscribe(countupdatedeviceafterchangepackage => {
  console.log('Countupdatedeviceafterchangepackage:', countupdatedeviceafterchangepackage);
});
```

**10. confirmDialogUpdatePackage**

```javascript
otapackageservice.confirmDialogUpdatePackage(entity, originEntity).subscribe(confirmdialogupdatepackage => {
  console.log('Confirmdialogupdatepackage:', confirmdialogupdatepackage);
});
```

