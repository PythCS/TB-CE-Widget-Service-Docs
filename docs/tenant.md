# Tenant

```javascript
// Service name: tenant
// File: tenant.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenant = $injector.get(self.ctx.servicesMap.get('tenant'));
```

### **1. getTenants**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenant.getTenants(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **2. getTenantsByIds**

```javascript
tenant.getTenantsByIds(tenantIds).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **3. getTenantInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenant.getTenantInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **4. getTenant**

```javascript
tenant.getTenant(tenantId).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

### **5. getTenantInfo**

```javascript
tenant.getTenantInfo(tenantId).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

### **6. saveTenant**

```javascript
tenant.saveTenant(tenant).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```
