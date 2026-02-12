# OAUTH2

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

## Methods

### getOAuth2Template

```javascript
oAuth2Service.getOAuth2Template().subscribe(result => {
  console.log('OAuth2Template:', result);
});
```

### saveOAuth2Client

```javascript
const oAuth2Client = {
  // your oAuth2Client object
};

oAuth2Service.saveOAuth2Client(oAuth2Client).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### findTenantOAuth2ClientInfos

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

### findTenantOAuth2ClientInfosByIds

```javascript
const clientIds = 'your-clients-id';

oAuth2Service.findTenantOAuth2ClientInfosByIds(clientIds).subscribe(info => {
  console.log('Info:', info);
});
```

### getOAuth2ClientById

```javascript
const id = 'your--id';

oAuth2Service.getOAuth2ClientById(id).subscribe(result => {
  console.log('OAuth2ClientById:', result);
});
```

### deleteOauth2Client

```javascript
const id = 'your--id';

oAuth2Service.deleteOauth2Client(id).subscribe(result => {
  console.log('Result:', result);
});
```

### getLoginProcessingUrl

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(url => {
  console.log('URL:', url);
});
```

