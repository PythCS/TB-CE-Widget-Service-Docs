# Two Factor Authentication

```javascript
// Service name: twoFactorAuthentication
// File: two-factor-authentication.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthentication = $injector.get(self.ctx.servicesMap.get('twoFactorAuthentication'));
```

### **1. getTwoFaSettings**

```javascript
twoFactorAuthentication.getTwoFaSettings().subscribe(twoFaSetting => {
  console.log('Two Fa Setting:', twoFaSetting);
});
```

### **2. saveTwoFaSettings**

```javascript
twoFactorAuthentication.saveTwoFaSettings(settings).subscribe(saveTwoFaSetting => {
  console.log('Save Two Fa Setting:', saveTwoFaSetting);
});
```

### **3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthentication.getAvailableTwoFaProviders().subscribe(availableTwoFaProviders => {
  console.log('Available Two Fa Providers:', availableTwoFaProviders);
});
```

### **4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthentication.generateTwoFaAccountConfig(providerType).subscribe(generateTwoFaAccountConfig => {
  console.log('Generate Two Fa Account Config:', generateTwoFaAccountConfig);
});
```

### **5. getAccountTwoFaSettings**

```javascript
twoFactorAuthentication.getAccountTwoFaSettings().subscribe(accountTwoFaSetting => {
  console.log('Account Two Fa Setting:', accountTwoFaSetting);
});
```

### **6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthentication.updateTwoFaAccountConfig(providerType, useByDefault).subscribe(updateTwoFaAccountConfig => {
  console.log('Update Two Fa Account Config:', updateTwoFaAccountConfig);
});
```

### **7. submitTwoFaAccountConfig**

```javascript
twoFactorAuthentication.submitTwoFaAccountConfig(authConfig).subscribe(submitTwoFaAccountConfig => {
  console.log('Submit Two Fa Account Config:', submitTwoFaAccountConfig);
});
```

### **8. verifyAndSaveTwoFaAccountConfig**

```javascript
twoFactorAuthentication.verifyAndSaveTwoFaAccountConfig(authConfig).subscribe(verifyAndSaveTwoFaAccountConfig => {
  console.log('Verify And Save Two Fa Account Config:', verifyAndSaveTwoFaAccountConfig);
});
```

### **9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthentication.deleteTwoFaAccountConfig(providerType).subscribe(deleteTwoFaAccountConfig => {
  console.log('Delete Two Fa Account Config:', deleteTwoFaAccountConfig);
});
```
