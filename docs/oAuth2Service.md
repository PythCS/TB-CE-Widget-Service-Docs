# O AUTH SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **O AUTH SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template().subscribe(oAuth2Template => {
  console.log('Get O Auth Template: oAuth2Template');
});
```

**2. saveOAuth2Client**

```javascript
const oAuth2Client = oAuth2Client;
oAuth2Service.saveOAuth2Client(oAuth2Client).subscribe(savedOAuth2Client => {
  console.log('Save O Auth Client: savedOAuth2Client');
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(results => {
  console.log('Find Tenant O Auth Client Infos:results');
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2Service.findTenantOAuth2ClientInfosByIds('your-id').subscribe(results => {
  console.log('Find Tenant O Auth Client Infos By Ids:results');
});
```

**5. getOAuth2ClientById**

```javascript
oAuth2Service.getOAuth2ClientById('your-id').subscribe(oAuth2ClientById => {
  console.log('Get O Auth Client By Id: oAuth2ClientById');
});
```

**6. deleteOauth2Client**

```javascript
oAuth2Service.deleteOauth2Client('your-id').subscribe(result => {
  console.log('Delete Oauth Client: result');
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url: loginProcessingUrl');
});
```
