# DOMAIN SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const domain = {  // Domain object
  // ... set the fields you need
};
const oauth2ClientIds = ['your-oauth2-client-i-1', 'your-oauth2-client-i-2'];
domainService.saveDomain(domain, oauth2ClientIds).subscribe(savedDomain => {
  console.log('Saved Domain:', savedDomain);
});
```

**2. updateOauth2Clients**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const id = 'your-id';
const oauth2ClientIds = ['your-oauth2-client-i-1', 'your-oauth2-client-i-2'];
domainService.updateOauth2Clients(id, oauth2ClientIds).subscribe(savedOauth2Clients => {
  console.log('Saved Oauth2 Clients:', savedOauth2Clients);
});
```

**3. getDomainInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domainService.getDomainInfos(pageLink).subscribe(domainInfos => {
  console.log('List of Domain Infos:', domainInfos);
});
```

**4. getDomainInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const id = 'your-id';
domainService.getDomainInfoById(id).subscribe(domainInfoBy => {
  console.log('Get Domain Info By Id:', domainInfoBy);
});
```

**5. deleteDomain**

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
const id = 'your-id';
domainService.deleteDomain(id).subscribe(result => {
  console.log('Delete Domain result:', result);
});
```
