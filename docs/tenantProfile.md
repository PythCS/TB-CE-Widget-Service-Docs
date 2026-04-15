# Tenant Profile

```javascript
// Service name: tenantProfile
// File: tenant-profile.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfile = $injector.get(self.ctx.servicesMap.get('tenantProfile'));
```

### **1. getTenantProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfile.getTenantProfiles(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **2. getTenantProfile**

```javascript
tenantProfile.getTenantProfile(tenantProfileId).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

### **3. saveTenantProfile**

```javascript
tenantProfile.saveTenantProfile(tenantProfile).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

### **4. setDefaultTenantProfile**

```javascript
tenantProfile.setDefaultTenantProfile(tenantProfileId).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

### **5. getDefaultTenantProfileInfo**

```javascript
tenantProfile.getDefaultTenantProfileInfo().subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

### **6. getTenantProfileInfo**

```javascript
tenantProfile.getTenantProfileInfo(tenantProfileId).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

### **7. getTenantProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfile.getTenantProfileInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **8. getTenantProfilesByIds**

```javascript
tenantProfile.getTenantProfilesByIds(tenantProfileIds).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```
