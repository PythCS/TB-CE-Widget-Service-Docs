# EdgeService

### **EDGESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

**1. getEdges**

```javascript
edgeService.getEdges(['id1', 'id2'], { /* your config */ }).subscribe(edge => {
  console.log('Edges:', edge);
});
```

**2. getEdge**

```javascript
edgeService.getEdge('your-edge-id', { /* your config */ }).subscribe(edge => {
  console.log('Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo('your-edge-id', { /* your config */ }).subscribe(edgeinfo => {
  console.log('Edge Info:', edgeinfo);
});
```

**4. saveEdge**

```javascript
edgeService.saveEdge({ /* your edge object */ }, { /* your config */ }).subscribe(savedEdge => {
  console.log('Saved Edge:', savedEdge);
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes({ /* your config */ }).subscribe(edgetype => {
  console.log('Edge Types:', edgetype);
});
```

**6. getCustomerEdgeInfos**

```javascript
edgeService.getCustomerEdgeInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(cutomeredgeinfo => {
  console.log('Customer Edge Infos:', cutomeredgeinfo);
});
```

**7. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer('your-customer-id', 'your-edge-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. makeEdgePublic**

```javascript
edgeService.makeEdgePublic('your-edge-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. getTenantEdgeInfos**

```javascript
edgeService.getTenantEdgeInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(tenantedgeinfo => {
  console.log('Tenant Edge Infos:', tenantedgeinfo);
});
```

**10. findByQuery**

```javascript
edgeService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. getEdgeEvents**

```javascript
edgeService.getEdgeEvents('your-entity-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(edgeevent => {
  console.log('Edge Events:', edgeevent);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains('your-edge-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. findByName**

```javascript
edgeService.findByName('your-edgeName', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**14. bulkImportEdges**

```javascript
edgeService.bulkImportEdges({ /* your entitiesData */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getEdgeInstallInstructions**

```javascript
edgeService.getEdgeInstallInstructions('your-edge-id', { /* your method */ }, { /* your config */ }).subscribe(edgeintallintruction => {
  console.log('Edge Install Instructions:', edgeintallintruction);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
edgeService.getEdgeUpgradeInstructions('your-edgeVersion', { /* your method */ }, { /* your config */ }).subscribe(edgeupgradeintruction => {
  console.log('Edge Upgrade Instructions:', edgeupgradeintruction);
});
```

**17. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable('your-edge-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
