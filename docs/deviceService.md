# DEVICE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
self.ctx.deviceService.getDeviceInfosByQuery('your-deviceinfoquery-value').subscribe(deviceInfosByQuery => {
  console.log('Get Device Infos By Query:', deviceInfosByQuery);
});
```

**2. getTenantDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getTenantDevices(pageLink, 'your-type-value').subscribe(tenantDevices => {
  console.log('Get Tenant Devices:', tenantDevices);
});
```

**3. getCustomerDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getCustomerDevices('your-customer-id', pageLink, 'your-type-value').subscribe(customerDevices => {
  console.log('Get Customer Devices:', customerDevices);
});
```

**4. getDevice**

```javascript
self.ctx.deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Get Device:', device);
});
```

**5. getDevices**

```javascript
self.ctx.deviceService.getDevices('your-deviceids-value').subscribe(devices => {
  console.log('Get Devices:', devices);
});
```

**6. getUserDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getUserDevices(pageLink, 'your-type-value').subscribe(userDevices => {
  console.log('Get User Devices:', userDevices);
});
```

**7. getAllDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getAllDeviceInfos(true, pageLink, 'your-deviceprofile-id').subscribe(allDeviceInfos => {
  console.log('Get All Device Infos:', allDeviceInfos);
});
```

**8. getCustomerDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getCustomerDeviceInfos(true, 'your-customer-id', pageLink, 'your-deviceprofile-id').subscribe(customerDeviceInfos => {
  console.log('Get Customer Device Infos:', customerDeviceInfos);
});
```

**9. getDeviceInfo**

```javascript
self.ctx.deviceService.getDeviceInfo('your-device-id').subscribe(deviceInfo => {
  console.log('Get Device Info:', deviceInfo);
});
```

**10. saveDevice**

```javascript
self.ctx.deviceService.saveDevice('your-device-value', 'your-entitygroupids-value').subscribe(device => {
  console.log('Save Device:', device);
});
```

**11. saveDeviceWithCredentials**

```javascript
self.ctx.deviceService.saveDeviceWithCredentials('your-device-value', 'your-credentials-value', 'your-entitygroupids-value').subscribe(deviceWithCredentials => {
  console.log('Save Device With Credentials:', deviceWithCredentials);
});
```

**12. getDeviceTypes**

```javascript
self.ctx.deviceService.getDeviceTypes().subscribe(deviceTypes => {
  console.log('Get Device Types:', deviceTypes);
});
```

**13. getDeviceCredentials**

```javascript
self.ctx.deviceService.getDeviceCredentials('your-device-id', true).subscribe(deviceCredentials => {
  console.log('Get Device Credentials:', deviceCredentials);
});
```
