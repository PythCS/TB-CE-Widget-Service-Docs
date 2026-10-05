# TENANT PROFILE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfiles(pageLink).subscribe(tenantProfiles => {
  console.log('List of Tenant Profiles:', tenantProfiles);
});
```

**2. getTenantProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.getTenantProfile(tenantProfileId).subscribe(tenantProfile => {
  console.log('Get Tenant Profile:', tenantProfile);
});
```

**3. saveTenantProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfile = {  // TenantProfile object
  // ... set the fields you need
};
tenantProfileService.saveTenantProfile(tenantProfile).subscribe(savedTenantProfile => {
  console.log('Saved Tenant Profile:', savedTenantProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.setDefaultTenantProfile(tenantProfileId).subscribe(setDefaultTenantProfile => {
  console.log('Set Default Tenant Profile:', setDefaultTenantProfile);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
tenantProfileService.getDefaultTenantProfileInfo().subscribe(defaultTenantProfileInfo => {
  console.log('Get Default Tenant Profile Info:', defaultTenantProfileInfo);
});
```

**6. getTenantProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.getTenantProfileInfo(tenantProfileId).subscribe(tenantProfileInfo => {
  console.log('Get Tenant Profile Info:', tenantProfileInfo);
});
```

**7. getTenantProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(tenantProfileInfos => {
  console.log('List of Tenant Profile Infos:', tenantProfileInfos);
});
```

**8. getTenantProfilesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
const tenantProfileIds = ['your-tenant-profile-i-1', 'your-tenant-profile-i-2'];
tenantProfileService.getTenantProfilesByIds(tenantProfileIds).subscribe(tenantProfilesBys => {
  console.log('List of Tenant Profiles By Ids:', tenantProfilesBys);
});
```
