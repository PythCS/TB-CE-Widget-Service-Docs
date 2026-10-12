# EDGE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

**1. getEdges**

```javascript
edgeService.getEdges('your-edgeids-value').subscribe(edges => {
  console.log('Get Edges:', edges);
});
```

**2. getEdge**

```javascript
edgeService.getEdge('your-edge-id').subscribe(edge => {
  console.log('Get Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo('your-edge-id').subscribe(info => {
  console.log('Get Edge Info:', info);
});
```

**4. saveEdge**

```javascript
edgeService.saveEdge('your-edge-value', 'your-entitygroupids-value').subscribe(edge => {
  console.log('Save Edge:', edge);
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes().subscribe(edgeTypes => {
  console.log('Get Edge Types:', edgeTypes);
});
```

**6. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer('your-customer-id', 'your-edge-id').subscribe(edgeToCustomer => {
  console.log('Assign Edge To Customer:', edgeToCustomer);
});
```

**7. makeEdgePublic**

```javascript
edgeService.makeEdgePublic('your-edge-id').subscribe(makeEdgePublic => {
  console.log('Make Edge Public:', makeEdgePublic);
});
```

**8. getTenantEdges**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getTenantEdges(pageLink, 'your-type-value').subscribe(tenantEdges => {
  console.log('Get Tenant Edges:', tenantEdges);
});
```

**9. getTenantEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getTenantEdgeInfos(pageLink, 'your-type-value').subscribe(tenantEdgeInfos => {
  console.log('Get Tenant Edge Infos:', tenantEdgeInfos);
});
```

**10. getUserEdges**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getUserEdges(pageLink, 'your-type-value').subscribe(userEdges => {
  console.log('Get User Edges:', userEdges);
});
```

**11. getAllEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getAllEdgeInfos(true, pageLink, 'your-type-value').subscribe(allEdgeInfos => {
  console.log('Get All Edge Infos:', allEdgeInfos);
});
```

**12. getCustomerEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getCustomerEdgeInfos(true, 'your-customer-id', pageLink, 'your-type-value').subscribe(customerEdgeInfos => {
  console.log('Get Customer Edge Infos:', customerEdgeInfos);
});
```

**13. findByQuery**

```javascript
edgeService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**14. getEdgeEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getEdgeEvents('your-entity-id', pageLink).subscribe(edgeEvents => {
  console.log('Get Edge Events:', edgeEvents);
});
```

**15. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains('your-edge-id').subscribe(missingToRelatedRuleChains => {
  console.log('Find Missing To Related Rule Chains:', missingToRelatedRuleChains);
});
```

**16. findByName**

```javascript
edgeService.findByName('your-edgename-value').subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**17. bulkImportEdges**

```javascript
edgeService.bulkImportEdges('your-entitiesdata-value').subscribe(bulkImportEdges => {
  console.log('Bulk Import Edges:', bulkImportEdges);
});
```

**18. getEdgeInstallInstructions**

```javascript
edgeService.getEdgeInstallInstructions('your-edge-id', 'your-method-value').subscribe(edgeInstallInstructions => {
  console.log('Get Edge Install Instructions:', edgeInstallInstructions);
});
```

**19. getEdgeUpgradeInstructions**

```javascript
edgeService.getEdgeUpgradeInstructions('your-edgeversion-value', 'your-method-value').subscribe(edgeUpgradeInstructions => {
  console.log('Get Edge Upgrade Instructions:', edgeUpgradeInstructions);
});
```

**20. findAllRelatedEdgesMissingAttributes**

```javascript
edgeService.findAllRelatedEdgesMissingAttributes('your-integration-id').subscribe(allRelatedEdgesMissingAttributes => {
  console.log('Find All Related Edges Missing Attributes:', allRelatedEdgesMissingAttributes);
});
```

**21. findEdgeMissingAttributes**

```javascript
edgeService.findEdgeMissingAttributes('your-integrationids-value', 'your-edge-id').subscribe(edgeMissingAttributes => {
  console.log('Find Edge Missing Attributes:', edgeMissingAttributes);
});
```

**22. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable('your-edge-id').subscribe(isEdgeUpgradeAvailable => {
  console.log('Is Edge Upgrade Available:', isEdgeUpgradeAvailable);
});
```
