# REPORT SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const reportService = $injector.get(self.ctx.servicesMap.get('reportService'));
```

**1. getReport**

```javascript
reportService.getReport('your-report-id').subscribe(report => {
  console.log('Get Report:', report);
});
```

**2. getReports**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
reportService.getReports(pageLink).subscribe(reports => {
  console.log('Get Reports:', reports);
});
```

**3. getReportInfos**

```javascript
reportService.getReportInfos('your-query-value').subscribe(reportInfos => {
  console.log('Get Report Infos:', reportInfos);
});
```

**4. downloadReport**

```javascript
reportService.downloadReport('your-report-id').subscribe(downloadReport => {
  console.log('Download Report:', downloadReport);
});
```

**5. requestReport**

```javascript
reportService.requestReport('your-reportrequest-value').subscribe(requestReport => {
  console.log('Request Report:', requestReport);
});
```

**6. downloadTestReport**

```javascript
reportService.downloadTestReport('your-reportrequest-value').subscribe(downloadTestReport => {
  console.log('Download Test Report:', downloadTestReport);
});
```

**7. updateReportPublicStatus**

```javascript
reportService.updateReportPublicStatus('your-report-id', true).subscribe(reportPublicStatus => {
  console.log('Update Report Public Status:', reportPublicStatus);
});
```

**8. getPublicReportDownloadUrl**

```javascript
reportService.getPublicReportDownloadUrl('your-publickey-value').subscribe(publicReportDownloadUrl => {
  console.log('Get Public Report Download Url:', publicReportDownloadUrl);
});
```

**9. getReportsInfosByIds**

```javascript
reportService.getReportsInfosByIds('your-reportids-value').subscribe(reportsInfosByIds => {
  console.log('Get Reports Infos By Ids:', reportsInfosByIds);
});
```

**10. processDownloadReportResponse**

```javascript
reportService.processDownloadReportResponse('your-response-value').subscribe(processDownloadReportResponse => {
  console.log('Process Download Report Response:', processDownloadReportResponse);
});
```
