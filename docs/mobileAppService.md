# MOBILE APP SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
mobileAppService.saveMobileApp('your-mobileapp-value').subscribe(mobileApp => {
  console.log('Save Mobile App:', mobileApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppInfos(pageLink, 'your-platformtype-value').subscribe(tenantMobileAppInfos => {
  console.log('Get Tenant Mobile App Infos:', tenantMobileAppInfos);
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById('your--id').subscribe(mobileAppInfoById => {
  console.log('Get Mobile App Info By Id:', mobileAppInfoById);
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp('your--id').subscribe(result => {
  console.log('Delete Mobile App:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(tenantMobileAppBundleInfos => {
  console.log('Get Tenant Mobile App Bundle Infos:', tenantMobileAppBundleInfos);
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById('your--id').subscribe(mobileAppBundleInfoById => {
  console.log('Get Mobile App Bundle Info By Id:', mobileAppBundleInfoById);
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle('your--id').subscribe(result => {
  console.log('Delete Mobile App Bundle:', result);
});
```
