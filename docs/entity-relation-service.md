# ENTITY RELATION SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('entityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const relation = {  // EntityRelation object
  // ... set the fields you need
};
entityRelationService.saveRelation(relation).subscribe(savedRelation => {
  console.log('Saved Relation:', savedRelation);
});
```

**2. getRelation**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const fromId = {  // EntityId object
  // ... set the fields you need
};
const relationType = 'your-relation-type';
const toId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.getRelation(fromId, relationType, toId).subscribe(relation => {
  console.log('Get Relation:', relation);
});
```

**3. findByFrom**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const fromId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.findByFrom(fromId).subscribe(byFroms => {
  console.log('List of By Froms:', byFroms);
});
```

**4. findInfoByFrom**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const fromId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.findInfoByFrom(fromId).subscribe(infoByFroms => {
  console.log('List of Info By Froms:', infoByFroms);
});
```

**5. findByFromAndType**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const fromId = {  // EntityId object
  // ... set the fields you need
};
const relationType = 'your-relation-type';
entityRelationService.findByFromAndType(fromId, relationType).subscribe(byFromAndTypes => {
  console.log('List of By From And Types:', byFromAndTypes);
});
```

**6. findByTo**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const toId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.findByTo(toId).subscribe(byTos => {
  console.log('List of By Tos:', byTos);
});
```

**7. findInfoByTo**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const toId = {  // EntityId object
  // ... set the fields you need
};
entityRelationService.findInfoByTo(toId).subscribe(infoByTos => {
  console.log('List of Info By Tos:', infoByTos);
});
```

**8. findByToAndType**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const toId = {  // EntityId object
  // ... set the fields you need
};
const relationType = 'your-relation-type';
entityRelationService.findByToAndType(toId, relationType).subscribe(byToAndTypes => {
  console.log('List of By To And Types:', byToAndTypes);
});
```

**9. findByQuery**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const query = {  // EntityRelationsQuery object
  // ... set the fields you need
};
entityRelationService.findByQuery(query).subscribe(byQuerys => {
  console.log('List of By Querys:', byQuerys);
});
```

**10. findInfoByQuery**

```javascript
const entityRelationService = self.ctx.entityRelationService;
const query = {  // EntityRelationsQuery object
  // ... set the fields you need
};
entityRelationService.findInfoByQuery(query).subscribe(infoByQuerys => {
  console.log('List of Info By Querys:', infoByQuerys);
});
```
