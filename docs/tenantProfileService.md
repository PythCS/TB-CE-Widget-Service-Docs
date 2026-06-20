# TENANT PROFILE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **TENANT PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfiles(pageLink).subscribe(tenantprofiles => {
  console.log('Get Tenant Profiles: tenantprofiles');
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile('your-tenant-profile-id').subscribe(tenantProfile => {
  console.log('Get Tenant Profile: tenantProfile');
});
```

**3. saveTenantProfile**

```javascript
const tenantProfile = tenantProfile;
tenantProfileService.saveTenantProfile(tenantProfile).subscribe(savedTenantProfile => {
  console.log('Save Tenant Profile: savedTenantProfile');
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile('your-tenant-profile-id').subscribe(result => {
  console.log('Set Default Tenant Profile: result');
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(defaultTenantProfileInfo => {
  console.log('Get Default Tenant Profile Info:defaultTenantProfileInfo');
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo('your-tenant-profile-id').subscribe(tenantProfileInfo => {
  console.log('Get Tenant Profile Info: tenantProfileInfo');
});
```

**7. getTenantProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(tenantprofileinfos => {
  console.log('Get Tenant Profile Infos: tenantprofileinfos');
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds('your-id').subscribe(tenantprofilesbyids => {
  console.log('Get Tenant Profiles By Ids: tenantprofilesbyids');
});
```
