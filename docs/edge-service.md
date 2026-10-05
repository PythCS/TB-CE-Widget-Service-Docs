# EDGE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

**1. getEdges**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeIds = ['your-edge-i-1', 'your-edge-i-2'];
edgeService.getEdges(edgeIds).subscribe(edges => {
  console.log('List of Edges:', edges);
});
```

**2. getEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.getEdge(edgeId).subscribe(edge => {
  console.log('Get Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.getEdgeInfo(edgeId).subscribe(edgeInfo => {
  console.log('Get Edge Info:', edgeInfo);
});
```

**4. saveEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edge = {  // Edge object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
edgeService.saveEdge(edge, entityGroupIds).subscribe(savedEdge => {
  console.log('Saved Edge:', savedEdge);
});
```

**5. getEdgeTypes**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
edgeService.getEdgeTypes().subscribe(edgeTypes => {
  console.log('List of Edge Types:', edgeTypes);
});
```

**6. assignEdgeToCustomer**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const customerId = 'your-customer-id';
const edgeId = 'your-edge-id';
edgeService.assignEdgeToCustomer(customerId, edgeId).subscribe(assignEdgeToCustomer => {
  console.log('Assign Edge To Customer:', assignEdgeToCustomer);
});
```

**7. makeEdgePublic**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.makeEdgePublic(edgeId).subscribe(makeEdgePublic => {
  console.log('Make Edge Public:', makeEdgePublic);
});
```

**8. getTenantEdges**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getTenantEdges(pageLink, type).subscribe(tenantEdges => {
  console.log('List of Tenant Edges:', tenantEdges);
});
```

**9. getTenantEdgeInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getTenantEdgeInfos(pageLink, type).subscribe(tenantEdgeInfos => {
  console.log('List of Tenant Edge Infos:', tenantEdgeInfos);
});
```

**10. getUserEdges**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getUserEdges(pageLink, type).subscribe(userEdges => {
  console.log('List of User Edges:', userEdges);
});
```

**11. getAllEdgeInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getAllEdgeInfos(includeCustomers, pageLink, type).subscribe(allEdgeInfos => {
  console.log('List of All Edge Infos:', allEdgeInfos);
});
```

**12. getCustomerEdgeInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
edgeService.getCustomerEdgeInfos(includeCustomers, customerId, pageLink, type).subscribe(customerEdgeInfos => {
  console.log('List of Customer Edge Infos:', customerEdgeInfos);
});
```

**13. findByQuery**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const query = {  // EdgeSearchQuery object
  // ... set the fields you need
};
edgeService.findByQuery(query).subscribe(byQuerys => {
  console.log('List of By Querys:', byQuerys);
});
```

**14. getEdgeEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const entityId = {  // EntityId object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getEdgeEvents(entityId, pageLink).subscribe(edgeEvents => {
  console.log('List of Edge Events:', edgeEvents);
});
```

**15. findMissingToRelatedRuleChains**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.findMissingToRelatedRuleChains(edgeId).subscribe(missingToRelatedRuleChains => {
  console.log('Find Missing To Related Rule Chains:', missingToRelatedRuleChains);
});
```

**16. findByName**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeName = 'your-edge-name';
edgeService.findByName(edgeName).subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**17. bulkImportEdges**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const entitiesData = {  // BulkImportRequest object
  // ... set the fields you need
};
edgeService.bulkImportEdges(entitiesData).subscribe(bulkImportEdges => {
  console.log('Bulk Import Edges:', bulkImportEdges);
});
```

**18. getEdgeInstallInstructions**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
const method = 'value';
edgeService.getEdgeInstallInstructions(edgeId, method).subscribe(edgeInstallInstructions => {
  console.log('Get Edge Install Instructions:', edgeInstallInstructions);
});
```

**19. getEdgeUpgradeInstructions**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeVersion = 'your-edge-version';
const method = 'value';
edgeService.getEdgeUpgradeInstructions(edgeVersion, method).subscribe(edgeUpgradeInstructions => {
  console.log('Get Edge Upgrade Instructions:', edgeUpgradeInstructions);
});
```

**20. findAllRelatedEdgesMissingAttributes**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const integrationId = 'your-integration-id';
edgeService.findAllRelatedEdgesMissingAttributes(integrationId).subscribe(allRelatedEdgesMissingAttributes => {
  console.log('Find All Related Edges Missing Attributes:', allRelatedEdgesMissingAttributes);
});
```

**21. findEdgeMissingAttributes**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const integrationIds = ['your-integration-i-1', 'your-integration-i-2'];
const edgeId = 'your-edge-id';
edgeService.findEdgeMissingAttributes(integrationIds, edgeId).subscribe(edgeMissingAttributes => {
  console.log('Find Edge Missing Attributes:', edgeMissingAttributes);
});
```

**22. isEdgeUpgradeAvailable**

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
const edgeId = 'your-edge-id';
edgeService.isEdgeUpgradeAvailable(edgeId).subscribe(isEdgeUpgradeAvailable => {
  console.log('Is Edge Upgrade Available:', isEdgeUpgradeAvailable);
});
```
