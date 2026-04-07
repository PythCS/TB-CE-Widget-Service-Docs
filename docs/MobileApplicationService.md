# MobileApplicationService

### **MOBILEAPPLICATIONSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
mobileApplicationService.getMobileAppSettings({ /* your config */ }).subscribe(mobileappetting => {
  console.log('Mobile App Settings:', mobileappetting);
});
```

**2. saveMobileAppSettings**

```javascript
mobileApplicationService.saveMobileAppSettings({ /* your mobileAppSettings */ }, { /* your config */ }).subscribe(savedMobileAppSettings => {
  console.log('Saved MobileAppSettings:', savedMobileAppSettings);
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink({ /* your config */ }).subscribe(mobileappdeeplink => {
  console.log('Mobile App Deep Link:', mobileappdeeplink);
});
```
