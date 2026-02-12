# DEVICE PROFILE

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

## Methods

### getDeviceProfiles

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

deviceProfileService.getDeviceProfiles(pageLink).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### getDeviceProfilesByIds

```javascript
const deviceProfileIds = 'your-deviceprofiles-id';

deviceProfileService.getDeviceProfilesByIds(deviceProfileIds).subscribe(device => {
  console.log('Device:', device);
});
```

### getDeviceProfile

```javascript
const deviceProfileId = 'your-deviceprofile-id';

deviceProfileService.getDeviceProfile(deviceProfileId).subscribe(device => {
  console.log('Device:', device);
});
```

### exportDeviceProfile

```javascript
const deviceProfileId = 'your-deviceprofile-id';

deviceProfileService.exportDeviceProfile(deviceProfileId).subscribe(device => {
  console.log('Device:', device);
});
```

### getLwm2mObjects

```javascript
const sortOrder = {
  // your sortOrder object
};
const objectIds = 'your-objects-id';
const searchText = 'your-searchtext';

deviceProfileService.getLwm2mObjects(sortOrder, objectIds, searchText).subscribe(result => {
  console.log('Lwm2mObjects:', result);
});
```

### getLwm2mBootstrapSecurityInfo

```javascript
const isBootstrapServer = true;

deviceProfileService.getLwm2mBootstrapSecurityInfo(isBootstrapServer).subscribe(info => {
  console.log('Info:', info);
});
```

### getLwm2mBootstrapSecurityInfoBySecurityType

```javascript
const isBootstrapServer = true;

deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(isBootstrapServer).subscribe(result => {
  console.log('Lwm2mBootstrapSecurityInfoBySecurityType:', result);
});
```

### getLwm2mObjectsPage

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(result => {
  console.log('Lwm2mObjectsPage:', result);
});
```

### saveDeviceProfileAndConfirmOtaChange

```javascript
const originDeviceProfile = {
  // your originDeviceProfile object
};
const deviceProfile = {
  // your deviceProfile object
};

deviceProfileService.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(device => {
  console.log('Device:', device);
});
```

### saveDeviceProfile

```javascript
deviceProfileService.saveDeviceProfile().subscribe(device => {
  console.log('Device:', device);
});
```

### setDefaultDeviceProfile

```javascript
const deviceProfileId = 'your-deviceprofile-id';

deviceProfileService.setDefaultDeviceProfile(deviceProfileId).subscribe(device => {
  console.log('Device:', device);
});
```

### getDefaultDeviceProfileInfo

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(device => {
  console.log('Device:', device);
});
```

### getDeviceProfileInfo

```javascript
const deviceProfileId = 'your-deviceprofile-id';

deviceProfileService.getDeviceProfileInfo(deviceProfileId).subscribe(device => {
  console.log('Device:', device);
});
```

### getDeviceProfileInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const transportType = {
  // your transportType object
};

deviceProfileService.getDeviceProfileInfos(pageLink, transportType).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### getDeviceProfileDevicesAttributesKeys

```javascript
const deviceProfileId = 'your-deviceprofile-id';

deviceProfileService.getDeviceProfileDevicesAttributesKeys(deviceProfileId).subscribe(result => {
  console.log('Result:', result);
});
```

### getDeviceProfileDevicesTimeseriesKeys

```javascript
const deviceProfileId = 'your-deviceprofile-id';

deviceProfileService.getDeviceProfileDevicesTimeseriesKeys(deviceProfileId).subscribe(result => {
  console.log('Result:', result);
});
```

### getDeviceProfileNames

```javascript
const activeOnly = {
  // your activeOnly object
};

deviceProfileService.getDeviceProfileNames(activeOnly).subscribe(info => {
  console.log('Info:', info);
});
```

