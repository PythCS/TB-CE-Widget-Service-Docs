# RULE CHAIN SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'value';
ruleChainService.getRuleChains(pageLink, type).subscribe(ruleChains => {
  console.log('List of Rule Chains:', ruleChains);
});
```

**2. getRuleChainsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainIds = ['your-rule-chain-i-1', 'your-rule-chain-i-2'];
ruleChainService.getRuleChainsByIds(ruleChainIds).subscribe(ruleChainsBys => {
  console.log('List of Rule Chains By Ids:', ruleChainsBys);
});
```

**3. getRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.getRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Get Rule Chain:', ruleChain);
});
```

**4. getRuleChainOutputLabels**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.getRuleChainOutputLabels(ruleChainId).subscribe(ruleChainOutputLabels => {
  console.log('List of Rule Chain Output Labels:', ruleChainOutputLabels);
});
```

**5. createDefaultRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainName = 'your-rule-chain-name';
ruleChainService.createDefaultRuleChain(ruleChainName).subscribe(createDefaultRuleChain => {
  console.log('Create Default Rule Chain:', createDefaultRuleChain);
});
```

**6. saveRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChain = {  // RuleChain object
  // ... set the fields you need
};
ruleChainService.saveRuleChain(ruleChain).subscribe(savedRuleChain => {
  console.log('Saved Rule Chain:', savedRuleChain);
});
```

**7. setRootRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setRootRuleChain(ruleChainId).subscribe(setRootRuleChain => {
  console.log('Set Root Rule Chain:', setRootRuleChain);
});
```

**8. getRuleChainMetadata**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.getRuleChainMetadata(ruleChainId).subscribe(ruleChainMetadata => {
  console.log('Get Rule Chain Metadata:', ruleChainMetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainMetaData = {  // RuleChainMetaData object
  // ... set the fields you need
};
ruleChainService.saveRuleChainMetadata(ruleChainMetaData).subscribe(savedRuleChainMetadata => {
  console.log('Saved Rule Chain Metadata:', savedRuleChainMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const modulesMap = {  // IModulesMap object
  // ... set the fields you need
};
const ruleChainType = {  // RuleChainType object
  // ... set the fields you need
};
ruleChainService.getRuleNodeComponents(modulesMap, ruleChainType).subscribe(ruleNodeComponents => {
  console.log('List of Rule Node Components:', ruleNodeComponents);
});
```

**11. getRuleNodeConfigComponent**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const directive = 'your-directive';
const result = ruleChainService.getRuleNodeConfigComponent(directive);
console.log('Result:', result);
```

**12. getRuleNodeComponentByClazz**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainType = 'value';
const clazz = 'your-clazz';
const result = ruleChainService.getRuleNodeComponentByClazz(ruleChainType, clazz);
console.log('Result:', result);
```

**13. getRuleNodeSupportedLinks**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const component = {  // RuleNodeComponentDescriptor object
  // ... set the fields you need
};
const result = ruleChainService.getRuleNodeSupportedLinks(component);
console.log('Result:', result);
```

**14. ruleNodeAllowCustomLinks**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const component = {  // RuleNodeComponentDescriptor object
  // ... set the fields you need
};
const result = ruleChainService.ruleNodeAllowCustomLinks(component);
console.log('Result:', result);
```

**15. ruleNodeSourceRuleChainId**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const component = {  // RuleNodeComponentDescriptor object
  // ... set the fields you need
};
const config = {  // RuleNodeConfiguration object
  // ... set the fields you need
};
const result = ruleChainService.ruleNodeSourceRuleChainId(component, config);
console.log('Result:', result);
```

**16. getLatestRuleNodeDebugInput**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleNodeId = 'your-rule-node-id';
ruleChainService.getLatestRuleNodeDebugInput(ruleNodeId).subscribe(latestRuleNodeDebugInput => {
  console.log('Get Latest Rule Node Debug Input:', latestRuleNodeDebugInput);
});
```

**17. testScript**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const inputParams = {  // TestScriptInputParams object
  // ... set the fields you need
};
const scriptLang = {  // ScriptLanguage object
  // ... set the fields you need
};
ruleChainService.testScript(inputParams, scriptLang).subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**18. loadRuleNodeComponents**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainType = {  // RuleChainType object
  // ... set the fields you need
};
ruleChainService.loadRuleNodeComponents(ruleChainType).subscribe(ruleNodeComponents => {
  console.log('List of Rule Node Components:', ruleNodeComponents);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const components = [];  // e.g. array of components values
const modulesMap = {  // IModulesMap object
  // ... set the fields you need
};
ruleChainService.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(resolveRuleNodeComponentsUiResources => {
  console.log('List of Resolve Rule Node Components Ui Resources:', resolveRuleNodeComponentsUiResources);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const component = {  // RuleNodeComponentDescriptor object
  // ... set the fields you need
};
const modulesMap = {  // IModulesMap object
  // ... set the fields you need
};
ruleChainService.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(resolveRuleNodeComponentUiResources => {
  console.log('Resolve Rule Node Component Ui Resources:', resolveRuleNodeComponentUiResources);
});
```

**21. getEdgeRuleChains**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getEdgeRuleChains(edgeId, pageLink).subscribe(edgeRuleChains => {
  console.log('List of Edge Rule Chains:', edgeRuleChains);
});
```

**22. assignRuleChainToEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.assignRuleChainToEdge(edgeId, ruleChainId).subscribe(assignRuleChainToEdge => {
  console.log('Assign Rule Chain To Edge:', assignRuleChainToEdge);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeTemplateRootRuleChain(ruleChainId).subscribe(setEdgeTemplateRootRuleChain => {
  console.log('Set Edge Template Root Rule Chain:', setEdgeTemplateRootRuleChain);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setAutoAssignToEdgeRuleChain(ruleChainId).subscribe(setAutoAssignToEdgeRuleChain => {
  console.log('Set Auto Assign To Edge Rule Chain:', setAutoAssignToEdgeRuleChain);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const ruleChainId = 'your-rule-chain-id';
ruleChainService.unsetAutoAssignToEdgeRuleChain(ruleChainId).subscribe(unsetAutoAssignToEdgeRuleChain => {
  console.log('Unset Auto Assign To Edge Rule Chain:', unsetAutoAssignToEdgeRuleChain);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoAssignToEdgeRuleChains => {
  console.log('List of Auto Assign To Edge Rule Chains:', autoAssignToEdgeRuleChains);
});
```

**27. setEdgeRootRuleChain**

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeRootRuleChain(edgeId, ruleChainId).subscribe(setEdgeRootRuleChain => {
  console.log('Set Edge Root Rule Chain:', setEdgeRootRuleChain);
});
```
