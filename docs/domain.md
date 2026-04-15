# Domain

```javascript
// Service name: domain
// File: domain.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domain = $injector.get(self.ctx.servicesMap.get('domain'));
```

### **1. saveDomain**

```javascript
domain.saveDomain(domain).subscribe(domain => {
  console.log('Domain:', domain);
});
```

### **2. updateOauth2Clients**

```javascript
domain.updateOauth2Clients(id, oauth2ClientIds).subscribe(updateOauth2Client => {
  console.log('Update Oauth2 Client:', updateOauth2Client);
});
```

### **3. getTenantDomainInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domain.getTenantDomainInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **4. getDomainInfoById**

```javascript
domain.getDomainInfoById(id).subscribe(domain => {
  console.log('Domain:', domain);
});
```

### **5. deleteDomain**

```javascript
domain.deleteDomain(id).subscribe(domain => {
  console.log('Domain:', domain);
});
```
