# Device Profile

```javascript
// Service name: deviceProfile
// File: device-profile.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfile = $injector.get(self.ctx.servicesMap.get('deviceProfile'));
```

### **1. getDeviceProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfile.getDeviceProfiles(pageLink).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **2. getDeviceProfilesByIds**

```javascript
deviceProfile.getDeviceProfilesByIds(deviceProfileIds).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **3. getDeviceProfile**

```javascript
deviceProfile.getDeviceProfile(deviceProfileId).subscribe(device => {
  console.log('Device:', device);
});
```

### **4. exportDeviceProfile**

```javascript
deviceProfile.exportDeviceProfile(deviceProfileId).subscribe(device => {
  console.log('Device:', device);
});
```

### **5. getLwm2mObjects**

```javascript
deviceProfile.getLwm2mObjects(sortOrder).subscribe(lwm2mObjects => {
  console.log('Lwm2m Objects:', lwm2mObjects);
});
```

### **6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfile.getLwm2mBootstrapSecurityInfo(isBootstrapServer).subscribe(lwm2mBootstrapSecurity => {
  console.log('Lwm2m Bootstrap Security:', lwm2mBootstrapSecurity);
});
```

### **7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfile.getLwm2mBootstrapSecurityInfoBySecurityType(isBootstrapServer).subscribe(lwm2mBootstrapSecurityInfoBySecurityType => {
  console.log('Lwm2m Bootstrap Security Info By Security Type:', lwm2mBootstrapSecurityInfoBySecurityType);
});
```

### **8. getLwm2mObjectsPage**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfile.getLwm2mObjectsPage(pageLink).subscribe(lwm2mObjectsPages => {
  console.log('Lwm2m Objects Pages:', lwm2mObjectsPages);
});
```

### **9. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceProfile.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(device => {
  console.log('Device:', device);
});
```

### **10. saveDeviceProfile**

```javascript
deviceProfile.saveDeviceProfile().subscribe(device => {
  console.log('Device:', device);
});
```

### **11. setDefaultDeviceProfile**

```javascript
deviceProfile.setDefaultDeviceProfile(deviceProfileId).subscribe(device => {
  console.log('Device:', device);
});
```

### **12. getDefaultDeviceProfileInfo**

```javascript
deviceProfile.getDefaultDeviceProfileInfo().subscribe(device => {
  console.log('Device:', device);
});
```

### **13. getDeviceProfileInfo**

```javascript
deviceProfile.getDeviceProfileInfo(deviceProfileId).subscribe(device => {
  console.log('Device:', device);
});
```

### **14. getDeviceProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfile.getDeviceProfileInfos(pageLink).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfile.getDeviceProfileDevicesAttributesKeys().subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfile.getDeviceProfileDevicesTimeseriesKeys().subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **17. getDeviceProfileNames**

```javascript
deviceProfile.getDeviceProfileNames(activeOnly).subscribe(devices => {
  console.log('Devices:', devices);
});
```
