# DeviceService

**Source:** `device.service.ts`  
**Direct context access:** `deviceService`

---

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
deviceService.getDeviceInfosByQuery(null).subscribe(deviceInfosByQuery => {
  console.log('Device infosByQuery:', deviceInfosByQuery);
});
```

**2. getTenantDeviceInfos**

```javascript
deviceService.getTenantDeviceInfos(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantDeviceInfos => {
  console.log('TenantDevice infos:', tenantDeviceInfos);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
deviceService.getTenantDeviceInfosByDeviceProfileId(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantDeviceInfosByDeviceProfileId => {
  console.log('TenantDevice infosByDeviceProfileId:', tenantDeviceInfosByDeviceProfileId);
});
```

**4. getCustomerDeviceInfos**

```javascript
deviceService.getCustomerDeviceInfos(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(customerDeviceInfos => {
  console.log('CustomerDevice infos:', customerDeviceInfos);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
deviceService.getCustomerDeviceInfosByDeviceProfileId(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(customerDeviceInfosByDeviceProfileId => {
  console.log('CustomerDevice infosByDeviceProfileId:', customerDeviceInfosByDeviceProfileId);
});
```

**6. getDevice**

```javascript
deviceService.getDevice(/* deviceId */ null).subscribe(device => {
  console.log('Device:', device);
});
```

**7. getDevices**

```javascript
deviceService.getDevices(['id1', 'id2']).subscribe(devices => {
  console.log('Devices:', devices);
});
```

**8. getDeviceInfo**

```javascript
deviceService.getDeviceInfo(/* deviceId */ null).subscribe(deviceInfo => {
  console.log('Device:', deviceInfo);
});
```

**9. saveDevice**

```javascript
deviceService.saveDevice(/* device */ null).subscribe(device => {
  console.log('Device:', device);
});
```

**10. saveDeviceWithCredentials**

```javascript
deviceService.saveDeviceWithCredentials(/* device */ null, /* credentials */ null).subscribe(deviceWithCredentials => {
  console.log('DeviceWithCredentials:', deviceWithCredentials);
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes().subscribe(deviceTypes => {
  console.log('DeviceTypes:', deviceTypes);
});
```

**12. getDeviceCredentials**

```javascript
deviceService.getDeviceCredentials(/* deviceId */ null, null).subscribe(deviceCredentials => {
  console.log('DeviceCredentials:', deviceCredentials);
});
```

**13. saveDeviceCredentials**

```javascript
deviceService.saveDeviceCredentials(/* deviceCredentials */ null).subscribe(deviceCredentials => {
  console.log('DeviceCredentials:', deviceCredentials);
});
```

**14. makeDevicePublic**

```javascript
deviceService.makeDevicePublic(/* deviceId */ null).subscribe(devicePublic => {
  console.log('makeDevicePublic:', devicePublic);
});
```

**15. assignDeviceToCustomer**

```javascript
deviceService.assignDeviceToCustomer(/* customerId */ null, /* deviceId */ null).subscribe(deviceToCustomer => {
  console.log('assignDeviceToCustomer:', deviceToCustomer);
});
```

**16. sendOneWayRpcCommand**

```javascript
deviceService.sendOneWayRpcCommand(/* deviceId */ null, /* requestBody */ null).subscribe(oneWayRpcCommand => {
  console.log('sendOneWayRpcCommand:', oneWayRpcCommand);
});
```

**17. sendTwoWayRpcCommand**

```javascript
deviceService.sendTwoWayRpcCommand(/* deviceId */ null, /* requestBody */ null).subscribe(twoWayRpcCommand => {
  console.log('sendTwoWayRpcCommand:', twoWayRpcCommand);
});
```

**18. getPersistedRpc**

```javascript
deviceService.getPersistedRpc(/* rpcId */ null).subscribe(persistedRpc => {
  console.log('PersistedRpc:', persistedRpc);
});
```

**19. getPersistedRpcRequests**

```javascript
deviceService.getPersistedRpcRequests(/* deviceId */ null, self.ctx.pageLink(10, 0, null, null, null), /* rpcStatus */ null).subscribe(persistedRpcRequests => {
  console.log('PersistedRpcRequests:', persistedRpcRequests);
});
```

**20. findByQuery**

```javascript
deviceService.findByQuery(null).subscribe(byQuery => {
  console.log('ByQuery:', byQuery);
});
```

**21. findByName**

```javascript
deviceService.findByName(/* deviceName */ null).subscribe(byName => {
  console.log('ByName:', byName);
});
```

**22. claimDevice**

```javascript
deviceService.claimDevice(/* deviceName */ null, /* claimRequest */ null).subscribe(claimDevice => {
  console.log('claimDevice:', claimDevice);
});
```

**23. assignDeviceToEdge**

```javascript
deviceService.assignDeviceToEdge(/* edgeId */ null, /* deviceId */ null).subscribe(deviceToEdge => {
  console.log('assignDeviceToEdge:', deviceToEdge);
});
```

**24. getEdgeDevices**

```javascript
deviceService.getEdgeDevices(/* edgeId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(edgeDevices => {
  console.log('EdgeDevices:', edgeDevices);
});
```

**25. bulkImportDevices**

```javascript
deviceService.bulkImportDevices(/* entitiesData */ null).subscribe(bulkImportDevices => {
  console.log('bulkImportDevices:', bulkImportDevices);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
deviceService.getDevicePublishTelemetryCommands(/* deviceId */ null).subscribe(devicePublishTelemetryCommands => {
  console.log('DevicePublishTelemetryCommands:', devicePublishTelemetryCommands);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
deviceService.downloadGatewayDockerComposeFile(/* deviceId */ null).subscribe(downGatewayDockerComposeFile => {
  console.log('downloadGatewayDockerComposeFile:', downGatewayDockerComposeFile);
});
```

**28. rebootDevice**

```javascript
deviceService.rebootDevice(/* deviceId */ null, true).subscribe(rebootDevice => {
  console.log('rebootDevice:', rebootDevice);
});
```

**29. rebootTrigger**

```javascript
deviceService.rebootTrigger(/* deviceId */ null, /* resourcePath */ null).subscribe(rebootTrigger => {
  console.log('rebootTrigger:', rebootTrigger);
});
```

---

*Auto-generated by ThingsBoardDocUpdater*