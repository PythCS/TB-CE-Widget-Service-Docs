### **ENTITY RELATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityrelationservice = $injector.get(self.ctx.servicesMap.get('entityrelationservice'));

// Alternative: Direct context access
const entityrelationservice = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.saveRelation(relation).subscribe(saverelation => {
  console.log('Saverelation:', saverelation);
});
```

**2. getRelation**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.getRelation('your-from-id', 'your-relationtype', 'your-to-id').subscribe(relation => {
  console.log('Relation:', relation);
});
```

**3. findByFrom**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.findByFrom('your-from-id').subscribe(byfrom => {
  console.log('Byfrom:', byfrom);
});
```

**4. findInfoByFrom**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.findInfoByFrom('your-from-id').subscribe(infobyfrom => {
  console.log('Infobyfrom:', infobyfrom);
});
```

**5. findByFromAndType**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.findByFromAndType('your-from-id', 'your-relationtype').subscribe(byfromandtype => {
  console.log('Byfromandtype:', byfromandtype);
});
```

**6. findByTo**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.findByTo('your-to-id').subscribe(byto => {
  console.log('Byto:', byto);
});
```

**7. findInfoByTo**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.findInfoByTo('your-to-id').subscribe(infobyto => {
  console.log('Infobyto:', infobyto);
});
```

**8. findByToAndType**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.findByToAndType('your-to-id', 'your-relationtype').subscribe(bytoandtype => {
  console.log('Bytoandtype:', bytoandtype);
});
```

**9. findByQuery**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.findByQuery(query).subscribe(byquery => {
  console.log('Byquery:', byquery);
});
```

**10. findInfoByQuery**

```javascript
const entityrelationservice = self.ctx.entityRelationService;
entityrelationservice.findInfoByQuery(query).subscribe(infobyquery => {
  console.log('Infobyquery:', infobyquery);
});
```

