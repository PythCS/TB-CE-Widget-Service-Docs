# TWO FACTOR AUTHENTICATION SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **TWO FACTOR AUTHENTICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings().subscribe(twofasettings => {
  console.log('Get Two Fa Settings: twofasettings');
});
```

**2. saveTwoFaSettings**

```javascript
const settings = settings;
twoFactorAuthenticationService.saveTwoFaSettings(settings).subscribe(savedTwoFaSettings => {
  console.log('Save Two Fa Settings: savedTwoFaSettings');
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(availabletwofaproviders => {
  console.log('Get Available Two Fa Providers:availabletwofaproviders');
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig('your-id').subscribe(result => {
  console.log('Generate Two Fa Account Config:result');
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(accounttwofasettings => {
  console.log('Get Account Two Fa Settings: accounttwofasettings');
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig('your-id', true).subscribe(result => {
  console.log('Update Two Fa Account Config: result');
});
```

**7. submitTwoFaAccountConfig**

```javascript
const authConfig = authConfig;
twoFactorAuthenticationService.submitTwoFaAccountConfig(authConfig).subscribe(result => {
  console.log('Submit Two Fa Account Config: result');
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
const authConfig = authConfig;
const verificationCode = verificationCode;
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(authConfig, verificationCode).subscribe(result => {
  console.log('Verify And Save Two Fa Account Config:result');
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig('your-id').subscribe(result => {
  console.log('Delete Two Fa Account Config: result');
});
```
