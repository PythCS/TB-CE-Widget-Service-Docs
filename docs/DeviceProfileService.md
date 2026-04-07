# DeviceProfileService

### **DEVICEPROFILESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
deviceProfileService.getDeviceProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(deviceprofile => {
  console.log('Device Profiles:', deviceprofile);
});
```

**2. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds(['id1', 'id2'], { /* your config */ }).subscribe(deviceprofilebyid => {
  console.log('Device Profiles By Ids:', deviceprofilebyid);
});
```

**3. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile('your-deviceprofile-id', { /* your config */ }).subscribe(deviceprofile => {
  console.log('Device Profile:', deviceprofile);
});
```

**4. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile('your-deviceprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects({ /* your sortOrder */ }, ['id1', 'id2'], 'your-searchText', { /* your config */ }).subscribe(lwm2mobject => {
  console.log('Lwm2m Objects:', lwm2mobject);
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true, { /* your config */ }).subscribe(lwm2mbootstrapsecurityinfo => {
  console.log('Lwm2m Bootstrap Security Info:', lwm2mbootstrapsecurityinfo);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true, { /* your config */ }).subscribe(lwm2mbootstrapsecurityinfobysecuritytype => {
  console.log('Lwm2m Bootstrap Security Info By Security Type:', lwm2mbootstrapsecurityinfobysecuritytype);
});
```

**8. getLwm2mObjectsPage**

```javascript
deviceProfileService.getLwm2mObjectsPage(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(lwm2mobjectspage => {
  console.log('Lwm2m Objects Page:', lwm2mobjectspage);
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceProfileService.saveDeviceProfileAndConfirmOtaChange({ /* your originDeviceProfile */ }, { /* your deviceProfile */ }, { /* your config */ }).subscribe(savedDeviceProfileAndConfirmOtaChange => {
  console.log('Saved DeviceProfileAndConfirmOtaChange:', savedDeviceProfileAndConfirmOtaChange);
});
```

**10. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(savedDeviceProfile => {
  console.log('Saved DeviceProfile:', savedDeviceProfile);
});
```

**11. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile('your-deviceprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo({ /* your config */ }).subscribe(defaultdeviceprofileinfo => {
  console.log('Default Device Profile Info:', defaultdeviceprofileinfo);
});
```

**13. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo('your-deviceprofile-id', { /* your config */ }).subscribe(deviceprofileinfo => {
  console.log('Device Profile Info:', deviceprofileinfo);
});
```

**14. getDeviceProfileInfos**

```javascript
deviceProfileService.getDeviceProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-transporttype', { /* your config */ }).subscribe(deviceprofileinfo => {
  console.log('Device Profile Infos:', deviceprofileinfo);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys('your-deviceprofile-id', { /* your config */ }).subscribe(deviceprofiledeviceattributekey => {
  console.log('Device Profile Devices Attributes Keys:', deviceprofiledeviceattributekey);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys('your-deviceprofile-id', { /* your config */ }).subscribe(deviceprofiledevicetimeeriekey => {
  console.log('Device Profile Devices Timeseries Keys:', deviceprofiledevicetimeeriekey);
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames({ /* your activeOnly */ }, { /* your config */ }).subscribe(deviceprofilename => {
  console.log('Device Profile Names:', deviceprofilename);
});
```
