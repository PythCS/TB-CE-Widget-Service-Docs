# OAuth2Service

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('OAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template().subscribe(result => {
  console.log('Fetched  O Auth2 Template result:', result);
});
```

**2. saveOAuth2Client**

```javascript
oAuth2Service.saveOAuth2Client('your-oauth2client-value').subscribe(result => {
  console.log('Saved  O Auth2 Client result:', result);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
oAuth2Service.findTenantOAuth2ClientInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('find Tenant O Auth2 Client Infos tenant:', tenant);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2Service.findTenantOAuth2ClientInfosByIds('your-clientids-value').subscribe(tenant => {
  console.log('find Tenant O Auth2 Client Infos By Ids tenant:', tenant);
});
```

**5. getOAuth2ClientById**

```javascript
oAuth2Service.getOAuth2ClientById('your--id').subscribe(result => {
  console.log('Fetched  O Auth2 Client By Id result:', result);
});
```

**6. deleteOauth2Client**

```javascript
oAuth2Service.deleteOauth2Client('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(result => {
  console.log('Fetched  Login Processing Url result:', result);
});
```
