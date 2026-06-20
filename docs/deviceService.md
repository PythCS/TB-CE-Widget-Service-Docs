# DEVICE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **DEVICE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
const deviceInfoQuery = query;
deviceService.getDeviceInfosByQuery(deviceInfoQuery).subscribe(deviceInfosByQuery => {
  console.log('Get Device Infos By Query: deviceInfosByQuery');
});
```

**2. getTenantDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getTenantDeviceInfos(pageLink, 'type').subscribe(tenantdeviceinfos => {
  console.log('Get Tenant Device Infos: tenantdeviceinfos');
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getTenantDeviceInfosByDeviceProfileId(pageLink, 'your-device-profile-id').subscribe(tenantDeviceInfosByDeviceProfileId => {
  console.log('Get Tenant Device Infos By Device Profile Id:tenantDeviceInfosByDeviceProfileId');
});
```

**4. getCustomerDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getCustomerDeviceInfos('your-customer-id', pageLink, 'type').subscribe(customerdeviceinfos => {
  console.log('Get Customer Device Infos: customerdeviceinfos');
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getCustomerDeviceInfosByDeviceProfileId('your-customer-id', pageLink, 'your-device-profile-id').subscribe(customerDeviceInfosByDeviceProfileId => {
  console.log('Get Customer Device Infos By Device Profile Id:customerDeviceInfosByDeviceProfileId');
});
```

**6. getDevice**

```javascript
deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Get Device: device');
});
```

**7. getDevices**

```javascript
deviceService.getDevices('your-id').subscribe(devices => {
  console.log('Get Devices: devices');
});
```

**8. getDeviceInfo**

```javascript
deviceService.getDeviceInfo('your-device-id').subscribe(deviceInfo => {
  console.log('Get Device Info: deviceInfo');
});
```

**9. saveDevice**

```javascript
const device = device;
deviceService.saveDevice(device).subscribe(savedDevice => {
  console.log('Save Device: savedDevice');
});
```

**10. saveDeviceWithCredentials**

```javascript
const device = device;
const credentials = credentials;
deviceService.saveDeviceWithCredentials(device, credentials).subscribe(savedDeviceWithCredentials => {
  console.log('Save Device With Credentials: savedDeviceWithCredentials');
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes().subscribe(devicetypes => {
  console.log('Get Device Types: devicetypes');
});
```

**12. getDeviceCredentials**

```javascript
deviceService.getDeviceCredentials('your-device-id', false).subscribe(devicecredentials => {
  console.log('Get Device Credentials: devicecredentials');
});
```

**13. saveDeviceCredentials**

```javascript
const deviceCredentials = deviceCredentials;
deviceService.saveDeviceCredentials(deviceCredentials).subscribe(savedDeviceCredentials => {
  console.log('Save Device Credentials: savedDeviceCredentials');
});
```

**14. makeDevicePublic**

```javascript
deviceService.makeDevicePublic('your-device-id').subscribe(result => {
  console.log('Make Device Public: result');
});
```

**15. assignDeviceToCustomer**

```javascript
deviceService.assignDeviceToCustomer('your-customer-id', 'your-device-id').subscribe(result => {
  console.log('Assign Device To Customer: result');
});
```

**16. sendOneWayRpcCommand**

```javascript
deviceService.sendOneWayRpcCommand('your-device-id', { method: 'getMethod', params: {} }).subscribe(result => {
  console.log('Send One Way Rpc Command: result');
});
```

**17. sendTwoWayRpcCommand**

```javascript
deviceService.sendTwoWayRpcCommand('your-device-id', { method: 'getMethod', params: {} }).subscribe(result => {
  console.log('Send Two Way Rpc Command: result');
});
```

**18. getPersistedRpc**

```javascript
deviceService.getPersistedRpc('your-rpc-id').subscribe(persistedRpc => {
  console.log('Get Persisted Rpc: persistedRpc');
});
```

**19. getPersistedRpcRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const rpcStatus = rpcStatus;
deviceService.getPersistedRpcRequests('your-device-id', pageLink, rpcStatus).subscribe(persistedrpcrequests => {
  console.log('Get Persisted Rpc Requests: persistedrpcrequests');
});
```

**20. findByQuery**

```javascript
const query = query;
deviceService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**21. findByName**

```javascript
const deviceName = deviceName;
deviceService.findByName(deviceName).subscribe(entity => {
  console.log('Find By Name: entity');
});
```

**22. claimDevice**

```javascript
const deviceName = deviceName;
const claimRequest = claimRequest;
deviceService.claimDevice(deviceName, claimRequest).subscribe(result => {
  console.log('Claim Device: result');
});
```

**23. assignDeviceToEdge**

```javascript
deviceService.assignDeviceToEdge('your-edge-id', 'your-device-id').subscribe(result => {
  console.log('Assign Device To Edge: result');
});
```

**24. getEdgeDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getEdgeDevices('your-edge-id', pageLink, 'type').subscribe(edgedevices => {
  console.log('Get Edge Devices: edgedevices');
});
```

**25. bulkImportDevices**

```javascript
const entitiesData = entitiesData;
deviceService.bulkImportDevices(entitiesData).subscribe(result => {
  console.log('Bulk Import Devices: result');
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
deviceService.getDevicePublishTelemetryCommands('your-device-id').subscribe(devicepublishtelemetrycommands => {
  console.log('Get Device Publish Telemetry Commands:devicepublishtelemetrycommands');
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
deviceService.downloadGatewayDockerComposeFile('your-device-id').subscribe(result => {
  console.log('Download Gateway Docker Compose File:result');
});
```

**28. rebootDevice**

```javascript
deviceService.rebootDevice('your-device-id', true).subscribe(result => {
  console.log('Reboot Device: result');
});
```

**29. rebootTrigger**

```javascript
const resourcePath = resourcePath;
deviceService.rebootTrigger('your-device-id', resourcePath).subscribe(result => {
  console.log('Reboot Trigger: result');
});
```
