# INTEGRATION SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
```

**1. getIntegrations**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getIntegrations(pageLink).subscribe(integrations => {
  console.log('List of Integrations:', integrations);
});
```

**2. getIntegrationsConvertersInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
integrationService.getIntegrationsConvertersInfo().subscribe(integrationsConvertersInfo => {
  console.log('Get Integrations Converters Info:', integrationsConvertersInfo);
});
```

**3. getIntegrationsConvertersInfoCached**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
integrationService.getIntegrationsConvertersInfoCached().subscribe(integrationsConvertersInfoCached => {
  console.log('Get Integrations Converters Info Cached:', integrationsConvertersInfoCached);
});
```

**4. getIntegrationsInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const isEdgeTemplate = true;
integrationService.getIntegrationsInfo(pageLink, isEdgeTemplate).subscribe(integrationsInfos => {
  console.log('List of Integrations Infos:', integrationsInfos);
});
```

**5. getIntegrationsByEdgeTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const isEdgeTemplate = true;
integrationService.getIntegrationsByEdgeTemplate(pageLink, isEdgeTemplate).subscribe(integrationsByEdgeTemplates => {
  console.log('List of Integrations By Edge Templates:', integrationsByEdgeTemplates);
});
```

**6. getIntegrationsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const integrationIds = ['your-integration-i-1', 'your-integration-i-2'];
integrationService.getIntegrationsByIds(integrationIds).subscribe(integrationsBys => {
  console.log('List of Integrations By Ids:', integrationsBys);
});
```

**7. getIntegration**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const integrationId = 'your-integration-id';
integrationService.getIntegration(integrationId).subscribe(integration => {
  console.log('Get Integration:', integration);
});
```

**8. saveIntegration**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const integration = {  // Integration object
  // ... set the fields you need
};
integrationService.saveIntegration(integration).subscribe(savedIntegration => {
  console.log('Saved Integration:', savedIntegration);
});
```

**9. getIntegrationHttpEndpointLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const configuration = {  // any object
  // ... set the fields you need
};
const integrationType = {  // IntegrationType object
  // ... set the fields you need
};
const routingKey = 'your-routing-key';
const result = integrationService.getIntegrationHttpEndpointLink(configuration, integrationType, routingKey);
console.log('Result:', result);
```

**10. toLowerCase**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const result = integrationService.toLowerCase();
console.log('Result:', result);
```

**11. assignIntegrationToEdge**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const edgeId = 'your-edge-id';
const integrationId = 'your-integration-id';
integrationService.assignIntegrationToEdge(edgeId, integrationId).subscribe(assignIntegrationToEdge => {
  console.log('Assign Integration To Edge:', assignIntegrationToEdge);
});
```

**12. getEdgeIntegrations**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getEdgeIntegrations(edgeId, pageLink).subscribe(edgeIntegrations => {
  console.log('List of Edge Integrations:', edgeIntegrations);
});
```

**13. exportIntegrationPackage**

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
const integrationId = 'your-integration-id';
integrationService.exportIntegrationPackage(integrationId).subscribe(exportIntegrationPackage => {
  console.log('Export Integration Package:', exportIntegrationPackage);
});
```
