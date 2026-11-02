# DASHBOARD REPORT SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardReportService = $injector.get(self.ctx.servicesMap.get('dashboardReportService'));

// Alternative: Direct context access
const dashboardReportService = self.ctx.reportService;
```

**1. loadReportParams**

```javascript
self.ctx.reportService.loadReportParams().subscribe(loadReportParams => {
  console.log('Load Report Params:', loadReportParams);
});
```

**2. onWaitForMap**

```javascript
self.ctx.reportService.onWaitForMap().subscribe(onWaitForMap => {
  console.log('On Wait For Map:', onWaitForMap);
});
```

**3. onWaitForWidget**

```javascript
self.ctx.reportService.onWaitForWidget().subscribe(onWaitForWidget => {
  console.log('On Wait For Widget:', onWaitForWidget);
});
```

**4. onMapLoaded**

```javascript
self.ctx.reportService.onMapLoaded('your-uu-id').subscribe(onMapLoaded => {
  console.log('On Map Loaded:', onMapLoaded);
});
```

**5. onWidgetLoaded**

```javascript
self.ctx.reportService.onWidgetLoaded('your-uu-id').subscribe(onWidgetLoaded => {
  console.log('On Widget Loaded:', onWidgetLoaded);
});
```

**6. downloadDashboardReport**

```javascript
self.ctx.reportService.downloadDashboardReport('your-dashboard-id', 'your-reporttype-value', 'your-state-value', 'your-timewindow-value').subscribe(downloadDashboardReport => {
  console.log('Download Dashboard Report:', downloadDashboardReport);
});
```

**7. downloadTestReport**

```javascript
self.ctx.reportService.downloadTestReport('your-reportconfig-value', 'your-reportsserverendpointurl-value').subscribe(downloadTestReport => {
  console.log('Download Test Report:', downloadTestReport);
});
```

**8. openReport**

```javascript
self.ctx.reportService.openReport('your-openreportmessage-value').subscribe(openReport => {
  console.log('Open Report:', openReport);
});
```

**9. pageHeight**

```javascript
self.ctx.reportService.pageHeight().subscribe(pageHeight => {
  console.log('Page Height:', pageHeight);
});
```

**10. waitForLayoutReady**

```javascript
self.ctx.reportService.waitForLayoutReady().subscribe(waitForLayoutReady => {
  console.log('Wait For Layout Ready:', waitForLayoutReady);
});
```

**11. waitForReportPage**

```javascript
self.ctx.reportService.waitForReportPage().subscribe(waitForReportPage => {
  console.log('Wait For Report Page:', waitForReportPage);
});
```

**12. waitForWebsocketData**

```javascript
self.ctx.reportService.waitForWebsocketData().subscribe(waitForWebsocketData => {
  console.log('Wait For Websocket Data:', waitForWebsocketData);
});
```

**13. waitWidgets**

```javascript
self.ctx.reportService.waitWidgets().subscribe(waitWidgets => {
  console.log('Wait Widgets:', waitWidgets);
});
```

**14. waitForWidgetsLoaded**

```javascript
self.ctx.reportService.waitForWidgetsLoaded().subscribe(waitForWidgetsLoaded => {
  console.log('Wait For Widgets Loaded:', waitForWidgetsLoaded);
});
```

**15. isReportPageDomReady**

```javascript
self.ctx.reportService.isReportPageDomReady().subscribe(isReportPageDomReady => {
  console.log('Is Report Page Dom Ready:', isReportPageDomReady);
});
```

**16. clearReport**

```javascript
self.ctx.reportService.clearReport().subscribe(report => {
  console.log('Clear Report:', report);
});
```

**17. loadUser**

```javascript
self.ctx.reportService.loadUser('your-access-token', 'your-public-id').subscribe(loadUser => {
  console.log('Load User:', loadUser);
});
```

**18. downloadReport**

```javascript
self.ctx.reportService.downloadReport('your-url-value', 'your-reportparams-value', 'your-params-value').subscribe(downloadReport => {
  console.log('Download Report:', downloadReport);
});
```
