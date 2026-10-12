# SOLUTIONS CREATOR SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const solutionsCreatorService = $injector.get(self.ctx.servicesMap.get('solutionsCreatorService'));
```

**1. getSolutionById**

```javascript
solutionsCreatorService.getSolutionById('your-solution-id').subscribe(solutionById => {
  console.log('Get Solution By Id:', solutionById);
});
```

**2. startSolution**

```javascript
solutionsCreatorService.startSolution().subscribe(startSolution => {
  console.log('Start Solution:', startSolution);
});
```

**3. clearStep**

```javascript
solutionsCreatorService.clearStep('your-solution-id', 'your-step-value').subscribe(result => {
  console.log('Clear Step:', result);
});
```

**4. createSolution**

```javascript
solutionsCreatorService.createSolution('your-solution-id').subscribe(solution => {
  console.log('Create Solution:', solution);
});
```

**5. chatSolution**

```javascript
solutionsCreatorService.chatSolution('your-solution-id', 'your-step-value', 'your-msg-value').subscribe(chatSolution => {
  console.log('Chat Solution:', chatSolution);
});
```

**6. updateSolutionData**

```javascript
solutionsCreatorService.updateSolutionData('your-solution-id', 'your-datakey-value', 'your-msg-value').subscribe(solutionData => {
  console.log('Update Solution Data:', solutionData);
});
```

**7. installSolution**

```javascript
solutionsCreatorService.installSolution('your-solution-id').subscribe(installSolution => {
  console.log('Install Solution:', installSolution);
});
```

**8. uninstallSolution**

```javascript
solutionsCreatorService.uninstallSolution('your-solution-id').subscribe(uninstallSolution => {
  console.log('Uninstall Solution:', uninstallSolution);
});
```

**9. getSolutions**

```javascript
solutionsCreatorService.getSolutions().subscribe(solutions => {
  console.log('Get Solutions:', solutions);
});
```

**10. deleteSolution**

```javascript
solutionsCreatorService.deleteSolution('your-solution-id').subscribe(result => {
  console.log('Delete Solution:', result);
});
```
