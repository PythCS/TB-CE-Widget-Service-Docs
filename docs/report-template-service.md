# REPORT TEMPLATE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
```

**1. getReportTemplateInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
const reportTemplateId = 'your-report-template-id';
reportTemplateService.getReportTemplateInfo(reportTemplateId).subscribe(reportTemplateInfo => {
  console.log('Get Report Template Info:', reportTemplateInfo);
});
```

**2. getAllReportTemplateInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
const query = {  // ReportTemplateQuery object
  // ... set the fields you need
};
reportTemplateService.getAllReportTemplateInfos(query).subscribe(allReportTemplateInfos => {
  console.log('List of All Report Template Infos:', allReportTemplateInfos);
});
```

**3. getReportTemplatesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
const reportTemplateIds = ['your-report-template-i-1', 'your-report-template-i-2'];
reportTemplateService.getReportTemplatesByIds(reportTemplateIds).subscribe(reportTemplatesBys => {
  console.log('List of Report Templates By Ids:', reportTemplatesBys);
});
```
