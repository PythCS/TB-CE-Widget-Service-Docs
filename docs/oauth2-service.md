# O AUTH2 SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
oAuth2Service.getOAuth2Template().subscribe(oAuth2Templates => {
  console.log('List of OAuth2 Templates:', oAuth2Templates);
});
```

**2. saveOAuth2Client**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const oAuth2Client = {  // OAuth2Client object
  // ... set the fields you need
};
oAuth2Service.saveOAuth2Client(oAuth2Client).subscribe(savedOAuth2Client => {
  console.log('Saved OAuth2 Client:', savedOAuth2Client);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(tenantOAuth2ClientInfos => {
  console.log('List of Tenant OAuth2 Client Infos:', tenantOAuth2ClientInfos);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const clientIds = ['your-client-i-1', 'your-client-i-2'];
oAuth2Service.findTenantOAuth2ClientInfosByIds(clientIds).subscribe(tenantOAuth2ClientInfosBys => {
  console.log('List of Tenant OAuth2 Client Infos By Ids:', tenantOAuth2ClientInfosBys);
});
```

**5. getOAuth2ClientById**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const id = 'your-id';
oAuth2Service.getOAuth2ClientById(id).subscribe(oAuth2ClientBy => {
  console.log('Get OAuth2 Client By Id:', oAuth2ClientBy);
});
```

**6. deleteOauth2Client**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
const id = 'your-id';
oAuth2Service.deleteOauth2Client(id).subscribe(result => {
  console.log('Delete Oauth2 Client result:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
oAuth2Service.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```
