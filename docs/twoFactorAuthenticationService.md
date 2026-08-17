# TWO FACTOR AUTHENTICATION SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings().subscribe(twoFaSettings => {
  console.log('Get Two Fa Settings:', twoFaSettings);
});
```

**2. saveTwoFaSettings**

```javascript
twoFactorAuthenticationService.saveTwoFaSettings('your-settings-value').subscribe(twoFaSettings => {
  console.log('Save Two Fa Settings:', twoFaSettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(availableTwoFaProviders => {
  console.log('Get Available Two Fa Providers:', availableTwoFaProviders);
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig('your-providertype-value').subscribe(twoFaAccountConfig => {
  console.log('Generate Two Fa Account Config:', twoFaAccountConfig);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(accountTwoFaSettings => {
  console.log('Get Account Two Fa Settings:', accountTwoFaSettings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig('your-providertype-value', true).subscribe(twoFaAccountConfig => {
  console.log('Update Two Fa Account Config:', twoFaAccountConfig);
});
```

**7. submitTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.submitTwoFaAccountConfig('your-authconfig-value').subscribe(submitTwoFaAccountConfig => {
  console.log('Submit Two Fa Account Config:', submitTwoFaAccountConfig);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig('your-authconfig-value', 0).subscribe(verifyAndSaveTwoFaAccountConfig => {
  console.log('Verify And Save Two Fa Account Config:', verifyAndSaveTwoFaAccountConfig);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig('your-providertype-value').subscribe(twoFaAccountConfig => {
  console.log('Delete Two Fa Account Config:', twoFaAccountConfig);
});
```
