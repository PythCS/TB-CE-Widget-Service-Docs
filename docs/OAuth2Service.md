# OAuth2Service

### **OAUTH2SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template({ /* your config */ }).subscribe(oauth2template => {
  console.log('O Auth2 Template:', oauth2template);
});
```

**2. saveOAuth2Client**

```javascript
oAuth2Service.saveOAuth2Client({ /* your oAuth2Client */ }, { /* your config */ }).subscribe(savedOAuth2Client => {
  console.log('Saved OAuth2Client:', savedOAuth2Client);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
oAuth2Service.findTenantOAuth2ClientInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2Service.findTenantOAuth2ClientInfosByIds(['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getOAuth2ClientById**

```javascript
oAuth2Service.getOAuth2ClientById('your-id', { /* your config */ }).subscribe(oauth2clientbyid => {
  console.log('O Auth2 Client By Id:', oauth2clientbyid);
});
```

**6. deleteOauth2Client**

```javascript
oAuth2Service.deleteOauth2Client('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl({ /* your config */ }).subscribe(loginprocessingurl => {
  console.log('Login Processing Url:', loginprocessingurl);
});
```
