# AI MODEL SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

**1. saveAiModel**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
const aiModel = {  // AiModel object
  // ... set the fields you need
};
aiModelService.saveAiModel(aiModel).subscribe(savedAiModel => {
  console.log('Saved Ai Model:', savedAiModel);
});
```

**2. getAiModels**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aiModelService.getAiModels(pageLink).subscribe(aiModels => {
  console.log('List of Ai Models:', aiModels);
});
```

**3. getAiModelById**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
const aiModelId = 'your-ai-model-id';
aiModelService.getAiModelById(aiModelId).subscribe(aiModelBy => {
  console.log('Get Ai Model By Id:', aiModelBy);
});
```

**4. checkConnectivity**

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
const aiModelWithUserMsg = {  // AiModelWithUserMsg object
  // ... set the fields you need
};
aiModelService.checkConnectivity(aiModelWithUserMsg).subscribe(checkConnectivity => {
  console.log('Check Connectivity:', checkConnectivity);
});
```
