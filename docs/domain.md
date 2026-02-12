### **DOMAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainservice = $injector.get(self.ctx.servicesMap.get('domainservice'));

```

**1. saveDomain**

```javascript
domainservice.saveDomain(domain, 'your-oauth2clients-id').subscribe(savedomain => {
  console.log('Savedomain:', savedomain);
});
```

**2. updateOauth2Clients**

```javascript
domainservice.updateOauth2Clients('your-id-id', 'your-oauth2clients-id').subscribe(updateoauth2clients => {
  console.log('Updateoauth2clients:', updateoauth2clients);
});
```

**3. getTenantDomainInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domainservice.getTenantDomainInfos(pageLink).subscribe(tenantdomaininfos => {
  console.log('Tenantdomaininfos:', tenantdomaininfos);
});
```

**4. getDomainInfoById**

```javascript
domainservice.getDomainInfoById('your-id-id').subscribe(domaininfobyid => {
  console.log('Domaininfobyid:', domaininfobyid);
});
```

**5. deleteDomain**

```javascript
domainservice.deleteDomain('your-id-id').subscribe(deletedomain => {
  console.log('Deletedomain:', deletedomain);
});
```

