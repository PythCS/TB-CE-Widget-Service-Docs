### **DEVICE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceservice = $injector.get(self.ctx.servicesMap.get('deviceservice'));

// Alternative: Direct context access
const deviceservice = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.getDeviceInfosByQuery(deviceInfoQuery).subscribe(deviceinfosbyquery => {
  console.log('Deviceinfosbyquery:', deviceinfosbyquery);
});
```

**2. getTenantDeviceInfos**

```javascript
const deviceservice = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceservice.getTenantDeviceInfos(pageLink, 'your-type').subscribe(tenantdeviceinfos => {
  console.log('Tenantdeviceinfos:', tenantdeviceinfos);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
const deviceservice = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceservice.getTenantDeviceInfosByDeviceProfileId(pageLink, 'your-device-id').subscribe(tenantdeviceinfosbydeviceprofileid => {
  console.log('Tenantdeviceinfosbydeviceprofileid:', tenantdeviceinfosbydeviceprofileid);
});
```

**4. getCustomerDeviceInfos**

```javascript
const deviceservice = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceservice.getCustomerDeviceInfos(pageLink, 'your-customer-id', 'your-type').subscribe(customerdeviceinfos => {
  console.log('Customerdeviceinfos:', customerdeviceinfos);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
const deviceservice = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceservice.getCustomerDeviceInfosByDeviceProfileId(pageLink, 'your-customer-id', 'your-device-id').subscribe(customerdeviceinfosbydeviceprofileid => {
  console.log('Customerdeviceinfosbydeviceprofileid:', customerdeviceinfosbydeviceprofileid);
});
```

**6. getDevice**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.getDevice('your-device-id').subscribe(device => {
  console.log('Device:', device);
});
```

**7. getDevices**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.getDevices('your-device-id').subscribe(devices => {
  console.log('Devices:', devices);
});
```

**8. getDeviceInfo**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.getDeviceInfo('your-device-id').subscribe(deviceinfo => {
  console.log('Deviceinfo:', deviceinfo);
});
```

**9. saveDevice**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.saveDevice(device).subscribe(savedevice => {
  console.log('Savedevice:', savedevice);
});
```

**10. saveDeviceWithCredentials**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.saveDeviceWithCredentials(device, credentials).subscribe(savedevicewithcredentials => {
  console.log('Savedevicewithcredentials:', savedevicewithcredentials);
});
```

**11. getDeviceTypes**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.getDeviceTypes().subscribe(devicetypes => {
  console.log('Devicetypes:', devicetypes);
});
```

**12. getDeviceCredentials**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.getDeviceCredentials('your-device-id', true).subscribe(devicecredentials => {
  console.log('Devicecredentials:', devicecredentials);
});
```

**13. saveDeviceCredentials**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.saveDeviceCredentials(deviceCredentials).subscribe(savedevicecredentials => {
  console.log('Savedevicecredentials:', savedevicecredentials);
});
```

**14. makeDevicePublic**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.makeDevicePublic('your-device-id').subscribe(makedevicepublic => {
  console.log('Makedevicepublic:', makedevicepublic);
});
```

**15. assignDeviceToCustomer**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.assignDeviceToCustomer('your-customer-id', 'your-device-id').subscribe(assigndevicetocustomer => {
  console.log('Assigndevicetocustomer:', assigndevicetocustomer);
});
```

**16. sendOneWayRpcCommand**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.sendOneWayRpcCommand('your-device-id', requestBody).subscribe(sendonewayrpccommand => {
  console.log('Sendonewayrpccommand:', sendonewayrpccommand);
});
```

**17. sendTwoWayRpcCommand**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.sendTwoWayRpcCommand('your-device-id', requestBody).subscribe(sendtwowayrpccommand => {
  console.log('Sendtwowayrpccommand:', sendtwowayrpccommand);
});
```

**18. getPersistedRpc**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.getPersistedRpc('your-rpc-id').subscribe(persistedrpc => {
  console.log('Persistedrpc:', persistedrpc);
});
```

**19. getPersistedRpcRequests**

```javascript
const deviceservice = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceservice.getPersistedRpcRequests(pageLink, 'your-device-id').subscribe(persistedrpcrequests => {
  console.log('Persistedrpcrequests:', persistedrpcrequests);
});
```

**20. findByQuery**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.findByQuery(query).subscribe(byquery => {
  console.log('Byquery:', byquery);
});
```

**21. findByName**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.findByName('Device Name').subscribe(byname => {
  console.log('Byname:', byname);
});
```

**22. claimDevice**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.claimDevice('Device Name', claimRequest).subscribe(claimdevice => {
  console.log('Claimdevice:', claimdevice);
});
```

**23. assignDeviceToEdge**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.assignDeviceToEdge('your-edge-id', 'your-device-id').subscribe(assigndevicetoedge => {
  console.log('Assigndevicetoedge:', assigndevicetoedge);
});
```

**24. getEdgeDevices**

```javascript
const deviceservice = self.ctx.deviceService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceservice.getEdgeDevices(pageLink, 'your-edge-id', 'your-type').subscribe(edgedevices => {
  console.log('Edgedevices:', edgedevices);
});
```

**25. bulkImportDevices**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.bulkImportDevices(entitiesData).subscribe(bulkimportdevices => {
  console.log('Bulkimportdevices:', bulkimportdevices);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.getDevicePublishTelemetryCommands('your-device-id').subscribe(devicepublishtelemetrycommands => {
  console.log('Devicepublishtelemetrycommands:', devicepublishtelemetrycommands);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.downloadGatewayDockerComposeFile('your-device-id').subscribe(downgatewaydockercomposefile => {
  console.log('Downgatewaydockercomposefile:', downgatewaydockercomposefile);
});
```

**28. rebootDevice**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.rebootDevice('your-device-id', true).subscribe(rebootdevice => {
  console.log('Rebootdevice:', rebootdevice);
});
```

**29. rebootTrigger**

```javascript
const deviceservice = self.ctx.deviceService;
deviceservice.rebootTrigger('your-device-id', 'your-resourcepath').subscribe(reboottrigger => {
  console.log('Reboottrigger:', reboottrigger);
});
```

