# MobileAppService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('MobileAppService'));
```

**1. saveMobileApp**

```javascript
mobileAppService.saveMobileApp('your-mobileapp-value').subscribe(result => {
  console.log('Saved  Mobile App result:', result);
});
```

**2. getTenantMobileAppInfos**

```javascript
mobileAppService.getTenantMobileAppInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-platformtype-value').subscribe(tenant => {
  console.log('Fetched  Tenant Mobile App Infos tenant:', tenant);
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById('your--id').subscribe(info => {
  console.log('Fetched  Mobile App Info By Id info:', info);
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
mobileAppService.getTenantMobileAppBundleInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Mobile App Bundle Infos tenant:', tenant);
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById('your--id').subscribe(info => {
  console.log('Fetched  Mobile App Bundle Info By Id info:', info);
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```
