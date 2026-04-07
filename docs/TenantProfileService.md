# TenantProfileService

### **TENANTPROFILESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
tenantProfileService.getTenantProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantprofile => {
  console.log('Tenant Profiles:', tenantprofile);
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile('your-tenantprofile-id', { /* your config */ }).subscribe(tenantprofile => {
  console.log('Tenant Profile:', tenantprofile);
});
```

**3. saveTenantProfile**

```javascript
tenantProfileService.saveTenantProfile({ /* your tenantProfile */ }, { /* your config */ }).subscribe(savedTenantProfile => {
  console.log('Saved TenantProfile:', savedTenantProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile('your-tenantprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo({ /* your config */ }).subscribe(defaulttenantprofileinfo => {
  console.log('Default Tenant Profile Info:', defaulttenantprofileinfo);
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo('your-tenantprofile-id', { /* your config */ }).subscribe(tenantprofileinfo => {
  console.log('Tenant Profile Info:', tenantprofileinfo);
});
```

**7. getTenantProfileInfos**

```javascript
tenantProfileService.getTenantProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantprofileinfo => {
  console.log('Tenant Profile Infos:', tenantprofileinfo);
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds(['id1', 'id2'], { /* your config */ }).subscribe(tenantprofilebyid => {
  console.log('Tenant Profiles By Ids:', tenantprofilebyid);
});
```
