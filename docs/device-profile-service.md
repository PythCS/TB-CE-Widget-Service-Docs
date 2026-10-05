# DEVICE PROFILE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfiles(pageLink).subscribe(deviceProfiles => {
  console.log('List of Device Profiles:', deviceProfiles);
});
```

**2. getDeviceProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfile(deviceProfileId).subscribe(deviceProfile => {
  console.log('Get Device Profile:', deviceProfile);
});
```

**3. exportDeviceProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.exportDeviceProfile(deviceProfileId).subscribe(exportDeviceProfile => {
  console.log('Export Device Profile:', exportDeviceProfile);
});
```

**4. getLwm2mObjects**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const sortOrder = {  // SortOrder object
  // ... set the fields you need
};
const objectIds = ['your-object-i-1', 'your-object-i-2'];
const searchText = 'searchText';
deviceProfileService.getLwm2mObjects(sortOrder, objectIds, searchText).subscribe(lwm2mObjects => {
  console.log('List of Lwm2m Objects:', lwm2mObjects);
});
```

**5. getLwm2mBootstrapSecurityInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const isBootstrapServer = true;
deviceProfileService.getLwm2mBootstrapSecurityInfo(isBootstrapServer).subscribe(lwm2mBootstrapSecurityInfo => {
  console.log('Get Lwm2m Bootstrap Security Info:', lwm2mBootstrapSecurityInfo);
});
```

**6. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const isBootstrapServer = true;
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(isBootstrapServer).subscribe(lwm2mBootstrapSecurityInfoBySecurityType => {
  console.log('Get Lwm2m Bootstrap Security Info By Security Type:', lwm2mBootstrapSecurityInfoBySecurityType);
});
```

**7. getLwm2mObjectsPage**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(lwm2mObjectsPages => {
  console.log('List of Lwm2m Objects Pages:', lwm2mObjectsPages);
});
```

**8. saveDeviceProfileAndConfirmOtaChange**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const originDeviceProfile = {  // DeviceProfile object
  // ... set the fields you need
};
const deviceProfile = {  // DeviceProfile object
  // ... set the fields you need
};
deviceProfileService.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(savedDeviceProfileAndConfirmOtaChange => {
  console.log('Saved Device Profile And Confirm Ota Change:', savedDeviceProfileAndConfirmOtaChange);
});
```

**9. saveDeviceProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const result = deviceProfileService.saveDeviceProfile();
console.log('Result:', result);
```

**10. setDefaultDeviceProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.setDefaultDeviceProfile(deviceProfileId).subscribe(setDefaultDeviceProfile => {
  console.log('Set Default Device Profile:', setDefaultDeviceProfile);
});
```

**11. getDefaultDeviceProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(defaultDeviceProfileInfo => {
  console.log('Get Default Device Profile Info:', defaultDeviceProfileInfo);
});
```

**12. getDeviceProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileInfo(deviceProfileId).subscribe(deviceProfileInfo => {
  console.log('Get Device Profile Info:', deviceProfileInfo);
});
```

**13. getDeviceProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const transportType = {  // DeviceTransportType object
  // ... set the fields you need
};
deviceProfileService.getDeviceProfileInfos(pageLink, transportType).subscribe(deviceProfileInfos => {
  console.log('List of Device Profile Infos:', deviceProfileInfos);
});
```

**14. getDeviceProfilesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileIds = ['your-device-profile-i-1', 'your-device-profile-i-2'];
deviceProfileService.getDeviceProfilesByIds(deviceProfileIds).subscribe(deviceProfilesBys => {
  console.log('List of Device Profiles By Ids:', deviceProfilesBys);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileDevicesAttributesKeys(deviceProfileId).subscribe(deviceProfileDevicesAttributesKeys => {
  console.log('List of Device Profile Devices Attributes Keys:', deviceProfileDevicesAttributesKeys);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys(deviceProfileId).subscribe(deviceProfileDevicesTimeseriesKeys => {
  console.log('List of Device Profile Devices Timeseries Keys:', deviceProfileDevicesTimeseriesKeys);
});
```

**17. getDeviceProfileNames**

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
const activeOnly = 'value';
deviceProfileService.getDeviceProfileNames(activeOnly).subscribe(deviceProfileNames => {
  console.log('List of Device Profile Names:', deviceProfileNames);
});
```
