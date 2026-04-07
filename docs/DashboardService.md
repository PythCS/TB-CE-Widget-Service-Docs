# DashboardService

### **DASHBOARDSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

**1. getTenantDashboards**

```javascript
dashboardService.getTenantDashboards(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantdahboard => {
  console.log('Tenant Dashboards:', tenantdahboard);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
dashboardService.getTenantDashboardsByTenantId('your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantdashboardsbytenantid => {
  console.log('Tenant Dashboards By Tenant Id:', tenantdashboardsbytenantid);
});
```

**3. getCustomerDashboards**

```javascript
dashboardService.getCustomerDashboards('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(cutomerdahboard => {
  console.log('Customer Dashboards:', cutomerdahboard);
});
```

**4. getDashboard**

```javascript
dashboardService.getDashboard('your-dashboard-id', { /* your config */ }).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
dashboardService.exportDashboard('your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. getDashboardInfo**

```javascript
dashboardService.getDashboardInfo('your-dashboard-id', { /* your config */ }).subscribe(dashboardinfo => {
  console.log('Dashboard Info:', dashboardinfo);
});
```

**7. getDashboards**

```javascript
dashboardService.getDashboards(['id1', 'id2'], { /* your config */ }).subscribe(dahboard => {
  console.log('Dashboards:', dahboard);
});
```

**8. saveDashboard**

```javascript
dashboardService.saveDashboard({ /* your dashboard object */ }, { /* your config */ }).subscribe(savedDashboard => {
  console.log('Saved Dashboard:', savedDashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
dashboardService.assignDashboardToCustomer('your-customer-id', 'your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. makeDashboardPublic**

```javascript
dashboardService.makeDashboardPublic('your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. makeDashboardPrivate**

```javascript
dashboardService.makeDashboardPrivate('your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. updateDashboardCustomers**

```javascript
dashboardService.updateDashboardCustomers('your-dashboard-id', ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. addDashboardCustomers**

```javascript
dashboardService.addDashboardCustomers('your-dashboard-id', ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**14. removeDashboardCustomers**

```javascript
dashboardService.removeDashboardCustomers('your-dashboard-id', ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getHomeDashboard**

```javascript
dashboardService.getHomeDashboard({ /* your config */ }).subscribe(homedashboard => {
  console.log('Home Dashboard:', homedashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
dashboardService.getTenantHomeDashboardInfo({ /* your config */ }).subscribe(tenanthomedashboardinfo => {
  console.log('Tenant Home Dashboard Info:', tenanthomedashboardinfo);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
dashboardService.setTenantHomeDashboardInfo({ /* your homeDashboardInfo */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**18. getPublicDashboardLink**

```javascript
dashboardService.getPublicDashboardLink({ /* your dashboard object */ }).subscribe(publicdashboardlink => {
  console.log('Public Dashboard Link:', publicdashboardlink);
});
```

**19. assignDashboardToEdge**

```javascript
dashboardService.assignDashboardToEdge('your-edge-id', 'your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
