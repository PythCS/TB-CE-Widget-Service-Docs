# Device Service

Manage devices, credentials, RPC calls, and device-related operations in ThingsBoard.

## Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

## Methods

**1. getDeviceInfosByQuery**

```javascript
const deviceInfoQuery = {
  entityFilter: {
    type: 'entitiesByType',
    entityType: 'DEVICE'
  },
  pageLink: self.ctx.pageLink(10, 0)
};

deviceService.getDeviceInfosByQuery(deviceInfoQuery).subscribe(response => {
  console.log('Device Infos by Query:', response.data);
});
```

**2. getTenantDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0);
const type = ''; // Device type filter, empty for all types

deviceService.getTenantDeviceInfos(pageLink, type).subscribe(response => {
  console.log('Tenant Device Infos:', response.data);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0);
const deviceProfileId = 'your-device-profile-id';

deviceService.getTenantDeviceInfosByDeviceProfileId(pageLink, deviceProfileId).subscribe(response => {
  console.log('Devices by Profile:', response.data);
});
```

**4. getCustomerDeviceInfos**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0);
const type = '';

deviceService.getCustomerDeviceInfos(customerId, pageLink, type).subscribe(response => {
  console.log('Customer Device Infos:', response.data);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0);
const deviceProfileId = 'your-device-profile-id';

deviceService.getCustomerDeviceInfosByDeviceProfileId(customerId, pageLink, deviceProfileId).subscribe(response => {
  console.log('Customer Devices by Profile:', response.data);
});
```

**6. getDevice**

```javascript
const deviceId = 'your-device-id';

deviceService.getDevice(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

**7. getDevices**

```javascript
const deviceIds = ['device-id-1', 'device-id-2'];

deviceService.getDevices(deviceIds).subscribe(devices => {
  console.log('Devices:', devices);
});
```

**8. getDeviceInfo**

```javascript
const deviceId = 'your-device-id';

deviceService.getDeviceInfo(deviceId).subscribe(deviceInfo => {
  console.log('Device Info:', deviceInfo);
});
```

**9. saveDevice**

```javascript
const device = {
  name: 'Temperature Sensor 001',
  type: 'sensor',
  customerId: { entityType: 'CUSTOMER', id: 'your-customer-id' }
};

deviceService.saveDevice(device).subscribe(savedDevice => {
  console.log('Saved Device:', savedDevice);
});
```

**10. saveDeviceWithCredentials**

```javascript
const device = {
  name: 'Temperature Sensor 002',
  type: 'sensor'
};
const credentials = {
  credentialsType: 'ACCESS_TOKEN',
  credentialsId: 'device-access-token'
};

deviceService.saveDeviceWithCredentials(device, credentials).subscribe(result => {
  console.log('Device Saved with Credentials:', result);
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes().subscribe(deviceTypes => {
  console.log('Device Types:', deviceTypes);
});
```

**12. getDeviceCredentials**

```javascript
const deviceId = 'your-device-id';
const sync = false;

deviceService.getDeviceCredentials(deviceId, sync).subscribe(credentials => {
  console.log('Device Credentials:', credentials);
});
```

**13. saveDeviceCredentials**

```javascript
const deviceCredentials = {
  deviceId: { entityType: 'DEVICE', id: 'your-device-id' },
  credentialsType: 'ACCESS_TOKEN',
  credentialsId: 'new-access-token'
};

deviceService.saveDeviceCredentials(deviceCredentials).subscribe(savedCredentials => {
  console.log('Saved Device Credentials:', savedCredentials);
});
```

**14. makeDevicePublic**

```javascript
const deviceId = 'your-device-id';

deviceService.makeDevicePublic(deviceId).subscribe(publicDevice => {
  console.log('Public Device:', publicDevice);
});
```

**15. assignDeviceToCustomer**

```javascript
const customerId = 'your-customer-id';
const deviceId = 'your-device-id';

deviceService.assignDeviceToCustomer(customerId, deviceId).subscribe(assignedDevice => {
  console.log('Assigned Device:', assignedDevice);
});
```

**16. sendOneWayRpcCommand**

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  method: 'setValue',
  params: { value: 25.5 }
};

deviceService.sendOneWayRpcCommand(deviceId, requestBody).subscribe(result => {
  console.log('One-way RPC sent successfully');
});
```

**17. sendTwoWayRpcCommand**

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  method: 'getValue',
  params: {}
};

deviceService.sendTwoWayRpcCommand(deviceId, requestBody).subscribe(response => {
  console.log('Two-way RPC Response:', response);
});
```

**18. getPersistedRpc**

```javascript
const rpcId = 'your-rpc-id';

deviceService.getPersistedRpc(rpcId).subscribe(persistedRpc => {
  console.log('Persisted RPC:', persistedRpc);
});
```

**19. getPersistedRpcRequests**

```javascript
const deviceId = 'your-device-id';
const pageLink = self.ctx.pageLink(10, 0);
const rpcStatus = 'SUCCESSFUL'; // Optional

deviceService.getPersistedRpcRequests(deviceId, pageLink, rpcStatus).subscribe(response => {
  console.log('Persisted RPC Requests:', response.data);
});
```

**20. findByQuery**

```javascript
const query = {
  entityFilter: {
    type: 'entitiesByType',
    entityType: 'DEVICE'
  },
  pageLink: self.ctx.pageLink(10, 0)
};

deviceService.findByQuery(query).subscribe(devices => {
  console.log('Devices by Query:', devices);
});
```

**21. findByName**

```javascript
const deviceName = 'Temperature Sensor 001';

deviceService.findByName(deviceName).subscribe(device => {
  console.log('Device by Name:', device);
});
```

**22. claimDevice**

```javascript
const deviceName = 'Claimable Device';
const claimRequest = {
  secretKey: 'device-secret-key'
};

deviceService.claimDevice(deviceName, claimRequest).subscribe(claimResult => {
  console.log('Device Claim Result:', claimResult);
});
```

**23. assignDeviceToEdge**

```javascript
const edgeId = 'your-edge-id';
const deviceId = 'your-device-id';

deviceService.assignDeviceToEdge(edgeId, deviceId).subscribe(assignedDevice => {
  console.log('Device Assigned to Edge:', assignedDevice);
});
```

**24. getEdgeDevices**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0);
const type = '';

deviceService.getEdgeDevices(edgeId, pageLink, type).subscribe(response => {
  console.log('Edge Devices:', response.data);
});
```

**25. bulkImportDevices**

```javascript
const entitiesData = {
  file: 'devices.csv',
  mapping: {
    name: 0,
    type: 1
  }
};

deviceService.bulkImportDevices(entitiesData).subscribe(importResult => {
  console.log('Bulk Import Result:', importResult);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
const deviceId = 'your-device-id';

deviceService.getDevicePublishTelemetryCommands(deviceId).subscribe(telemetryCommands => {
  console.log('Publish Telemetry Commands:', telemetryCommands);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
const deviceId = 'your-gateway-device-id';

deviceService.downloadGatewayDockerComposeFile(deviceId).subscribe(dockerCompose => {
  console.log('Gateway Docker Compose downloaded');
});
```

**28. rebootDevice**

```javascript
const deviceId = 'your-device-id';
const isBootstrapServer = false;

deviceService.rebootDevice(deviceId, isBootstrapServer).subscribe(result => {
  console.log('Device reboot initiated');
});
```

**29. rebootTrigger**

```javascript
const deviceId = 'your-device-id';
const resourcePath = '/3/0/4';

deviceService.rebootTrigger(deviceId, resourcePath).subscribe(result => {
  console.log('Device reboot trigger sent');
});
```