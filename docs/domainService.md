# DOMAIN SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
domainService.saveDomain('your-domain-value', 'your-oauth2clientids-value').subscribe(domain => {
  console.log('Save Domain:', domain);
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients('your--id', 'your-oauth2clientids-value').subscribe(result => {
  console.log('Update Oauth 2 Clients:', result);
});
```

**3. getTenantDomainInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domainService.getTenantDomainInfos(pageLink).subscribe(tenantDomainInfos => {
  console.log('Get Tenant Domain Infos:', tenantDomainInfos);
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById('your--id').subscribe(domainInfoById => {
  console.log('Get Domain Info By Id:', domainInfoById);
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain('your--id').subscribe(result => {
  console.log('Delete Domain:', result);
});
```
