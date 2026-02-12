### **AI MODEL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aimodelservice = $injector.get(self.ctx.servicesMap.get('aimodelservice'));

```

**1. saveAiModel**

```javascript
aimodelservice.saveAiModel(aiModel).subscribe(saveaimodel => {
  console.log('Saveaimodel:', saveaimodel);
});
```

**2. getAiModels**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aimodelservice.getAiModels(pageLink).subscribe(aimodels => {
  console.log('Aimodels:', aimodels);
});
```

**3. getAiModelById**

```javascript
aimodelservice.getAiModelById('your-aimodel-id').subscribe(aimodelbyid => {
  console.log('Aimodelbyid:', aimodelbyid);
});
```

**4. checkConnectivity**

```javascript
aimodelservice.checkConnectivity(aiModelWithUserMsg).subscribe(checkconnectivity => {
  console.log('Checkconnectivity:', checkconnectivity);
});
```

