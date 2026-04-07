# EntityRelationService

### **ENTITYRELATIONSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('entityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
entityRelationService.saveRelation({ /* your relation */ }, { /* your config */ }).subscribe(savedRelation => {
  console.log('Saved Relation:', savedRelation);
});
```

**2. getRelation**

```javascript
entityRelationService.getRelation('your-from-id', 'your-relationtype', 'your-to-id', { /* your config */ }).subscribe(relation => {
  console.log('Relation:', relation);
});
```

**3. findByFrom**

```javascript
entityRelationService.findByFrom('your-from-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. findInfoByFrom**

```javascript
entityRelationService.findInfoByFrom('your-from-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. findByFromAndType**

```javascript
entityRelationService.findByFromAndType('your-from-id', 'your-relationtype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. findByTo**

```javascript
entityRelationService.findByTo('your-to-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. findInfoByTo**

```javascript
entityRelationService.findInfoByTo('your-to-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. findByToAndType**

```javascript
entityRelationService.findByToAndType('your-to-id', 'your-relationtype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. findByQuery**

```javascript
entityRelationService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. findInfoByQuery**

```javascript
entityRelationService.findInfoByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
