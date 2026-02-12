### **ATTRIBUTE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeservice = $injector.get(self.ctx.servicesMap.get('attributeservice'));

// Alternative: Direct context access
const attributeservice = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
const attributeservice = self.ctx.attributeService;
attributeservice.getEntityAttributes('your-entity-id', 'your-keys').subscribe(entityattributes => {
  console.log('Entityattributes:', entityattributes);
});
```

**2. deleteEntityAttributes**

```javascript
const attributeservice = self.ctx.attributeService;
attributeservice.deleteEntityAttributes('your-entity-id', attributeScope, attributes).subscribe(deleteentityattributes => {
  console.log('Deleteentityattributes:', deleteentityattributes);
});
```

**3. deleteEntityTimeseries**

```javascript
const attributeservice = self.ctx.attributeService;
attributeservice.deleteEntityTimeseries('your-entity-id', timeseries, 10, 10).subscribe(deleteentitytimeseries => {
  console.log('Deleteentitytimeseries:', deleteentitytimeseries);
});
```

**4. saveEntityAttributes**

```javascript
const attributeservice = self.ctx.attributeService;
attributeservice.saveEntityAttributes('your-entity-id', attributeScope, attributes).subscribe(saveentityattributes => {
  console.log('Saveentityattributes:', saveentityattributes);
});
```

**5. saveEntityTimeseries**

```javascript
const attributeservice = self.ctx.attributeService;
attributeservice.saveEntityTimeseries('your-entity-id', 'your-timeseriesscope', timeseries).subscribe(saveentitytimeseries => {
  console.log('Saveentitytimeseries:', saveentitytimeseries);
});
```

**6. getEntityTimeseries**

```javascript
const attributeservice = self.ctx.attributeService;
attributeservice.getEntityTimeseries('your-entity-id', 'your-keys', 10, 10, 10, agg, 10, orderBy, true).subscribe(entitytimeseries => {
  console.log('Entitytimeseries:', entitytimeseries);
});
```

**7. getEntityTimeseriesLatest**

```javascript
const attributeservice = self.ctx.attributeService;
attributeservice.getEntityTimeseriesLatest('your-entity-id', 'your-keys').subscribe(entitytimeserieslatest => {
  console.log('Entitytimeserieslatest:', entitytimeserieslatest);
});
```

