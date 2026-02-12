### **GITHUB SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const githubservice = $injector.get(self.ctx.servicesMap.get('githubservice'));

```

**1. getGitHubStar**

```javascript
githubservice.getGitHubStar().subscribe(githubstar => {
  console.log('Githubstar:', githubstar);
});
```

