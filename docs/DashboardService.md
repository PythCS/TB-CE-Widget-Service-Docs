# DashboardService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('DashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

**1. getTenantDashboards**

```javascript
dashboardService.getTenantDashboards(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Dashboards tenant:', tenant);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
dashboardService.getTenantDashboardsByTenantId('your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Dashboards By Tenant Id tenant:', tenant);
});
```

**3. getCustomerDashboards**

```javascript
dashboardService.getCustomerDashboards('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(dashboard => {
  console.log('Fetched  Customer Dashboards dashboard:', dashboard);
});
```

**4. getDashboard**

```javascript
dashboardService.getDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Fetched  Dashboard dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
dashboardService.exportDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('export Dashboard dashboard:', dashboard);
});
```

**6. getDashboardInfo**

```javascript
dashboardService.getDashboardInfo('your-dashboard-id').subscribe(dashboard => {
  console.log('Fetched  Dashboard Info dashboard:', dashboard);
});
```

**7. getDashboards**

```javascript
dashboardService.getDashboards('your-dashboardids-value').subscribe(dashboard => {
  console.log('Fetched  Dashboards dashboard:', dashboard);
});
```

**8. saveDashboard**

```javascript
dashboardService.saveDashboard('your-dashboard-value').subscribe(dashboard => {
  console.log('Saved  Dashboard dashboard:', dashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
dashboardService.assignDashboardToCustomer('your-customer-id', 'your-dashboard-id').subscribe(dashboard => {
  console.log('assign Dashboard To Customer dashboard:', dashboard);
});
```

**10. makeDashboardPublic**

```javascript
dashboardService.makeDashboardPublic('your-dashboard-id').subscribe(dashboard => {
  console.log('make Dashboard Public dashboard:', dashboard);
});
```

**11. makeDashboardPrivate**

```javascript
dashboardService.makeDashboardPrivate('your-dashboard-id').subscribe(dashboard => {
  console.log('make Dashboard Private dashboard:', dashboard);
});
```

**12. updateDashboardCustomers**

```javascript
dashboardService.updateDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboard => {
  console.log('update Dashboard Customers dashboard:', dashboard);
});
```

**13. addDashboardCustomers**

```javascript
dashboardService.addDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboard => {
  console.log('add Dashboard Customers dashboard:', dashboard);
});
```

**14. removeDashboardCustomers**

```javascript
dashboardService.removeDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboard => {
  console.log('remove Dashboard Customers dashboard:', dashboard);
});
```

**15. getHomeDashboard**

```javascript
dashboardService.getHomeDashboard().subscribe(dashboard => {
  console.log('Fetched  Home Dashboard dashboard:', dashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
dashboardService.getTenantHomeDashboardInfo().subscribe(tenant => {
  console.log('Fetched  Tenant Home Dashboard Info tenant:', tenant);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
dashboardService.setTenantHomeDashboardInfo('your-homedashboardinfo-value').subscribe(tenant => {
  console.log('set Tenant Home Dashboard Info tenant:', tenant);
});
```

**18. getPublicDashboardLink**

```javascript
dashboardService.getPublicDashboardLink('your-dashboard-value').subscribe(dashboard => {
  console.log('Fetched  Public Dashboard Link dashboard:', dashboard);
});
```

**19. assignDashboardToEdge**

```javascript
dashboardService.assignDashboardToEdge('your-edge-id', 'your-dashboard-id').subscribe(dashboard => {
  console.log('assign Dashboard To Edge dashboard:', dashboard);
});
```
