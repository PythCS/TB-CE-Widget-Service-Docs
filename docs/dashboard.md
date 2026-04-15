# Dashboard

```javascript
// Service name: dashboard
// File: dashboard.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const dashboard = self.ctx.dashboardService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const dashboard = $injector.get(self.ctx.servicesMap.get('dashboard'));
```

### **1. getTenantDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboard.getTenantDashboards(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **2. getTenantDashboardsByTenantId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboard.getTenantDashboardsByTenantId(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **3. getCustomerDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboard.getCustomerDashboards(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **4. getDashboard**

```javascript
dashboard.getDashboard(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### **5. exportDashboard**

```javascript
dashboard.exportDashboard(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### **6. getDashboardInfo**

```javascript
dashboard.getDashboardInfo(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### **7. getDashboards**

```javascript
dashboard.getDashboards(dashboardIds).subscribe(dashboards => {
  console.log('Dashboards:', dashboards);
});
```

### **8. saveDashboard**

```javascript
dashboard.saveDashboard(dashboard).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### **9. assignDashboardToCustomer**

```javascript
dashboard.assignDashboardToCustomer(customerId, dashboardId).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### **10. makeDashboardPublic**

```javascript
dashboard.makeDashboardPublic(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### **11. makeDashboardPrivate**

```javascript
dashboard.makeDashboardPrivate(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### **12. updateDashboardCustomers**

```javascript
dashboard.updateDashboardCustomers(dashboardId, customerIds).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### **13. addDashboardCustomers**

```javascript
dashboard.addDashboardCustomers(dashboardId, customerIds).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### **14. removeDashboardCustomers**

```javascript
dashboard.removeDashboardCustomers(dashboardId, customerIds).subscribe(customer => {
  console.log('Customer:', customer);
});
```

### **15. getHomeDashboard**

```javascript
dashboard.getHomeDashboard().subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### **16. getTenantHomeDashboardInfo**

```javascript
dashboard.getTenantHomeDashboardInfo().subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

### **17. setTenantHomeDashboardInfo**

```javascript
dashboard.setTenantHomeDashboardInfo(homeDashboardInfo).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

### **18. getPublicDashboardLink**

```javascript
dashboard.getPublicDashboardLink(dashboard).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### **19. assignDashboardToEdge**

```javascript
dashboard.assignDashboardToEdge(edgeId, dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```
