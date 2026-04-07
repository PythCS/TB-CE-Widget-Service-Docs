# Dashboard Service

Manage dashboards, assignments, and dashboard-related operations in ThingsBoard.

## Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

## Methods

**1. getTenantDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'title', 'ASC');

dashboardService.getTenantDashboards(pageLink).subscribe(response => {
  console.log('Tenant Dashboards:', response.data);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0);

dashboardService.getTenantDashboardsByTenantId(tenantId, pageLink).subscribe(response => {
  console.log('Dashboards by Tenant:', response.data);
});
```

**3. getCustomerDashboards**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0);

dashboardService.getCustomerDashboards(customerId, pageLink).subscribe(response => {
  console.log('Customer Dashboards:', response.data);
});
```

**4. getDashboard**

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.getDashboard(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.exportDashboard(dashboardId).subscribe(exportedDashboard => {
  console.log('Exported Dashboard:', exportedDashboard);
});
```

**6. getDashboardInfo**

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.getDashboardInfo(dashboardId).subscribe(dashboardInfo => {
  console.log('Dashboard Info:', dashboardInfo);
});
```

**7. getDashboards**

```javascript
const dashboardIds = ['dashboard-id-1', 'dashboard-id-2'];

dashboardService.getDashboards(dashboardIds).subscribe(dashboards => {
  console.log('Dashboards by IDs:', dashboards);
});
```

**8. saveDashboard**

```javascript
const dashboard = {
  title: 'Device Monitoring Dashboard',
  configuration: {
    widgets: [],
    states: {
      default: {
        name: 'Default',
        layouts: {}
      }
    }
  }
};

dashboardService.saveDashboard(dashboard).subscribe(savedDashboard => {
  console.log('Saved Dashboard:', savedDashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
const customerId = 'your-customer-id';
const dashboardId = 'your-dashboard-id';

dashboardService.assignDashboardToCustomer(customerId, dashboardId).subscribe(assignedDashboard => {
  console.log('Assigned Dashboard:', assignedDashboard);
});
```

**10. makeDashboardPublic**

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.makeDashboardPublic(dashboardId).subscribe(publicDashboard => {
  console.log('Public Dashboard:', publicDashboard);
});
```

**11. makeDashboardPrivate**

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.makeDashboardPrivate(dashboardId).subscribe(privateDashboard => {
  console.log('Private Dashboard:', privateDashboard);
});
```

**12. updateDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['customer-id-1', 'customer-id-2'];

dashboardService.updateDashboardCustomers(dashboardId, customerIds).subscribe(updatedDashboard => {
  console.log('Dashboard Customers Updated:', updatedDashboard);
});
```

**13. addDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['customer-id-3', 'customer-id-4'];

dashboardService.addDashboardCustomers(dashboardId, customerIds).subscribe(updatedDashboard => {
  console.log('Dashboard Customers Added:', updatedDashboard);
});
```

**14. removeDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['customer-id-1'];

dashboardService.removeDashboardCustomers(dashboardId, customerIds).subscribe(updatedDashboard => {
  console.log('Dashboard Customers Removed:', updatedDashboard);
});
```

**15. getHomeDashboard**

```javascript
dashboardService.getHomeDashboard().subscribe(homeDashboard => {
  console.log('Home Dashboard:', homeDashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
dashboardService.getTenantHomeDashboardInfo().subscribe(homeInfo => {
  console.log('Tenant Home Dashboard Info:', homeInfo);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
const homeDashboardInfo = {
  dashboardId: { entityType: 'DASHBOARD', id: 'your-dashboard-id' },
  hideDashboardToolbar: false
};

dashboardService.setTenantHomeDashboardInfo(homeDashboardInfo).subscribe(result => {
  console.log('Home dashboard info set successfully');
});
```

**18. getPublicDashboardLink**

```javascript
const dashboard = { publicCustomerId: 'public-customer-id' };

const publicLink = dashboardService.getPublicDashboardLink(dashboard);
console.log('Public Dashboard Link:', publicLink);
```

**19. assignDashboardToEdge**

```javascript
const edgeId = 'your-edge-id';
const dashboardId = 'your-dashboard-id';

dashboardService.assignDashboardToEdge(edgeId, dashboardId).subscribe(assignedDashboard => {
  console.log('Dashboard Assigned to Edge:', assignedDashboard);
});
```