# INTEGRATION SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const integrationService = $injector.get(self.ctx.servicesMap.get('integrationService'));
```

**1. getIntegrations**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getIntegrations(pageLink).subscribe(integrations => {
  console.log('Get Integrations:', integrations);
});
```

**2. getIntegrationsConvertersInfo**

```javascript
integrationService.getIntegrationsConvertersInfo().subscribe(integrationsConvertersInfo => {
  console.log('Get Integrations Converters Info:', integrationsConvertersInfo);
});
```

**3. getIntegrationsConvertersInfoCached**

```javascript
integrationService.getIntegrationsConvertersInfoCached().subscribe(integrationsConvertersInfoCached => {
  console.log('Get Integrations Converters Info Cached:', integrationsConvertersInfoCached);
});
```

**4. getIntegrationsInfo**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getIntegrationsInfo(pageLink, true).subscribe(integrationsInfo => {
  console.log('Get Integrations Info:', integrationsInfo);
});
```

**5. getIntegrationsByEdgeTemplate**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getIntegrationsByEdgeTemplate(pageLink, true).subscribe(integrationsByEdgeTemplate => {
  console.log('Get Integrations By Edge Template:', integrationsByEdgeTemplate);
});
```

**6. getIntegrationsByIds**

```javascript
integrationService.getIntegrationsByIds('your-integrationids-value').subscribe(integrationsByIds => {
  console.log('Get Integrations By Ids:', integrationsByIds);
});
```

**7. getIntegration**

```javascript
integrationService.getIntegration('your-integration-id').subscribe(integration => {
  console.log('Get Integration:', integration);
});
```

**8. saveIntegration**

```javascript
integrationService.saveIntegration('your-integration-value').subscribe(integration => {
  console.log('Save Integration:', integration);
});
```

**9. getIntegrationHttpEndpointLink**

```javascript
integrationService.getIntegrationHttpEndpointLink('your-configuration-value', 'your-integrationtype-value', 'your-routingkey-value').subscribe(integrationHttpEndpointLink => {
  console.log('Get Integration Http Endpoint Link:', integrationHttpEndpointLink);
});
```

**10. toLowerCase**

```javascript
integrationService.toLowerCase().subscribe(toLowerCase => {
  console.log('To Lower Case:', toLowerCase);
});
```

**11. assignIntegrationToEdge**

```javascript
integrationService.assignIntegrationToEdge('your-edge-id', 'your-integration-id').subscribe(integrationToEdge => {
  console.log('Assign Integration To Edge:', integrationToEdge);
});
```

**12. getEdgeIntegrations**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
integrationService.getEdgeIntegrations('your-edge-id', pageLink).subscribe(edgeIntegrations => {
  console.log('Get Edge Integrations:', edgeIntegrations);
});
```

**13. exportIntegrationPackage**

```javascript
integrationService.exportIntegrationPackage('your-integration-id').subscribe(integrationPackage => {
  console.log('Export Integration Package:', integrationPackage);
});
```
