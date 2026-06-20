# CALCULATED FIELDS SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **CALCULATED FIELDS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
calculatedFieldsService.getCalculatedFieldById('your-calculated-field-id').subscribe(calculatedFieldById => {
  console.log('Get Calculated Field By Id: calculatedFieldById');
});
```

**2. saveCalculatedField**

```javascript
const calculatedField = calculatedField;
calculatedFieldsService.saveCalculatedField(calculatedField).subscribe(savedCalculatedField => {
  console.log('Save Calculated Field: savedCalculatedField');
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField('your-calculated-field-id').subscribe(result => {
  console.log('Delete Calculated Field: result');
});
```

**4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = query;
calculatedFieldsService.getCalculatedFields(pageLink, query).subscribe(calculatedfields => {
  console.log('Get Calculated Fields: calculatedfields');
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, 'type').subscribe(calculatedFieldsByEntityId => {
  console.log('Get Calculated Fields By Entity Id:calculatedFieldsByEntityId');
});
```

**6. testScript**

```javascript
const inputParams = inputParams;
calculatedFieldsService.testScript(inputParams).subscribe(result => {
  console.log('Test Script: result');
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent('your-id').subscribe(latestCalculatedFieldDebugEvent => {
  console.log('Get Latest Calculated Field Debug Event:latestCalculatedFieldDebugEvent');
});
```

**8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldNames(pageLink, 'type').subscribe(calculatedfieldnames => {
  console.log('Get Calculated Field Names: calculatedfieldnames');
});
```
