# SELF REGISTRATION SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
```

**1. getRegistrationLink**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
const domainName = 'your-domain-name';
const result = selfRegistrationService.getRegistrationLink(domainName);
console.log('Result:', result);
```

**2. loadSelfRegistrationParams**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.loadSelfRegistrationParams().subscribe(selfRegistrationParams => {
  console.log('Load Self Registration Params:', selfRegistrationParams);
});
```

**3. loadPrivacyPolicy**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.loadPrivacyPolicy().subscribe(privacyPolicy => {
  console.log('Load Privacy Policy:', privacyPolicy);
});
```

**4. loadTermsOfUse**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.loadTermsOfUse().subscribe(termsOfUse => {
  console.log('Load Terms Of Use:', termsOfUse);
});
```

**5. isAvailablePage**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.isAvailablePage().subscribe(isAvailablePage => {
  console.log('Is Available Page:', isAvailablePage);
});
```

**6. saveSelfRegistrationParams**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
const selfRegistrationParams = {  // WebSelfRegistrationParams object
  // ... set the fields you need
};
selfRegistrationService.saveSelfRegistrationParams(selfRegistrationParams).subscribe(savedSelfRegistrationParams => {
  console.log('Saved Self Registration Params:', savedSelfRegistrationParams);
});
```

**7. getSelfRegistrationParams**

```javascript
const $injector = self.ctx.$scope.$injector;
const selfRegistrationService = $injector.get(self.ctx.servicesMap.get('selfRegistrationService'));
selfRegistrationService.getSelfRegistrationParams().subscribe(selfRegistrationParams => {
  console.log('Get Self Registration Params:', selfRegistrationParams);
});
```
