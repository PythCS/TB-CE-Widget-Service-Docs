# ENTITY RELATION SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ENTITY RELATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('entityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
const relation = relation;
entityRelationService.saveRelation(relation).subscribe(savedRelation => {
  console.log('Save Relation: savedRelation');
});
```

**2. getRelation**

```javascript
entityRelationService.getRelation('your-id', 'type', 'your-id').subscribe(relation => {
  console.log('Get Relation: relation');
});
```

**3. findByFrom**

```javascript
entityRelationService.findByFrom('your-id').subscribe(relations => {
  console.log('Find By From: relations');
});
```

**4. findInfoByFrom**

```javascript
entityRelationService.findInfoByFrom('your-id').subscribe(relations => {
  console.log('Find Info By From: relations');
});
```

**5. findByFromAndType**

```javascript
entityRelationService.findByFromAndType('your-id', 'type').subscribe(relations => {
  console.log('Find By From And Type: relations');
});
```

**6. findByTo**

```javascript
entityRelationService.findByTo('your-id').subscribe(relations => {
  console.log('Find By To: relations');
});
```

**7. findInfoByTo**

```javascript
entityRelationService.findInfoByTo('your-id').subscribe(relations => {
  console.log('Find Info By To: relations');
});
```

**8. findByToAndType**

```javascript
entityRelationService.findByToAndType('your-id', 'type').subscribe(relations => {
  console.log('Find By To And Type: relations');
});
```

**9. findByQuery**

```javascript
const query = query;
entityRelationService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**10. findInfoByQuery**

```javascript
const query = query;
entityRelationService.findInfoByQuery(query).subscribe(relations => {
  console.log('Find Info By Query: relations');
});
```
