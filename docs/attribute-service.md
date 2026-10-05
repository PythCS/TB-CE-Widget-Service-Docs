# ATTRIBUTE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const attributeScope = {  // AttributeScope object
  // ... set the fields you need
};
const keys = [];  // e.g. array of keys values
attributeService.getEntityAttributes(entityId, attributeScope, keys).subscribe(entityAttributes => {
  console.log('List of Entity Attributes:', entityAttributes);
});
```

**2. deleteEntityAttributes**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const attributeScope = {  // AttributeScope object
  // ... set the fields you need
};
const attributes = [];  // e.g. array of attributes values
attributeService.deleteEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Delete Entity Attributes result:', result);
});
```

**3. deleteEntityTimeseries**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const timeseries = [];  // e.g. array of timeseries values
const startTs = 10;
const endTs = 10;
attributeService.deleteEntityTimeseries(entityId, timeseries, startTs, endTs).subscribe(result => {
  console.log('Delete Entity Timeseries result:', result);
});
```

**4. saveEntityAttributes**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const attributeScope = {  // AttributeScope object
  // ... set the fields you need
};
const attributes = [];  // e.g. array of attributes values
attributeService.saveEntityAttributes(entityId, attributeScope, attributes).subscribe(savedEntityAttributes => {
  console.log('Saved Entity Attributes:', savedEntityAttributes);
});
```

**5. saveEntityTimeseries**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const timeseriesScope = 'your-timeseries-scope';
const timeseries = [];  // e.g. array of timeseries values
attributeService.saveEntityTimeseries(entityId, timeseriesScope, timeseries).subscribe(savedEntityTimeseries => {
  console.log('Saved Entity Timeseries:', savedEntityTimeseries);
});
```

**6. getEntityTimeseries**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const keys = [];  // e.g. array of keys values
const startTs = 10;
const endTs = 10;
const limit = 'value';
const agg = 'value';
const interval = 10;
const orderBy = 'value';
const useStrictDataTypes = 'value';
attributeService.getEntityTimeseries(entityId, keys, startTs, endTs, limit, agg, interval, orderBy, useStrictDataTypes).subscribe(entityTimeseries => {
  console.log('Get Entity Timeseries:', entityTimeseries);
});
```

**7. getEntityTimeseriesLatest**

```javascript
const attributeService = self.ctx.attributeService;
const entityId = {  // EntityId object
  // ... set the fields you need
};
const keys = [];  // e.g. array of keys values
attributeService.getEntityTimeseriesLatest(entityId, keys).subscribe(entityTimeseriesLatest => {
  console.log('Get Entity Timeseries Latest:', entityTimeseriesLatest);
});
```
