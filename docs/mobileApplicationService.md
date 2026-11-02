# MOBILE APPLICATION SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
mobileApplicationService.getMobileAppSettings().subscribe(settings => {
  console.log('Get Mobile App Settings:', settings);
});
```

**2. getMergedMobileAppSettings**

```javascript
mobileApplicationService.getMergedMobileAppSettings().subscribe(mergedMobileAppSettings => {
  console.log('Get Merged Mobile App Settings:', mergedMobileAppSettings);
});
```

**3. saveMobileAppSettings**

```javascript
mobileApplicationService.saveMobileAppSettings('your-mobileappsettings-value').subscribe(mobileAppSettings => {
  console.log('Save Mobile App Settings:', mobileAppSettings);
});
```

**4. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(mobileAppDeepLink => {
  console.log('Get Mobile App Deep Link:', mobileAppDeepLink);
});
```
