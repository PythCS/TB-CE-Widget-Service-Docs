# Mobile Application

```javascript
// Service name: mobileApplication
// File: mobile-application.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplication = $injector.get(self.ctx.servicesMap.get('mobileApplication'));
```

### **1. getMobileAppSettings**

```javascript
mobileApplication.getMobileAppSettings().subscribe(mobileApp => {
  console.log('Mobile App:', mobileApp);
});
```

### **2. saveMobileAppSettings**

```javascript
mobileApplication.saveMobileAppSettings(mobileAppSettings).subscribe(mobileApp => {
  console.log('Mobile App:', mobileApp);
});
```

### **3. getMobileAppDeepLink**

```javascript
mobileApplication.getMobileAppDeepLink().subscribe(mobileApp => {
  console.log('Mobile App:', mobileApp);
});
```
