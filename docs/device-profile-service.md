# DEVICE PROFILE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfiles(pageLink).subscribe(deviceProfiles => {
  console.log('Get Device Profiles:', deviceProfiles);
});
```

**2. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile('your-deviceprofile-id').subscribe(deviceProfile => {
  console.log('Get Device Profile:', deviceProfile);
});
```

**3. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile('your-deviceprofile-id').subscribe(deviceProfile => {
  console.log('Export Device Profile:', deviceProfile);
});
```

**4. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects('your-sortorder-value', 'your-objectids-value', 'your-searchtext-value').subscribe(lwm2mObjects => {
  console.log('Get Lwm 2 m Objects:', lwm2mObjects);
});
```

**5. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true).subscribe(lwm2mBootstrapSecurityInfo => {
  console.log('Get Lwm 2 m Bootstrap Security Info:', lwm2mBootstrapSecurityInfo);
});
```

**6. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true).subscribe(lwm2mBootstrapSecurityInfoBySecurityType => {
  console.log('Get Lwm 2 m Bootstrap Security Info By Security Type:', lwm2mBootstrapSecurityInfoBySecurityType);
});
```

**7. getLwm2mObjectsPage**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(lwm2mObjectsPage => {
  console.log('Get Lwm 2 m Objects Page:', lwm2mObjectsPage);
});
```

**8. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceProfileService.saveDeviceProfileAndConfirmOtaChange('your-origindeviceprofile-value', 'your-deviceprofile-value').subscribe(deviceProfileAndConfirmOtaChange => {
  console.log('Save Device Profile And Confirm Ota Change:', deviceProfileAndConfirmOtaChange);
});
```

**9. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(deviceProfile => {
  console.log('Save Device Profile:', deviceProfile);
});
```

**10. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile('your-deviceprofile-id').subscribe(defaultDeviceProfile => {
  console.log('Set Default Device Profile:', defaultDeviceProfile);
});
```

**11. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(defaultDeviceProfileInfo => {
  console.log('Get Default Device Profile Info:', defaultDeviceProfileInfo);
});
```

**12. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo('your-deviceprofile-id').subscribe(info => {
  console.log('Get Device Profile Info:', info);
});
```

**13. getDeviceProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfileInfos(pageLink, 'your-transporttype-value').subscribe(deviceProfileInfos => {
  console.log('Get Device Profile Infos:', deviceProfileInfos);
});
```

**14. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds('your-deviceprofileids-value').subscribe(deviceProfilesByIds => {
  console.log('Get Device Profiles By Ids:', deviceProfilesByIds);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys('your-deviceprofile-id').subscribe(deviceProfileDevicesAttributesKeys => {
  console.log('Get Device Profile Devices Attributes Keys:', deviceProfileDevicesAttributesKeys);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys('your-deviceprofile-id').subscribe(deviceProfileDevicesTimeseriesKeys => {
  console.log('Get Device Profile Devices Timeseries Keys:', deviceProfileDevicesTimeseriesKeys);
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames('your-activeonly-value').subscribe(deviceProfileNames => {
  console.log('Get Device Profile Names:', deviceProfileNames);
});
```
