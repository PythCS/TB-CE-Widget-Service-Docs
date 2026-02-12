### **TENANT PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantprofileservice = $injector.get(self.ctx.servicesMap.get('tenantprofileservice'));

```

**1. getTenantProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantprofileservice.getTenantProfiles(pageLink).subscribe(tenantprofiles => {
  console.log('Tenantprofiles:', tenantprofiles);
});
```

**2. getTenantProfile**

```javascript
tenantprofileservice.getTenantProfile('your-tenant-id').subscribe(tenantprofile => {
  console.log('Tenantprofile:', tenantprofile);
});
```

**3. saveTenantProfile**

```javascript
tenantprofileservice.saveTenantProfile(tenantProfile).subscribe(savetenantprofile => {
  console.log('Savetenantprofile:', savetenantprofile);
});
```

**4. setDefaultTenantProfile**

```javascript
tenantprofileservice.setDefaultTenantProfile('your-tenant-id').subscribe(setdefaulttenantprofile => {
  console.log('Setdefaulttenantprofile:', setdefaulttenantprofile);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantprofileservice.getDefaultTenantProfileInfo().subscribe(defaulttenantprofileinfo => {
  console.log('Defaulttenantprofileinfo:', defaulttenantprofileinfo);
});
```

**6. getTenantProfileInfo**

```javascript
tenantprofileservice.getTenantProfileInfo('your-tenant-id').subscribe(tenantprofileinfo => {
  console.log('Tenantprofileinfo:', tenantprofileinfo);
});
```

**7. getTenantProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantprofileservice.getTenantProfileInfos(pageLink).subscribe(tenantprofileinfos => {
  console.log('Tenantprofileinfos:', tenantprofileinfos);
});
```

**8. getTenantProfilesByIds**

```javascript
tenantprofileservice.getTenantProfilesByIds('your-tenant-id').subscribe(tenantprofilesbyids => {
  console.log('Tenantprofilesbyids:', tenantprofilesbyids);
});
```

