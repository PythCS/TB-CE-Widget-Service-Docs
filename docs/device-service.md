# Device Service

Complete reference for DeviceService - manage devices, credentials, RPC commands, and device operations.

## Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

## Methods

### getTenantDeviceInfos

Get paginated list of tenant devices with optional type filtering.

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = ''; // empty string for all types
deviceService.getTenantDeviceInfos(pageLink, type).subscribe(devices => {
  console.log('Tenant Devices:', devices);
});
```

### getDevice

Get a specific device by ID.

```javascript
const deviceId = 'your-device-id';
deviceService.getDevice(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

### saveDevice

Create or update a device.

```javascript
const device = {
  name: 'My Device',
  type: 'thermostat'
};
deviceService.saveDevice(device).subscribe(savedDevice => {
  console.log('Saved Device:', savedDevice);
});
```

### getDeviceCredentials

Get device credentials for connectivity.

```javascript
const deviceId = 'your-device-id';
const sync = false;
deviceService.getDeviceCredentials(deviceId, sync).subscribe(credentials => {
  console.log('Device Credentials:', credentials);
});
```

### sendTwoWayRpcCommand

Send RPC command and wait for response.

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  method: 'getTemperature',
  timeout: 5000
};
deviceService.sendTwoWayRpcCommand(deviceId, requestBody).subscribe(response => {
  console.log('RPC Response:', response);
});
```

### assignDeviceToCustomer

Assign a device to a customer.

```javascript
const customerId = 'your-customer-id';
const deviceId = 'your-device-id';
deviceService.assignDeviceToCustomer(customerId, deviceId).subscribe(assignedDevice => {
  console.log('Assigned Device:', assignedDevice);
});
```

### findByName

Find device by name.

```javascript
const deviceName = 'Device Name';
deviceService.findByName(deviceName).subscribe(device => {
  console.log('Device by Name:', device);
});
```

## Common Use Cases

### Device Management Dashboard

```javascript
// Get all devices
const pageLink = self.ctx.pageLink(50, 0, '', 'name', 'ASC');
deviceService.getTenantDeviceInfos(pageLink, '').subscribe(devices => {
  // Display in table or list
  devices.data.forEach(device => {
    console.log(`${device.name} - ${device.type}`);
  });
});
```

### Device Control Widget

```javascript
// Send command to device
const deviceId = self.ctx.datasources[0].entity.id;
const command = {
  method: 'setValue',
  params: { value: 25 }
};

deviceService.sendTwoWayRpcCommand(deviceId, command).subscribe(
  response => {
    console.log('Command successful:', response);
  },
  error => {
    console.error('Command failed:', error);
  }
);
```

### Device Provisioning

```javascript
// Create new device with credentials
const device = {
  name: 'New Sensor',
  type: 'temperature_sensor',
  label: 'Office Temperature Sensor'
};

const credentials = {
  credentialsType: 'ACCESS_TOKEN',
  credentialsId: 'my-unique-token-123'
};

deviceService.saveDeviceWithCredentials(device, credentials).subscribe(result => {
  console.log('Device created with credentials:', result);
});
```

## Related Services

- **AttributeService** - Read/write device attributes and telemetry
- **AlarmService** - Manage device alarms
- **DeviceProfileService** - Manage device configurations
- **EntityRelationService** - Create relationships between devices

See the complete [DeviceService documentation](../DOCUMENTATION.md#device-service) for all 29 methods.