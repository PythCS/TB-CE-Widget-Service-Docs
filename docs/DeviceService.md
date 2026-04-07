# DeviceService

### **DEVICESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
deviceService.getDeviceInfosByQuery({ /* your deviceInfoQuery */ }, { /* your config */ }).subscribe(deviceinfobyquery => {
  console.log('Device Infos By Query:', deviceinfobyquery);
});
```

**2. getTenantDeviceInfos**

```javascript
deviceService.getTenantDeviceInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(tenantdeviceinfo => {
  console.log('Tenant Device Infos:', tenantdeviceinfo);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
deviceService.getTenantDeviceInfosByDeviceProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id', { /* your config */ }).subscribe(tenantdeviceinfobydeviceprofileid => {
  console.log('Tenant Device Infos By Device Profile Id:', tenantdeviceinfobydeviceprofileid);
});
```

**4. getCustomerDeviceInfos**

```javascript
deviceService.getCustomerDeviceInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(cutomerdeviceinfo => {
  console.log('Customer Device Infos:', cutomerdeviceinfo);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
deviceService.getCustomerDeviceInfosByDeviceProfileId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id', { /* your config */ }).subscribe(cutomerdeviceinfobydeviceprofileid => {
  console.log('Customer Device Infos By Device Profile Id:', cutomerdeviceinfobydeviceprofileid);
});
```

**6. getDevice**

```javascript
deviceService.getDevice('your-device-id', { /* your config */ }).subscribe(device => {
  console.log('Device:', device);
});
```

**7. getDevices**

```javascript
deviceService.getDevices(['id1', 'id2'], { /* your config */ }).subscribe(device => {
  console.log('Devices:', device);
});
```

**8. getDeviceInfo**

```javascript
deviceService.getDeviceInfo('your-device-id', { /* your config */ }).subscribe(deviceinfo => {
  console.log('Device Info:', deviceinfo);
});
```

**9. saveDevice**

```javascript
deviceService.saveDevice({ /* your device object */ }, { /* your config */ }).subscribe(savedDevice => {
  console.log('Saved Device:', savedDevice);
});
```

**10. saveDeviceWithCredentials**

```javascript
deviceService.saveDeviceWithCredentials({ /* your device object */ }, { /* your credentials */ }, { /* your config */ }).subscribe(savedDeviceWithCredentials => {
  console.log('Saved DeviceWithCredentials:', savedDeviceWithCredentials);
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes({ /* your config */ }).subscribe(devicetype => {
  console.log('Device Types:', devicetype);
});
```

**12. getDeviceCredentials**

```javascript
deviceService.getDeviceCredentials('your-device-id', { /* your sync */ }, { /* your config */ }).subscribe(devicecredential => {
  console.log('Device Credentials:', devicecredential);
});
```

**13. saveDeviceCredentials**

```javascript
deviceService.saveDeviceCredentials({ /* your deviceCredentials */ }, { /* your config */ }).subscribe(savedDeviceCredentials => {
  console.log('Saved DeviceCredentials:', savedDeviceCredentials);
});
```

**14. makeDevicePublic**

```javascript
deviceService.makeDevicePublic('your-device-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. assignDeviceToCustomer**

```javascript
deviceService.assignDeviceToCustomer('your-customer-id', 'your-device-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**16. sendOneWayRpcCommand**

```javascript
deviceService.sendOneWayRpcCommand('your-device-id', { /* your requestBody */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**17. sendTwoWayRpcCommand**

```javascript
deviceService.sendTwoWayRpcCommand('your-device-id', { /* your requestBody */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**18. getPersistedRpc**

```javascript
deviceService.getPersistedRpc('your-rpc-id', { /* your config */ }).subscribe(persistedrpc => {
  console.log('Persisted Rpc:', persistedrpc);
});
```

**19. getPersistedRpcRequests**

```javascript
deviceService.getPersistedRpcRequests('your-device-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your rpcStatus */ }, { /* your config */ }).subscribe(peritedrpcrequet => {
  console.log('Persisted Rpc Requests:', peritedrpcrequet);
});
```

**20. findByQuery**

```javascript
deviceService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**21. findByName**

```javascript
deviceService.findByName('your-deviceName', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**22. claimDevice**

```javascript
deviceService.claimDevice('your-deviceName', { /* your claimRequest */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**23. assignDeviceToEdge**

```javascript
deviceService.assignDeviceToEdge('your-edge-id', 'your-device-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**24. getEdgeDevices**

```javascript
deviceService.getEdgeDevices('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(edgedevice => {
  console.log('Edge Devices:', edgedevice);
});
```

**25. bulkImportDevices**

```javascript
deviceService.bulkImportDevices({ /* your entitiesData */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
deviceService.getDevicePublishTelemetryCommands('your-device-id', { /* your config */ }).subscribe(devicepublihtelemetrycommand => {
  console.log('Device Publish Telemetry Commands:', devicepublihtelemetrycommand);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
deviceService.downloadGatewayDockerComposeFile('your-device-id').subscribe(result => {
  console.log('Result:', result);
});
```

**28. rebootDevice**

```javascript
deviceService.rebootDevice('your-device-id', true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**29. rebootTrigger**

```javascript
deviceService.rebootTrigger('your-device-id', 'your-resourcePath', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
