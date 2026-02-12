# DEVICE

Device management and telemetry operations.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

## Methods

### getDeviceInfosByQuery

```javascript
const deviceInfoQuery = {
  // your deviceInfoQuery object
};

deviceService.getDeviceInfosByQuery(deviceInfoQuery).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### getTenantDeviceInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

deviceService.getTenantDeviceInfos(pageLink, type).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### getTenantDeviceInfosByDeviceProfileId

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'your-deviceprofile-id';

deviceService.getTenantDeviceInfosByDeviceProfileId(pageLink, deviceProfileId).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### getCustomerDeviceInfos

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

deviceService.getCustomerDeviceInfos(customerId, pageLink, type).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### getCustomerDeviceInfosByDeviceProfileId

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'your-deviceprofile-id';

deviceService.getCustomerDeviceInfosByDeviceProfileId(customerId, pageLink, deviceProfileId).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### getDevice

```javascript
const deviceId = 'your-device-id';

deviceService.getDevice(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### getDevices

```javascript
const deviceIds = 'your-devices-id';

deviceService.getDevices(deviceIds).subscribe(device => {
  console.log('Device:', device);
});
```

### getDeviceInfo

```javascript
const deviceId = 'your-device-id';

deviceService.getDeviceInfo(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### saveDevice

```javascript
const device = {
  // your device object
};

deviceService.saveDevice(device).subscribe(device => {
  console.log('Device:', device);
});
```

### saveDeviceWithCredentials

```javascript
const device = {
  // your device object
};
const credentials = {
  // your credentials object
};

deviceService.saveDeviceWithCredentials(device, credentials).subscribe(device => {
  console.log('Device:', device);
});
```

### getDeviceTypes

```javascript
deviceService.getDeviceTypes().subscribe(result => {
  console.log('DeviceTypes:', result);
});
```

### getDeviceCredentials

```javascript
const deviceId = 'your-device-id';
const sync = {
  // your sync object
};

deviceService.getDeviceCredentials(deviceId, sync).subscribe(device => {
  console.log('Device:', device);
});
```

### saveDeviceCredentials

```javascript
const deviceCredentials = {
  // your deviceCredentials object
};

deviceService.saveDeviceCredentials(deviceCredentials).subscribe(device => {
  console.log('Device:', device);
});
```

### makeDevicePublic

```javascript
const deviceId = 'your-device-id';

deviceService.makeDevicePublic(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### assignDeviceToCustomer

```javascript
const customerId = 'your-customer-id';
const deviceId = 'your-device-id';

deviceService.assignDeviceToCustomer(customerId, deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### sendOneWayRpcCommand

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  // your requestBody object
};

deviceService.sendOneWayRpcCommand(deviceId, requestBody).subscribe(result => {
  console.log('sendOneWayRpcCommand:', result);
});
```

### sendTwoWayRpcCommand

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  // your requestBody object
};

deviceService.sendTwoWayRpcCommand(deviceId, requestBody).subscribe(result => {
  console.log('sendTwoWayRpcCommand:', result);
});
```

### getPersistedRpc

```javascript
const rpcId = 'your-rpc-id';

deviceService.getPersistedRpc(rpcId).subscribe(result => {
  console.log('PersistedRpc:', result);
});
```

### getPersistedRpcRequests

```javascript
const deviceId = 'your-device-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const rpcStatus = {
  // your rpcStatus object
};

deviceService.getPersistedRpcRequests(deviceId, pageLink, rpcStatus).subscribe(result => {
  console.log('PersistedRpcRequests:', result);
});
```

### findByQuery

```javascript
const query = {
  // your query object
};

deviceService.findByQuery(query).subscribe(device => {
  console.log('Device:', device);
});
```

### findByName

```javascript
const deviceName = 'your-devicename';

deviceService.findByName(deviceName).subscribe(device => {
  console.log('Device:', device);
});
```

### claimDevice

```javascript
const deviceName = 'your-devicename';
const claimRequest = {
  // your claimRequest object
};

deviceService.claimDevice(deviceName, claimRequest).subscribe(result => {
  console.log('Result:', result);
});
```

### assignDeviceToEdge

```javascript
const edgeId = 'your-edge-id';
const deviceId = 'your-device-id';

deviceService.assignDeviceToEdge(edgeId, deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### getEdgeDevices

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

deviceService.getEdgeDevices(edgeId, pageLink, type).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### bulkImportDevices

```javascript
const entitiesData = {
  // your entitiesData object
};

deviceService.bulkImportDevices(entitiesData).subscribe(result => {
  console.log('Result:', result);
});
```

### getDevicePublishTelemetryCommands

```javascript
const deviceId = 'your-device-id';

deviceService.getDevicePublishTelemetryCommands(deviceId).subscribe(result => {
  console.log('DevicePublishTelemetryCommands:', result);
});
```

### downloadGatewayDockerComposeFile

```javascript
const deviceId = 'your-device-id';

deviceService.downloadGatewayDockerComposeFile(deviceId).subscribe(result => {
  console.log('downloadGatewayDockerComposeFile:', result);
});
```

### rebootDevice

```javascript
const deviceId = 'your-device-id';
const isBootstrapServer = true;

deviceService.rebootDevice(deviceId, isBootstrapServer).subscribe(result => {
  console.log('rebootDevice:', result);
});
```

### rebootTrigger

```javascript
const deviceId = 'your-device-id';
const resourcePath = 'your-resourcepath';

deviceService.rebootTrigger(deviceId, resourcePath).subscribe(result => {
  console.log('rebootTrigger:', result);
});
```

