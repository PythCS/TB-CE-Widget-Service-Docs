# SIGNUP SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const signupService = $injector.get(self.ctx.servicesMap.get('signupService'));
```

**1. signup**

```javascript
signupService.signup('your-signuprequest-value').subscribe(signup => {
  console.log('Signup:', signup);
});
```

**2. acceptPrivacyPolicy**

```javascript
signupService.acceptPrivacyPolicy().subscribe(acceptPrivacyPolicy => {
  console.log('Accept Privacy Policy:', acceptPrivacyPolicy);
});
```

**3. deleteTenantAccount**

```javascript
signupService.deleteTenantAccount().subscribe(tenantAccount => {
  console.log('Delete Tenant Account:', tenantAccount);
});
```

**4. isDisplayWelcome**

```javascript
signupService.isDisplayWelcome().subscribe(isDisplayWelcome => {
  console.log('Is Display Welcome:', isDisplayWelcome);
});
```

**5. setNotDisplayWelcome**

```javascript
signupService.setNotDisplayWelcome().subscribe(notDisplayWelcome => {
  console.log('Set Not Display Welcome:', notDisplayWelcome);
});
```
