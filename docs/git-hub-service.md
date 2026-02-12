# GIT HUB

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
```

## Methods

### getGitHubStar

```javascript
gitHubService.getGitHubStar().subscribe(result => {
  console.log('Result:', result);
});
```

