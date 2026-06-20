# RULE CHAIN SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **RULE CHAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getRuleChains(pageLink, 'type').subscribe(rulechains => {
  console.log('Get Rule Chains: rulechains');
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds('your-id').subscribe(rulechainsbyids => {
  console.log('Get Rule Chains By Ids: rulechainsbyids');
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain('your-rule-chain-id').subscribe(ruleChain => {
  console.log('Get Rule Chain: ruleChain');
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels('your-rule-chain-id').subscribe(rulechainoutputlabels => {
  console.log('Get Rule Chain Output Labels: rulechainoutputlabels');
});
```

**5. createDefaultRuleChain**

```javascript
const ruleChainName = ruleChainName;
ruleChainService.createDefaultRuleChain(ruleChainName).subscribe(result => {
  console.log('Create Default Rule Chain: result');
});
```

**6. saveRuleChain**

```javascript
const ruleChain = ruleChain;
ruleChainService.saveRuleChain(ruleChain).subscribe(savedRuleChain => {
  console.log('Save Rule Chain: savedRuleChain');
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain('your-rule-chain-id').subscribe(result => {
  console.log('Set Root Rule Chain: result');
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata('your-rule-chain-id').subscribe(ruleChainMetadata => {
  console.log('Get Rule Chain Metadata: ruleChainMetadata');
});
```

**9. saveRuleChainMetadata**

```javascript
const ruleChainMetaData = ruleChainMetaData;
ruleChainService.saveRuleChainMetadata(ruleChainMetaData).subscribe(savedRuleChainMetadata => {
  console.log('Save Rule Chain Metadata: savedRuleChainMetadata');
});
```

**10. getRuleNodeComponents**

```javascript
const modulesMap = modulesMap;
ruleChainService.getRuleNodeComponents(modulesMap, 'type').subscribe(rulenodecomponents => {
  console.log('Get Rule Node Components: rulenodecomponents');
});
```

**11. getRuleNodeConfigComponent**

```javascript
const directive = directive;
ruleChainService.getRuleNodeConfigComponent(directive).subscribe(ruleNodeConfigComponent => {
  console.log('Get Rule Node Config Component:ruleNodeConfigComponent');
});
```

**12. getRuleNodeComponentByClazz**

```javascript
const clazz = clazz;
ruleChainService.getRuleNodeComponentByClazz('type', clazz).subscribe(ruleNodeComponentByClazz => {
  console.log('Get Rule Node Component By Clazz:ruleNodeComponentByClazz');
});
```

**13. getRuleNodeSupportedLinks**

```javascript
const component = component;
ruleChainService.getRuleNodeSupportedLinks(component).subscribe(rulenodesupportedlinks => {
  console.log('Get Rule Node Supported Links: rulenodesupportedlinks');
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
const component = component;
ruleChainService.ruleNodeAllowCustomLinks(component).subscribe(result => {
  console.log('Rule Node Allow Custom Links: result');
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
const component = component;
ruleChainService.ruleNodeSourceRuleChainId(component).subscribe(result => {
  console.log('Rule Node Source Rule Chain Id:result');
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput('your-id').subscribe(latestRuleNodeDebugInput => {
  console.log('Get Latest Rule Node Debug Input:latestRuleNodeDebugInput');
});
```

**17. testScript**

```javascript
const inputParams = inputParams;
const scriptLang = scriptLang;
ruleChainService.testScript(inputParams, scriptLang).subscribe(result => {
  console.log('Test Script: result');
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents('type').subscribe(result => {
  console.log('Load Rule Node Components: result');
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
const components = components;
const modulesMap = modulesMap;
ruleChainService.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(result => {
  console.log('Resolve Rule Node Components Ui Resources:result');
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
const component = component;
const modulesMap = modulesMap;
ruleChainService.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(result => {
  console.log('Resolve Rule Node Component Ui Resources:result');
});
```

**21. getEdgeRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getEdgeRuleChains('your-edge-id', pageLink).subscribe(edgerulechains => {
  console.log('Get Edge Rule Chains: edgerulechains');
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge('your-edge-id', 'your-rule-chain-id').subscribe(result => {
  console.log('Assign Rule Chain To Edge: result');
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain('your-rule-chain-id').subscribe(result => {
  console.log('Set Edge Template Root Rule Chain:result');
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain('your-rule-chain-id').subscribe(result => {
  console.log('Set Auto Assign To Edge Rule Chain:result');
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain('your-rule-chain-id').subscribe(result => {
  console.log('Unset Auto Assign To Edge Rule Chain:result');
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoassigntoedgerulechains => {
  console.log('Get Auto Assign To Edge Rule Chains:autoassigntoedgerulechains');
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain('your-edge-id', 'your-rule-chain-id').subscribe(result => {
  console.log('Set Edge Root Rule Chain: result');
});
```
