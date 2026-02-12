# Device Service

Complete reference for the DeviceService in ThingsBoard widget development.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

## Methods

### getDevice

Get a device by ID.

```javascript
const deviceId = 'your-device-id';
deviceService.getDevice(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### getTenantDeviceInfos

Get paginated list of tenant devices.

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'sensor'; // Optional device type filter
deviceService.getTenantDeviceInfos(pageLink, type).subscribe(devices => {
  console.log('Tenant Devices:', devices);
});
```

### saveDevice

Create or update a device.

```javascript
const device = {
  name: 'Temperature Sensor 01',
  type: 'sensor',
  // Additional device properties
};
deviceService.saveDevice(device).subscribe(savedDevice => {
  console.log('Saved Device:', savedDevice);
});
```

### getDeviceCredentials

Get device access credentials.

```javascript
const deviceId = 'your-device-id';
const sync = false;
deviceService.getDeviceCredentials(deviceId, sync).subscribe(credentials => {
  console.log('Device Credentials:', credentials);
});
```

### sendTwoWayRpcCommand

Send a two-way RPC command to a device.

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  method: 'getTemperature',
  params: {}
};
deviceService.sendTwoWayRpcCommand(deviceId, requestBody).subscribe(response => {
  console.log('Two-way RPC Response:', response);
});
```

### findByName

Find a device by name.

```javascript
const deviceName = 'Temperature Sensor 01';
deviceService.findByName(deviceName).subscribe(device => {
  console.log('Device by Name:', device);
});
```

## Common Use Cases

### Getting Device List for Dashboard

```javascript
const pageLink = self.ctx.pageLink(20, 0, '', 'name', 'ASC');
deviceService.getTenantDeviceInfos(pageLink, '').subscribe(devicePage => {
  const devices = devicePage.data;
  console.log(`Found ${devices.length} devices`);
  
  devices.forEach(device => {
    console.log(`Device: ${device.name} (${device.type})`);
  });
});
```

### Sending Commands to Multiple Devices

```javascript
const deviceIds = ['device-1', 'device-2', 'device-3'];
const command = {
  method: 'setRelayStatus',
  params: { status: true }
};

deviceIds.forEach(deviceId => {
  deviceService.sendOneWayRpcCommand(deviceId, command).subscribe(() => {
    console.log(`Command sent to device: ${deviceId}`);
  });
});
```

### Creating Device with Credentials

```javascript
const device = {
  name: 'New Sensor Device',
  type: 'sensor',
  label: 'Warehouse Sensor #5'
};

const credentials = {
  credentialsType: 'ACCESS_STRING',
  credentialsId: 'warehouse_sensor_05_identifier'
};

deviceService.saveDeviceWithCredentials(device, credentials).subscribe(result => {
  console.log('Created device with credentials:', result);
});
```

## Error Handling

Always handle errors in device operations:

```javascript
deviceService.getDevice(deviceId).subscribe(
  device => {
    console.log('Device loaded:', device);
  },
  error => {
    console.error('Failed to load device:', error);
    // Handle error appropriately
  }
);
```