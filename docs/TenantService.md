# TenantService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('TenantService'));
```

**1. getTenants**

```javascript
tenantService.getTenants(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenants tenant:', tenant);
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds('your-tenantids-value').subscribe(tenant => {
  console.log('Fetched  Tenants By Ids tenant:', tenant);
});
```

**3. getTenantInfos**

```javascript
tenantService.getTenantInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Infos tenant:', tenant);
});
```

**4. getTenant**

```javascript
tenantService.getTenant('your-tenant-id').subscribe(tenant => {
  console.log('Fetched  Tenant tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo('your-tenant-id').subscribe(tenant => {
  console.log('Fetched  Tenant Info tenant:', tenant);
});
```

**6. saveTenant**

```javascript
tenantService.saveTenant('your-tenant-value').subscribe(tenant => {
  console.log('Saved  Tenant tenant:', tenant);
});
```
