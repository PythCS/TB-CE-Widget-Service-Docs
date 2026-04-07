# AttributeService

### **ATTRIBUTESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
attributeService.getEntityAttributes('your-entity-id', { /* your attributeScope */ }, ['id1', 'id2'], { /* your config */ }).subscribe(entityattribute => {
  console.log('Entity Attributes:', entityattribute);
});
```

**2. deleteEntityAttributes**

```javascript
attributeService.deleteEntityAttributes('your-entity-id', { /* your attributeScope */ }, ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**3. deleteEntityTimeseries**

```javascript
attributeService.deleteEntityTimeseries('your-entity-id', ['id1', 'id2'], 100, 100, { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**4. saveEntityAttributes**

```javascript
attributeService.saveEntityAttributes('your-entity-id', { /* your attributeScope */ }, ['id1', 'id2'], { /* your config */ }).subscribe(savedEntityAttributes => {
  console.log('Saved EntityAttributes:', savedEntityAttributes);
});
```

**5. saveEntityTimeseries**

```javascript
attributeService.saveEntityTimeseries('your-entity-id', 'your-timeseriesScope', ['id1', 'id2'], { /* your config */ }).subscribe(savedEntityTimeseries => {
  console.log('Saved EntityTimeseries:', savedEntityTimeseries);
});
```

**6. getEntityTimeseries**

```javascript
attributeService.getEntityTimeseries('your-entity-id', ['id1', 'id2'], 100, 100, { /* your limit */ }, { /* your agg */ }, 100, { /* your orderBy */ }, 'your-usestrictdatatypes', { /* your config */ }).subscribe(entitytimeery => {
  console.log('Entity Timeseries:', entitytimeery);
});
```

**7. getEntityTimeseriesLatest**

```javascript
attributeService.getEntityTimeseriesLatest('your-entity-id', ['id1', 'id2'], { /* your config */ }).subscribe(entitytimeserieslatest => {
  console.log('Entity Timeseries Latest:', entitytimeserieslatest);
});
```
