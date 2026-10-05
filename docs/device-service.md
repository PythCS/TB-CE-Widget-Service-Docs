# DEVICE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
const deviceService = self.ctx.deviceService;
const deviceInfoQuery = {  // DeviceInfoQuery object
  // ... set the fields you need
};
deviceService.getDeviceInfosByQuery(deviceInfoQuery).subscribe(deviceInfosByQuerys => {
  console.log('List of Device Infos By Querys:', deviceInfosByQuerys);
});
```

**2. getTenantDevices**

```javascript
const deviceService = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
deviceService.getTenantDevices(pageLink, type).subscribe(tenantDevices => {
  console.log('List of Tenant Devices:', tenantDevices);
});
```

**3. getCustomerDevices**

```javascript
const deviceService = self.ctx.deviceService;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
deviceService.getCustomerDevices(customerId, pageLink, type).subscribe(customerDevices => {
  console.log('List of Customer Devices:', customerDevices);
});
```

**4. getDevice**

```javascript
const deviceService = self.ctx.deviceService;
const deviceId = 'your-device-id';
deviceService.getDevice(deviceId).subscribe(device => {
  console.log('Get Device:', device);
});
```

**5. getDevices**

```javascript
const deviceService = self.ctx.deviceService;
const deviceIds = ['your-device-i-1', 'your-device-i-2'];
deviceService.getDevices(deviceIds).subscribe(devices => {
  console.log('List of Devices:', devices);
});
```

**6. getUserDevices**

```javascript
const deviceService = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
deviceService.getUserDevices(pageLink, type).subscribe(userDevices => {
  console.log('List of User Devices:', userDevices);
});
```

**7. getAllDeviceInfos**

```javascript
const deviceService = self.ctx.deviceService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'value';
deviceService.getAllDeviceInfos(includeCustomers, pageLink, deviceProfileId).subscribe(allDeviceInfos => {
  console.log('List of All Device Infos:', allDeviceInfos);
});
```

**8. getCustomerDeviceInfos**

```javascript
const deviceService = self.ctx.deviceService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'value';
deviceService.getCustomerDeviceInfos(includeCustomers, customerId, pageLink, deviceProfileId).subscribe(customerDeviceInfos => {
  console.log('List of Customer Device Infos:', customerDeviceInfos);
});
```

**9. getDeviceInfo**

```javascript
const deviceService = self.ctx.deviceService;
const deviceId = 'your-device-id';
deviceService.getDeviceInfo(deviceId).subscribe(deviceInfo => {
  console.log('Get Device Info:', deviceInfo);
});
```

**10. saveDevice**

```javascript
const deviceService = self.ctx.deviceService;
const device = {  // Device object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = deviceService.saveDevice(device, entityGroupIds);
console.log('Result:', result);
```

**11. saveDeviceWithCredentials**

```javascript
const deviceService = self.ctx.deviceService;
const device = {  // Device object
  // ... set the fields you need
};
const credentials = {  // DeviceCredentials object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
const result = deviceService.saveDeviceWithCredentials(device, credentials, entityGroupIds);
console.log('Result:', result);
```

**12. getDeviceTypes**

```javascript
const deviceService = self.ctx.deviceService;
deviceService.getDeviceTypes().subscribe(deviceTypes => {
  console.log('List of Device Types:', deviceTypes);
});
```

**13. getDeviceCredentials**

```javascript
const deviceService = self.ctx.deviceService;
const deviceId = 'your-device-id';
const sync = 'value';
deviceService.getDeviceCredentials(deviceId, sync).subscribe(deviceCredentials => {
  console.log('Get Device Credentials:', deviceCredentials);
});
```
