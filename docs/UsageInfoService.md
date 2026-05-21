# UsageInfoService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('UsageInfoService'));
```

**1. getUsageInfo**

```javascript
usageInfoService.getUsageInfo().subscribe(info => {
  console.log('Fetched  Usage Info info:', info);
});
```
