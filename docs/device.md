# Device

```javascript
// Service name: device
// File: device.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const device = self.ctx.deviceService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const device = $injector.get(self.ctx.servicesMap.get('device'));
```

### **1. getDeviceInfosByQuery**

```javascript
device.getDeviceInfosByQuery(deviceInfoQuery).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **2. getTenantDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
device.getTenantDeviceInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **3. getTenantDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
device.getTenantDeviceInfosByDeviceProfileId(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **4. getCustomerDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
device.getCustomerDeviceInfos(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
device.getCustomerDeviceInfosByDeviceProfileId(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **6. getDevice**

```javascript
device.getDevice(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### **7. getDevices**

```javascript
device.getDevices(deviceIds).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **8. getDeviceInfo**

```javascript
device.getDeviceInfo(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### **9. saveDevice**

```javascript
device.saveDevice(device).subscribe(device => {
  console.log('Device:', device);
});
```

### **10. saveDeviceWithCredentials**

```javascript
device.saveDeviceWithCredentials(device, credentials).subscribe(device => {
  console.log('Device:', device);
});
```

### **11. getDeviceTypes**

```javascript
device.getDeviceTypes().subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **12. getDeviceCredentials**

```javascript
device.getDeviceCredentials(deviceId, sync).subscribe(device => {
  console.log('Device:', device);
});
```

### **13. saveDeviceCredentials**

```javascript
device.saveDeviceCredentials(deviceCredentials).subscribe(device => {
  console.log('Device:', device);
});
```

### **14. makeDevicePublic**

```javascript
device.makeDevicePublic(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### **15. assignDeviceToCustomer**

```javascript
device.assignDeviceToCustomer(customerId, deviceId).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### **16. sendOneWayRpcCommand**

```javascript
device.sendOneWayRpcCommand(deviceId, requestBody).subscribe(sendOneWayRpcCommand => {
  console.log('Send One Way Rpc Command:', sendOneWayRpcCommand);
});
```

### **17. sendTwoWayRpcCommand**

```javascript
device.sendTwoWayRpcCommand(deviceId, requestBody).subscribe(sendTwoWayRpcCommand => {
  console.log('Send Two Way Rpc Command:', sendTwoWayRpcCommand);
});
```

### **18. getPersistedRpc**

```javascript
device.getPersistedRpc(rpcId).subscribe(persistedRpc => {
  console.log('Persisted Rpc:', persistedRpc);
});
```

### **19. getPersistedRpcRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
device.getPersistedRpcRequests(pageLink).subscribe(persistedRpcRequests => {
  console.log('Persisted Rpc Requests:', persistedRpcRequests);
});
```

### **20. findByQuery**

```javascript
device.findByQuery(query).subscribe(findByQuerys => {
  console.log('Find By Querys:', findByQuerys);
});
```

### **21. findByName**

```javascript
device.findByName(deviceName).subscribe(find => {
  console.log('Find:', find);
});
```

### **22. claimDevice**

```javascript
device.claimDevice(deviceName, claimRequest).subscribe(device => {
  console.log('Device:', device);
});
```

### **23. assignDeviceToEdge**

```javascript
device.assignDeviceToEdge(edgeId, deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### **24. getEdgeDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
device.getEdgeDevices(pageLink).subscribe(devices => {
  console.log('Devices:', devices);
});
```

### **25. bulkImportDevices**

```javascript
device.bulkImportDevices(entitiesData).subscribe(device => {
  console.log('Device:', device);
});
```

### **26. getDevicePublishTelemetryCommands**

```javascript
device.getDevicePublishTelemetryCommands(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### **27. downloadGatewayDockerComposeFile**

```javascript
device.downloadGatewayDockerComposeFile(deviceId).subscribe(downloadGatewayDockerComposeFile => {
  console.log('Download Gateway Docker Compose File:', downloadGatewayDockerComposeFile);
});
```

### **28. rebootDevice**

```javascript
device.rebootDevice(deviceId, isBootstrapServer).subscribe(device => {
  console.log('Device:', device);
});
```

### **29. rebootTrigger**

```javascript
device.rebootTrigger(deviceId, resourcePath).subscribe(rebootTrigger => {
  console.log('Reboot Trigger:', rebootTrigger);
});
```
