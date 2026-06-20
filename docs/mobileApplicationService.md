# MOBILE APPLICATION SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **MOBILE APPLICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
mobileApplicationService.getMobileAppSettings().subscribe(mobileappsettings => {
  console.log('Get Mobile App Settings: mobileappsettings');
});
```

**2. saveMobileAppSettings**

```javascript
const mobileAppSettings = mobileAppSettings;
mobileApplicationService.saveMobileAppSettings(mobileAppSettings).subscribe(savedMobileAppSettings => {
  console.log('Save Mobile App Settings: savedMobileAppSettings');
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(mobileAppDeepLink => {
  console.log('Get Mobile App Deep Link: mobileAppDeepLink');
});
```
