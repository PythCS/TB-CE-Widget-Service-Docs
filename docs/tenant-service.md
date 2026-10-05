# TENANT SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenants(pageLink).subscribe(tenants => {
  console.log('List of Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const tenantIds = ['your-tenant-i-1', 'your-tenant-i-2'];
tenantService.getTenantsByIds(tenantIds).subscribe(tenantsBys => {
  console.log('List of Tenants By Ids:', tenantsBys);
});
```

**3. getTenantInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenantInfos(pageLink).subscribe(tenantInfos => {
  console.log('List of Tenant Infos:', tenantInfos);
});
```

**4. getTenant**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const tenantId = 'your-tenant-id';
tenantService.getTenant(tenantId).subscribe(tenant => {
  console.log('Get Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const tenantId = 'your-tenant-id';
tenantService.getTenantInfo(tenantId).subscribe(tenantInfo => {
  console.log('Get Tenant Info:', tenantInfo);
});
```

**6. saveTenant**

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
const tenant = {  // Tenant object
  // ... set the fields you need
};
tenantService.saveTenant(tenant).subscribe(savedTenant => {
  console.log('Saved Tenant:', savedTenant);
});
```
