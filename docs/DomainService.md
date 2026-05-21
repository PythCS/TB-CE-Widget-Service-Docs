# DomainService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('DomainService'));
```

**1. saveDomain**

```javascript
domainService.saveDomain('your-domain-value', 'your-oauth2clientids-value').subscribe(result => {
  console.log('Saved  Domain result:', result);
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients('your--id', 'your-oauth2clientids-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**3. getTenantDomainInfos**

```javascript
domainService.getTenantDomainInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Domain Infos tenant:', tenant);
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById('your--id').subscribe(info => {
  console.log('Fetched  Domain Info By Id info:', info);
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```
