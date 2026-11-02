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

**3. getDashboards**

```javascript
self.ctx.dashboardService.getDashboards('your-dashboardids-value').subscribe(dashboards => {
  console.log('Get Dashboards:', dashboards);
});
```

**4. getUserDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getUserDashboards('your-user-id', 'your-operation-value', pageLink).subscribe(userDashboards => {
  console.log('Get User Dashboards:', userDashboards);
});
```

**5. getAllDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getAllDashboards(true, pageLink).subscribe(allDashboards => {
  console.log('Get All Dashboards:', allDashboards);
});
```

**6. getCustomerDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getCustomerDashboards(true, 'your-customer-id', pageLink).subscribe(customerDashboards => {
  console.log('Get Customer Dashboards:', customerDashboards);
});
```

**7. getGroupDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getGroupDashboards('your-group-id', pageLink).subscribe(groupDashboards => {
  console.log('Get Group Dashboards:', groupDashboards);
});
```

**8. getDashboard**

```javascript
self.ctx.dashboardService.getDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Get Dashboard:', dashboard);
});
```

**9. exportDashboard**

```javascript
self.ctx.dashboardService.exportDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Export Dashboard:', dashboard);
});
```

**10. getDashboardInfo**

```javascript
self.ctx.dashboardService.getDashboardInfo('your-dashboard-id').subscribe(dashboardInfo => {
  console.log('Get Dashboard Info:', dashboardInfo);
});
```

**11. saveDashboard**

```javascript
self.ctx.dashboardService.saveDashboard('your-dashboard-value', 'your-entitygroupids-value').subscribe(dashboard => {
  console.log('Save Dashboard:', dashboard);
});
```

**12. getPublicDashboardLink**

```javascript
self.ctx.dashboardService.getPublicDashboardLink('your-dashboard-value', 'your-entitygroup-value').subscribe(publicDashboardLink => {
  console.log('Get Public Dashboard Link:', publicDashboardLink);
});
```
