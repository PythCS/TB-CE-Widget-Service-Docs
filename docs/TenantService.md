# TenantService

### **TENANTSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
tenantService.getTenants(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenant => {
  console.log('Tenants:', tenant);
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds(['id1', 'id2'], { /* your config */ }).subscribe(tenantbyid => {
  console.log('Tenants By Ids:', tenantbyid);
});
```

**3. getTenantInfos**

```javascript
tenantService.getTenantInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantinfo => {
  console.log('Tenant Infos:', tenantinfo);
});
```

**4. getTenant**

```javascript
tenantService.getTenant('your-tenant-id', { /* your config */ }).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo('your-tenant-id', { /* your config */ }).subscribe(tenantinfo => {
  console.log('Tenant Info:', tenantinfo);
});
```

**6. saveTenant**

```javascript
tenantService.saveTenant({ /* your tenant object */ }, { /* your config */ }).subscribe(savedTenant => {
  console.log('Saved Tenant:', savedTenant);
});
```
