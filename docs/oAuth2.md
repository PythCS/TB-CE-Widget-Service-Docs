# O Auth2

```javascript
// Service name: oAuth2
// File: oauth2.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2 = $injector.get(self.ctx.servicesMap.get('oAuth2'));
```

### **1. getOAuth2Template**

```javascript
oAuth2.getOAuth2Template().subscribe(oAuth2Templates => {
  console.log('O Auth2 Templates:', oAuth2Templates);
});
```

### **2. saveOAuth2Client**

```javascript
oAuth2.saveOAuth2Client(oAuth2Client).subscribe(oauth2Client => {
  console.log('Oauth2 Client:', oauth2Client);
});
```

### **3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oAuth2.findTenantOAuth2ClientInfos(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2.findTenantOAuth2ClientInfosByIds(clientIds).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **5. getOAuth2ClientById**

```javascript
oAuth2.getOAuth2ClientById(id).subscribe(oauth2Client => {
  console.log('Oauth2 Client:', oauth2Client);
});
```

### **6. deleteOauth2Client**

```javascript
oAuth2.deleteOauth2Client(id).subscribe(deleteOauth2Client => {
  console.log('Delete Oauth2 Client:', deleteOauth2Client);
});
```

### **7. getLoginProcessingUrl**

```javascript
oAuth2.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Login Processing Url:', loginProcessingUrl);
});
```
