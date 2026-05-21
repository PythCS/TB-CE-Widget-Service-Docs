# EntityRelationService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('EntityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
entityRelationService.saveRelation('your-relation-value').subscribe(result => {
  console.log('Saved  Relation result:', result);
});
```

**2. getRelation**

```javascript
entityRelationService.getRelation('your-from-id', 'your-relationtype-value', 'your-to-id').subscribe(result => {
  console.log('Fetched  Relation result:', result);
});
```

**3. findByFrom**

```javascript
entityRelationService.findByFrom('your-from-id').subscribe(result => {
  console.log('find By From result:', result);
});
```

**4. findInfoByFrom**

```javascript
entityRelationService.findInfoByFrom('your-from-id').subscribe(info => {
  console.log('find Info By From info:', info);
});
```

**5. findByFromAndType**

```javascript
entityRelationService.findByFromAndType('your-from-id', 'your-relationtype-value').subscribe(result => {
  console.log('find By From And Type result:', result);
});
```

**6. findByTo**

```javascript
entityRelationService.findByTo('your-to-id').subscribe(result => {
  console.log('find By To result:', result);
});
```

**7. findInfoByTo**

```javascript
entityRelationService.findInfoByTo('your-to-id').subscribe(info => {
  console.log('find Info By To info:', info);
});
```

**8. findByToAndType**

```javascript
entityRelationService.findByToAndType('your-to-id', 'your-relationtype-value').subscribe(result => {
  console.log('find By To And Type result:', result);
});
```

**9. findByQuery**

```javascript
entityRelationService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**10. findInfoByQuery**

```javascript
entityRelationService.findInfoByQuery('your-query-value').subscribe(info => {
  console.log('find Info By Query info:', info);
});
```
