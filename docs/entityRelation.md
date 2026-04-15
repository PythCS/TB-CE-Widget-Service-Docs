# Entity Relation

```javascript
// Service name: entityRelation
// File: entity-relation.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const entityRelation = self.ctx.entityRelationService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const entityRelation = $injector.get(self.ctx.servicesMap.get('entityRelation'));
```

### **1. saveRelation**

```javascript
entityRelation.saveRelation(relation).subscribe(saveRelation => {
  console.log('Save Relation:', saveRelation);
});
```

### **2. getRelation**

```javascript
entityRelation.getRelation(fromId, relationType, toId).subscribe(relation => {
  console.log('Relation:', relation);
});
```

### **3. findByFrom**

```javascript
entityRelation.findByFrom(fromId).subscribe(findByFroms => {
  console.log('Find By Froms:', findByFroms);
});
```

### **4. findInfoByFrom**

```javascript
entityRelation.findInfoByFrom(fromId).subscribe(findInfoByFroms => {
  console.log('Find Info By Froms:', findInfoByFroms);
});
```

### **5. findByFromAndType**

```javascript
entityRelation.findByFromAndType(fromId, relationType).subscribe(findByFromAndTypes => {
  console.log('Find By From And Types:', findByFromAndTypes);
});
```

### **6. findByTo**

```javascript
entityRelation.findByTo(toId).subscribe(findByTos => {
  console.log('Find By Tos:', findByTos);
});
```

### **7. findInfoByTo**

```javascript
entityRelation.findInfoByTo(toId).subscribe(findInfoByTos => {
  console.log('Find Info By Tos:', findInfoByTos);
});
```

### **8. findByToAndType**

```javascript
entityRelation.findByToAndType(toId, relationType).subscribe(findByToAndTypes => {
  console.log('Find By To And Types:', findByToAndTypes);
});
```

### **9. findByQuery**

```javascript
entityRelation.findByQuery(query).subscribe(findByQuerys => {
  console.log('Find By Querys:', findByQuerys);
});
```

### **10. findInfoByQuery**

```javascript
entityRelation.findInfoByQuery(query).subscribe(findInfoByQuerys => {
  console.log('Find Info By Querys:', findInfoByQuerys);
});
```
