### **OAUTH2 SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oauth2service = $injector.get(self.ctx.servicesMap.get('oauth2service'));

```

**1. getOAuth2Template**

```javascript
oauth2service.getOAuth2Template().subscribe(oauth2template => {
  console.log('Oauth2template:', oauth2template);
});
```

**2. saveOAuth2Client**

```javascript
oauth2service.saveOAuth2Client(oAuth2Client).subscribe(saveoauth2client => {
  console.log('Saveoauth2client:', saveoauth2client);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oauth2service.findTenantOAuth2ClientInfos(pageLink).subscribe(tenantoauth2clientinfos => {
  console.log('Tenantoauth2clientinfos:', tenantoauth2clientinfos);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oauth2service.findTenantOAuth2ClientInfosByIds('your-clients-id').subscribe(tenantoauth2clientinfosbyids => {
  console.log('Tenantoauth2clientinfosbyids:', tenantoauth2clientinfosbyids);
});
```

**5. getOAuth2ClientById**

```javascript
oauth2service.getOAuth2ClientById('your-id-id').subscribe(oauth2clientbyid => {
  console.log('Oauth2clientbyid:', oauth2clientbyid);
});
```

**6. deleteOauth2Client**

```javascript
oauth2service.deleteOauth2Client('your-id-id').subscribe(deleteoauth2client => {
  console.log('Deleteoauth2client:', deleteoauth2client);
});
```

**7. getLoginProcessingUrl**

```javascript
oauth2service.getLoginProcessingUrl().subscribe(loginprocessingurl => {
  console.log('Loginprocessingurl:', loginprocessingurl);
});
```

