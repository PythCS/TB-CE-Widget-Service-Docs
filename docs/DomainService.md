# DomainService

### **DOMAINSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
domainService.saveDomain({ /* your domain */ }, ['id1', 'id2'], { /* your config */ }).subscribe(savedDomain => {
  console.log('Saved Domain:', savedDomain);
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients('your-id', ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**3. getTenantDomainInfos**

```javascript
domainService.getTenantDomainInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantdomaininfo => {
  console.log('Tenant Domain Infos:', tenantdomaininfo);
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById('your-id', { /* your config */ }).subscribe(domaininfobyid => {
  console.log('Domain Info By Id:', domaininfobyid);
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```
