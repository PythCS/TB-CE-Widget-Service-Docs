# ENTITY RELATION

Entity relationship management.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('entityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

## Methods

### saveRelation

```javascript
const relation = {
  // your relation object
};

entityRelationService.saveRelation(relation).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getRelation

```javascript
const fromId = { entityType: 'DEVICE', id: 'your-from-id' };
const relationType = 'your-relationtype';
const toId = { entityType: 'DEVICE', id: 'your-to-id' };

entityRelationService.getRelation(fromId, relationType, toId).subscribe(result => {
  console.log('Relation:', result);
});
```

### findByFrom

```javascript
const fromId = { entityType: 'DEVICE', id: 'your-from-id' };

entityRelationService.findByFrom(fromId).subscribe(result => {
  console.log('findByFrom:', result);
});
```

### findInfoByFrom

```javascript
const fromId = { entityType: 'DEVICE', id: 'your-from-id' };

entityRelationService.findInfoByFrom(fromId).subscribe(info => {
  console.log('Info:', info);
});
```

### findByFromAndType

```javascript
const fromId = { entityType: 'DEVICE', id: 'your-from-id' };
const relationType = 'your-relationtype';

entityRelationService.findByFromAndType(fromId, relationType).subscribe(result => {
  console.log('findByFromAndType:', result);
});
```

### findByTo

```javascript
const toId = { entityType: 'DEVICE', id: 'your-to-id' };

entityRelationService.findByTo(toId).subscribe(result => {
  console.log('findByTo:', result);
});
```

### findInfoByTo

```javascript
const toId = { entityType: 'DEVICE', id: 'your-to-id' };

entityRelationService.findInfoByTo(toId).subscribe(info => {
  console.log('Info:', info);
});
```

### findByToAndType

```javascript
const toId = { entityType: 'DEVICE', id: 'your-to-id' };
const relationType = 'your-relationtype';

entityRelationService.findByToAndType(toId, relationType).subscribe(result => {
  console.log('findByToAndType:', result);
});
```

### findByQuery

```javascript
const query = {
  // your query object
};

entityRelationService.findByQuery(query).subscribe(result => {
  console.log('findByQuery:', result);
});
```

### findInfoByQuery

```javascript
const query = {
  // your query object
};

entityRelationService.findInfoByQuery(query).subscribe(info => {
  console.log('Info:', info);
});
```

