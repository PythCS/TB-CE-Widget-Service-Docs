# GitHubService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('GitHubService'));
```

**1. getGitHubStar**

```javascript
gitHubService.getGitHubStar().subscribe(result => {
  console.log('Fetched  Git Hub Star result:', result);
});
```
