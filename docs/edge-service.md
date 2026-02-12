# EDGE

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

## Methods

### getEdges

```javascript
const edgeIds = 'your-edges-id';

edgeService.getEdges(edgeIds).subscribe(result => {
  console.log('Edges:', result);
});
```

### getEdge

```javascript
const edgeId = 'your-edge-id';

edgeService.getEdge(edgeId).subscribe(result => {
  console.log('Edge:', result);
});
```

### getEdgeInfo

```javascript
const edgeId = 'your-edge-id';

edgeService.getEdgeInfo(edgeId).subscribe(info => {
  console.log('Info:', info);
});
```

### saveEdge

```javascript
const edge = {
  // your edge object
};

edgeService.saveEdge(edge).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getEdgeTypes

```javascript
edgeService.getEdgeTypes().subscribe(result => {
  console.log('EdgeTypes:', result);
});
```

### getCustomerEdgeInfos

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

edgeService.getCustomerEdgeInfos(customerId, pageLink, type).subscribe(info => {
  console.log('Info:', info);
});
```

### assignEdgeToCustomer

```javascript
const customerId = 'your-customer-id';
const edgeId = 'your-edge-id';

edgeService.assignEdgeToCustomer(customerId, edgeId).subscribe(result => {
  console.log('assignEdgeToCustomer:', result);
});
```

### makeEdgePublic

```javascript
const edgeId = 'your-edge-id';

edgeService.makeEdgePublic(edgeId).subscribe(result => {
  console.log('makeEdgePublic:', result);
});
```

### getTenantEdgeInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

edgeService.getTenantEdgeInfos(pageLink, type).subscribe(info => {
  console.log('Info:', info);
});
```

### findByQuery

```javascript
const query = {
  // your query object
};

edgeService.findByQuery(query).subscribe(result => {
  console.log('findByQuery:', result);
});
```

### getEdgeEvents

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

edgeService.getEdgeEvents(entityId, pageLink).subscribe(result => {
  console.log('EdgeEvents:', result);
});
```

### findMissingToRelatedRuleChains

```javascript
const edgeId = 'your-edge-id';

edgeService.findMissingToRelatedRuleChains(edgeId).subscribe(result => {
  console.log('Result:', result);
});
```

### findByName

```javascript
const edgeName = 'your-edgename';

edgeService.findByName(edgeName).subscribe(result => {
  console.log('findByName:', result);
});
```

### bulkImportEdges

```javascript
const entitiesData = {
  // your entitiesData object
};

edgeService.bulkImportEdges(entitiesData).subscribe(result => {
  console.log('Result:', result);
});
```

### getEdgeInstallInstructions

```javascript
const edgeId = 'your-edge-id';
const method = {
  // your method object
};

edgeService.getEdgeInstallInstructions(edgeId, method).subscribe(result => {
  console.log('EdgeInstallInstructions:', result);
});
```

### getEdgeUpgradeInstructions

```javascript
const edgeVersion = 'your-edgeversion';
const method = {
  // your method object
};

edgeService.getEdgeUpgradeInstructions(edgeVersion, method).subscribe(result => {
  console.log('EdgeUpgradeInstructions:', result);
});
```

### isEdgeUpgradeAvailable

```javascript
const edgeId = 'your-edge-id';

edgeService.isEdgeUpgradeAvailable(edgeId).subscribe(result => {
  console.log('Result:', result);
});
```

