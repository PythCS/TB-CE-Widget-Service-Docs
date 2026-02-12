# MOBILE APPLICATION

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

## Methods

### getMobileAppSettings

```javascript
mobileApplicationService.getMobileAppSettings().subscribe(settings => {
  console.log('Settings:', settings);
});
```

### saveMobileAppSettings

```javascript
const mobileAppSettings = {
  // your mobileAppSettings object
};

mobileApplicationService.saveMobileAppSettings(mobileAppSettings).subscribe(settings => {
  console.log('Settings:', settings);
});
```

### getMobileAppDeepLink

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(url => {
  console.log('URL:', url);
});
```

