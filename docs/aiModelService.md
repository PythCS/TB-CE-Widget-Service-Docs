# AI MODEL SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **AI MODEL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

**1. saveAiModel**

```javascript
const aiModel = aiModel;
aiModelService.saveAiModel(aiModel).subscribe(savedAiModel => {
  console.log('Save Ai Model: savedAiModel');
});
```

**2. getAiModels**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aiModelService.getAiModels(pageLink).subscribe(aimodels => {
  console.log('Get Ai Models: aimodels');
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById('your-id').subscribe(aiModelById => {
  console.log('Get Ai Model By Id: aiModelById');
});
```

**4. checkConnectivity**

```javascript
const aiModelWithUserMsg = aiModelWithUserMsg;
aiModelService.checkConnectivity(aiModelWithUserMsg).subscribe(result => {
  console.log('Check Connectivity: result');
});
```
