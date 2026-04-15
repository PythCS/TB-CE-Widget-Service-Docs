# Mobile App

```javascript
// Service name: mobileApp
// File: mobile-app.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApp = $injector.get(self.ctx.servicesMap.get('mobileApp'));
```

### **1. saveMobileApp**

```javascript
mobileApp.saveMobileApp(mobileApp).subscribe(mobileApp => {
  console.log('Mobile App:', mobileApp);
});
```

### **2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileApp.getTenantMobileAppInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **3. getMobileAppInfoById**

```javascript
mobileApp.getMobileAppInfoById(id).subscribe(mobileApp => {
  console.log('Mobile App:', mobileApp);
});
```

### **4. deleteMobileApp**

```javascript
mobileApp.deleteMobileApp(id).subscribe(mobileApp => {
  console.log('Mobile App:', mobileApp);
});
```

### **5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileApp.getTenantMobileAppBundleInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **6. getMobileAppBundleInfoById**

```javascript
mobileApp.getMobileAppBundleInfoById(id).subscribe(mobileApp => {
  console.log('Mobile App:', mobileApp);
});
```

### **7. deleteMobileAppBundle**

```javascript
mobileApp.deleteMobileAppBundle(id).subscribe(mobileApp => {
  console.log('Mobile App:', mobileApp);
});
```
