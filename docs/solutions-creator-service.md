# SOLUTIONS CREATOR SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
```

**1. getSolutionById**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.getSolutionById(solutionId).subscribe(solutionBy => {
  console.log('Get Solution By Id:', solutionBy);
});
```

**2. startSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
solutionsCreatorService.startSolution().subscribe(startSolution => {
  console.log('Start Solution:', startSolution);
});
```

**3. clearStep**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
const step = {  // SolutionStep object
  // ... set the fields you need
};
solutionsCreatorService.clearStep(solutionId, step).subscribe(clearStep => {
  console.log('Clear Step:', clearStep);
});
```

**4. createSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.createSolution(solutionId).subscribe(createSolution => {
  console.log('Create Solution:', createSolution);
});
```

**5. chatSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
const step = {  // SolutionStep object
  // ... set the fields you need
};
const msg = 'your-msg';
solutionsCreatorService.chatSolution(solutionId, step, msg).subscribe(chatSolution => {
  console.log('Chat Solution:', chatSolution);
});
```

**6. updateSolutionData**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
const dataKey = {  // SolutionDataKey object
  // ... set the fields you need
};
const msg = {  // SolutionDataValues object
  // ... set the fields you need
};
solutionsCreatorService.updateSolutionData(solutionId, dataKey, msg).subscribe(savedSolutionData => {
  console.log('Saved Solution Data:', savedSolutionData);
});
```

**7. installSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.installSolution(solutionId).subscribe(installSolution => {
  console.log('Install Solution:', installSolution);
});
```

**8. uninstallSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.uninstallSolution(solutionId).subscribe(uninstallSolution => {
  console.log('Uninstall Solution:', uninstallSolution);
});
```

**9. getSolutions**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
solutionsCreatorService.getSolutions().subscribe(solutions => {
  console.log('List of Solutions:', solutions);
});
```

**10. deleteSolution**

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
const solutionId = 'your-solution-id';
solutionsCreatorService.deleteSolution(solutionId).subscribe(result => {
  console.log('Delete Solution result:', result);
});
```
