# CALCULATED FIELDS SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
calculatedFieldsService.getCalculatedFieldById('your-calculatedfield-id').subscribe(field => {
  console.log('Get Calculated Field By Id:', field);
});
```

**2. saveCalculatedField**

```javascript
calculatedFieldsService.saveCalculatedField('your-calculatedfield-value').subscribe(calculatedField => {
  console.log('Save Calculated Field:', calculatedField);
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField('your-calculatedfield-id').subscribe(calculatedField => {
  console.log('Delete Calculated Field:', calculatedField);
});
```

**4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFields(pageLink, 'your-query-value').subscribe(fields => {
  console.log('Get Calculated Fields:', fields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, 'your-type-value').subscribe(calculatedFieldsByEntityId => {
  console.log('Get Calculated Fields By Entity Id:', calculatedFieldsByEntityId);
});
```

**6. testScript**

```javascript
calculatedFieldsService.testScript('your-inputparams-value').subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent('your--id').subscribe(latestCalculatedFieldDebugEvent => {
  console.log('Get Latest Calculated Field Debug Event:', latestCalculatedFieldDebugEvent);
});
```

**8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldNames(pageLink, 'your-type-value').subscribe(calculatedFieldNames => {
  console.log('Get Calculated Field Names:', calculatedFieldNames);
});
```
