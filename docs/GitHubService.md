# GitHubService

### **GITHUBSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
```

**1. getGitHubStar**

```javascript
gitHubService.getGitHubStar({ /* your config */ }).subscribe(githubstar => {
  console.log('Git Hub Star:', githubstar);
});
```
