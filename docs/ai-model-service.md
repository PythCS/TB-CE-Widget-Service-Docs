# AI MODEL SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

**1. saveAiModel**

```javascript
aiModelService.saveAiModel('your-aimodel-value').subscribe(aiModel => {
  console.log('Save Ai Model:', aiModel);
});
```

**2. getAiModels**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aiModelService.getAiModels(pageLink).subscribe(aiModels => {
  console.log('Get Ai Models:', aiModels);
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById('your-aimodel-id').subscribe(aiModelById => {
  console.log('Get Ai Model By Id:', aiModelById);
});
```

**4. checkConnectivity**

```javascript
aiModelService.checkConnectivity('your-aimodelwithusermsg-value').subscribe(connectivity => {
  console.log('Check Connectivity:', connectivity);
});
```
