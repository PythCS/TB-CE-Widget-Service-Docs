### **TWO FACTOR AUTHENTICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twofactorauthenticationservice = $injector.get(self.ctx.servicesMap.get('twofactorauthenticationservice'));

```

**1. getTwoFaSettings**

```javascript
twofactorauthenticationservice.getTwoFaSettings().subscribe(twofasettings => {
  console.log('Twofasettings:', twofasettings);
});
```

**2. saveTwoFaSettings**

```javascript
twofactorauthenticationservice.saveTwoFaSettings(settings).subscribe(savetwofasettings => {
  console.log('Savetwofasettings:', savetwofasettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twofactorauthenticationservice.getAvailableTwoFaProviders().subscribe(availabletwofaproviders => {
  console.log('Availabletwofaproviders:', availabletwofaproviders);
});
```

**4. generateTwoFaAccountConfig**

```javascript
twofactorauthenticationservice.generateTwoFaAccountConfig('your-providertype-id').subscribe(generatetwofaaccountconfig => {
  console.log('Generatetwofaaccountconfig:', generatetwofaaccountconfig);
});
```

**5. getAccountTwoFaSettings**

```javascript
twofactorauthenticationservice.getAccountTwoFaSettings().subscribe(accounttwofasettings => {
  console.log('Accounttwofasettings:', accounttwofasettings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
twofactorauthenticationservice.updateTwoFaAccountConfig('your-providertype-id', true).subscribe(updatetwofaaccountconfig => {
  console.log('Updatetwofaaccountconfig:', updatetwofaaccountconfig);
});
```

**7. submitTwoFaAccountConfig**

```javascript
twofactorauthenticationservice.submitTwoFaAccountConfig(authConfig).subscribe(submittwofaaccountconfig => {
  console.log('Submittwofaaccountconfig:', submittwofaaccountconfig);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
twofactorauthenticationservice.verifyAndSaveTwoFaAccountConfig(authConfig, 10).subscribe(verifyandsavetwofaaccountconfig => {
  console.log('Verifyandsavetwofaaccountconfig:', verifyandsavetwofaaccountconfig);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twofactorauthenticationservice.deleteTwoFaAccountConfig('your-providertype-id').subscribe(deletetwofaaccountconfig => {
  console.log('Deletetwofaaccountconfig:', deletetwofaaccountconfig);
});
```

