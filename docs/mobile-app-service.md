# MOBILE APP

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

## Methods

### saveMobileApp

```javascript
const mobileApp = {
  // your mobileApp object
};

mobileAppService.saveMobileApp(mobileApp).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getTenantMobileAppInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const platformType = {
  // your platformType object
};

mobileAppService.getTenantMobileAppInfos(pageLink, platformType).subscribe(result => {
  console.log('TenantMobileAppInfos:', result);
});
```

### getMobileAppInfoById

```javascript
const id = 'your--id';

mobileAppService.getMobileAppInfoById(id).subscribe(result => {
  console.log('MobileAppInfoById:', result);
});
```

### deleteMobileApp

```javascript
const id = 'your--id';

mobileAppService.deleteMobileApp(id).subscribe(result => {
  console.log('Result:', result);
});
```

### getTenantMobileAppBundleInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

### getMobileAppBundleInfoById

```javascript
const id = 'your--id';

mobileAppService.getMobileAppBundleInfoById(id).subscribe(info => {
  console.log('Info:', info);
});
```

### deleteMobileAppBundle

```javascript
const id = 'your--id';

mobileAppService.deleteMobileAppBundle(id).subscribe(result => {
  console.log('Result:', result);
});
```

