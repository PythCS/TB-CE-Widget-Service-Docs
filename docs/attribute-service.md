# Attribute Service

Manage device attributes, timeseries data, and attribute-related operations in ThingsBoard.

## Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

## Methods

**1. getEntityAttributes**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'CLIENT_SCOPE'; // or 'SERVER_SCOPE', 'SHARED_SCOPE'
const keys = ['temperature', 'humidity']; // Optional: specific attribute keys

attributeService.getEntityAttributes(entityId, attributeScope, keys).subscribe(attributes => {
  console.log('Entity Attributes:', attributes);
});
```

**2. deleteEntityAttributes**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'CLIENT_SCOPE';
const attributes = [
  { key: 'oldAttribute', value: 'someValue' }
];

attributeService.deleteEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Attributes deleted successfully');
});
```

**3. deleteEntityTimeseries**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const timeseries = [
  { key: 'temperature', value: 25.5 }
];
const startTs = 1609459200000; // Optional start timestamp
const endTs = 1609545600000;   // Optional end timestamp

attributeService.deleteEntityTimeseries(entityId, timeseries, startTs, endTs).subscribe(result => {
  console.log('Timeseries data deleted successfully');
});
```

**4. saveEntityAttributes**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'CLIENT_SCOPE';
const attributes = [
  { key: 'firmware', value: 'v1.2.3' },
  { key: 'location', value: 'Building A' }
];

attributeService.saveEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Attributes saved successfully');
});
```

**5. saveEntityTimeseries**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const timeseriesScope = 'ANY';
const timeseries = [
  { key: 'temperature', ts: Date.now(), value: 25.5 },
  { key: 'humidity', ts: Date.now(), value: 60.0 }
];

attributeService.saveEntityTimeseries(entityId, timeseriesScope, timeseries).subscribe(result => {
  console.log('Timeseries data saved successfully');
});
```

**6. getEntityTimeseries**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const keys = ['temperature', 'humidity'];
const startTs = 1609459200000;
const endTs = Date.now();
const limit = 100;
const agg = 'NONE'; // or 'MIN', 'MAX', 'AVG', 'SUM', 'COUNT'
const interval = 60000; // Optional: aggregation interval in ms
const orderBy = 'ASC'; // or 'DESC'
const useStrictDataTypes = false;

attributeService.getEntityTimeseries(entityId, keys, startTs, endTs, limit, agg, interval, orderBy, useStrictDataTypes).subscribe(timeseriesData => {
  console.log('Timeseries Data:', timeseriesData);
});
```

**7. getEntityTimeseriesLatest**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const keys = ['temperature', 'humidity']; // Optional: specific keys

attributeService.getEntityTimeseriesLatest(entityId, keys).subscribe(latestData => {
  console.log('Latest Timeseries Data:', latestData);
});
```