# TENANT SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **TENANT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenants(pageLink).subscribe(tenants => {
  console.log('Get Tenants: tenants');
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds('your-id').subscribe(tenantsbyids => {
  console.log('Get Tenants By Ids: tenantsbyids');
});
```

**3. getTenantInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenantInfos(pageLink).subscribe(tenantinfos => {
  console.log('Get Tenant Infos: tenantinfos');
});
```

**4. getTenant**

```javascript
tenantService.getTenant('your-tenant-id').subscribe(tenant => {
  console.log('Get Tenant: tenant');
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo('your-tenant-id').subscribe(tenantInfo => {
  console.log('Get Tenant Info: tenantInfo');
});
```

**6. saveTenant**

```javascript
const tenant = tenant;
tenantService.saveTenant(tenant).subscribe(savedTenant => {
  console.log('Save Tenant: savedTenant');
});
```
