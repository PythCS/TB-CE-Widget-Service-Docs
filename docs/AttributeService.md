# AttributeService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('AttributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
attributeService.getEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-api-key').subscribe(entity => {
  console.log('Fetched  Entity Attributes entity:', entity);
});
```

**2. deleteEntityAttributes**

```javascript
attributeService.deleteEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entity => {
  console.log('Deleted  Entity Attributes entity:', entity);
});
```

**3. deleteEntityTimeseries**

```javascript
attributeService.deleteEntityTimeseries('your-entity-id', 'your-timeseries-value', 0, 0).subscribe(entity => {
  console.log('Deleted  Entity Timeseries entity:', entity);
});
```

**4. saveEntityAttributes**

```javascript
attributeService.saveEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entity => {
  console.log('Saved  Entity Attributes entity:', entity);
});
```

**5. saveEntityTimeseries**

```javascript
attributeService.saveEntityTimeseries('your-entity-id', 'your-timeseriesscope-value', 'your-timeseries-value').subscribe(entity => {
  console.log('Saved  Entity Timeseries entity:', entity);
});
```

**6. getEntityTimeseries**

```javascript
attributeService.getEntityTimeseries('your-entity-id', 'your-api-key', 0, 0, 'your-limit-value', 'your-agg-value', 0, 'your-orderby-value', 'your-usestrictdatatypes-value').subscribe(entity => {
  console.log('Fetched  Entity Timeseries entity:', entity);
});
```

**7. getEntityTimeseriesLatest**

```javascript
attributeService.getEntityTimeseriesLatest('your-entity-id', 'your-api-key').subscribe(entity => {
  console.log('Fetched  Entity Timeseries Latest entity:', entity);
});
```
