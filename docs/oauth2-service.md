# O AUTH 2 SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template().subscribe(oAuth2Template => {
  console.log('Get O Auth 2 Template:', oAuth2Template);
});
```

**2. saveOAuth2Client**

```javascript
oAuth2Service.saveOAuth2Client('your-oauth2client-value').subscribe(oAuth2Client => {
  console.log('Save O Auth 2 Client:', oAuth2Client);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(tenantOAuth2ClientInfos => {
  console.log('Find Tenant O Auth 2 Client Infos:', tenantOAuth2ClientInfos);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2Service.findTenantOAuth2ClientInfosByIds('your-clientids-value').subscribe(tenantOAuth2ClientInfosByIds => {
  console.log('Find Tenant O Auth 2 Client Infos By Ids:', tenantOAuth2ClientInfosByIds);
});
```

**5. getOAuth2ClientById**

```javascript
oAuth2Service.getOAuth2ClientById('your--id').subscribe(oAuth2ClientById => {
  console.log('Get O Auth 2 Client By Id:', oAuth2ClientById);
});
```

**6. deleteOauth2Client**

```javascript
oAuth2Service.deleteOauth2Client('your--id').subscribe(result => {
  console.log('Delete Oauth 2 Client:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```
