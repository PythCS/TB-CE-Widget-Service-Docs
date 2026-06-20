# ATTRIBUTE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ATTRIBUTE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
attributeService.getEntityAttributes('your-entity-id', 'SERVER_SCOPE', ['key1', 'key2']).subscribe(entityattributes => {
  console.log('Get Entity Attributes: entityattributes');
});
```

**2. deleteEntityAttributes**

```javascript
attributeService.deleteEntityAttributes('your-entity-id', 'SERVER_SCOPE', [{key: 'key1', value: 'value1'}]).subscribe(result => {
  console.log('Delete Entity Attributes: result');
});
```

**3. deleteEntityTimeseries**

```javascript
const startTs = Date.now() - 86400000;
const endTs = Date.now();
attributeService.deleteEntityTimeseries('your-entity-id', [{key: 'tsKey', ts: Date.now(), value: 42}], startTs, endTs).subscribe(result => {
  console.log('Delete Entity Timeseries: result');
});
```

**4. saveEntityAttributes**

```javascript
attributeService.saveEntityAttributes('your-entity-id', 'SERVER_SCOPE', [{key: 'key1', value: 'value1'}]).subscribe(savedEntityAttributes => {
  console.log('Save Entity Attributes: savedEntityAttributes');
});
```

**5. saveEntityTimeseries**

```javascript
attributeService.saveEntityTimeseries('your-entity-id', 'SERVER_SCOPE', [{key: 'tsKey', ts: Date.now(), value: 42}]).subscribe(savedEntityTimeseries => {
  console.log('Save Entity Timeseries: savedEntityTimeseries');
});
```

**6. getEntityTimeseries**

```javascript
const startTs = Date.now() - 86400000;
const endTs = Date.now();
attributeService.getEntityTimeseries('your-entity-id', ['key1', 'key2'], startTs, endTs, 100, 'NONE', 3600000, 'ASC', 'type').subscribe(entitytimeseries => {
  console.log('Get Entity Timeseries: entitytimeseries');
});
```

**7. getEntityTimeseriesLatest**

```javascript
attributeService.getEntityTimeseriesLatest('your-entity-id', ['key1', 'key2']).subscribe(entityTimeseriesLatest => {
  console.log('Get Entity Timeseries Latest: entityTimeseriesLatest');
});
```
