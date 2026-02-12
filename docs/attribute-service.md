# ATTRIBUTE

Entity attributes and timeseries data.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

## Methods

### getEntityAttributes

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const attributeScope = {
  // your attributeScope object
};
const keys = ['id1', 'id2', 'id3'];

attributeService.getEntityAttributes(entityId, attributeScope, keys).subscribe(result => {
  console.log('EntityAttributes:', result);
});
```

### deleteEntityAttributes

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const attributeScope = {
  // your attributeScope object
};
const attributes = {
  // your attributes object
};

attributeService.deleteEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Deleted Result:', result);
});
```

### deleteEntityTimeseries

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const timeseries = {
  // your timeseries object
};
const startTs = Date.now();
const endTs = Date.now();

attributeService.deleteEntityTimeseries(entityId, timeseries, startTs, endTs).subscribe(result => {
  console.log('Deleted Result:', result);
});
```

### saveEntityAttributes

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const attributeScope = {
  // your attributeScope object
};
const attributes = {
  // your attributes object
};

attributeService.saveEntityAttributes(entityId, attributeScope, attributes).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### saveEntityTimeseries

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const timeseriesScope = 'your-timeseriesscope';
const timeseries = {
  // your timeseries object
};

attributeService.saveEntityTimeseries(entityId, timeseriesScope, timeseries).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getEntityTimeseries

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const keys = ['id1', 'id2', 'id3'];
const startTs = Date.now();
const endTs = Date.now();
const limit = {
  // your limit object
};
const agg = {
  // your agg object
};
const interval = 100;
const orderBy = {
  // your orderBy object
};
const useStrictDataTypes = {
  // your useStrictDataTypes object
};

attributeService.getEntityTimeseries(entityId, keys, startTs, endTs, limit, agg, interval, orderBy, useStrictDataTypes).subscribe(result => {
  console.log('EntityTimeseries:', result);
});
```

### getEntityTimeseriesLatest

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const keys = ['id1', 'id2', 'id3'];

attributeService.getEntityTimeseriesLatest(entityId, keys).subscribe(result => {
  console.log('EntityTimeseriesLatest:', result);
});
```

