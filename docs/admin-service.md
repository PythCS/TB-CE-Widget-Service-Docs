# ADMIN SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const adminSettings = {  // AdminSettings<MailServerSettings> object
  // ... set the fields you need
};
adminService.sendTestMail(adminSettings).subscribe(sendTestMail => {
  console.log('Send Test Mail:', sendTestMail);
});
```

**2. sendTestSms**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const testSmsRequest = {  // TestSmsRequest object
  // ... set the fields you need
};
adminService.sendTestSms(testSmsRequest).subscribe(sendTestSms => {
  console.log('Send Test Sms:', sendTestSms);
});
```

**3. getSecuritySettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getSecuritySettings().subscribe(securitySettings => {
  console.log('Get Security Settings:', securitySettings);
});
```

**4. saveSecuritySettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const securitySettings = {  // SecuritySettings object
  // ... set the fields you need
};
adminService.saveSecuritySettings(securitySettings).subscribe(savedSecuritySettings => {
  console.log('Saved Security Settings:', savedSecuritySettings);
});
```

**5. getJwtSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getJwtSettings().subscribe(jwtSettings => {
  console.log('Get Jwt Settings:', jwtSettings);
});
```

**6. saveJwtSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const jwtSettings = {  // JwtSettings object
  // ... set the fields you need
};
adminService.saveJwtSettings(jwtSettings).subscribe(savedJwtSettings => {
  console.log('Saved Jwt Settings:', savedJwtSettings);
});
```

**7. getRepositorySettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getRepositorySettings().subscribe(repositorySettings => {
  console.log('Get Repository Settings:', repositorySettings);
});
```

**8. saveRepositorySettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const repositorySettings = {  // RepositorySettings object
  // ... set the fields you need
};
adminService.saveRepositorySettings(repositorySettings).subscribe(savedRepositorySettings => {
  console.log('Saved Repository Settings:', savedRepositorySettings);
});
```

**9. checkRepositoryAccess**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const repositorySettings = {  // RepositorySettings object
  // ... set the fields you need
};
adminService.checkRepositoryAccess(repositorySettings).subscribe(checkRepositoryAccess => {
  console.log('Check Repository Access:', checkRepositoryAccess);
});
```

**10. getRepositorySettingsInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getRepositorySettingsInfo().subscribe(repositorySettingsInfo => {
  console.log('Get Repository Settings Info:', repositorySettingsInfo);
});
```

**11. getAutoCommitSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getAutoCommitSettings().subscribe(autoCommitSettings => {
  console.log('Get Auto Commit Settings:', autoCommitSettings);
});
```

**12. autoCommitSettingsExists**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.autoCommitSettingsExists().subscribe(autoCommitSettingsExists => {
  console.log('Auto Commit Settings Exists:', autoCommitSettingsExists);
});
```

**13. saveAutoCommitSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
const autoCommitSettings = {  // AutoCommitSettings object
  // ... set the fields you need
};
adminService.saveAutoCommitSettings(autoCommitSettings).subscribe(savedAutoCommitSettings => {
  console.log('Saved Auto Commit Settings:', savedAutoCommitSettings);
});
```

**14. checkUpdates**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.checkUpdates().subscribe(checkUpdates => {
  console.log('Check Updates:', checkUpdates);
});
```

**15. getFeaturesInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getFeaturesInfo().subscribe(featuresInfo => {
  console.log('Get Features Info:', featuresInfo);
});
```

**16. getLicenseUsageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getLicenseUsageInfo().subscribe(licenseUsageInfo => {
  console.log('Get License Usage Info:', licenseUsageInfo);
});
```

**17. getSubscriptionInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getSubscriptionInfo().subscribe(subscriptionInfo => {
  console.log('Get Subscription Info:', subscriptionInfo);
});
```

**18. refreshLicense**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.refreshLicense().subscribe(refreshLicense => {
  console.log('Refresh License:', refreshLicense);
});
```

**19. getLoginProcessingUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```

**20. generateAccessToken**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.generateAccessToken().subscribe(generateAccessToken => {
  console.log('Generate Access Token:', generateAccessToken);
});
```

**21. getMailConfigTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
adminService.getMailConfigTemplate().subscribe(mailConfigTemplates => {
  console.log('List of Mail Config Templates:', mailConfigTemplates);
});
```
