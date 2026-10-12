# SELF REGISTRATION SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
```

**1. getRegistrationLink**

```javascript
selfRegistrationService.getRegistrationLink('your-domainname-value').subscribe(registrationLink => {
  console.log('Get Registration Link:', registrationLink);
});
```

**2. loadSelfRegistrationParams**

```javascript
selfRegistrationService.loadSelfRegistrationParams().subscribe(loadSelfRegistrationParams => {
  console.log('Load Self Registration Params:', loadSelfRegistrationParams);
});
```

**3. loadPrivacyPolicy**

```javascript
selfRegistrationService.loadPrivacyPolicy().subscribe(loadPrivacyPolicy => {
  console.log('Load Privacy Policy:', loadPrivacyPolicy);
});
```

**4. loadTermsOfUse**

```javascript
selfRegistrationService.loadTermsOfUse().subscribe(loadTermsOfUse => {
  console.log('Load Terms Of Use:', loadTermsOfUse);
});
```

**5. isAvailablePage**

```javascript
selfRegistrationService.isAvailablePage().subscribe(isAvailablePage => {
  console.log('Is Available Page:', isAvailablePage);
});
```

**6. saveSelfRegistrationParams**

```javascript
selfRegistrationService.saveSelfRegistrationParams('your-selfregistrationparams-value').subscribe(selfRegistrationParams => {
  console.log('Save Self Registration Params:', selfRegistrationParams);
});
```

**7. getSelfRegistrationParams**

```javascript
selfRegistrationService.getSelfRegistrationParams().subscribe(selfRegistrationParams => {
  console.log('Get Self Registration Params:', selfRegistrationParams);
});
```
