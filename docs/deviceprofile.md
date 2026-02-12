### **DEVICE PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceprofileservice = $injector.get(self.ctx.servicesMap.get('deviceprofileservice'));

```

**1. getDeviceProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceprofileservice.getDeviceProfiles(pageLink).subscribe(deviceprofiles => {
  console.log('Deviceprofiles:', deviceprofiles);
});
```

**2. getDeviceProfilesByIds**

```javascript
deviceprofileservice.getDeviceProfilesByIds('your-device-id').subscribe(deviceprofilesbyids => {
  console.log('Deviceprofilesbyids:', deviceprofilesbyids);
});
```

**3. getDeviceProfile**

```javascript
deviceprofileservice.getDeviceProfile('your-device-id').subscribe(deviceprofile => {
  console.log('Deviceprofile:', deviceprofile);
});
```

**4. exportDeviceProfile**

```javascript
deviceprofileservice.exportDeviceProfile('your-device-id').subscribe(exportdeviceprofile => {
  console.log('Exportdeviceprofile:', exportdeviceprofile);
});
```

**5. getLwm2mObjects**

```javascript
deviceprofileservice.getLwm2mObjects(sortOrder, 'your-objects-id', 'your-searchtext').subscribe(lwm2mobjects => {
  console.log('Lwm2mobjects:', lwm2mobjects);
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceprofileservice.getLwm2mBootstrapSecurityInfo(true).subscribe(lwm2mbootstrapsecurityinfo => {
  console.log('Lwm2mbootstrapsecurityinfo:', lwm2mbootstrapsecurityinfo);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceprofileservice.getLwm2mBootstrapSecurityInfoBySecurityType(true).subscribe(lwm2mbootstrapsecurityinfobysecuritytype => {
  console.log('Lwm2mbootstrapsecurityinfobysecuritytype:', lwm2mbootstrapsecurityinfobysecuritytype);
});
```

**8. getLwm2mObjectsPage**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceprofileservice.getLwm2mObjectsPage(pageLink).subscribe(lwm2mobjectspage => {
  console.log('Lwm2mobjectspage:', lwm2mobjectspage);
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceprofileservice.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(savedeviceprofileandconfirmotachange => {
  console.log('Savedeviceprofileandconfirmotachange:', savedeviceprofileandconfirmotachange);
});
```

**10. saveDeviceProfile**

```javascript
deviceprofileservice.saveDeviceProfile().subscribe(savedeviceprofile => {
  console.log('Savedeviceprofile:', savedeviceprofile);
});
```

**11. setDefaultDeviceProfile**

```javascript
deviceprofileservice.setDefaultDeviceProfile('your-device-id').subscribe(setdefaultdeviceprofile => {
  console.log('Setdefaultdeviceprofile:', setdefaultdeviceprofile);
});
```

**12. getDefaultDeviceProfileInfo**

```javascript
deviceprofileservice.getDefaultDeviceProfileInfo().subscribe(defaultdeviceprofileinfo => {
  console.log('Defaultdeviceprofileinfo:', defaultdeviceprofileinfo);
});
```

**13. getDeviceProfileInfo**

```javascript
deviceprofileservice.getDeviceProfileInfo('your-device-id').subscribe(deviceprofileinfo => {
  console.log('Deviceprofileinfo:', deviceprofileinfo);
});
```

**14. getDeviceProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceprofileservice.getDeviceProfileInfos(pageLink).subscribe(deviceprofileinfos => {
  console.log('Deviceprofileinfos:', deviceprofileinfos);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceprofileservice.getDeviceProfileDevicesAttributesKeys('your-device-id').subscribe(deviceprofiledevicesattributeskeys => {
  console.log('Deviceprofiledevicesattributeskeys:', deviceprofiledevicesattributeskeys);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceprofileservice.getDeviceProfileDevicesTimeseriesKeys('your-device-id').subscribe(deviceprofiledevicestimeserieskeys => {
  console.log('Deviceprofiledevicestimeserieskeys:', deviceprofiledevicestimeserieskeys);
});
```

**17. getDeviceProfileNames**

```javascript
deviceprofileservice.getDeviceProfileNames(true).subscribe(deviceprofilenames => {
  console.log('Deviceprofilenames:', deviceprofilenames);
});
```

