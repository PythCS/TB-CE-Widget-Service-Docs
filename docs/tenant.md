### **TENANT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantservice = $injector.get(self.ctx.servicesMap.get('tenantservice'));

```

**1. getTenants**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantservice.getTenants(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
tenantservice.getTenantsByIds('your-tenant-id').subscribe(tenantsbyids => {
  console.log('Tenantsbyids:', tenantsbyids);
});
```

**3. getTenantInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantservice.getTenantInfos(pageLink).subscribe(tenantinfos => {
  console.log('Tenantinfos:', tenantinfos);
});
```

**4. getTenant**

```javascript
tenantservice.getTenant('your-tenant-id').subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
tenantservice.getTenantInfo('your-tenant-id').subscribe(tenantinfo => {
  console.log('Tenantinfo:', tenantinfo);
});
```

**6. saveTenant**

```javascript
tenantservice.saveTenant(tenant).subscribe(savetenant => {
  console.log('Savetenant:', savetenant);
});
```

