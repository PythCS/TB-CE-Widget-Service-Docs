# Attribute

```javascript
// Service name: attribute
// File: attribute.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const attribute = self.ctx.attributeService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const attribute = $injector.get(self.ctx.servicesMap.get('attribute'));
```

### **1. getEntityAttributes**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
attribute.getEntityAttributes(entityId).subscribe(entitys => {
  console.log('Entitys:', entitys);
});
```

### **2. deleteEntityAttributes**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
attribute.deleteEntityAttributes(entityId).subscribe(entity => {
  console.log('Entity:', entity);
});
```

### **3. deleteEntityTimeseries**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
attribute.deleteEntityTimeseries(entityId).subscribe(entity => {
  console.log('Entity:', entity);
});
```

### **4. saveEntityAttributes**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
attribute.saveEntityAttributes(entityId).subscribe(entity => {
  console.log('Entity:', entity);
});
```

### **5. saveEntityTimeseries**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
attribute.saveEntityTimeseries(entityId).subscribe(entity => {
  console.log('Entity:', entity);
});
```

### **6. getEntityTimeseries**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
attribute.getEntityTimeseries(entityId).subscribe(entity => {
  console.log('Entity:', entity);
});
```

### **7. getEntityTimeseriesLatest**

```javascript
const entityId = { id: 'your-entity-id', entityType: 1 };
attribute.getEntityTimeseriesLatest(entityId).subscribe(entity => {
  console.log('Entity:', entity);
});
```
