# TENANT PROFILE

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

## Methods

### getTenantProfiles

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

tenantProfileService.getTenantProfiles(pageLink).subscribe(result => {
  console.log('TenantProfiles:', result);
});
```

### getTenantProfile

```javascript
const tenantProfileId = 'your-tenantprofile-id';

tenantProfileService.getTenantProfile(tenantProfileId).subscribe(result => {
  console.log('TenantProfile:', result);
});
```

### saveTenantProfile

```javascript
const tenantProfile = {
  // your tenantProfile object
};

tenantProfileService.saveTenantProfile(tenantProfile).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### setDefaultTenantProfile

```javascript
const tenantProfileId = 'your-tenantprofile-id';

tenantProfileService.setDefaultTenantProfile(tenantProfileId).subscribe(result => {
  console.log('setDefaultTenantProfile:', result);
});
```

### getDefaultTenantProfileInfo

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(info => {
  console.log('Info:', info);
});
```

### getTenantProfileInfo

```javascript
const tenantProfileId = 'your-tenantprofile-id';

tenantProfileService.getTenantProfileInfo(tenantProfileId).subscribe(info => {
  console.log('Info:', info);
});
```

### getTenantProfileInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

tenantProfileService.getTenantProfileInfos(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

### getTenantProfilesByIds

```javascript
const tenantProfileIds = 'your-tenantprofiles-id';

tenantProfileService.getTenantProfilesByIds(tenantProfileIds).subscribe(info => {
  console.log('Info:', info);
});
```

