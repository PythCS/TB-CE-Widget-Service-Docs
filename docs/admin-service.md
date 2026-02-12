# Admin Service

Administrative functions for ThingsBoard system management.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

## Methods

### sendTestMail

```javascript
const adminSettings = {
  // your admin settings object
};
adminService.sendTestMail(adminSettings).subscribe(result => {
  console.log('Test Mail Sent:', result);
});
```

### sendTestSms

```javascript
const testSmsRequest = {
  // your test SMS request object
};
adminService.sendTestSms(testSmsRequest).subscribe(result => {
  console.log('Test SMS Sent:', result);
});
```

### getSecuritySettings

```javascript
adminService.getSecuritySettings().subscribe(settings => {
  console.log('Security Settings:', settings);
});
```

### saveSecuritySettings

```javascript
const securitySettings = {
  // your security settings object
};
adminService.saveSecuritySettings(securitySettings).subscribe(savedSettings => {
  console.log('Saved Security Settings:', savedSettings);
});
```

### getJwtSettings

```javascript
adminService.getJwtSettings().subscribe(settings => {
  console.log('JWT Settings:', settings);
});
```

### saveJwtSettings

```javascript
const jwtSettings = {
  // your JWT settings object
};
adminService.saveJwtSettings(jwtSettings).subscribe(response => {
  console.log('Saved JWT Settings:', response);
});
```

### getRepositorySettings

```javascript
adminService.getRepositorySettings().subscribe(settings => {
  console.log('Repository Settings:', settings);
});
```

### saveRepositorySettings

```javascript
const repositorySettings = {
  // your repository settings object
};
adminService.saveRepositorySettings(repositorySettings).subscribe(savedSettings => {
  console.log('Saved Repository Settings:', savedSettings);
});
```

### checkRepositoryAccess

```javascript
const repositorySettings = {
  // your repository settings object
};
adminService.checkRepositoryAccess(repositorySettings).subscribe(result => {
  console.log('Repository Access Check:', result);
});
```

### getRepositorySettingsInfo

```javascript
adminService.getRepositorySettingsInfo().subscribe(info => {
  console.log('Repository Settings Info:', info);
});
```

### getAutoCommitSettings

```javascript
adminService.getAutoCommitSettings().subscribe(settings => {
  console.log('Auto Commit Settings:', settings);
});
```

### autoCommitSettingsExists

```javascript
adminService.autoCommitSettingsExists().subscribe(exists => {
  console.log('Auto Commit Settings Exists:', exists);
});
```

### saveAutoCommitSettings

```javascript
const autoCommitSettings = {
  // your auto commit settings object
};
adminService.saveAutoCommitSettings(autoCommitSettings).subscribe(savedSettings => {
  console.log('Saved Auto Commit Settings:', savedSettings);
});
```

### checkUpdates

```javascript
adminService.checkUpdates().subscribe(updateMessage => {
  console.log('Update Message:', updateMessage);
});
```

### getFeaturesInfo

```javascript
adminService.getFeaturesInfo().subscribe(features => {
  console.log('Features Info:', features);
});
```

### getLoginProcessingUrl

```javascript
adminService.getLoginProcessingUrl().subscribe(url => {
  console.log('Login Processing URL:', url);
});
```

### generateAccessToken

```javascript
adminService.generateAccessToken().subscribe(token => {
  console.log('Generated Access Token:', token);
});
```

### getMailConfigTemplate

```javascript
adminService.getMailConfigTemplate().subscribe(templates => {
  console.log('Mail Config Templates:', templates);
});
```