# Edge

```javascript
// Service name: edge
// File: edge.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edge = $injector.get(self.ctx.servicesMap.get('edge'));
```

### **1. getEdges**

```javascript
edge.getEdges(edgeIds).subscribe(edges => {
  console.log('Edges:', edges);
});
```

### **2. getEdge**

```javascript
edge.getEdge(edgeId).subscribe(edge => {
  console.log('Edge:', edge);
});
```

### **3. getEdgeInfo**

```javascript
edge.getEdgeInfo(edgeId).subscribe(edge => {
  console.log('Edge:', edge);
});
```

### **4. saveEdge**

```javascript
edge.saveEdge(edge).subscribe(edge => {
  console.log('Edge:', edge);
});
```

### **5. getEdgeTypes**

```javascript
edge.getEdgeTypes().subscribe(edges => {
  console.log('Edges:', edges);
});
```

### **6. getCustomerEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edge.getCustomerEdgeInfos(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **7. assignEdgeToCustomer**

```javascript
edge.assignEdgeToCustomer(customerId, edgeId).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### **8. makeEdgePublic**

```javascript
edge.makeEdgePublic(edgeId).subscribe(edge => {
  console.log('Edge:', edge);
});
```

### **9. getTenantEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edge.getTenantEdgeInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **10. findByQuery**

```javascript
edge.findByQuery(query).subscribe(findByQuerys => {
  console.log('Find By Querys:', findByQuerys);
});
```

### **11. getEdgeEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edge.getEdgeEvents(pageLink).subscribe(events => {
  console.log('Events:', events);
});
```

### **12. findMissingToRelatedRuleChains**

```javascript
edge.findMissingToRelatedRuleChains(edgeId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **13. findByName**

```javascript
edge.findByName(edgeName).subscribe(find => {
  console.log('Find:', find);
});
```

### **14. bulkImportEdges**

```javascript
edge.bulkImportEdges(entitiesData).subscribe(edge => {
  console.log('Edge:', edge);
});
```

### **15. getEdgeInstallInstructions**

```javascript
edge.getEdgeInstallInstructions(edgeId, method).subscribe(edge => {
  console.log('Edge:', edge);
});
```

### **16. getEdgeUpgradeInstructions**

```javascript
edge.getEdgeUpgradeInstructions(edgeVersion, method).subscribe(edge => {
  console.log('Edge:', edge);
});
```

### **17. isEdgeUpgradeAvailable**

```javascript
edge.isEdgeUpgradeAvailable(edgeId).subscribe(edge => {
  console.log('Edge:', edge);
});
```
