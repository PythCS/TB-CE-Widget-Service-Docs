### **DASHBOARD SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardservice = $injector.get(self.ctx.servicesMap.get('dashboardservice'));

// Alternative: Direct context access
const dashboardservice = self.ctx.dashboardService;
```

**1. getTenantDashboards**

```javascript
const dashboardservice = self.ctx.dashboardService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardservice.getTenantDashboards(pageLink).subscribe(tenantdashboards => {
  console.log('Tenantdashboards:', tenantdashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const dashboardservice = self.ctx.dashboardService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardservice.getTenantDashboardsByTenantId(pageLink, 'your-tenant-id').subscribe(tenantdashboardsbytenantid => {
  console.log('Tenantdashboardsbytenantid:', tenantdashboardsbytenantid);
});
```

**3. getCustomerDashboards**

```javascript
const dashboardservice = self.ctx.dashboardService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardservice.getCustomerDashboards(pageLink, 'your-customer-id').subscribe(customerdashboards => {
  console.log('Customerdashboards:', customerdashboards);
});
```

**4. getDashboard**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.getDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.exportDashboard('your-dashboard-id').subscribe(exportdashboard => {
  console.log('Exportdashboard:', exportdashboard);
});
```

**6. getDashboardInfo**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.getDashboardInfo('your-dashboard-id').subscribe(dashboardinfo => {
  console.log('Dashboardinfo:', dashboardinfo);
});
```

**7. getDashboards**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.getDashboards('your-dashboard-id').subscribe(dashboards => {
  console.log('Dashboards:', dashboards);
});
```

**8. saveDashboard**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.saveDashboard(dashboard).subscribe(savedashboard => {
  console.log('Savedashboard:', savedashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.assignDashboardToCustomer('your-customer-id', 'your-dashboard-id').subscribe(assigndashboardtocustomer => {
  console.log('Assigndashboardtocustomer:', assigndashboardtocustomer);
});
```

**10. makeDashboardPublic**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.makeDashboardPublic('your-dashboard-id').subscribe(makedashboardpublic => {
  console.log('Makedashboardpublic:', makedashboardpublic);
});
```

**11. makeDashboardPrivate**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.makeDashboardPrivate('your-dashboard-id').subscribe(makedashboardprivate => {
  console.log('Makedashboardprivate:', makedashboardprivate);
});
```

**12. updateDashboardCustomers**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.updateDashboardCustomers('your-dashboard-id', 'your-customers-id').subscribe(updatedashboardcustomers => {
  console.log('Updatedashboardcustomers:', updatedashboardcustomers);
});
```

**13. addDashboardCustomers**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.addDashboardCustomers('your-dashboard-id', 'your-customers-id').subscribe(adddashboardcustomers => {
  console.log('Adddashboardcustomers:', adddashboardcustomers);
});
```

**14. removeDashboardCustomers**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.removeDashboardCustomers('your-dashboard-id', 'your-customers-id').subscribe(removedashboardcustomers => {
  console.log('Removedashboardcustomers:', removedashboardcustomers);
});
```

**15. getHomeDashboard**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.getHomeDashboard().subscribe(homedashboard => {
  console.log('Homedashboard:', homedashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.getTenantHomeDashboardInfo().subscribe(tenanthomedashboardinfo => {
  console.log('Tenanthomedashboardinfo:', tenanthomedashboardinfo);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.setTenantHomeDashboardInfo(homeDashboardInfo).subscribe(settenanthomedashboardinfo => {
  console.log('Settenanthomedashboardinfo:', settenanthomedashboardinfo);
});
```

**18. getPublicDashboardLink**

```javascript
const dashboardservice = self.ctx.dashboardService;
const result = dashboardservice.getPublicDashboardLink(dashboard);
console.log('Result:', result);
```

**19. getServerTimeDiff**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.getServerTimeDiff().subscribe(servertimediff => {
  console.log('Servertimediff:', servertimediff);
});
```

**20. getEdgeDashboards**

```javascript
const dashboardservice = self.ctx.dashboardService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardservice.getEdgeDashboards(pageLink, 'your-edge-id', 'your-type').subscribe(edgedashboards => {
  console.log('Edgedashboards:', edgedashboards);
});
```

**21. assignDashboardToEdge**

```javascript
const dashboardservice = self.ctx.dashboardService;
dashboardservice.assignDashboardToEdge('your-edge-id', 'your-dashboard-id').subscribe(assigndashboardtoedge => {
  console.log('Assigndashboardtoedge:', assigndashboardtoedge);
});
```

