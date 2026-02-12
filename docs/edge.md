### **EDGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeservice = $injector.get(self.ctx.servicesMap.get('edgeservice'));

```

**1. getEdges**

```javascript
edgeservice.getEdges('your-edges-id').subscribe(edges => {
  console.log('Edges:', edges);
});
```

**2. getEdge**

```javascript
edgeservice.getEdge('your-edge-id').subscribe(edge => {
  console.log('Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
edgeservice.getEdgeInfo('your-edge-id').subscribe(edgeinfo => {
  console.log('Edgeinfo:', edgeinfo);
});
```

**4. saveEdge**

```javascript
edgeservice.saveEdge(edge).subscribe(saveedge => {
  console.log('Saveedge:', saveedge);
});
```

**5. getEdgeTypes**

```javascript
edgeservice.getEdgeTypes().subscribe(edgetypes => {
  console.log('Edgetypes:', edgetypes);
});
```

**6. getCustomerEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeservice.getCustomerEdgeInfos(pageLink, 'your-customer-id', 'your-type').subscribe(customeredgeinfos => {
  console.log('Customeredgeinfos:', customeredgeinfos);
});
```

**7. assignEdgeToCustomer**

```javascript
edgeservice.assignEdgeToCustomer('your-customer-id', 'your-edge-id').subscribe(assignedgetocustomer => {
  console.log('Assignedgetocustomer:', assignedgetocustomer);
});
```

**8. makeEdgePublic**

```javascript
edgeservice.makeEdgePublic('your-edge-id').subscribe(makeedgepublic => {
  console.log('Makeedgepublic:', makeedgepublic);
});
```

**9. getTenantEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeservice.getTenantEdgeInfos(pageLink, 'your-type').subscribe(tenantedgeinfos => {
  console.log('Tenantedgeinfos:', tenantedgeinfos);
});
```

**10. findByQuery**

```javascript
edgeservice.findByQuery(query).subscribe(byquery => {
  console.log('Byquery:', byquery);
});
```

**11. getEdgeEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeservice.getEdgeEvents(pageLink, 'your-entity-id').subscribe(edgeevents => {
  console.log('Edgeevents:', edgeevents);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
edgeservice.findMissingToRelatedRuleChains('your-edge-id').subscribe(missingtorelatedrulechains => {
  console.log('Missingtorelatedrulechains:', missingtorelatedrulechains);
});
```

**13. findByName**

```javascript
edgeservice.findByName('Device Name').subscribe(byname => {
  console.log('Byname:', byname);
});
```

**14. bulkImportEdges**

```javascript
edgeservice.bulkImportEdges(entitiesData).subscribe(bulkimportedges => {
  console.log('Bulkimportedges:', bulkimportedges);
});
```

**15. getEdgeInstallInstructions**

```javascript
edgeservice.getEdgeInstallInstructions('your-edge-id', 'your-method').subscribe(edgeinstallinstructions => {
  console.log('Edgeinstallinstructions:', edgeinstallinstructions);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
edgeservice.getEdgeUpgradeInstructions('your-edgeversion', 'your-method').subscribe(edgeupgradeinstructions => {
  console.log('Edgeupgradeinstructions:', edgeupgradeinstructions);
});
```

**17. isEdgeUpgradeAvailable**

```javascript
edgeservice.isEdgeUpgradeAvailable('your-edge-id').subscribe(isedgeupgradeavailable => {
  console.log('Isedgeupgradeavailable:', isedgeupgradeavailable);
});
```

