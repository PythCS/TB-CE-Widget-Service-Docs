# MOBILE APP SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const mobileApp = {  // MobileApp object
  // ... set the fields you need
};
mobileAppService.saveMobileApp(mobileApp).subscribe(savedMobileApp => {
  console.log('Saved Mobile App:', savedMobileApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const platformType = {  // PlatformType object
  // ... set the fields you need
};
mobileAppService.getTenantMobileAppInfos(pageLink, platformType).subscribe(tenantMobileAppInfos => {
  console.log('List of Tenant Mobile App Infos:', tenantMobileAppInfos);
});
```

**3. getMobileAppInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const id = 'your-id';
mobileAppService.getMobileAppInfoById(id).subscribe(mobileAppInfoBy => {
  console.log('Get Mobile App Info By Id:', mobileAppInfoBy);
});
```

**4. deleteMobileApp**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const id = 'your-id';
mobileAppService.deleteMobileApp(id).subscribe(result => {
  console.log('Delete Mobile App result:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(tenantMobileAppBundleInfos => {
  console.log('List of Tenant Mobile App Bundle Infos:', tenantMobileAppBundleInfos);
});
```

**6. getMobileAppBundleInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const id = 'your-id';
mobileAppService.getMobileAppBundleInfoById(id).subscribe(mobileAppBundleInfoBy => {
  console.log('Get Mobile App Bundle Info By Id:', mobileAppBundleInfoBy);
});
```

**7. deleteMobileAppBundle**

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
const id = 'your-id';
mobileAppService.deleteMobileAppBundle(id).subscribe(result => {
  console.log('Delete Mobile App Bundle result:', result);
});
```
