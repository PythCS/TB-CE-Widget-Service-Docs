# CalculatedFieldsService

### **CALCULATEDFIELDSSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
calculatedFieldsService.getCalculatedFieldById('your-calculatedfield-id', { /* your config */ }).subscribe(calculatedfieldbyid => {
  console.log('Calculated Field By Id:', calculatedfieldbyid);
});
```

**2. saveCalculatedField**

```javascript
calculatedFieldsService.saveCalculatedField({ /* your calculatedField */ }, { /* your config */ }).subscribe(savedCalculatedField => {
  console.log('Saved CalculatedField:', savedCalculatedField);
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField('your-calculatedfield-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**4. getCalculatedFields**

```javascript
calculatedFieldsService.getCalculatedFields(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your query */ }, { /* your config */ }).subscribe(calculatedfield => {
  console.log('Calculated Fields:', calculatedfield);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
calculatedFieldsService.getCalculatedFieldsByEntityId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(calculatedfieldsbyentityid => {
  console.log('Calculated Fields By Entity Id:', calculatedfieldsbyentityid);
});
```

**6. testScript**

```javascript
calculatedFieldsService.testScript({ /* your inputParams */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent('your-id', { /* your config */ }).subscribe(latestcalculatedfielddebugevent => {
  console.log('Latest Calculated Field Debug Event:', latestcalculatedfielddebugevent);
});
```

**8. getCalculatedFieldNames**

```javascript
calculatedFieldsService.getCalculatedFieldNames(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(calculatedfieldname => {
  console.log('Calculated Field Names:', calculatedfieldname);
});
```
