# RULE CHAIN SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getRuleChains(pageLink, 'your-type-value').subscribe(ruleChains => {
  console.log('Get Rule Chains:', ruleChains);
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds('your-rulechainids-value').subscribe(ruleChainsByIds => {
  console.log('Get Rule Chains By Ids:', ruleChainsByIds);
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain('your-rulechain-id').subscribe(ruleChain => {
  console.log('Get Rule Chain:', ruleChain);
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels('your-rulechain-id').subscribe(ruleChainOutputLabels => {
  console.log('Get Rule Chain Output Labels:', ruleChainOutputLabels);
});
```

**5. createDefaultRuleChain**

```javascript
ruleChainService.createDefaultRuleChain('your-rulechainname-value').subscribe(defaultRuleChain => {
  console.log('Create Default Rule Chain:', defaultRuleChain);
});
```

**6. saveRuleChain**

```javascript
ruleChainService.saveRuleChain('your-rulechain-value').subscribe(ruleChain => {
  console.log('Save Rule Chain:', ruleChain);
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain('your-rulechain-id').subscribe(rootRuleChain => {
  console.log('Set Root Rule Chain:', rootRuleChain);
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata('your-rulechain-id').subscribe(ruleChainMetadata => {
  console.log('Get Rule Chain Metadata:', ruleChainMetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
ruleChainService.saveRuleChainMetadata('your-rulechainmetadata-value').subscribe(ruleChainMetadata => {
  console.log('Save Rule Chain Metadata:', ruleChainMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
ruleChainService.getRuleNodeComponents('your-modulesmap-value', 'your-rulechaintype-value').subscribe(ruleNodeComponents => {
  console.log('Get Rule Node Components:', ruleNodeComponents);
});
```

**11. getRuleNodeConfigComponent**

```javascript
ruleChainService.getRuleNodeConfigComponent('your-directive-value').subscribe(ruleNodeConfigComponent => {
  console.log('Get Rule Node Config Component:', ruleNodeConfigComponent);
});
```

**12. getRuleNodeComponentByClazz**

```javascript
ruleChainService.getRuleNodeComponentByClazz('your-rulechaintype-value', 'your-clazz-value').subscribe(ruleNodeComponentByClazz => {
  console.log('Get Rule Node Component By Clazz:', ruleNodeComponentByClazz);
});
```

**13. getRuleNodeSupportedLinks**

```javascript
ruleChainService.getRuleNodeSupportedLinks('your-component-value').subscribe(ruleNodeSupportedLinks => {
  console.log('Get Rule Node Supported Links:', ruleNodeSupportedLinks);
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
ruleChainService.ruleNodeAllowCustomLinks('your-component-value').subscribe(ruleNodeAllowCustomLinks => {
  console.log('Rule Node Allow Custom Links:', ruleNodeAllowCustomLinks);
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
ruleChainService.ruleNodeSourceRuleChainId('your-component-value').subscribe(ruleNodeSourceRuleChainId => {
  console.log('Rule Node Source Rule Chain Id:', ruleNodeSourceRuleChainId);
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput('your-rulenode-id').subscribe(latestRuleNodeDebugInput => {
  console.log('Get Latest Rule Node Debug Input:', latestRuleNodeDebugInput);
});
```

**17. testScript**

```javascript
ruleChainService.testScript('your-inputparams-value', 'your-scriptlang-value').subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents('your-rulechaintype-value').subscribe(loadRuleNodeComponents => {
  console.log('Load Rule Node Components:', loadRuleNodeComponents);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentsUiResources('your-components-value', 'your-modulesmap-value').subscribe(resolveRuleNodeComponentsUiResources => {
  console.log('Resolve Rule Node Components Ui Resources:', resolveRuleNodeComponentsUiResources);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentUiResources('your-component-value', 'your-modulesmap-value').subscribe(resolveRuleNodeComponentUiResources => {
  console.log('Resolve Rule Node Component Ui Resources:', resolveRuleNodeComponentUiResources);
});
```

**21. getEdgeRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getEdgeRuleChains('your-edge-id', pageLink).subscribe(edgeRuleChains => {
  console.log('Get Edge Rule Chains:', edgeRuleChains);
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge('your-edge-id', 'your-rulechain-id').subscribe(ruleChainToEdge => {
  console.log('Assign Rule Chain To Edge:', ruleChainToEdge);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain('your-rulechain-id').subscribe(edgeTemplateRootRuleChain => {
  console.log('Set Edge Template Root Rule Chain:', edgeTemplateRootRuleChain);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(autoAssignToEdgeRuleChain => {
  console.log('Set Auto Assign To Edge Rule Chain:', autoAssignToEdgeRuleChain);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(unsetAutoAssignToEdgeRuleChain => {
  console.log('Unset Auto Assign To Edge Rule Chain:', unsetAutoAssignToEdgeRuleChain);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoAssignToEdgeRuleChains => {
  console.log('Get Auto Assign To Edge Rule Chains:', autoAssignToEdgeRuleChains);
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain('your-edge-id', 'your-rulechain-id').subscribe(edgeRootRuleChain => {
  console.log('Set Edge Root Rule Chain:', edgeRootRuleChain);
});
```
