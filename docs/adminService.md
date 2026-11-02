# ADMIN SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
adminService.sendTestMail('your-adminsettings-value').subscribe(result => {
  console.log('Send Test Mail:', result);
});
```

**2. sendTestSms**

```javascript
adminService.sendTestSms('your-testsmsrequest-value').subscribe(result => {
  console.log('Send Test Sms:', result);
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings().subscribe(securitySettings => {
  console.log('Get Security Settings:', securitySettings);
});
```

**4. saveSecuritySettings**

```javascript
adminService.saveSecuritySettings('your-securitysettings-value').subscribe(securitySettings => {
  console.log('Save Security Settings:', securitySettings);
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings().subscribe(jwtSettings => {
  console.log('Get Jwt Settings:', jwtSettings);
});
```

**6. saveJwtSettings**

```javascript
adminService.saveJwtSettings('your-jwtsettings-value').subscribe(jwtSettings => {
  console.log('Save Jwt Settings:', jwtSettings);
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(repositorySettings => {
  console.log('Get Repository Settings:', repositorySettings);
});
```

**8. saveRepositorySettings**

```javascript
adminService.saveRepositorySettings('your-repositorysettings-value').subscribe(repositorySettings => {
  console.log('Save Repository Settings:', repositorySettings);
});
```

**9. checkRepositoryAccess**

```javascript
adminService.checkRepositoryAccess('your-repositorysettings-value').subscribe(result => {
  console.log('Check Repository Access:', result);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(repositorySettingsInfo => {
  console.log('Get Repository Settings Info:', repositorySettingsInfo);
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(autoCommitSettings => {
  console.log('Get Auto Commit Settings:', autoCommitSettings);
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(autoCommitSettingsExists => {
  console.log('Auto Commit Settings Exists:', autoCommitSettingsExists);
});
```

**13. saveAutoCommitSettings**

```javascript
adminService.saveAutoCommitSettings('your-autocommitsettings-value').subscribe(autoCommitSettings => {
  console.log('Save Auto Commit Settings:', autoCommitSettings);
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(updates => {
  console.log('Check Updates:', updates);
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(featuresInfo => {
  console.log('Get Features Info:', featuresInfo);
});
```

**16. getLicenseUsageInfo**

```javascript
adminService.getLicenseUsageInfo().subscribe(licenseUsageInfo => {
  console.log('Get License Usage Info:', licenseUsageInfo);
});
```

**17. getSubscriptionInfo**

```javascript
adminService.getSubscriptionInfo().subscribe(subscriptionInfo => {
  console.log('Get Subscription Info:', subscriptionInfo);
});
```

**18. refreshLicense**

```javascript
adminService.refreshLicense().subscribe(refreshLicense => {
  console.log('Refresh License:', refreshLicense);
});
```

**19. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```

**20. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(accessToken => {
  console.log('Generate Access Token:', accessToken);
});
```

**21. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(mailConfigTemplate => {
  console.log('Get Mail Config Template:', mailConfigTemplate);
});
```
