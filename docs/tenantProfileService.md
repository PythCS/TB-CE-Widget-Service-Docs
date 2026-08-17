# TENANT PROFILE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfiles(pageLink).subscribe(tenantProfiles => {
  console.log('Get Tenant Profiles:', tenantProfiles);
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile('your-tenantprofile-id').subscribe(tenantProfile => {
  console.log('Get Tenant Profile:', tenantProfile);
});
```

**3. saveTenantProfile**

```javascript
tenantProfileService.saveTenantProfile('your-tenantprofile-value').subscribe(tenantProfile => {
  console.log('Save Tenant Profile:', tenantProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile('your-tenantprofile-id').subscribe(defaultTenantProfile => {
  console.log('Set Default Tenant Profile:', defaultTenantProfile);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(defaultTenantProfileInfo => {
  console.log('Get Default Tenant Profile Info:', defaultTenantProfileInfo);
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo('your-tenantprofile-id').subscribe(tenantProfileInfo => {
  console.log('Get Tenant Profile Info:', tenantProfileInfo);
});
```

**7. getTenantProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(tenantProfileInfos => {
  console.log('Get Tenant Profile Infos:', tenantProfileInfos);
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds('your-tenantprofileids-value').subscribe(tenantProfilesByIds => {
  console.log('Get Tenant Profiles By Ids:', tenantProfilesByIds);
});
```
