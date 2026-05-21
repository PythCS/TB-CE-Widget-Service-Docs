# TenantProfileService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('TenantProfileService'));
```

**1. getTenantProfiles**

```javascript
tenantProfileService.getTenantProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Profiles tenant:', tenant);
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile('your-tenantprofile-id').subscribe(tenant => {
  console.log('Fetched  Tenant Profile tenant:', tenant);
});
```

**3. saveTenantProfile**

```javascript
tenantProfileService.saveTenantProfile('your-tenantprofile-value').subscribe(tenant => {
  console.log('Saved  Tenant Profile tenant:', tenant);
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile('your-tenantprofile-id').subscribe(tenant => {
  console.log('set Default Tenant Profile tenant:', tenant);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(tenant => {
  console.log('Fetched  Default Tenant Profile Info tenant:', tenant);
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo('your-tenantprofile-id').subscribe(tenant => {
  console.log('Fetched  Tenant Profile Info tenant:', tenant);
});
```

**7. getTenantProfileInfos**

```javascript
tenantProfileService.getTenantProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Profile Infos tenant:', tenant);
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds('your-tenantprofileids-value').subscribe(tenant => {
  console.log('Fetched  Tenant Profiles By Ids tenant:', tenant);
});
```
