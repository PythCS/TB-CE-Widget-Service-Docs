# AiModelService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('AiModelService'));
```

**1. saveAiModel**

```javascript
aiModelService.saveAiModel('your-aimodel-value').subscribe(result => {
  console.log('Saved  Ai Model result:', result);
});
```

**2. getAiModels**

```javascript
aiModelService.getAiModels(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Ai Models result:', result);
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById('your-aimodel-id').subscribe(result => {
  console.log('Fetched  Ai Model By Id result:', result);
});
```

**4. checkConnectivity**

```javascript
aiModelService.checkConnectivity('your-aimodelwithusermsg-value').subscribe(result => {
  console.log('check Connectivity result:', result);
});
```
