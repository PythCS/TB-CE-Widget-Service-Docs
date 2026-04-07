# UsageInfoService

### **USAGEINFOSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('usageInfoService'));
```

**1. getUsageInfo**

```javascript
usageInfoService.getUsageInfo({ /* your config */ }).subscribe(usageinfo => {
  console.log('Usage Info:', usageinfo);
});
```
