# DEVICE PROFILE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **DEVICE PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfiles(pageLink).subscribe(deviceprofiles => {
  console.log('Get Device Profiles: deviceprofiles');
});
```

**2. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds('your-id').subscribe(deviceprofilesbyids => {
  console.log('Get Device Profiles By Ids: deviceprofilesbyids');
});
```

**3. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile('your-device-profile-id').subscribe(deviceProfile => {
  console.log('Get Device Profile: deviceProfile');
});
```

**4. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile('your-device-profile-id').subscribe(exported => {
  console.log('Export Device Profile: exported');
});
```

**5. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects('ASC', 'your-id', 'searchText').subscribe(lwm2mobjects => {
  console.log('Get Lwm m Objects: lwm2mobjects');
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true).subscribe(lwm2mBootstrapSecurityInfo => {
  console.log('Get Lwm m Bootstrap Security Info:lwm2mBootstrapSecurityInfo');
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true).subscribe(lwm2mBootstrapSecurityInfoBySecurityType => {
  console.log('Get Lwm m Bootstrap Security Info By Security Type:lwm2mBootstrapSecurityInfoBySecurityType');
});
```

**8. getLwm2mObjectsPage**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(lwm2mObjectsPage => {
  console.log('Get Lwm m Objects Page: lwm2mObjectsPage');
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
const originDeviceProfile = originEntity;
const deviceProfile = deviceProfile;
deviceProfileService.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(savedDeviceProfileAndConfirmOtaChange => {
  console.log('Save Device Profile And Confirm Ota Change:savedDeviceProfileAndConfirmOtaChange');
});
```

**10. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(savedDeviceProfile => {
  console.log('Save Device Profile: savedDeviceProfile');
});
```

**11. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile('your-device-profile-id').subscribe(result => {
  console.log('Set Default Device Profile: result');
});
```

**12. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(defaultDeviceProfileInfo => {
  console.log('Get Default Device Profile Info:defaultDeviceProfileInfo');
});
```

**13. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo('your-device-profile-id').subscribe(deviceProfileInfo => {
  console.log('Get Device Profile Info: deviceProfileInfo');
});
```

**14. getDeviceProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfileInfos(pageLink, 'type').subscribe(deviceprofileinfos => {
  console.log('Get Device Profile Infos: deviceprofileinfos');
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys('your-device-profile-id').subscribe(deviceprofiledevicesattributeskeys => {
  console.log('Get Device Profile Devices Attributes Keys:deviceprofiledevicesattributeskeys');
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys('your-device-profile-id').subscribe(deviceprofiledevicestimeserieskeys => {
  console.log('Get Device Profile Devices Timeseries Keys:deviceprofiledevicestimeserieskeys');
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames(true).subscribe(deviceprofilenames => {
  console.log('Get Device Profile Names: deviceprofilenames');
});
```
