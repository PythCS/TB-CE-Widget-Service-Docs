# Git Hub

```javascript
// Service name: gitHub
// File: git-hub.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHub = $injector.get(self.ctx.servicesMap.get('gitHub'));
```

### **1. getGitHubStar**

```javascript
gitHub.getGitHubStar().subscribe(github => {
  console.log('Github:', github);
});
```
