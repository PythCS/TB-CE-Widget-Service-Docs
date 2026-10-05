# SIGNUP SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
```

**1. signup**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
const signupRequest = {  // SignupRequestValues object
  // ... set the fields you need
};
signupService.signup(signupRequest).subscribe(signup => {
  console.log('Signup:', signup);
});
```

**2. acceptPrivacyPolicy**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
signupService.acceptPrivacyPolicy().subscribe(acceptPrivacyPolicy => {
  console.log('Accept Privacy Policy:', acceptPrivacyPolicy);
});
```

**3. deleteTenantAccount**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
signupService.deleteTenantAccount().subscribe(result => {
  console.log('Delete Tenant Account result:', result);
});
```

**4. isDisplayWelcome**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
signupService.isDisplayWelcome().subscribe(isDisplayWelcome => {
  console.log('Is Display Welcome:', isDisplayWelcome);
});
```

**5. setNotDisplayWelcome**

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
signupService.setNotDisplayWelcome().subscribe(setNotDisplayWelcome => {
  console.log('Set Not Display Welcome:', setNotDisplayWelcome);
});
```
