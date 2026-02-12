# DOMAIN

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

## Methods

### saveDomain

```javascript
const domain = {
  // your domain object
};
const oauth2ClientIds = 'your-oauth2clients-id';

domainService.saveDomain(domain, oauth2ClientIds).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### updateOauth2Clients

```javascript
const id = 'your--id';
const oauth2ClientIds = 'your-oauth2clients-id';

domainService.updateOauth2Clients(id, oauth2ClientIds).subscribe(result => {
  console.log('Result:', result);
});
```

### getTenantDomainInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

domainService.getTenantDomainInfos(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

### getDomainInfoById

```javascript
const id = 'your--id';

domainService.getDomainInfoById(id).subscribe(info => {
  console.log('Info:', info);
});
```

### deleteDomain

```javascript
const id = 'your--id';

domainService.deleteDomain(id).subscribe(result => {
  console.log('Result:', result);
});
```

