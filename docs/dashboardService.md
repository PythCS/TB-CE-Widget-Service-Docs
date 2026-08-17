# DASHBOARD SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

**1. getTenantDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getTenantDashboards(pageLink).subscribe(tenantDashboards => {
  console.log('Get Tenant Dashboards:', tenantDashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getTenantDashboardsByTenantId('your-tenant-id', pageLink).subscribe(tenantDashboardsByTenantId => {
  console.log('Get Tenant Dashboards By Tenant Id:', tenantDashboardsByTenantId);
});
```

**3. getCustomerDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getCustomerDashboards('your-customer-id', pageLink).subscribe(customerDashboards => {
  console.log('Get Customer Dashboards:', customerDashboards);
});
```

**4. getDashboard**

```javascript
self.ctx.dashboardService.getDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Get Dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
self.ctx.dashboardService.exportDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Export Dashboard:', dashboard);
});
```

**6. getDashboardInfo**

```javascript
self.ctx.dashboardService.getDashboardInfo('your-dashboard-id').subscribe(dashboardInfo => {
  console.log('Get Dashboard Info:', dashboardInfo);
});
```

**7. getDashboards**

```javascript
self.ctx.dashboardService.getDashboards('your-dashboardids-value').subscribe(dashboards => {
  console.log('Get Dashboards:', dashboards);
});
```

**8. saveDashboard**

```javascript
self.ctx.dashboardService.saveDashboard('your-dashboard-value').subscribe(dashboard => {
  console.log('Save Dashboard:', dashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
self.ctx.dashboardService.assignDashboardToCustomer('your-customer-id', 'your-dashboard-id').subscribe(dashboardToCustomer => {
  console.log('Assign Dashboard To Customer:', dashboardToCustomer);
});
```

**10. makeDashboardPublic**

```javascript
self.ctx.dashboardService.makeDashboardPublic('your-dashboard-id').subscribe(makeDashboardPublic => {
  console.log('Make Dashboard Public:', makeDashboardPublic);
});
```

**11. makeDashboardPrivate**

```javascript
self.ctx.dashboardService.makeDashboardPrivate('your-dashboard-id').subscribe(makeDashboardPrivate => {
  console.log('Make Dashboard Private:', makeDashboardPrivate);
});
```

**12. updateDashboardCustomers**

```javascript
self.ctx.dashboardService.updateDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboardCustomers => {
  console.log('Update Dashboard Customers:', dashboardCustomers);
});
```

**13. addDashboardCustomers**

```javascript
self.ctx.dashboardService.addDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(addDashboardCustomers => {
  console.log('Add Dashboard Customers:', addDashboardCustomers);
});
```

**14. removeDashboardCustomers**

```javascript
self.ctx.dashboardService.removeDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboardCustomers => {
  console.log('Remove Dashboard Customers:', dashboardCustomers);
});
```

**15. getHomeDashboard**

```javascript
self.ctx.dashboardService.getHomeDashboard().subscribe(homeDashboard => {
  console.log('Get Home Dashboard:', homeDashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
self.ctx.dashboardService.getTenantHomeDashboardInfo().subscribe(tenantHomeDashboardInfo => {
  console.log('Get Tenant Home Dashboard Info:', tenantHomeDashboardInfo);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
self.ctx.dashboardService.setTenantHomeDashboardInfo('your-homedashboardinfo-value').subscribe(tenantHomeDashboardInfo => {
  console.log('Set Tenant Home Dashboard Info:', tenantHomeDashboardInfo);
});
```

**18. getPublicDashboardLink**

```javascript
self.ctx.dashboardService.getPublicDashboardLink('your-dashboard-value').subscribe(publicDashboardLink => {
  console.log('Get Public Dashboard Link:', publicDashboardLink);
});
```

**19. assignDashboardToEdge**

```javascript
self.ctx.dashboardService.assignDashboardToEdge('your-edge-id', 'your-dashboard-id').subscribe(dashboardToEdge => {
  console.log('Assign Dashboard To Edge:', dashboardToEdge);
});
```
