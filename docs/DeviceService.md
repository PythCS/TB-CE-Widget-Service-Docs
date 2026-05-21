# DeviceService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('DeviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
deviceService.getDeviceInfosByQuery('your-deviceinfoquery-value').subscribe(device => {
  console.log('Fetched  Device Infos By Query device:', device);
});
```

**2. getTenantDeviceInfos**

```javascript
deviceService.getTenantDeviceInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(device => {
  console.log('Fetched  Tenant Device Infos device:', device);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
deviceService.getTenantDeviceInfosByDeviceProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Tenant Device Infos By Device Profile Id device:', device);
});
```

**4. getCustomerDeviceInfos**

```javascript
deviceService.getCustomerDeviceInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(device => {
  console.log('Fetched  Customer Device Infos device:', device);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
deviceService.getCustomerDeviceInfosByDeviceProfileId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Customer Device Infos By Device Profile Id device:', device);
});
```

**6. getDevice**

```javascript
deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Fetched  Device device:', device);
});
```

**7. getDevices**

```javascript
deviceService.getDevices('your-deviceids-value').subscribe(device => {
  console.log('Fetched  Devices device:', device);
});
```

**8. getDeviceInfo**

```javascript
deviceService.getDeviceInfo('your-device-id').subscribe(device => {
  console.log('Fetched  Device Info device:', device);
});
```

**9. saveDevice**

```javascript
deviceService.saveDevice('your-device-value').subscribe(device => {
  console.log('Saved  Device device:', device);
});
```

**10. saveDeviceWithCredentials**

```javascript
deviceService.saveDeviceWithCredentials('your-device-value', 'your-credentials-value').subscribe(device => {
  console.log('Saved  Device With Credentials device:', device);
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes().subscribe(device => {
  console.log('Fetched  Device Types device:', device);
});
```

**12. getDeviceCredentials**

```javascript
deviceService.getDeviceCredentials('your-device-id', 'your-sync-value').subscribe(device => {
  console.log('Fetched  Device Credentials device:', device);
});
```

**13. saveDeviceCredentials**

```javascript
deviceService.saveDeviceCredentials('your-devicecredentials-value').subscribe(device => {
  console.log('Saved  Device Credentials device:', device);
});
```

**14. makeDevicePublic**

```javascript
deviceService.makeDevicePublic('your-device-id').subscribe(device => {
  console.log('make Device Public device:', device);
});
```

**15. assignDeviceToCustomer**

```javascript
deviceService.assignDeviceToCustomer('your-customer-id', 'your-device-id').subscribe(device => {
  console.log('assign Device To Customer device:', device);
});
```

**16. sendOneWayRpcCommand**

```javascript
deviceService.sendOneWayRpcCommand('your-device-id', 'your-requestbody-value').subscribe(result => {
  console.log('send One Way Rpc Command result:', result);
});
```

**17. sendTwoWayRpcCommand**

```javascript
deviceService.sendTwoWayRpcCommand('your-device-id', 'your-requestbody-value').subscribe(result => {
  console.log('send Two Way Rpc Command result:', result);
});
```

**18. getPersistedRpc**

```javascript
deviceService.getPersistedRpc('your-rpc-id').subscribe(result => {
  console.log('Fetched  Persisted Rpc result:', result);
});
```

**19. getPersistedRpcRequests**

```javascript
deviceService.getPersistedRpcRequests('your-device-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-rpcstatus-value').subscribe(result => {
  console.log('Fetched  Persisted Rpc Requests result:', result);
});
```

**20. findByQuery**

```javascript
deviceService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**21. findByName**

```javascript
deviceService.findByName('your-devicename-value').subscribe(result => {
  console.log('find By Name result:', result);
});
```

**22. claimDevice**

```javascript
deviceService.claimDevice('your-devicename-value', 'your-claimrequest-value').subscribe(device => {
  console.log('claim Device device:', device);
});
```

**23. assignDeviceToEdge**

```javascript
deviceService.assignDeviceToEdge('your-edge-id', 'your-device-id').subscribe(device => {
  console.log('assign Device To Edge device:', device);
});
```

**24. getEdgeDevices**

```javascript
deviceService.getEdgeDevices('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(device => {
  console.log('Fetched  Edge Devices device:', device);
});
```

**25. bulkImportDevices**

```javascript
deviceService.bulkImportDevices('your-entitiesdata-value').subscribe(device => {
  console.log('bulk Import Devices device:', device);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
deviceService.getDevicePublishTelemetryCommands('your-device-id').subscribe(device => {
  console.log('Fetched  Device Publish Telemetry Commands device:', device);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
deviceService.downloadGatewayDockerComposeFile('your-device-id').subscribe(result => {
  console.log('download Gateway Docker Compose File result:', result);
});
```

**28. rebootDevice**

```javascript
deviceService.rebootDevice('your-device-id', true).subscribe(device => {
  console.log('reboot Device device:', device);
});
```

**29. rebootTrigger**

```javascript
deviceService.rebootTrigger('your-device-id', 'your-resourcepath-value').subscribe(result => {
  console.log('reboot Trigger result:', result);
});
```
