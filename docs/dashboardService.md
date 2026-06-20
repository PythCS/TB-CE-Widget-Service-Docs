# DASHBOARD SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **DASHBOARD SERVICE**

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
dashboardService.getTenantDashboards(pageLink).subscribe(tenantdashboards => {
  console.log('Get Tenant Dashboards: tenantdashboards');
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getTenantDashboardsByTenantId('your-tenant-id', pageLink).subscribe(tenantDashboardsByTenantId => {
  console.log('Get Tenant Dashboards By Tenant Id:tenantDashboardsByTenantId');
});
```

**3. getCustomerDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getCustomerDashboards('your-customer-id', pageLink).subscribe(customerdashboards => {
  console.log('Get Customer Dashboards: customerdashboards');
});
```

**4. getDashboard**

```javascript
dashboardService.getDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Get Dashboard: dashboard');
});
```

**5. exportDashboard**

```javascript
dashboardService.exportDashboard('your-dashboard-id').subscribe(exported => {
  console.log('Export Dashboard: exported');
});
```

**6. getDashboardInfo**

```javascript
dashboardService.getDashboardInfo('your-dashboard-id').subscribe(dashboardInfo => {
  console.log('Get Dashboard Info: dashboardInfo');
});
```

**7. getDashboards**

```javascript
dashboardService.getDashboards('your-id').subscribe(dashboards => {
  console.log('Get Dashboards: dashboards');
});
```

**8. saveDashboard**

```javascript
const dashboard = dashboard;
dashboardService.saveDashboard(dashboard).subscribe(savedDashboard => {
  console.log('Save Dashboard: savedDashboard');
});
```

**9. assignDashboardToCustomer**

```javascript
dashboardService.assignDashboardToCustomer('your-customer-id', 'your-dashboard-id').subscribe(result => {
  console.log('Assign Dashboard To Customer: result');
});
```

**10. makeDashboardPublic**

```javascript
dashboardService.makeDashboardPublic('your-dashboard-id').subscribe(result => {
  console.log('Make Dashboard Public: result');
});
```

**11. makeDashboardPrivate**

```javascript
dashboardService.makeDashboardPrivate('your-dashboard-id').subscribe(result => {
  console.log('Make Dashboard Private: result');
});
```

**12. updateDashboardCustomers**

```javascript
dashboardService.updateDashboardCustomers('your-dashboard-id', 'your-id').subscribe(result => {
  console.log('Update Dashboard Customers: result');
});
```

**13. addDashboardCustomers**

```javascript
dashboardService.addDashboardCustomers('your-dashboard-id', 'your-id').subscribe(result => {
  console.log('Add Dashboard Customers: result');
});
```

**14. removeDashboardCustomers**

```javascript
dashboardService.removeDashboardCustomers('your-dashboard-id', 'your-id').subscribe(result => {
  console.log('Remove Dashboard Customers: result');
});
```

**15. getHomeDashboard**

```javascript
dashboardService.getHomeDashboard().subscribe(homeDashboard => {
  console.log('Get Home Dashboard: homeDashboard');
});
```

**16. getTenantHomeDashboardInfo**

```javascript
dashboardService.getTenantHomeDashboardInfo().subscribe(tenantHomeDashboardInfo => {
  console.log('Get Tenant Home Dashboard Info:tenantHomeDashboardInfo');
});
```

**17. setTenantHomeDashboardInfo**

```javascript
const homeDashboardInfo = homeDashboardInfo;
dashboardService.setTenantHomeDashboardInfo(homeDashboardInfo).subscribe(result => {
  console.log('Set Tenant Home Dashboard Info:result');
});
```

**18. getPublicDashboardLink**

```javascript
const dashboard = dashboard;
dashboardService.getPublicDashboardLink(dashboard).subscribe(publicDashboardLink => {
  console.log('Get Public Dashboard Link: publicDashboardLink');
});
```

**19. assignDashboardToEdge**

```javascript
dashboardService.assignDashboardToEdge('your-edge-id', 'your-dashboard-id').subscribe(result => {
  console.log('Assign Dashboard To Edge: result');
});
```
