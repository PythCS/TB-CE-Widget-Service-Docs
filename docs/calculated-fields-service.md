# CALCULATED FIELDS SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const calculatedFieldId = 'your-calculated-field-id';
calculatedFieldsService.getCalculatedFieldById(calculatedFieldId).subscribe(calculatedFieldBy => {
  console.log('Get Calculated Field By Id:', calculatedFieldBy);
});
```

**2. saveCalculatedField**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const calculatedField = {  // CalculatedField object
  // ... set the fields you need
};
calculatedFieldsService.saveCalculatedField(calculatedField).subscribe(savedCalculatedField => {
  console.log('Saved Calculated Field:', savedCalculatedField);
});
```

**3. deleteCalculatedField**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const calculatedFieldId = 'your-calculated-field-id';
calculatedFieldsService.deleteCalculatedField(calculatedFieldId).subscribe(result => {
  console.log('Delete Calculated Field result:', result);
});
```

**4. getCalculatedFields**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = {  // CalculatedFieldsQuery object
  // ... set the fields you need
};
calculatedFieldsService.getCalculatedFields(pageLink, query).subscribe(calculatedFields => {
  console.log('List of Calculated Fields:', calculatedFields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {  // CalculatedFieldType object
  // ... set the fields you need
};
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, type).subscribe(calculatedFieldsByEntitys => {
  console.log('List of Calculated Fields By Entity Ids:', calculatedFieldsByEntitys);
});
```

**6. testScript**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const inputParams = {  // CalculatedFieldTestScriptInputParams object
  // ... set the fields you need
};
calculatedFieldsService.testScript(inputParams).subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const id = 'your-id';
calculatedFieldsService.getLatestCalculatedFieldDebugEvent(id).subscribe(latestCalculatedFieldDebugEvent => {
  console.log('Get Latest Calculated Field Debug Event:', latestCalculatedFieldDebugEvent);
});
```

**8. getCalculatedFieldNames**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {  // CalculatedFieldType object
  // ... set the fields you need
};
calculatedFieldsService.getCalculatedFieldNames(pageLink, type).subscribe(calculatedFieldNames => {
  console.log('List of Calculated Field Names:', calculatedFieldNames);
});
```

**9. reprocessCalculatedField**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const id = 'your-id';
const startTs = 10;
const endTs = 10;
calculatedFieldsService.reprocessCalculatedField(id, startTs, endTs).subscribe(reprocessCalculatedField => {
  console.log('Reprocess Calculated Field:', reprocessCalculatedField);
});
```

**10. getLastCalculatedFieldReprocessingJob**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const id = 'your-id';
calculatedFieldsService.getLastCalculatedFieldReprocessingJob(id).subscribe(lastCalculatedFieldReprocessingJob => {
  console.log('Get Last Calculated Field Reprocessing Job:', lastCalculatedFieldReprocessingJob);
});
```

**11. validateCalculatedFieldReprocessing**

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
const id = 'your-id';
calculatedFieldsService.validateCalculatedFieldReprocessing(id).subscribe(validateCalculatedFieldReprocessing => {
  console.log('Validate Calculated Field Reprocessing:', validateCalculatedFieldReprocessing);
});
```
