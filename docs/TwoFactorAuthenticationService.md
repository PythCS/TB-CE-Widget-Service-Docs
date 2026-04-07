# TwoFactorAuthenticationService

### **TWOFACTORAUTHENTICATIONSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings({ /* your config */ }).subscribe(twofaetting => {
  console.log('Two Fa Settings:', twofaetting);
});
```

**2. saveTwoFaSettings**

```javascript
twoFactorAuthenticationService.saveTwoFaSettings({ /* your settings */ }, { /* your config */ }).subscribe(savedTwoFaSettings => {
  console.log('Saved TwoFaSettings:', savedTwoFaSettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders({ /* your config */ }).subscribe(availabletwofaprovider => {
  console.log('Available Two Fa Providers:', availabletwofaprovider);
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig('your-providertype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings({ /* your config */ }).subscribe(accounttwofaetting => {
  console.log('Account Two Fa Settings:', accounttwofaetting);
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig('your-providertype', true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. submitTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.submitTwoFaAccountConfig({ /* your authConfig */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig({ /* your authConfig */ }, 100, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig('your-providertype', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```
