# MobileAppService

### **MOBILEAPPSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
mobileAppService.saveMobileApp({ /* your mobileApp */ }, { /* your config */ }).subscribe(savedMobileApp => {
  console.log('Saved MobileApp:', savedMobileApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
mobileAppService.getTenantMobileAppInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-platformtype', { /* your config */ }).subscribe(tenantmobileappinfo => {
  console.log('Tenant Mobile App Infos:', tenantmobileappinfo);
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById('your-id', { /* your config */ }).subscribe(mobileappinfobyid => {
  console.log('Mobile App Info By Id:', mobileappinfobyid);
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
mobileAppService.getTenantMobileAppBundleInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantmobileappbundleinfo => {
  console.log('Tenant Mobile App Bundle Infos:', tenantmobileappbundleinfo);
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById('your-id', { /* your config */ }).subscribe(mobileappbundleinfobyid => {
  console.log('Mobile App Bundle Info By Id:', mobileappbundleinfobyid);
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```
