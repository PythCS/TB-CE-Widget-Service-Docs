# Rule Chain

```javascript
// Service name: ruleChain
// File: rule-chain.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChain = $injector.get(self.ctx.servicesMap.get('ruleChain'));
```

### **1. getRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChain.getRuleChains(pageLink).subscribe(ruleChains => {
  console.log('Rule Chains:', ruleChains);
});
```

### **2. getRuleChainsByIds**

```javascript
ruleChain.getRuleChainsByIds(ruleChainIds).subscribe(ruleChains => {
  console.log('Rule Chains:', ruleChains);
});
```

### **3. getRuleChain**

```javascript
ruleChain.getRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **4. getRuleChainOutputLabels**

```javascript
ruleChain.getRuleChainOutputLabels(ruleChainId).subscribe(ruleChains => {
  console.log('Rule Chains:', ruleChains);
});
```

### **5. createDefaultRuleChain**

```javascript
ruleChain.createDefaultRuleChain(ruleChainName).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **6. saveRuleChain**

```javascript
ruleChain.saveRuleChain(ruleChain).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **7. setRootRuleChain**

```javascript
ruleChain.setRootRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **8. getRuleChainMetadata**

```javascript
ruleChain.getRuleChainMetadata(ruleChainId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **9. saveRuleChainMetadata**

```javascript
ruleChain.saveRuleChainMetadata(ruleChainMetaData).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **10. getRuleNodeComponents**

```javascript
ruleChain.getRuleNodeComponents(modulesMap, ruleChainType).subscribe(rules => {
  console.log('Rules:', rules);
});
```

### **11. getRuleNodeConfigComponent**

```javascript
ruleChain.getRuleNodeConfigComponent(directive).subscribe(rule => {
  console.log('Rule:', rule);
});
```

### **12. getRuleNodeComponentByClazz**

```javascript
ruleChain.getRuleNodeComponentByClazz(ruleChainType, clazz).subscribe(rule => {
  console.log('Rule:', rule);
});
```

### **13. getRuleNodeSupportedLinks**

```javascript
ruleChain.getRuleNodeSupportedLinks(component).subscribe(rule => {
  console.log('Rule:', rule);
});
```

### **14. ruleNodeAllowCustomLinks**

```javascript
ruleChain.ruleNodeAllowCustomLinks(component).subscribe(ruleNodeowCustomLink => {
  console.log('Rule Nodeow Custom Link:', ruleNodeowCustomLink);
});
```

### **15. ruleNodeSourceRuleChainId**

```javascript
ruleChain.ruleNodeSourceRuleChainId(component, config).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **16. getLatestRuleNodeDebugInput**

```javascript
ruleChain.getLatestRuleNodeDebugInput(ruleNodeId).subscribe(rule => {
  console.log('Rule:', rule);
});
```

### **17. testScript**

```javascript
ruleChain.testScript(inputParams).subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

### **18. loadRuleNodeComponents**

```javascript
ruleChain.loadRuleNodeComponents(ruleChainType).subscribe(rules => {
  console.log('Rules:', rules);
});
```

### **19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChain.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(resources => {
  console.log('Resources:', resources);
});
```

### **20. resolveRuleNodeComponentUiResources**

```javascript
ruleChain.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(resource => {
  console.log('Resource:', resource);
});
```

### **21. getEdgeRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChain.getEdgeRuleChains(pageLink).subscribe(ruleChains => {
  console.log('Rule Chains:', ruleChains);
});
```

### **22. assignRuleChainToEdge**

```javascript
ruleChain.assignRuleChainToEdge(edgeId, ruleChainId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **23. setEdgeTemplateRootRuleChain**

```javascript
ruleChain.setEdgeTemplateRootRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChain.setAutoAssignToEdgeRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChain.unsetAutoAssignToEdgeRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

### **26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChain.getAutoAssignToEdgeRuleChains().subscribe(ruleChains => {
  console.log('Rule Chains:', ruleChains);
});
```

### **27. setEdgeRootRuleChain**

```javascript
ruleChain.setEdgeRootRuleChain(edgeId, ruleChainId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```
