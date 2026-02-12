### **CALCULATED FIELDS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedfieldsservice = $injector.get(self.ctx.servicesMap.get('calculatedfieldsservice'));

```

**1. getCalculatedFieldById**

```javascript
calculatedfieldsservice.getCalculatedFieldById('your-calculatedfield-id').subscribe(calculatedfieldbyid => {
  console.log('Calculatedfieldbyid:', calculatedfieldbyid);
});
```

**2. saveCalculatedField**

```javascript
calculatedfieldsservice.saveCalculatedField(calculatedField).subscribe(savecalculatedfield => {
  console.log('Savecalculatedfield:', savecalculatedfield);
});
```

**3. deleteCalculatedField**

```javascript
calculatedfieldsservice.deleteCalculatedField('your-calculatedfield-id').subscribe(deletecalculatedfield => {
  console.log('Deletecalculatedfield:', deletecalculatedfield);
});
```

**4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedfieldsservice.getCalculatedFields(pageLink, query).subscribe(calculatedfields => {
  console.log('Calculatedfields:', calculatedfields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedfieldsservice.getCalculatedFieldsByEntityId(pageLink).subscribe(calculatedfieldsbyentityid => {
  console.log('Calculatedfieldsbyentityid:', calculatedfieldsbyentityid);
});
```

**6. testScript**

```javascript
calculatedfieldsservice.testScript(inputParams).subscribe(testscript => {
  console.log('Testscript:', testscript);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedfieldsservice.getLatestCalculatedFieldDebugEvent('your-id-id').subscribe(latestcalculatedfielddebugevent => {
  console.log('Latestcalculatedfielddebugevent:', latestcalculatedfielddebugevent);
});
```

**8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedfieldsservice.getCalculatedFieldNames(pageLink, type).subscribe(calculatedfieldnames => {
  console.log('Calculatedfieldnames:', calculatedfieldnames);
});
```

