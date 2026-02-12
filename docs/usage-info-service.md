# USAGE INFO

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('usageInfoService'));
```

## Methods

### getUsageInfo

```javascript
usageInfoService.getUsageInfo().subscribe(info => {
  console.log('Info:', info);
});
```

