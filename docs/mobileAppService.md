# MOBILE APP SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **MOBILE APP SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
const mobileApp = mobileApp;
mobileAppService.saveMobileApp(mobileApp).subscribe(savedMobileApp => {
  console.log('Save Mobile App: savedMobileApp');
});
```

**2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppInfos(pageLink, 'type').subscribe(tenantmobileappinfos => {
  console.log('Get Tenant Mobile App Infos: tenantmobileappinfos');
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById('your-id').subscribe(mobileAppInfoById => {
  console.log('Get Mobile App Info By Id: mobileAppInfoById');
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp('your-id').subscribe(result => {
  console.log('Delete Mobile App: result');
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(tenantmobileappbundleinfos => {
  console.log('Get Tenant Mobile App Bundle Infos:tenantmobileappbundleinfos');
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById('your-id').subscribe(mobileAppBundleInfoById => {
  console.log('Get Mobile App Bundle Info By Id:mobileAppBundleInfoById');
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle('your-id').subscribe(result => {
  console.log('Delete Mobile App Bundle: result');
});
```
