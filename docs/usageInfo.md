# Usage Info

```javascript
// Service name: usageInfo
// File: usage-info.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfo = $injector.get(self.ctx.servicesMap.get('usageInfo'));
```

### **1. getUsageInfo**

```javascript
usageInfo.getUsageInfo().subscribe(usage => {
  console.log('Usage:', usage);
});
```
