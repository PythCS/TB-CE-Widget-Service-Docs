# RuleChainService

**Source:** `rule-chain.service.ts`  
**Direct context access:** `none`

---

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```
**1. getRuleChains**

```javascript
ruleChainService.getRuleChains(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(ruleChains => {
  console.log('RuleChains:', ruleChains);
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds(['id1', 'id2']).subscribe(ruleChainsByIds => {
  console.log('RuleChainsByIds:', ruleChainsByIds);
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain(/* ruleChainId */ null).subscribe(ruleChain => {
  console.log('RuleChain:', ruleChain);
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels(/* ruleChainId */ null).subscribe(ruleChainOutputLabels => {
  console.log('RuleChainOutputLabels:', ruleChainOutputLabels);
});
```

**5. createDefaultRuleChain**

```javascript
ruleChainService.createDefaultRuleChain(/* ruleChainName */ null).subscribe(defaultRuleChain => {
  console.log('createDefaultRuleChain:', defaultRuleChain);
});
```

**6. saveRuleChain**

```javascript
ruleChainService.saveRuleChain(/* ruleChain */ null).subscribe(ruleChain => {
  console.log('RuleChain:', ruleChain);
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain(/* ruleChainId */ null).subscribe(rootRuleChain => {
  console.log('setRootRuleChain:', rootRuleChain);
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata(/* ruleChainId */ null).subscribe(ruleChainMetadata => {
  console.log('RuleChainMetadata:', ruleChainMetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
ruleChainService.saveRuleChainMetadata(/* ruleChainMetaData */ null).subscribe(ruleChainMetadata => {
  console.log('RuleChainMetadata:', ruleChainMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
ruleChainService.getRuleNodeComponents(/* modulesMap */ null, null).subscribe(ruleNodeComponents => {
  console.log('RuleNodeComponents:', ruleNodeComponents);
});
```

**11. getRuleNodeConfigComponent**

```javascript
ruleChainService.getRuleNodeConfigComponent(/* directive */ null).subscribe(ruleNodeConfigComponent => {
  console.log('RuleNodeConfigComponent:', ruleNodeConfigComponent);
});
```

**12. getRuleNodeComponentByClazz**

```javascript
ruleChainService.getRuleNodeComponentByClazz(null, /* clazz */ null).subscribe(ruleNodeComponentByClazz => {
  console.log('RuleNodeComponentByClazz:', ruleNodeComponentByClazz);
});
```

**13. getRuleNodeSupportedLinks**

```javascript
ruleChainService.getRuleNodeSupportedLinks(/* component */ null).subscribe(ruleNodeSupportedLinks => {
  console.log('RuleNodeSupportedLinks:', ruleNodeSupportedLinks);
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
ruleChainService.ruleNodeAllowCustomLinks(/* component */ null).subscribe(ruleNodeAllowCustomLinks => {
  console.log('ruleNodeAllowCustomLinks:', ruleNodeAllowCustomLinks);
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
ruleChainService.ruleNodeSourceRuleChainId(/* component */ null).subscribe(ruleNodeSourceRuleChainId => {
  console.log('ruleNodeSourceRuleChainId:', ruleNodeSourceRuleChainId);
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput(/* ruleNodeId */ null).subscribe(laRuleNodeDebugInput => {
  console.log('LatestRuleNodeDebugInput:', laRuleNodeDebugInput);
});
```

**17. testScript**

```javascript
ruleChainService.testScript(/* inputParams */ null, null).subscribe(script => {
  console.log('testScript:', script);
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents(null).subscribe(ruleNodeComponents => {
  console.log('loadRuleNodeComponents:', ruleNodeComponents);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentsUiResources(/* components */ null, /* modulesMap */ null).subscribe(ruleNodeComponentsUiResources => {
  console.log('resolveRuleNodeComponentsUiResources:', ruleNodeComponentsUiResources);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentUiResources(/* component */ null, /* modulesMap */ null).subscribe(ruleNodeComponentUiResources => {
  console.log('resolveRuleNodeComponentUiResources:', ruleNodeComponentUiResources);
});
```

**21. getEdgeRuleChains**

```javascript
ruleChainService.getEdgeRuleChains(/* edgeId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(edgeRuleChains => {
  console.log('EdgeRuleChains:', edgeRuleChains);
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge(/* edgeId */ null, /* ruleChainId */ null).subscribe(ruleChainToEdge => {
  console.log('assignRuleChainToEdge:', ruleChainToEdge);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain(/* ruleChainId */ null).subscribe(edgeTemplateRootRuleChain => {
  console.log('setEdgeTemplateRootRuleChain:', edgeTemplateRootRuleChain);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain(/* ruleChainId */ null).subscribe(autoAssignToEdgeRuleChain => {
  console.log('setAutoAssignToEdgeRuleChain:', autoAssignToEdgeRuleChain);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain(/* ruleChainId */ null).subscribe(unAutoAssignToEdgeRuleChain => {
  console.log('unsetAutoAssignToEdgeRuleChain:', unAutoAssignToEdgeRuleChain);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoAssignToEdgeRuleChains => {
  console.log('AutoAssignToEdgeRuleChains:', autoAssignToEdgeRuleChains);
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain(/* edgeId */ null, /* ruleChainId */ null).subscribe(edgeRootRuleChain => {
  console.log('setEdgeRootRuleChain:', edgeRootRuleChain);
});
```

---

*Auto-generated by ThingsBoardDocUpdater*