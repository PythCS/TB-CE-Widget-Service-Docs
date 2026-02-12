### **USAGE INFO SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageinfoservice = $injector.get(self.ctx.servicesMap.get('usageinfoservice'));

```

**1. getUsageInfo**

```javascript
usageinfoservice.getUsageInfo().subscribe(usageinfo => {
  console.log('Usageinfo:', usageinfo);
});
```

