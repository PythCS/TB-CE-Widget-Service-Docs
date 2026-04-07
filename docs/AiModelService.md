# AiModelService

### **AIMODELSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

**1. saveAiModel**

```javascript
aiModelService.saveAiModel({ /* your aiModel */ }, { /* your config */ }).subscribe(savedAiModel => {
  console.log('Saved AiModel:', savedAiModel);
});
```

**2. getAiModels**

```javascript
aiModelService.getAiModels(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(aimodel => {
  console.log('Ai Models:', aimodel);
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById('your-aimodel-id', { /* your config */ }).subscribe(aimodelbyid => {
  console.log('Ai Model By Id:', aimodelbyid);
});
```

**4. checkConnectivity**

```javascript
aiModelService.checkConnectivity({ /* your aiModelWithUserMsg */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
