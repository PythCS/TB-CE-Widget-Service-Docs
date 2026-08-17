# ENTITY RELATION SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('entityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
self.ctx.entityRelationService.saveRelation('your-relation-value').subscribe(relation => {
  console.log('Save Relation:', relation);
});
```

**2. getRelation**

```javascript
self.ctx.entityRelationService.getRelation('your-from-id', 'your-relationtype-value', 'your-to-id').subscribe(relation => {
  console.log('Get Relation:', relation);
});
```

**3. findByFrom**

```javascript
self.ctx.entityRelationService.findByFrom('your-from-id').subscribe(byFrom => {
  console.log('Find By From:', byFrom);
});
```

**4. findInfoByFrom**

```javascript
self.ctx.entityRelationService.findInfoByFrom('your-from-id').subscribe(infoByFrom => {
  console.log('Find Info By From:', infoByFrom);
});
```

**5. findByFromAndType**

```javascript
self.ctx.entityRelationService.findByFromAndType('your-from-id', 'your-relationtype-value').subscribe(byFromAndType => {
  console.log('Find By From And Type:', byFromAndType);
});
```

**6. findByTo**

```javascript
self.ctx.entityRelationService.findByTo('your-to-id').subscribe(byTo => {
  console.log('Find By To:', byTo);
});
```

**7. findInfoByTo**

```javascript
self.ctx.entityRelationService.findInfoByTo('your-to-id').subscribe(infoByTo => {
  console.log('Find Info By To:', infoByTo);
});
```

**8. findByToAndType**

```javascript
self.ctx.entityRelationService.findByToAndType('your-to-id', 'your-relationtype-value').subscribe(byToAndType => {
  console.log('Find By To And Type:', byToAndType);
});
```

**9. findByQuery**

```javascript
self.ctx.entityRelationService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**10. findInfoByQuery**

```javascript
self.ctx.entityRelationService.findInfoByQuery('your-query-value').subscribe(infoByQuery => {
  console.log('Find Info By Query:', infoByQuery);
});
```
