# EDGE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **EDGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

**1. getEdges**

```javascript
edgeService.getEdges('your-id').subscribe(edges => {
  console.log('Get Edges: edges');
});
```

**2. getEdge**

```javascript
edgeService.getEdge('your-edge-id').subscribe(edge => {
  console.log('Get Edge: edge');
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo('your-edge-id').subscribe(edgeInfo => {
  console.log('Get Edge Info: edgeInfo');
});
```

**4. saveEdge**

```javascript
const edge = edge;
edgeService.saveEdge(edge).subscribe(savedEdge => {
  console.log('Save Edge: savedEdge');
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes().subscribe(edgetypes => {
  console.log('Get Edge Types: edgetypes');
});
```

**6. getCustomerEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getCustomerEdgeInfos('your-customer-id', pageLink, 'type').subscribe(customeredgeinfos => {
  console.log('Get Customer Edge Infos: customeredgeinfos');
});
```

**7. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer('your-customer-id', 'your-edge-id').subscribe(result => {
  console.log('Assign Edge To Customer: result');
});
```

**8. makeEdgePublic**

```javascript
edgeService.makeEdgePublic('your-edge-id').subscribe(result => {
  console.log('Make Edge Public: result');
});
```

**9. getTenantEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getTenantEdgeInfos(pageLink, 'type').subscribe(tenantedgeinfos => {
  console.log('Get Tenant Edge Infos: tenantedgeinfos');
});
```

**10. findByQuery**

```javascript
const query = query;
edgeService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**11. getEdgeEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getEdgeEvents('your-entity-id', pageLink).subscribe(edgeevents => {
  console.log('Get Edge Events: edgeevents');
});
```

**12. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains('your-edge-id').subscribe(ruleChains => {
  console.log('Find Missing To Related Rule Chains:ruleChains');
});
```

**13. findByName**

```javascript
const edgeName = edgeName;
edgeService.findByName(edgeName).subscribe(entity => {
  console.log('Find By Name: entity');
});
```

**14. bulkImportEdges**

```javascript
const entitiesData = entitiesData;
edgeService.bulkImportEdges(entitiesData).subscribe(result => {
  console.log('Bulk Import Edges: result');
});
```

**15. getEdgeInstallInstructions**

```javascript
const method = method;
edgeService.getEdgeInstallInstructions('your-edge-id', method).subscribe(edgeinstallinstructions => {
  console.log('Get Edge Install Instructions: edgeinstallinstructions');
});
```

**16. getEdgeUpgradeInstructions**

```javascript
const edgeVersion = edgeVersion;
const method = method;
edgeService.getEdgeUpgradeInstructions(edgeVersion, method).subscribe(edgeupgradeinstructions => {
  console.log('Get Edge Upgrade Instructions: edgeupgradeinstructions');
});
```

**17. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable('your-edge-id').subscribe(result => {
  console.log('Is Edge Upgrade Available: result');
});
```
