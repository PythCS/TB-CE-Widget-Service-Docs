# MobileApplicationService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('MobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
mobileApplicationService.getMobileAppSettings().subscribe(settings => {
  console.log('Fetched  Mobile App Settings settings:', settings);
});
```

**2. saveMobileAppSettings**

```javascript
mobileApplicationService.saveMobileAppSettings('your-mobileappsettings-value').subscribe(settings => {
  console.log('Saved  Mobile App Settings settings:', settings);
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(result => {
  console.log('Fetched  Mobile App Deep Link result:', result);
});
```
