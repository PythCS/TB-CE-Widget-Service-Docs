# ATTRIBUTE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
self.ctx.attributeService.getEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-keys-value').subscribe(entityAttributes => {
  console.log('Get Entity Attributes:', entityAttributes);
});
```

**2. deleteEntityAttributes**

```javascript
self.ctx.attributeService.deleteEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entityAttributes => {
  console.log('Delete Entity Attributes:', entityAttributes);
});
```

**3. deleteEntityTimeseries**

```javascript
self.ctx.attributeService.deleteEntityTimeseries('your-entity-id', 'your-timeseries-value', 0, 0).subscribe(entityTimeseries => {
  console.log('Delete Entity Timeseries:', entityTimeseries);
});
```

**4. saveEntityAttributes**

```javascript
self.ctx.attributeService.saveEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entityAttributes => {
  console.log('Save Entity Attributes:', entityAttributes);
});
```

**5. saveEntityTimeseries**

```javascript
self.ctx.attributeService.saveEntityTimeseries('your-entity-id', 'your-timeseriesscope-value', 'your-timeseries-value').subscribe(entityTimeseries => {
  console.log('Save Entity Timeseries:', entityTimeseries);
});
```

**6. getEntityTimeseries**

```javascript
self.ctx.attributeService.getEntityTimeseries('your-entity-id', 'your-keys-value', 0, 0, 'your-limit-value', 'your-agg-value', 0, 'your-orderby-value', 'your-usestrictdatatypes-value').subscribe(entityTimeseries => {
  console.log('Get Entity Timeseries:', entityTimeseries);
});
```

**7. getEntityTimeseriesLatest**

```javascript
self.ctx.attributeService.getEntityTimeseriesLatest('your-entity-id', 'your-keys-value').subscribe(entityTimeseriesLatest => {
  console.log('Get Entity Timeseries Latest:', entityTimeseriesLatest);
});
```
