### **RULE CHAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const rulechainservice = $injector.get(self.ctx.servicesMap.get('rulechainservice'));

```

**1. getRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
rulechainservice.getRuleChains(pageLink, type).subscribe(rulechains => {
  console.log('Rulechains:', rulechains);
});
```

**2. getRuleChainsByIds**

```javascript
rulechainservice.getRuleChainsByIds('your-rulechains-id').subscribe(rulechainsbyids => {
  console.log('Rulechainsbyids:', rulechainsbyids);
});
```

**3. getRuleChain**

```javascript
rulechainservice.getRuleChain('your-rulechain-id').subscribe(rulechain => {
  console.log('Rulechain:', rulechain);
});
```

**4. getRuleChainOutputLabels**

```javascript
rulechainservice.getRuleChainOutputLabels('your-rulechain-id').subscribe(rulechainoutputlabels => {
  console.log('Rulechainoutputlabels:', rulechainoutputlabels);
});
```

**5. createDefaultRuleChain**

```javascript
rulechainservice.createDefaultRuleChain('Device Name').subscribe(createdefaultrulechain => {
  console.log('Createdefaultrulechain:', createdefaultrulechain);
});
```

**6. saveRuleChain**

```javascript
rulechainservice.saveRuleChain(ruleChain).subscribe(saverulechain => {
  console.log('Saverulechain:', saverulechain);
});
```

**7. setRootRuleChain**

```javascript
rulechainservice.setRootRuleChain('your-rulechain-id').subscribe(setrootrulechain => {
  console.log('Setrootrulechain:', setrootrulechain);
});
```

**8. getRuleChainMetadata**

```javascript
rulechainservice.getRuleChainMetadata('your-rulechain-id').subscribe(rulechainmetadata => {
  console.log('Rulechainmetadata:', rulechainmetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
rulechainservice.saveRuleChainMetadata(ruleChainMetaData).subscribe(saverulechainmetadata => {
  console.log('Saverulechainmetadata:', saverulechainmetadata);
});
```

**10. getRuleNodeComponents**

```javascript
rulechainservice.getRuleNodeComponents(modulesMap, ruleChainType).subscribe(rulenodecomponents => {
  console.log('Rulenodecomponents:', rulenodecomponents);
});
```

**11. getRuleNodeConfigComponent**

```javascript
const result = rulechainservice.getRuleNodeConfigComponent('your-directive');
console.log('Result:', result);
```

**12. getRuleNodeComponentByClazz**

```javascript
const result = rulechainservice.getRuleNodeComponentByClazz(ruleChainType, 'your-clazz');
console.log('Result:', result);
```

**13. getRuleNodeSupportedLinks**

```javascript
const result = rulechainservice.getRuleNodeSupportedLinks(component);
console.log('Result:', result);
```

**14. ruleNodeAllowCustomLinks**

```javascript
const result = rulechainservice.ruleNodeAllowCustomLinks(component);
console.log('Result:', result);
```

**15. ruleNodeSourceRuleChainId**

```javascript
const result = rulechainservice.ruleNodeSourceRuleChainId(component, config);
console.log('Result:', result);
```

**16. getLatestRuleNodeDebugInput**

```javascript
rulechainservice.getLatestRuleNodeDebugInput('your-rulenode-id').subscribe(latestrulenodedebuginput => {
  console.log('Latestrulenodedebuginput:', latestrulenodedebuginput);
});
```

**17. testScript**

```javascript
rulechainservice.testScript(inputParams).subscribe(testscript => {
  console.log('Testscript:', testscript);
});
```

**18. loadRuleNodeComponents**

```javascript
rulechainservice.loadRuleNodeComponents(ruleChainType).subscribe(rulenodecomponents => {
  console.log('Rulenodecomponents:', rulenodecomponents);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
rulechainservice.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(resolverulenodecomponentsuiresources => {
  console.log('Resolverulenodecomponentsuiresources:', resolverulenodecomponentsuiresources);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
rulechainservice.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(resolverulenodecomponentuiresources => {
  console.log('Resolverulenodecomponentuiresources:', resolverulenodecomponentuiresources);
});
```

**21. getEdgeRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
rulechainservice.getEdgeRuleChains(pageLink, 'your-edge-id').subscribe(edgerulechains => {
  console.log('Edgerulechains:', edgerulechains);
});
```

**22. assignRuleChainToEdge**

```javascript
rulechainservice.assignRuleChainToEdge('your-edge-id', 'your-rulechain-id').subscribe(assignrulechaintoedge => {
  console.log('Assignrulechaintoedge:', assignrulechaintoedge);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
rulechainservice.setEdgeTemplateRootRuleChain('your-rulechain-id').subscribe(setedgetemplaterootrulechain => {
  console.log('Setedgetemplaterootrulechain:', setedgetemplaterootrulechain);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
rulechainservice.setAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(setautoassigntoedgerulechain => {
  console.log('Setautoassigntoedgerulechain:', setautoassigntoedgerulechain);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
rulechainservice.unsetAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(unsetautoassigntoedgerulechain => {
  console.log('Unsetautoassigntoedgerulechain:', unsetautoassigntoedgerulechain);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
rulechainservice.getAutoAssignToEdgeRuleChains().subscribe(autoassigntoedgerulechains => {
  console.log('Autoassigntoedgerulechains:', autoassigntoedgerulechains);
});
```

**27. setEdgeRootRuleChain**

```javascript
rulechainservice.setEdgeRootRuleChain('your-edge-id', 'your-rulechain-id').subscribe(setedgerootrulechain => {
  console.log('Setedgerootrulechain:', setedgerootrulechain);
});
```

