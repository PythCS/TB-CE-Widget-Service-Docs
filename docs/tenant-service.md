# TENANT SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenants(pageLink).subscribe(tenants => {
  console.log('Get Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds('your-tenantids-value').subscribe(tenantsByIds => {
  console.log('Get Tenants By Ids:', tenantsByIds);
});
```

**3. getTenantInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenantInfos(pageLink).subscribe(tenantInfos => {
  console.log('Get Tenant Infos:', tenantInfos);
});
```

**4. getTenant**

```javascript
tenantService.getTenant('your-tenant-id').subscribe(tenant => {
  console.log('Get Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo('your-tenant-id').subscribe(tenantInfo => {
  console.log('Get Tenant Info:', tenantInfo);
});
```

**6. saveTenant**

```javascript
tenantService.saveTenant('your-tenant-value').subscribe(tenant => {
  console.log('Save Tenant:', tenant);
});
```
