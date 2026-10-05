# TWO FACTOR AUTHENTICATION SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
twoFactorAuthenticationService.getTwoFaSettings().subscribe(twoFaSettings => {
  console.log('Get Two Fa Settings:', twoFaSettings);
});
```

**2. saveTwoFaSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const settings = {  // TwoFactorAuthSettings object
  // ... set the fields you need
};
twoFactorAuthenticationService.saveTwoFaSettings(settings).subscribe(savedTwoFaSettings => {
  console.log('Saved Two Fa Settings:', savedTwoFaSettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(availableTwoFaProviders => {
  console.log('List of Available Two Fa Providers:', availableTwoFaProviders);
});
```

**4. generateTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const providerType = {  // TwoFactorAuthProviderType object
  // ... set the fields you need
};
twoFactorAuthenticationService.generateTwoFaAccountConfig(providerType).subscribe(generateTwoFaAccountConfig => {
  console.log('Generate Two Fa Account Config:', generateTwoFaAccountConfig);
});
```

**5. getAccountTwoFaSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(accountTwoFaSettings => {
  console.log('Get Account Two Fa Settings:', accountTwoFaSettings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const providerType = {  // TwoFactorAuthProviderType object
  // ... set the fields you need
};
const useByDefault = true;
twoFactorAuthenticationService.updateTwoFaAccountConfig(providerType, useByDefault).subscribe(savedTwoFaAccountConfig => {
  console.log('Saved Two Fa Account Config:', savedTwoFaAccountConfig);
});
```

**7. submitTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const authConfig = {  // TwoFactorAuthAccountConfig object
  // ... set the fields you need
};
twoFactorAuthenticationService.submitTwoFaAccountConfig(authConfig).subscribe(submitTwoFaAccountConfig => {
  console.log('Submit Two Fa Account Config:', submitTwoFaAccountConfig);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const authConfig = {  // TwoFactorAuthAccountConfig object
  // ... set the fields you need
};
const verificationCode = 10;
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(authConfig, verificationCode).subscribe(verifyAndSaveTwoFaAccountConfig => {
  console.log('Verify And Save Two Fa Account Config:', verifyAndSaveTwoFaAccountConfig);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
const providerType = {  // TwoFactorAuthProviderType object
  // ... set the fields you need
};
twoFactorAuthenticationService.deleteTwoFaAccountConfig(providerType).subscribe(result => {
  console.log('Delete Two Fa Account Config result:', result);
});
```
