# REPORT TEMPLATE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const reportTemplateService = $injector.get(self.ctx.servicesMap.get('reportTemplateService'));
```

**1. getReportTemplateInfo**

```javascript
reportTemplateService.getReportTemplateInfo('your-reporttemplate-id').subscribe(reportTemplateInfo => {
  console.log('Get Report Template Info:', reportTemplateInfo);
});
```

**2. getAllReportTemplateInfos**

```javascript
reportTemplateService.getAllReportTemplateInfos('your-query-value').subscribe(allReportTemplateInfos => {
  console.log('Get All Report Template Infos:', allReportTemplateInfos);
});
```

**3. getReportTemplatesByIds**

```javascript
reportTemplateService.getReportTemplatesByIds('your-reporttemplateids-value').subscribe(reportTemplatesByIds => {
  console.log('Get Report Templates By Ids:', reportTemplatesByIds);
});
```
