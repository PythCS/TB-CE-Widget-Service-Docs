### **MOBILE APP SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileappservice = $injector.get(self.ctx.servicesMap.get('mobileappservice'));

```

**1. saveMobileApp**

```javascript
mobileappservice.saveMobileApp(mobileApp).subscribe(savemobileapp => {
  console.log('Savemobileapp:', savemobileapp);
});
```

**2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileappservice.getTenantMobileAppInfos(pageLink).subscribe(tenantmobileappinfos => {
  console.log('Tenantmobileappinfos:', tenantmobileappinfos);
});
```

**3. getMobileAppInfoById**

```javascript
mobileappservice.getMobileAppInfoById('your-id-id').subscribe(mobileappinfobyid => {
  console.log('Mobileappinfobyid:', mobileappinfobyid);
});
```

**4. deleteMobileApp**

```javascript
mobileappservice.deleteMobileApp('your-id-id').subscribe(deletemobileapp => {
  console.log('Deletemobileapp:', deletemobileapp);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileappservice.getTenantMobileAppBundleInfos(pageLink).subscribe(tenantmobileappbundleinfos => {
  console.log('Tenantmobileappbundleinfos:', tenantmobileappbundleinfos);
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileappservice.getMobileAppBundleInfoById('your-id-id').subscribe(mobileappbundleinfobyid => {
  console.log('Mobileappbundleinfobyid:', mobileappbundleinfobyid);
});
```

**7. deleteMobileAppBundle**

```javascript
mobileappservice.deleteMobileAppBundle('your-id-id').subscribe(deletemobileappbundle => {
  console.log('Deletemobileappbundle:', deletemobileappbundle);
});
```

