# RuleChainService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('RuleChainService'));
```

**1. getRuleChains**

```javascript
ruleChainService.getRuleChains(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(rule => {
  console.log('Fetched  Rule Chains rule:', rule);
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds('your-rulechainids-value').subscribe(rule => {
  console.log('Fetched  Rule Chains By Ids rule:', rule);
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('Fetched  Rule Chain rule:', rule);
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels('your-rulechain-id').subscribe(rule => {
  console.log('Fetched  Rule Chain Output Labels rule:', rule);
});
```

**5. createDefaultRuleChain**

```javascript
ruleChainService.createDefaultRuleChain('your-rulechainname-value').subscribe(rule => {
  console.log('create Default Rule Chain rule:', rule);
});
```

**6. saveRuleChain**

```javascript
ruleChainService.saveRuleChain('your-rulechain-value').subscribe(rule => {
  console.log('Saved  Rule Chain rule:', rule);
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('set Root Rule Chain rule:', rule);
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata('your-rulechain-id').subscribe(rule => {
  console.log('Fetched  Rule Chain Metadata rule:', rule);
});
```

**9. saveRuleChainMetadata**

```javascript
ruleChainService.saveRuleChainMetadata('your-rulechainmetadata-value').subscribe(rule => {
  console.log('Saved  Rule Chain Metadata rule:', rule);
});
```

**10. getRuleNodeComponents**

```javascript
ruleChainService.getRuleNodeComponents('your-modulesmap-value', 'your-rulechaintype-value').subscribe(rule => {
  console.log('Fetched  Rule Node Components rule:', rule);
});
```

**11. getRuleNodeConfigComponent**

```javascript
ruleChainService.getRuleNodeConfigComponent('your-directive-value').subscribe(rule => {
  console.log('Fetched  Rule Node Config Component rule:', rule);
});
```

**12. getRuleNodeComponentByClazz**

```javascript
ruleChainService.getRuleNodeComponentByClazz('your-rulechaintype-value', 'your-clazz-value').subscribe(rule => {
  console.log('Fetched  Rule Node Component By Clazz rule:', rule);
});
```

**13. getRuleNodeSupportedLinks**

```javascript
ruleChainService.getRuleNodeSupportedLinks('your-component-value').subscribe(rule => {
  console.log('Fetched  Rule Node Supported Links rule:', rule);
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
ruleChainService.ruleNodeAllowCustomLinks('your-component-value').subscribe(result => {
  console.log('rule Node Allow Custom Links result:', result);
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
ruleChainService.ruleNodeSourceRuleChainId('your-component-value').subscribe(rule => {
  console.log('rule Node Source Rule Chain Id rule:', rule);
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput('your-rulenode-id').subscribe(rule => {
  console.log('Fetched  Latest Rule Node Debug Input rule:', rule);
});
```

**17. testScript**

```javascript
ruleChainService.testScript('your-inputparams-value', 'your-scriptlang-value').subscribe(result => {
  console.log('test Script result:', result);
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents('your-rulechaintype-value').subscribe(rule => {
  console.log('load Rule Node Components rule:', rule);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentsUiResources('your-components-value', 'your-modulesmap-value').subscribe(rule => {
  console.log('resolve Rule Node Components Ui Resources rule:', rule);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentUiResources('your-component-value', 'your-modulesmap-value').subscribe(rule => {
  console.log('resolve Rule Node Component Ui Resources rule:', rule);
});
```

**21. getEdgeRuleChains**

```javascript
ruleChainService.getEdgeRuleChains('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(rule => {
  console.log('Fetched  Edge Rule Chains rule:', rule);
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge('your-edge-id', 'your-rulechain-id').subscribe(rule => {
  console.log('assign Rule Chain To Edge rule:', rule);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('set Edge Template Root Rule Chain rule:', rule);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('set Auto Assign To Edge Rule Chain rule:', rule);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('unset Auto Assign To Edge Rule Chain rule:', rule);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(rule => {
  console.log('Fetched  Auto Assign To Edge Rule Chains rule:', rule);
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain('your-edge-id', 'your-rulechain-id').subscribe(rule => {
  console.log('set Edge Root Rule Chain rule:', rule);
});
```
