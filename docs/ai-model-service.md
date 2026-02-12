# AI MODEL

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

## Methods

### saveAiModel

```javascript
const aiModel = {
  // your aiModel object
};

aiModelService.saveAiModel(aiModel).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getAiModels

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

aiModelService.getAiModels(pageLink).subscribe(result => {
  console.log('AiModels:', result);
});
```

### getAiModelById

```javascript
const aiModelId = 'your-aimodel-id';

aiModelService.getAiModelById(aiModelId).subscribe(result => {
  console.log('AiModelById:', result);
});
```

### checkConnectivity

```javascript
const aiModelWithUserMsg = {
  // your aiModelWithUserMsg object
};

aiModelService.checkConnectivity(aiModelWithUserMsg).subscribe(result => {
  console.log('Result:', result);
});
```

