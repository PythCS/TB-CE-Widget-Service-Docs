# RuleChainService

### **RULECHAINSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
ruleChainService.getRuleChains(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(rulechain => {
  console.log('Rule Chains:', rulechain);
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds(['id1', 'id2'], { /* your config */ }).subscribe(rulechainbyid => {
  console.log('Rule Chains By Ids:', rulechainbyid);
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain('your-rulechain-id', { /* your config */ }).subscribe(rulechain => {
  console.log('Rule Chain:', rulechain);
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels('your-rulechain-id', { /* your config */ }).subscribe(rulechainoutputlabel => {
  console.log('Rule Chain Output Labels:', rulechainoutputlabel);
});
```

**5. createDefaultRuleChain**

```javascript
ruleChainService.createDefaultRuleChain('your-ruleChainName', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. saveRuleChain**

```javascript
ruleChainService.saveRuleChain({ /* your ruleChain */ }, { /* your config */ }).subscribe(savedRuleChain => {
  console.log('Saved RuleChain:', savedRuleChain);
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain('your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata('your-rulechain-id', { /* your config */ }).subscribe(rulechainmetadata => {
  console.log('Rule Chain Metadata:', rulechainmetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
ruleChainService.saveRuleChainMetadata({ /* your ruleChainMetaData */ }, { /* your config */ }).subscribe(savedRuleChainMetadata => {
  console.log('Saved RuleChainMetadata:', savedRuleChainMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
ruleChainService.getRuleNodeComponents({ /* your modulesMap */ }, 'your-rulechaintype', { /* your config */ }).subscribe(rulenodecomponent => {
  console.log('Rule Node Components:', rulenodecomponent);
});
```

**11. getRuleNodeConfigComponent**

```javascript
ruleChainService.getRuleNodeConfigComponent('your-directive').subscribe(rulenodeconfigcomponent => {
  console.log('Rule Node Config Component:', rulenodeconfigcomponent);
});
```

**12. getRuleNodeComponentByClazz**

```javascript
ruleChainService.getRuleNodeComponentByClazz('your-rulechaintype', 'your-clazz').subscribe(rulenodecomponentbyclazz => {
  console.log('Rule Node Component By Clazz:', rulenodecomponentbyclazz);
});
```

**13. getRuleNodeSupportedLinks**

```javascript
ruleChainService.getRuleNodeSupportedLinks({ /* your component */ }).subscribe(rulenodeupportedlink => {
  console.log('Rule Node Supported Links:', rulenodeupportedlink);
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
ruleChainService.ruleNodeAllowCustomLinks({ /* your component */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
ruleChainService.ruleNodeSourceRuleChainId({ /* your component */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput('your-rulenode-id', { /* your config */ }).subscribe(latestrulenodedebuginput => {
  console.log('Latest Rule Node Debug Input:', latestrulenodedebuginput);
});
```

**17. testScript**

```javascript
ruleChainService.testScript({ /* your inputParams */ }, { /* your scriptLang */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents('your-rulechaintype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentsUiResources(['id1', 'id2'], { /* your modulesMap */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentUiResources({ /* your component */ }, { /* your modulesMap */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**21. getEdgeRuleChains**

```javascript
ruleChainService.getEdgeRuleChains('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(edgerulechain => {
  console.log('Edge Rule Chains:', edgerulechain);
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge('your-edge-id', 'your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain('your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain('your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain('your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains({ /* your config */ }).subscribe(autoaigntoedgerulechain => {
  console.log('Auto Assign To Edge Rule Chains:', autoaigntoedgerulechain);
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain('your-edge-id', 'your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
