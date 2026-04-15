# Ai Model

```javascript
// Service name: aiModel
// File: ai-model.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModel = $injector.get(self.ctx.servicesMap.get('aiModel'));
```

### **1. saveAiModel**

```javascript
aiModel.saveAiModel(aiModel).subscribe(saveAiModel => {
  console.log('Save Ai Model:', saveAiModel);
});
```

### **2. getAiModels**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aiModel.getAiModels(pageLink).subscribe(aiModels => {
  console.log('Ai Models:', aiModels);
});
```

### **3. getAiModelById**

```javascript
aiModel.getAiModelById(aiModelId).subscribe(aiModel => {
  console.log('Ai Model:', aiModel);
});
```

### **4. checkConnectivity**

```javascript
aiModel.checkConnectivity(aiModelWithUserMsg).subscribe(checkConnectivity => {
  console.log('Check Connectivity:', checkConnectivity);
});
```
