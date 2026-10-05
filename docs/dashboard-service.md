# DASHBOARD SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

**1. getTenantDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getTenantDashboards(pageLink).subscribe(tenantDashboards => {
  console.log('List of Tenant Dashboards:', tenantDashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const dashboardService = self.ctx.dashboardService;
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getTenantDashboardsByTenantId(tenantId, pageLink).subscribe(tenantDashboardsByTenants => {
  console.log('List of Tenant Dashboards By Tenant Ids:', tenantDashboardsByTenants);
});
```

**3. getDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboardIds = ['your-dashboard-i-1', 'your-dashboard-i-2'];
dashboardService.getDashboards(dashboardIds).subscribe(dashboards => {
  console.log('List of Dashboards:', dashboards);
});
```

**4. getUserDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const userId = 'your-user-id';
const operation = {  // Operation object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getUserDashboards(userId, operation, pageLink).subscribe(userDashboards => {
  console.log('List of User Dashboards:', userDashboards);
});
```

**5. getAllDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getAllDashboards(includeCustomers, pageLink).subscribe(allDashboards => {
  console.log('List of All Dashboards:', allDashboards);
});
```

**6. getCustomerDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getCustomerDashboards(includeCustomers, customerId, pageLink).subscribe(customerDashboards => {
  console.log('List of Customer Dashboards:', customerDashboards);
});
```

**7. getGroupDashboards**

```javascript
const dashboardService = self.ctx.dashboardService;
const groupId = 'your-group-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getGroupDashboards(groupId, pageLink).subscribe(groupDashboards => {
  console.log('List of Group Dashboards:', groupDashboards);
});
```

**8. getDashboard**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboardId = 'your-dashboard-id';
dashboardService.getDashboard(dashboardId).subscribe(dashboard => {
  console.log('Get Dashboard:', dashboard);
});
```

**9. exportDashboard**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboardId = 'your-dashboard-id';
dashboardService.exportDashboard(dashboardId).subscribe(exportDashboard => {
  console.log('Export Dashboard:', exportDashboard);
});
```

**10. getDashboardInfo**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboardId = 'your-dashboard-id';
dashboardService.getDashboardInfo(dashboardId).subscribe(dashboardInfo => {
  console.log('Get Dashboard Info:', dashboardInfo);
});
```

**11. saveDashboard**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboard = {  // Dashboard object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
dashboardService.saveDashboard(dashboard, entityGroupIds).subscribe(savedDashboard => {
  console.log('Saved Dashboard:', savedDashboard);
});
```

**12. getPublicDashboardLink**

```javascript
const dashboardService = self.ctx.dashboardService;
const dashboard = 'dashboard';  // e.g. one of the allowed DashboardInfo
const entityGroup = {  // EntityGroup object
  // ... set the fields you need
};
const result = dashboardService.getPublicDashboardLink(dashboard, entityGroup);
console.log('Result:', result);
```
