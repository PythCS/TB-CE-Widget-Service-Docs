# DeviceProfileService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('DeviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
deviceProfileService.getDeviceProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(device => {
  console.log('Fetched  Device Profiles device:', device);
});
```

**2. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds('your-deviceprofileids-value').subscribe(device => {
  console.log('Fetched  Device Profiles By Ids device:', device);
});
```

**3. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile('your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Device Profile device:', device);
});
```

**4. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile('your-deviceprofile-id').subscribe(device => {
  console.log('export Device Profile device:', device);
});
```

**5. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects('your-sortorder-value', 'your-objectids-value', 'your-searchtext-value').subscribe(result => {
  console.log('Fetched  Lwm2m Objects result:', result);
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true).subscribe(info => {
  console.log('Fetched  Lwm2m Bootstrap Security Info info:', info);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true).subscribe(info => {
  console.log('Fetched  Lwm2m Bootstrap Security Info By Security Type info:', info);
});
```

**8. getLwm2mObjectsPage**

```javascript
deviceProfileService.getLwm2mObjectsPage(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Lwm2m Objects Page result:', result);
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceProfileService.saveDeviceProfileAndConfirmOtaChange('your-origindeviceprofile-value', 'your-deviceprofile-value').subscribe(device => {
  console.log('Saved  Device Profile And Confirm Ota Change device:', device);
});
```

**10. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(device => {
  console.log('Saved  Device Profile device:', device);
});
```

**11. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile('your-deviceprofile-id').subscribe(device => {
  console.log('set Default Device Profile device:', device);
});
```

**12. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(device => {
  console.log('Fetched  Default Device Profile Info device:', device);
});
```

**13. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo('your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Device Profile Info device:', device);
});
```

**14. getDeviceProfileInfos**

```javascript
deviceProfileService.getDeviceProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-transporttype-value').subscribe(device => {
  console.log('Fetched  Device Profile Infos device:', device);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys('your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Device Profile Devices Attributes Keys device:', device);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys('your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Device Profile Devices Timeseries Keys device:', device);
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames('your-activeonly-value').subscribe(device => {
  console.log('Fetched  Device Profile Names device:', device);
});
```
