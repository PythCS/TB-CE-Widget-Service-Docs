# Dashboard Service

Complete reference for the DashboardService in ThingsBoard widget development.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

## Methods

### getDashboard

Get a dashboard by ID.

```javascript
const dashboardId = 'your-dashboard-id';
dashboardService.getDashboard(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### getTenantDashboards

Get paginated list of tenant dashboards.

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
dashboardService.getTenantDashboards(pageLink).subscribe(dashboards => {
  console.log('Tenant Dashboards:', dashboards);
});
```

### saveDashboard

Create or update a dashboard.

```javascript
const dashboard = {
  title: 'My Dashboard',
  configuration: {
    // Dashboard configuration
  },
  // Additional dashboard properties
};
dashboardService.saveDashboard(dashboard).subscribe(savedDashboard => {
  console.log('Saved Dashboard:', savedDashboard);
});
```

### getPublicDashboardLink

Generate a public link for a dashboard.

```javascript
const dashboard = {
  id: { id: 'your-dashboard-id' },
  publicCustomerId: 'public-customer-id'
};
const publicLink = dashboardService.getPublicDashboardLink(dashboard);
console.log('Public Dashboard Link:', publicLink);
```

### assignDashboardToCustomer

Assign a dashboard to a customer.

```javascript
const customerId = 'your-customer-id';
const dashboardId = 'your-dashboard-id';
dashboardService.assignDashboardToCustomer(customerId, dashboardId).subscribe(assignedDashboard => {
  console.log('Dashboard Assigned to Customer:', assignedDashboard);
});
```

## Common Use Cases

### Loading Dashboard List for User

```javascript
const pageLink = self.ctx.pageLink(50, 0, '', 'title', 'ASC');
dashboardService.getTenantDashboards(pageLink).subscribe(dashboardPage => {
  const dashboards = dashboardPage.data;
  console.log(`Found ${dashboards.length} dashboards`);
  
  dashboards.forEach(dashboard => {
    console.log(`Dashboard: ${dashboard.title}`);
  });
});
```

### Creating Dashboard Navigation

```javascript
// Get all dashboards for navigation menu
dashboardService.getTenantDashboards(self.ctx.pageLink(100, 0)).subscribe(dashboardPage => {
  const navigationItems = dashboardPage.data.map(dashboard => ({
    id: dashboard.id.id,
    title: dashboard.title,
    url: `/dashboard/${dashboard.id.id}`
  }));
  
  console.log('Navigation items:', navigationItems);
});
```