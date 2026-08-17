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

**2. getTenantDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getTenantDeviceInfos(pageLink, 'your-type-value').subscribe(tenantDeviceInfos => {
  console.log('Get Tenant Device Infos:', tenantDeviceInfos);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getTenantDeviceInfosByDeviceProfileId(pageLink, 'your-deviceprofile-id').subscribe(tenantDeviceInfosByDeviceProfileId => {
  console.log('Get Tenant Device Infos By Device Profile Id:', tenantDeviceInfosByDeviceProfileId);
});
```

**4. getCustomerDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getCustomerDeviceInfos('your-customer-id', pageLink, 'your-type-value').subscribe(customerDeviceInfos => {
  console.log('Get Customer Device Infos:', customerDeviceInfos);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getCustomerDeviceInfosByDeviceProfileId('your-customer-id', pageLink, 'your-deviceprofile-id').subscribe(customerDeviceInfosByDeviceProfileId => {
  console.log('Get Customer Device Infos By Device Profile Id:', customerDeviceInfosByDeviceProfileId);
});
```

**6. getDevice**

```javascript
self.ctx.deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Get Device:', device);
});
```

**7. getDevices**

```javascript
self.ctx.deviceService.getDevices('your-deviceids-value').subscribe(devices => {
  console.log('Get Devices:', devices);
});
```

**8. getDeviceInfo**

```javascript
self.ctx.deviceService.getDeviceInfo('your-device-id').subscribe(deviceInfo => {
  console.log('Get Device Info:', deviceInfo);
});
```

**9. saveDevice**

```javascript
self.ctx.deviceService.saveDevice('your-device-value').subscribe(device => {
  console.log('Save Device:', device);
});
```

**10. saveDeviceWithCredentials**

```javascript
self.ctx.deviceService.saveDeviceWithCredentials('your-device-value', 'your-credentials-value').subscribe(deviceWithCredentials => {
  console.log('Save Device With Credentials:', deviceWithCredentials);
});
```

**11. getDeviceTypes**

```javascript
self.ctx.deviceService.getDeviceTypes().subscribe(deviceTypes => {
  console.log('Get Device Types:', deviceTypes);
});
```

**12. getDeviceCredentials**

```javascript
self.ctx.deviceService.getDeviceCredentials('your-device-id', true).subscribe(deviceCredentials => {
  console.log('Get Device Credentials:', deviceCredentials);
});
```

**13. saveDeviceCredentials**

```javascript
self.ctx.deviceService.saveDeviceCredentials('your-devicecredentials-value').subscribe(deviceCredentials => {
  console.log('Save Device Credentials:', deviceCredentials);
});
```

**14. makeDevicePublic**

```javascript
self.ctx.deviceService.makeDevicePublic('your-device-id').subscribe(makeDevicePublic => {
  console.log('Make Device Public:', makeDevicePublic);
});
```

**15. assignDeviceToCustomer**

```javascript
self.ctx.deviceService.assignDeviceToCustomer('your-customer-id', 'your-device-id').subscribe(deviceToCustomer => {
  console.log('Assign Device To Customer:', deviceToCustomer);
});
```

**16. sendOneWayRpcCommand**

```javascript
self.ctx.deviceService.sendOneWayRpcCommand('your-device-id', 'your-requestbody-value').subscribe(oneWayRpcCommand => {
  console.log('Send One Way Rpc Command:', oneWayRpcCommand);
});
```

**17. sendTwoWayRpcCommand**

```javascript
self.ctx.deviceService.sendTwoWayRpcCommand('your-device-id', 'your-requestbody-value').subscribe(twoWayRpcCommand => {
  console.log('Send Two Way Rpc Command:', twoWayRpcCommand);
});
```

**18. getPersistedRpc**

```javascript
self.ctx.deviceService.getPersistedRpc('your-rpc-id').subscribe(persistedRpc => {
  console.log('Get Persisted Rpc:', persistedRpc);
});
```

**19. getPersistedRpcRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getPersistedRpcRequests('your-device-id', pageLink, 'your-rpcstatus-value').subscribe(persistedRpcRequests => {
  console.log('Get Persisted Rpc Requests:', persistedRpcRequests);
});
```

**20. findByQuery**

```javascript
self.ctx.deviceService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**21. findByName**

```javascript
self.ctx.deviceService.findByName('your-devicename-value').subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**22. claimDevice**

```javascript
self.ctx.deviceService.claimDevice('your-devicename-value', 'your-claimrequest-value').subscribe(claimDevice => {
  console.log('Claim Device:', claimDevice);
});
```

**23. assignDeviceToEdge**

```javascript
self.ctx.deviceService.assignDeviceToEdge('your-edge-id', 'your-device-id').subscribe(deviceToEdge => {
  console.log('Assign Device To Edge:', deviceToEdge);
});
```

**24. getEdgeDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getEdgeDevices('your-edge-id', pageLink, 'your-type-value').subscribe(edgeDevices => {
  console.log('Get Edge Devices:', edgeDevices);
});
```

**25. bulkImportDevices**

```javascript
self.ctx.deviceService.bulkImportDevices('your-entitiesdata-value').subscribe(bulkImportDevices => {
  console.log('Bulk Import Devices:', bulkImportDevices);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
self.ctx.deviceService.getDevicePublishTelemetryCommands('your-device-id').subscribe(devicePublishTelemetryCommands => {
  console.log('Get Device Publish Telemetry Commands:', devicePublishTelemetryCommands);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
self.ctx.deviceService.downloadGatewayDockerComposeFile('your-device-id').subscribe(downloadGatewayDockerComposeFile => {
  console.log('Download Gateway Docker Compose File:', downloadGatewayDockerComposeFile);
});
```

**28. rebootDevice**

```javascript
self.ctx.deviceService.rebootDevice('your-device-id', true).subscribe(rebootDevice => {
  console.log('Reboot Device:', rebootDevice);
});
```

**29. rebootTrigger**

```javascript
self.ctx.deviceService.rebootTrigger('your-device-id', 'your-resourcepath-value').subscribe(rebootTrigger => {
  console.log('Reboot Trigger:', rebootTrigger);
});
```
