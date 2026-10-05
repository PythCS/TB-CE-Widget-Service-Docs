# DASHBOARD REPORT SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardReportService = $injector.get(self.ctx.servicesMap.get('dashboardReportService'));

// Alternative: Direct context access
const dashboardReportService = self.ctx.reportService;
```

**1. loadReportParams**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.loadReportParams();
console.log('Result:', result);
```

**2. onWaitForMap**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.onWaitForMap();
console.log('Result:', result);
```

**3. onWaitForWidget**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.onWaitForWidget();
console.log('Result:', result);
```

**4. onMapLoaded**

```javascript
const dashboardReportService = self.ctx.reportService;
const uuid = 'your-uuid';
const result = dashboardReportService.onMapLoaded(uuid);
console.log('Result:', result);
```

**5. onWidgetLoaded**

```javascript
const dashboardReportService = self.ctx.reportService;
const uuid = 'your-uuid';
const result = dashboardReportService.onWidgetLoaded(uuid);
console.log('Result:', result);
```

**6. downloadDashboardReport**

```javascript
const dashboardReportService = self.ctx.reportService;
const dashboardId = 'your-dashboard-id';
const reportType = {  // DashboardReportType object
  // ... set the fields you need
};
const state = 'state-value';
const timewindow = {  // Timewindow object
  // ... set the fields you need
};
dashboardReportService.downloadDashboardReport(dashboardId, reportType, state, timewindow).subscribe(downloadDashboardReport => {
  console.log('Download Dashboard Report:', downloadDashboardReport);
});
```

**7. downloadTestReport**

```javascript
const dashboardReportService = self.ctx.reportService;
const reportConfig = {  // DashboardReportParams object
  // ... set the fields you need
};
const reportsServerEndpointUrl = 'your-reports-server-endpoint-url';
dashboardReportService.downloadTestReport(reportConfig, reportsServerEndpointUrl).subscribe(downloadTestReport => {
  console.log('Download Test Report:', downloadTestReport);
});
```

**8. openReport**

```javascript
const dashboardReportService = self.ctx.reportService;
const openReportMessage = {  // OpenReportMessage object
  // ... set the fields you need
};
dashboardReportService.openReport(openReportMessage).subscribe(openReport => {
  console.log('Open Report:', openReport);
});
```

**9. pageHeight**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.pageHeight();
console.log('Result:', result);
```

**10. waitForLayoutReady**

```javascript
const dashboardReportService = self.ctx.reportService;
dashboardReportService.waitForLayoutReady().subscribe(waitForLayoutReady => {
  console.log('Wait For Layout Ready:', waitForLayoutReady);
});
```

**11. waitForReportPage**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.waitForReportPage();
console.log('Result:', result);
```

**12. waitForWebsocketData**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.waitForWebsocketData();
console.log('Result:', result);
```

**13. waitWidgets**

```javascript
const dashboardReportService = self.ctx.reportService;
dashboardReportService.waitWidgets().subscribe(waitWidgets => {
  console.log('Wait Widgets:', waitWidgets);
});
```

**14. waitForWidgetsLoaded**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.waitForWidgetsLoaded();
console.log('Result:', result);
```

**15. isReportPageDomReady**

```javascript
const dashboardReportService = self.ctx.reportService;
const result = dashboardReportService.isReportPageDomReady();
console.log('Result:', result);
```

**16. clearReport**

```javascript
const dashboardReportService = self.ctx.reportService;
dashboardReportService.clearReport().subscribe(clearReport => {
  console.log('Clear Report:', clearReport);
});
```

**17. loadUser**

```javascript
const dashboardReportService = self.ctx.reportService;
const accessToken = 'your-access-token';
const publicId = 'your-public-id';
dashboardReportService.loadUser(accessToken, publicId).subscribe(user => {
  console.log('Load User:', user);
});
```

**18. downloadReport**

```javascript
const dashboardReportService = self.ctx.reportService;
const url = 'your-url';
const reportParams = {  // DashboardReportParams object
  // ... set the fields you need
};
const params = 'value';
dashboardReportService.downloadReport(url, reportParams, params).subscribe(downloadReport => {
  console.log('Download Report:', downloadReport);
});
```
