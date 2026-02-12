### **MOBILE APPLICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileapplicationservice = $injector.get(self.ctx.servicesMap.get('mobileapplicationservice'));

```

**1. getMobileAppSettings**

```javascript
mobileapplicationservice.getMobileAppSettings().subscribe(mobileappsettings => {
  console.log('Mobileappsettings:', mobileappsettings);
});
```

**2. saveMobileAppSettings**

```javascript
mobileapplicationservice.saveMobileAppSettings(mobileAppSettings).subscribe(savemobileappsettings => {
  console.log('Savemobileappsettings:', savemobileappsettings);
});
```

**3. getMobileAppDeepLink**

```javascript
mobileapplicationservice.getMobileAppDeepLink().subscribe(mobileappdeeplink => {
  console.log('Mobileappdeeplink:', mobileappdeeplink);
});
```

