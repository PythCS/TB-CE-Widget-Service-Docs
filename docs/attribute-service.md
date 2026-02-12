# Attribute Service

Complete reference for AttributeService - read and write entity attributes, telemetry, and timeseries data.

## Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

## Methods

### getEntityAttributes

Get entity attributes by scope and optional key filter.

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'SERVER_SCOPE'; // or CLIENT_SCOPE, SHARED_SCOPE
const keys = ['temperature', 'humidity']; // optional - get all if not specified
attributeService.getEntityAttributes(entityId, attributeScope, keys).subscribe(attributes => {
  console.log('Entity Attributes:', attributes);
});
```

### saveEntityAttributes

Save attributes to an entity.

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'SERVER_SCOPE';
const attributes = [
  { key: 'temperature', value: 25.5 },
  { key: 'humidity', value: 65 }
];
attributeService.saveEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Saved Attributes:', result);
});
```

### getEntityTimeseries

Get timeseries data for an entity with time range and aggregation.

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const keys = ['temperature', 'humidity'];
const startTs = Date.now() - 86400000; // 24 hours ago
const endTs = Date.now();
const limit = 100;
const agg = 'NONE'; // or AVG, MIN, MAX, SUM, COUNT
const interval = 3600000; // 1 hour in milliseconds
const orderBy = 'ASC'; // or DESC
const useStrictDataTypes = false;
attributeService.getEntityTimeseries(entityId, keys, startTs, endTs, limit, agg, interval, orderBy, useStrictDataTypes).subscribe(timeseries => {
  console.log('Entity Timeseries:', timeseries);
});
```

### getEntityTimeseriesLatest

Get the latest timeseries values for an entity.

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const keys = ['temperature', 'humidity']; // optional
attributeService.getEntityTimeseriesLatest(entityId, keys).subscribe(latestData => {
  console.log('Latest Timeseries:', latestData);
});
```

### saveEntityTimeseries

Save timeseries data to an entity.

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const timeseriesScope = 'ANY';
const timeseries = [
  { key: 'temperature', value: 25.5, ts: Date.now() },
  { key: 'humidity', value: 65, ts: Date.now() }
];
attributeService.saveEntityTimeseries(entityId, timeseriesScope, timeseries).subscribe(result => {
  console.log('Saved Timeseries:', result);
});
```

### deleteEntityAttributes

Delete attributes from an entity.

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'SERVER_SCOPE';
const attributes = [
  { key: 'temperature' },
  { key: 'humidity' }
];
attributeService.deleteEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Deleted Attributes:', result);
});
```

## Common Use Cases

### Real-time Widget Data

```javascript
// Get latest values for widget display
const entityId = self.ctx.defaultSubscription.entityId;
attributeService.getEntityTimeseriesLatest(entityId).subscribe(data => {
  Object.keys(data).forEach(key => {
    console.log(`${key}: ${data[key][0].value}`);
  });
});
```

### Configuration Management

```javascript
// Save device configuration
const deviceId = { entityType: 'DEVICE', id: 'your-device-id' };
const config = [
  { key: 'updateInterval', value: 60 },
  { key: 'threshold', value: 25.0 },
  { key: 'enabled', value: true }
];

attributeService.saveEntityAttributes(deviceId, 'SERVER_SCOPE', config).subscribe(result => {
  console.log('Configuration saved');
});
```

### Historical Data Analysis

```javascript
// Get last 7 days of temperature data with hourly aggregation
const entityId = { entityType: 'DEVICE', id: 'sensor-1' };
const keys = ['temperature'];
const startTs = Date.now() - (7 * 24 * 60 * 60 * 1000); // 7 days ago
const endTs = Date.now();

attributeService.getEntityTimeseries(
  entityId, 
  keys, 
  startTs, 
  endTs, 
  168, // 7 days * 24 hours
  'AVG', 
  3600000, // 1 hour interval
  'ASC', 
  false
).subscribe(data => {
  console.log('Weekly temperature trend:', data);
});
```

## Attribute Scopes

- **SERVER_SCOPE** - Server-side attributes (read-only from device perspective)
- **CLIENT_SCOPE** - Client-side attributes (read-write from device)
- **SHARED_SCOPE** - Shared attributes (server-to-client configuration)

## Related Services

- **DeviceService** - Manage the devices that own the attributes
- **EntityService** - Generic entity operations
- **AlarmService** - Create alarms based on attribute values

See the complete [AttributeService documentation](../DOCUMENTATION.md#attribute-service) for all 7 methods.