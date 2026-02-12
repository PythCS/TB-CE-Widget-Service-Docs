# TWO FACTOR AUTHENTICATION

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

## Methods

### getTwoFaSettings

```javascript
twoFactorAuthenticationService.getTwoFaSettings().subscribe(settings => {
  console.log('Settings:', settings);
});
```

### saveTwoFaSettings

```javascript
const settings = {
  // your settings object
};

twoFactorAuthenticationService.saveTwoFaSettings(settings).subscribe(settings => {
  console.log('Settings:', settings);
});
```

### getAvailableTwoFaProviders

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(result => {
  console.log('AvailableTwoFaProviders:', result);
});
```

### generateTwoFaAccountConfig

```javascript
const providerType = {
  // your providerType object
};

twoFactorAuthenticationService.generateTwoFaAccountConfig(providerType).subscribe(result => {
  console.log('generateTwoFaAccountConfig:', result);
});
```

### getAccountTwoFaSettings

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(settings => {
  console.log('Settings:', settings);
});
```

### updateTwoFaAccountConfig

```javascript
const providerType = {
  // your providerType object
};
const useByDefault = true;

twoFactorAuthenticationService.updateTwoFaAccountConfig(providerType, useByDefault).subscribe(settings => {
  console.log('Settings:', settings);
});
```

### submitTwoFaAccountConfig

```javascript
const authConfig = {
  // your authConfig object
};

twoFactorAuthenticationService.submitTwoFaAccountConfig(authConfig).subscribe(result => {
  console.log('submitTwoFaAccountConfig:', result);
});
```

### verifyAndSaveTwoFaAccountConfig

```javascript
const authConfig = {
  // your authConfig object
};
const verificationCode = 100;

twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(authConfig, verificationCode).subscribe(settings => {
  console.log('Settings:', settings);
});
```

### deleteTwoFaAccountConfig

```javascript
const providerType = {
  // your providerType object
};

twoFactorAuthenticationService.deleteTwoFaAccountConfig(providerType).subscribe(settings => {
  console.log('Settings:', settings);
});
```

