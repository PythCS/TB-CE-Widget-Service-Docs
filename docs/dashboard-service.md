# DASHBOARD

Dashboard creation and management.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

## Methods

### getTenantDashboards

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

dashboardService.getTenantDashboards(pageLink).subscribe(dashboards => {
  console.log('Dashboards:', dashboards);
});
```

### getTenantDashboardsByTenantId

```javascript
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

dashboardService.getTenantDashboardsByTenantId(tenantId, pageLink).subscribe(dashboards => {
  console.log('Dashboards:', dashboards);
});
```

### getCustomerDashboards

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

dashboardService.getCustomerDashboards(customerId, pageLink).subscribe(dashboards => {
  console.log('Dashboards:', dashboards);
});
```

### getDashboard

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.getDashboard(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### exportDashboard

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.exportDashboard(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### getDashboardInfo

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.getDashboardInfo(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### getDashboards

```javascript
const dashboardIds = 'your-dashboards-id';

dashboardService.getDashboards(dashboardIds).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### saveDashboard

```javascript
const dashboard = {
  // your dashboard object
};

dashboardService.saveDashboard(dashboard).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### assignDashboardToCustomer

```javascript
const customerId = 'your-customer-id';
const dashboardId = 'your-dashboard-id';

dashboardService.assignDashboardToCustomer(customerId, dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### makeDashboardPublic

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.makeDashboardPublic(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### makeDashboardPrivate

```javascript
const dashboardId = 'your-dashboard-id';

dashboardService.makeDashboardPrivate(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### updateDashboardCustomers

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = 'your-customers-id';

dashboardService.updateDashboardCustomers(dashboardId, customerIds).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### addDashboardCustomers

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = 'your-customers-id';

dashboardService.addDashboardCustomers(dashboardId, customerIds).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### removeDashboardCustomers

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = 'your-customers-id';

dashboardService.removeDashboardCustomers(dashboardId, customerIds).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### getHomeDashboard

```javascript
dashboardService.getHomeDashboard().subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### getTenantHomeDashboardInfo

```javascript
dashboardService.getTenantHomeDashboardInfo().subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### setTenantHomeDashboardInfo

```javascript
const homeDashboardInfo = {
  // your homeDashboardInfo object
};

dashboardService.setTenantHomeDashboardInfo(homeDashboardInfo).subscribe(result => {
  console.log('setTenantHomeDashboardInfo:', result);
});
```

### getPublicDashboardLink

```javascript
const dashboard = {
  // your dashboard object
};

const url = dashboardService.getPublicDashboardLink(dashboard);
console.log('URL:', url);
```

### getServerTimeDiff

```javascript
dashboardService.getServerTimeDiff().subscribe(result => {
  console.log('Result:', result);
});
```

### getEdgeDashboards

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

dashboardService.getEdgeDashboards(edgeId, pageLink, type).subscribe(dashboards => {
  console.log('Dashboards:', dashboards);
});
```

### assignDashboardToEdge

```javascript
const edgeId = 'your-edge-id';
const dashboardId = 'your-dashboard-id';

dashboardService.assignDashboardToEdge(edgeId, dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

