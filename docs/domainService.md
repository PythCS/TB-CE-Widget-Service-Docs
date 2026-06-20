# DOMAIN SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **DOMAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
const domain = domain;
domainService.saveDomain(domain, 'your-id').subscribe(savedDomain => {
  console.log('Save Domain: savedDomain');
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients('your-id', 'your-id').subscribe(result => {
  console.log('Update Oauth Clients: result');
});
```

**3. getTenantDomainInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domainService.getTenantDomainInfos(pageLink).subscribe(tenantdomaininfos => {
  console.log('Get Tenant Domain Infos: tenantdomaininfos');
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById('your-id').subscribe(domainInfoById => {
  console.log('Get Domain Info By Id: domainInfoById');
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain('your-id').subscribe(result => {
  console.log('Delete Domain: result');
});
```
