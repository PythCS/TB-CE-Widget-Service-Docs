# TwoFactorAuthenticationService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('TwoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings().subscribe(settings => {
  console.log('Fetched  Two Fa Settings settings:', settings);
});
```

**2. saveTwoFaSettings**

```javascript
twoFactorAuthenticationService.saveTwoFaSettings('your-settings-value').subscribe(settings => {
  console.log('Saved  Two Fa Settings settings:', settings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(result => {
  console.log('Fetched  Available Two Fa Providers result:', result);
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig('your-providertype-value').subscribe(result => {
  console.log('generate Two Fa Account Config result:', result);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(settings => {
  console.log('Fetched  Account Two Fa Settings settings:', settings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig('your-providertype-value', true).subscribe(result => {
  console.log('update Two Fa Account Config result:', result);
});
```

**7. submitTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.submitTwoFaAccountConfig().subscribe(result => {
  console.log('submit Two Fa Account Config result:', result);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(0).subscribe(result => {
  console.log('verify And Save Two Fa Account Config result:', result);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig('your-providertype-value').subscribe(result => {
  console.log('Deleted  Two Fa Account Config result:', result);
});
```
