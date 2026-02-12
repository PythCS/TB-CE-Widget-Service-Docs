# CALCULATED FIELDS

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

## Methods

### getCalculatedFieldById

```javascript
const calculatedFieldId = 'your-calculatedfield-id';

calculatedFieldsService.getCalculatedFieldById(calculatedFieldId).subscribe(result => {
  console.log('CalculatedFieldById:', result);
});
```

### saveCalculatedField

```javascript
const calculatedField = {
  // your calculatedField object
};

calculatedFieldsService.saveCalculatedField(calculatedField).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### deleteCalculatedField

```javascript
const calculatedFieldId = 'your-calculatedfield-id';

calculatedFieldsService.deleteCalculatedField(calculatedFieldId).subscribe(result => {
  console.log('Result:', result);
});
```

### getCalculatedFields

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = {
  // your query object
};

calculatedFieldsService.getCalculatedFields(pageLink, query).subscribe(info => {
  console.log('Info:', info);
});
```

### getCalculatedFieldsByEntityId

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, type).subscribe(result => {
  console.log('CalculatedFieldsByEntityId:', result);
});
```

### testScript

```javascript
const inputParams = {
  // your inputParams object
};

calculatedFieldsService.testScript(inputParams).subscribe(result => {
  console.log('Result:', result);
});
```

### getLatestCalculatedFieldDebugEvent

```javascript
const id = 'your--id';

calculatedFieldsService.getLatestCalculatedFieldDebugEvent(id).subscribe(result => {
  console.log('LatestCalculatedFieldDebugEvent:', result);
});
```

### getCalculatedFieldNames

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

calculatedFieldsService.getCalculatedFieldNames(pageLink, type).subscribe(result => {
  console.log('Result:', result);
});
```

