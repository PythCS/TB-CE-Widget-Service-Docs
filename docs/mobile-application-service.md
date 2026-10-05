# MOBILE APPLICATION SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
mobileApplicationService.getMobileAppSettings().subscribe(mobileAppSettings => {
  console.log('Get Mobile App Settings:', mobileAppSettings);
});
```

**2. getMergedMobileAppSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
mobileApplicationService.getMergedMobileAppSettings().subscribe(mergedMobileAppSettings => {
  console.log('Get Merged Mobile App Settings:', mergedMobileAppSettings);
});
```

**3. saveMobileAppSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
const mobileAppSettings = {  // QrCodeSettings object
  // ... set the fields you need
};
mobileApplicationService.saveMobileAppSettings(mobileAppSettings).subscribe(savedMobileAppSettings => {
  console.log('Saved Mobile App Settings:', savedMobileAppSettings);
});
```

**4. getMobileAppDeepLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
mobileApplicationService.getMobileAppDeepLink().subscribe(mobileAppDeepLink => {
  console.log('Get Mobile App Deep Link:', mobileAppDeepLink);
});
```
