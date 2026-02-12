# OTA PACKAGE

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

## Methods

### getOtaPackages

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

otaPackageService.getOtaPackages(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

### getOtaPackagesInfoByDeviceProfileId

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'your-deviceprofile-id';
const type = {
  // your type object
};

otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, deviceProfileId, type).subscribe(info => {
  console.log('Info:', info);
});
```

### getOtaPackage

```javascript
const otaPackageId = 'your-otapackage-id';

otaPackageService.getOtaPackage(otaPackageId).subscribe(result => {
  console.log('OtaPackage:', result);
});
```

### getOtaPackageInfo

```javascript
const otaPackageId = 'your-otapackage-id';

otaPackageService.getOtaPackageInfo(otaPackageId).subscribe(info => {
  console.log('Info:', info);
});
```

### downloadOtaPackage

```javascript
const otaPackageId = 'your-otapackage-id';

otaPackageService.downloadOtaPackage(otaPackageId).subscribe(result => {
  console.log('downloadOtaPackage:', result);
});
```

### saveOtaPackage

```javascript
const otaPackage = {
  // your otaPackage object
};

otaPackageService.saveOtaPackage(otaPackage).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### saveOtaPackageInfo

```javascript
const otaPackageInfo = {
  // your otaPackageInfo object
};

otaPackageService.saveOtaPackageInfo(otaPackageInfo).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### uploadOtaPackageFile

```javascript
const otaPackageId = 'your-otapackage-id';
const file = new File(['content'], 'file.txt', { type: 'text/plain' });
const checksumAlgorithm = {
  // your checksumAlgorithm object
};
const checksum = 'your-checksum';

otaPackageService.uploadOtaPackageFile(otaPackageId, file, checksumAlgorithm, checksum).subscribe(result => {
  console.log('uploadOtaPackageFile:', result);
});
```

### countUpdateDeviceAfterChangePackage

```javascript
const type = {
  // your type object
};
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };

otaPackageService.countUpdateDeviceAfterChangePackage(type, entityId).subscribe(count => {
  console.log('Count:', count);
});
```

### confirmDialogUpdatePackage

```javascript
const entity = { entityType: 'DEVICE', id: 'your-entity-id' };
const originEntity = { entityType: 'DEVICE', id: 'your-originentity-id' };

otaPackageService.confirmDialogUpdatePackage(entity, originEntity).subscribe(result => {
  console.log('Result:', result);
});
```

