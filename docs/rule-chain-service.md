# RULE CHAIN

Rule chain and rule node management.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

## Methods

### getRuleChains

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

ruleChainService.getRuleChains(pageLink, type).subscribe(result => {
  console.log('RuleChains:', result);
});
```

### getRuleChainsByIds

```javascript
const ruleChainIds = 'your-rulechains-id';

ruleChainService.getRuleChainsByIds(ruleChainIds).subscribe(result => {
  console.log('RuleChainsByIds:', result);
});
```

### getRuleChain

```javascript
const ruleChainId = 'your-rulechain-id';

ruleChainService.getRuleChain(ruleChainId).subscribe(result => {
  console.log('RuleChain:', result);
});
```

### getRuleChainOutputLabels

```javascript
const ruleChainId = 'your-rulechain-id';

ruleChainService.getRuleChainOutputLabels(ruleChainId).subscribe(result => {
  console.log('Result:', result);
});
```

### createDefaultRuleChain

```javascript
const ruleChainName = 'your-rulechainname';

ruleChainService.createDefaultRuleChain(ruleChainName).subscribe(result => {
  console.log('createDefaultRuleChain:', result);
});
```

### saveRuleChain

```javascript
const ruleChain = {
  // your ruleChain object
};

ruleChainService.saveRuleChain(ruleChain).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### setRootRuleChain

```javascript
const ruleChainId = 'your-rulechain-id';

ruleChainService.setRootRuleChain(ruleChainId).subscribe(result => {
  console.log('setRootRuleChain:', result);
});
```

### getRuleChainMetadata

```javascript
const ruleChainId = 'your-rulechain-id';

ruleChainService.getRuleChainMetadata(ruleChainId).subscribe(result => {
  console.log('RuleChainMetadata:', result);
});
```

### saveRuleChainMetadata

```javascript
const ruleChainMetaData = {
  // your ruleChainMetaData object
};

ruleChainService.saveRuleChainMetadata(ruleChainMetaData).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getRuleNodeComponents

```javascript
const modulesMap = {
  // your modulesMap object
};
const ruleChainType = {
  // your ruleChainType object
};

ruleChainService.getRuleNodeComponents(modulesMap, ruleChainType).subscribe(result => {
  console.log('RuleNodeComponents:', result);
});
```

### getRuleNodeConfigComponent

```javascript
const directive = 'your-directive';

const result = ruleChainService.getRuleNodeConfigComponent(directive);
console.log('RuleNodeConfigComponent:', result);
```

### getRuleNodeComponentByClazz

```javascript
const ruleChainType = {
  // your ruleChainType object
};
const clazz = 'your-clazz';

const result = ruleChainService.getRuleNodeComponentByClazz(ruleChainType, clazz);
console.log('RuleNodeComponentByClazz:', result);
```

### getRuleNodeSupportedLinks

```javascript
const component = {
  // your component object
};

const result = ruleChainService.getRuleNodeSupportedLinks(component);
console.log('RuleNodeSupportedLinks:', result);
```

### ruleNodeAllowCustomLinks

```javascript
const component = {
  // your component object
};

const result = ruleChainService.ruleNodeAllowCustomLinks(component);
console.log('Result:', result);
```

### ruleNodeSourceRuleChainId

```javascript
const component = {
  // your component object
};
const config = {
  // your config object
};

const result = ruleChainService.ruleNodeSourceRuleChainId(component, config);
console.log('Result:', result);
```

### getLatestRuleNodeDebugInput

```javascript
const ruleNodeId = 'your-rulenode-id';

ruleChainService.getLatestRuleNodeDebugInput(ruleNodeId).subscribe(result => {
  console.log('LatestRuleNodeDebugInput:', result);
});
```

### testScript

```javascript
const inputParams = {
  // your inputParams object
};
const scriptLang = {
  // your scriptLang object
};

ruleChainService.testScript(inputParams, scriptLang).subscribe(result => {
  console.log('Result:', result);
});
```

### loadRuleNodeComponents

```javascript
const ruleChainType = {
  // your ruleChainType object
};

ruleChainService.loadRuleNodeComponents(ruleChainType).subscribe(result => {
  console.log('loadRuleNodeComponents:', result);
});
```

### resolveRuleNodeComponentsUiResources

```javascript
const components = {
  // your components object
};
const modulesMap = {
  // your modulesMap object
};

ruleChainService.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(result => {
  console.log('resolveRuleNodeComponentsUiResources:', result);
});
```

### resolveRuleNodeComponentUiResources

```javascript
const component = {
  // your component object
};
const modulesMap = {
  // your modulesMap object
};

ruleChainService.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(result => {
  console.log('resolveRuleNodeComponentUiResources:', result);
});
```

### getEdgeRuleChains

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

ruleChainService.getEdgeRuleChains(edgeId, pageLink).subscribe(result => {
  console.log('EdgeRuleChains:', result);
});
```

### assignRuleChainToEdge

```javascript
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rulechain-id';

ruleChainService.assignRuleChainToEdge(edgeId, ruleChainId).subscribe(result => {
  console.log('assignRuleChainToEdge:', result);
});
```

### setEdgeTemplateRootRuleChain

```javascript
const ruleChainId = 'your-rulechain-id';

ruleChainService.setEdgeTemplateRootRuleChain(ruleChainId).subscribe(result => {
  console.log('setEdgeTemplateRootRuleChain:', result);
});
```

### setAutoAssignToEdgeRuleChain

```javascript
const ruleChainId = 'your-rulechain-id';

ruleChainService.setAutoAssignToEdgeRuleChain(ruleChainId).subscribe(result => {
  console.log('setAutoAssignToEdgeRuleChain:', result);
});
```

### unsetAutoAssignToEdgeRuleChain

```javascript
const ruleChainId = 'your-rulechain-id';

ruleChainService.unsetAutoAssignToEdgeRuleChain(ruleChainId).subscribe(result => {
  console.log('unsetAutoAssignToEdgeRuleChain:', result);
});
```

### getAutoAssignToEdgeRuleChains

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(result => {
  console.log('AutoAssignToEdgeRuleChains:', result);
});
```

### setEdgeRootRuleChain

```javascript
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rulechain-id';

ruleChainService.setEdgeRootRuleChain(edgeId, ruleChainId).subscribe(result => {
  console.log('setEdgeRootRuleChain:', result);
});
```

