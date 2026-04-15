# Ota Package

```javascript
// Service name: otaPackage
// File: ota-package.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackage = $injector.get(self.ctx.servicesMap.get('otaPackage'));
```

### **1. getOtaPackages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackage.getOtaPackages(pageLink).subscribe(otaPackages => {
  console.log('Ota Packages:', otaPackages);
});
```

### **2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackage.getOtaPackagesInfoByDeviceProfileId(pageLink).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **3. getOtaPackage**

```javascript
otaPackage.getOtaPackage(otaPackageId).subscribe(otaPackage => {
  console.log('Ota Package:', otaPackage);
});
```

### **4. getOtaPackageInfo**

```javascript
otaPackage.getOtaPackageInfo(otaPackageId).subscribe(otaPackage => {
  console.log('Ota Package:', otaPackage);
});
```

### **5. downloadOtaPackage**

```javascript
otaPackage.downloadOtaPackage(otaPackageId).subscribe(otaPackage => {
  console.log('Ota Package:', otaPackage);
});
```

### **6. saveOtaPackage**

```javascript
otaPackage.saveOtaPackage(otaPackage).subscribe(otaPackage => {
  console.log('Ota Package:', otaPackage);
});
```

### **7. saveOtaPackageInfo**

```javascript
otaPackage.saveOtaPackageInfo(otaPackageInfo).subscribe(otaPackage => {
  console.log('Ota Package:', otaPackage);
});
```

### **8. uploadOtaPackageFile**

```javascript
otaPackage.uploadOtaPackageFile(otaPackageId, file, checksumAlgorithm).subscribe(otaPackage => {
  console.log('Ota Package:', otaPackage);
});
```

### **9. countUpdateDeviceAfterChangePackage**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
otaPackage.countUpdateDeviceAfterChangePackage(entityId).subscribe(device => {
  console.log('Device:', device);
});
```

### **10. confirmDialogUpdatePackage**

```javascript
otaPackage.confirmDialogUpdatePackage(entity, originEntity).subscribe(confirmDialogUpdatePackage => {
  console.log('Confirm Dialog Update Package:', confirmDialogUpdatePackage);
});
```
