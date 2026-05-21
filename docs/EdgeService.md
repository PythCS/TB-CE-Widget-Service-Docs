# EdgeService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('EdgeService'));
```

**1. getEdges**

```javascript
edgeService.getEdges('your-edgeids-value').subscribe(result => {
  console.log('Fetched  Edges result:', result);
});
```

**2. getEdge**

```javascript
edgeService.getEdge('your-edge-id').subscribe(result => {
  console.log('Fetched  Edge result:', result);
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo('your-edge-id').subscribe(info => {
  console.log('Fetched  Edge Info info:', info);
});
```

**4. saveEdge**

```javascript
edgeService.saveEdge('your-edge-value').subscribe(result => {
  console.log('Saved  Edge result:', result);
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes().subscribe(result => {
  console.log('Fetched  Edge Types result:', result);
});
```

**6. getCustomerEdgeInfos**

```javascript
edgeService.getCustomerEdgeInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(info => {
  console.log('Fetched  Customer Edge Infos info:', info);
});
```

**7. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer('your-customer-id', 'your-edge-id').subscribe(result => {
  console.log('assign Edge To Customer result:', result);
});
```

**8. makeEdgePublic**

```javascript
edgeService.makeEdgePublic('your-edge-id').subscribe(result => {
  console.log('make Edge Public result:', result);
});
```

**9. getTenantEdgeInfos**

```javascript
edgeService.getTenantEdgeInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(tenant => {
  console.log('Fetched  Tenant Edge Infos tenant:', tenant);
});
```

**10. findByQuery**

```javascript
edgeService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**11. getEdgeEvents**

```javascript
edgeService.getEdgeEvents('your-entity-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Edge Events result:', result);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains('your-edge-id').subscribe(rule => {
  console.log('find Missing To Related Rule Chains rule:', rule);
});
```

**13. findByName**

```javascript
edgeService.findByName('your-edgename-value').subscribe(result => {
  console.log('find By Name result:', result);
});
```

**14. bulkImportEdges**

```javascript
edgeService.bulkImportEdges('your-entitiesdata-value').subscribe(result => {
  console.log('bulk Import Edges result:', result);
});
```

**15. getEdgeInstallInstructions**

```javascript
edgeService.getEdgeInstallInstructions('your-edge-id', 'your-method-value').subscribe(result => {
  console.log('Fetched  Edge Install Instructions result:', result);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
edgeService.getEdgeUpgradeInstructions('your-edgeversion-value', 'your-method-value').subscribe(result => {
  console.log('Fetched  Edge Upgrade Instructions result:', result);
});
```

**17. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable('your-edge-id').subscribe(result => {
  console.log('is Edge Upgrade Available result:', result);
});
```
