# GIT HUB SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
```

**1. getGitHubStar**

```javascript
gitHubService.getGitHubStar().subscribe(gitHubStar => {
  console.log('Get Git Hub Star:', gitHubStar);
});
```
