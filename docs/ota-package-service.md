# OTA PACKAGE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackages(pageLink).subscribe(otaPackages => {
  console.log('List of Ota Packages:', otaPackages);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'your-device-profile-id';
const type = {  // OtaUpdateType object
  // ... set the fields you need
};
otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, deviceProfileId, type).subscribe(otaPackagesInfoByDeviceProfiles => {
  console.log('List of Ota Packages Info By Device Profile Ids:', otaPackagesInfoByDeviceProfiles);
});
```

**3. getOtaPackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageId = 'your-ota-package-id';
otaPackageService.getOtaPackage(otaPackageId).subscribe(otaPackage => {
  console.log('Get Ota Package:', otaPackage);
});
```

**4. getOtaPackageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageId = 'your-ota-package-id';
otaPackageService.getOtaPackageInfo(otaPackageId).subscribe(otaPackageInfo => {
  console.log('Get Ota Package Info:', otaPackageInfo);
});
```

**5. downloadOtaPackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageId = 'your-ota-package-id';
otaPackageService.downloadOtaPackage(otaPackageId).subscribe(downloadOtaPackage => {
  console.log('Download Ota Package:', downloadOtaPackage);
});
```

**6. saveOtaPackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackage = {  // OtaPackage object
  // ... set the fields you need
};
otaPackageService.saveOtaPackage(otaPackage).subscribe(savedOtaPackage => {
  console.log('Saved Ota Package:', savedOtaPackage);
});
```

**7. saveOtaPackageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageInfo = {  // OtaPackageInfo object
  // ... set the fields you need
};
otaPackageService.saveOtaPackageInfo(otaPackageInfo).subscribe(savedOtaPackageInfo => {
  console.log('Saved Ota Package Info:', savedOtaPackageInfo);
});
```

**8. uploadOtaPackageFile**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const otaPackageId = 'your-ota-package-id';
const file = {  // File object
  // ... set the fields you need
};
const checksumAlgorithm = {  // ChecksumAlgorithm object
  // ... set the fields you need
};
const checksum = 'your-checksum';
otaPackageService.uploadOtaPackageFile(otaPackageId, file, checksumAlgorithm, checksum).subscribe(savedOtaPackageFile => {
  console.log('Saved Ota Package File:', savedOtaPackageFile);
});
```

**9. getOtaPackageInfoByDeviceGroupId**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const deviceGroupId = 'your-device-group-id';
const type = {  // OtaUpdateType object
  // ... set the fields you need
};
otaPackageService.getOtaPackageInfoByDeviceGroupId(deviceGroupId, type).subscribe(otaPackageInfoByDeviceGroup => {
  console.log('Get Ota Package Info By Device Group Id:', otaPackageInfoByDeviceGroup);
});
```

**10. getOtaPackagesInfoByDeviceGroupId**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceGroupId = 'your-device-group-id';
const type = {  // OtaUpdateType object
  // ... set the fields you need
};
otaPackageService.getOtaPackagesInfoByDeviceGroupId(pageLink, deviceGroupId, type).subscribe(otaPackagesInfoByDeviceGroups => {
  console.log('List of Ota Packages Info By Device Group Ids:', otaPackagesInfoByDeviceGroups);
});
```

**11. countUpdateDeviceAfterChangePackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const type = {  // OtaUpdateType object
  // ... set the fields you need
};
const entityId = {  // EntityId object
  // ... set the fields you need
};
const packageId = 'your-package-id';
otaPackageService.countUpdateDeviceAfterChangePackage(type, entityId, packageId).subscribe(countUpdateDeviceAfterChangePackage => {
  console.log('Count Update Device After Change Package:', countUpdateDeviceAfterChangePackage);
});
```

**12. confirmDialogUpdatePackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
const entity = {  // BaseData<EntityId>&OtaPagesIds object
  // ... set the fields you need
};
const originEntity = {  // BaseData<EntityId>&OtaPagesIds object
  // ... set the fields you need
};
otaPackageService.confirmDialogUpdatePackage(entity, originEntity).subscribe(confirmDialogUpdatePackage => {
  console.log('Confirm Dialog Update Package:', confirmDialogUpdatePackage);
});
```
