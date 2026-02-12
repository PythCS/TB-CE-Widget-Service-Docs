# TENANT

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

## Methods

### getTenants

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

tenantService.getTenants(pageLink).subscribe(result => {
  console.log('Tenants:', result);
});
```

### getTenantsByIds

```javascript
const tenantIds = 'your-tenants-id';

tenantService.getTenantsByIds(tenantIds).subscribe(result => {
  console.log('TenantsByIds:', result);
});
```

### getTenantInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

tenantService.getTenantInfos(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

### getTenant

```javascript
const tenantId = 'your-tenant-id';

tenantService.getTenant(tenantId).subscribe(result => {
  console.log('Tenant:', result);
});
```

### getTenantInfo

```javascript
const tenantId = 'your-tenant-id';

tenantService.getTenantInfo(tenantId).subscribe(info => {
  console.log('Info:', info);
});
```

### saveTenant

```javascript
const tenant = {
  // your tenant object
};

tenantService.saveTenant(tenant).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

