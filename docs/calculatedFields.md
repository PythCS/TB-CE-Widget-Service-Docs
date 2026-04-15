# Calculated Fields

```javascript
// Service name: calculatedFields
// File: calculated-fields.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFields = $injector.get(self.ctx.servicesMap.get('calculatedFields'));
```

### **1. getCalculatedFieldById**

```javascript
calculatedFields.getCalculatedFieldById(calculatedFieldId).subscribe(calculatedField => {
  console.log('Calculated Field:', calculatedField);
});
```

### **2. saveCalculatedField**

```javascript
calculatedFields.saveCalculatedField(calculatedField).subscribe(calculatedField => {
  console.log('Calculated Field:', calculatedField);
});
```

### **3. deleteCalculatedField**

```javascript
calculatedFields.deleteCalculatedField(calculatedFieldId).subscribe(calculatedField => {
  console.log('Calculated Field:', calculatedField);
});
```

### **4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFields.getCalculatedFields(pageLink).subscribe(calculatedFields => {
  console.log('Calculated Fields:', calculatedFields);
});
```

### **5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFields.getCalculatedFieldsByEntityId(pageLink).subscribe(calculatedFields => {
  console.log('Calculated Fields:', calculatedFields);
});
```

### **6. testScript**

```javascript
calculatedFields.testScript(inputParams).subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

### **7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFields.getLatestCalculatedFieldDebugEvent(id).subscribe(calculatedField => {
  console.log('Calculated Field:', calculatedField);
});
```

### **8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFields.getCalculatedFieldNames(pageLink).subscribe(calculatedFields => {
  console.log('Calculated Fields:', calculatedFields);
});
```
