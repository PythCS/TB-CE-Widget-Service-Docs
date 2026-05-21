# CalculatedFieldsService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('CalculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
calculatedFieldsService.getCalculatedFieldById('your-calculatedfield-id').subscribe(result => {
  console.log('Fetched  Calculated Field By Id result:', result);
});
```

**2. saveCalculatedField**

```javascript
calculatedFieldsService.saveCalculatedField('your-calculatedfield-value').subscribe(result => {
  console.log('Saved  Calculated Field result:', result);
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField('your-calculatedfield-id').subscribe(result => {
  console.log('Deleted  Calculated Field result:', result);
});
```

**4. getCalculatedFields**

```javascript
calculatedFieldsService.getCalculatedFields(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-query-value').subscribe(result => {
  console.log('Fetched  Calculated Fields result:', result);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
calculatedFieldsService.getCalculatedFieldsByEntityId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(entity => {
  console.log('Fetched  Calculated Fields By Entity Id entity:', entity);
});
```

**6. testScript**

```javascript
calculatedFieldsService.testScript('your-inputparams-value').subscribe(result => {
  console.log('test Script result:', result);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent('your--id').subscribe(result => {
  console.log('Fetched  Latest Calculated Field Debug Event result:', result);
});
```

**8. getCalculatedFieldNames**

```javascript
calculatedFieldsService.getCalculatedFieldNames(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(result => {
  console.log('Fetched  Calculated Field Names result:', result);
});
```
