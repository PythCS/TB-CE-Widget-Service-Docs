# ADMIN SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ADMIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
const adminSettings = adminSettings;
adminService.sendTestMail(adminSettings).subscribe(result => {
  console.log('Send Test Mail: result');
});
```

**2. sendTestSms**

```javascript
const testSmsRequest = testSmsRequest;
adminService.sendTestSms(testSmsRequest).subscribe(result => {
  console.log('Send Test Sms: result');
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings().subscribe(securitysettings => {
  console.log('Get Security Settings: securitysettings');
});
```

**4. saveSecuritySettings**

```javascript
const securitySettings = securitySettings;
adminService.saveSecuritySettings(securitySettings).subscribe(savedSecuritySettings => {
  console.log('Save Security Settings: savedSecuritySettings');
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings().subscribe(jwtsettings => {
  console.log('Get Jwt Settings: jwtsettings');
});
```

**6. saveJwtSettings**

```javascript
const jwtSettings = jwtSettings;
adminService.saveJwtSettings(jwtSettings).subscribe(savedJwtSettings => {
  console.log('Save Jwt Settings: savedJwtSettings');
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(repositorysettings => {
  console.log('Get Repository Settings: repositorysettings');
});
```

**8. saveRepositorySettings**

```javascript
const repositorySettings = repositorySettings;
adminService.saveRepositorySettings(repositorySettings).subscribe(savedRepositorySettings => {
  console.log('Save Repository Settings: savedRepositorySettings');
});
```

**9. checkRepositoryAccess**

```javascript
const repositorySettings = repositorySettings;
adminService.checkRepositoryAccess(repositorySettings).subscribe(result => {
  console.log('Check Repository Access: result');
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(repositorySettingsInfo => {
  console.log('Get Repository Settings Info: repositorySettingsInfo');
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(autocommitsettings => {
  console.log('Get Auto Commit Settings: autocommitsettings');
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(result => {
  console.log('Auto Commit Settings Exists: result');
});
```

**13. saveAutoCommitSettings**

```javascript
const autoCommitSettings = autoCommitSettings;
adminService.saveAutoCommitSettings(autoCommitSettings).subscribe(savedAutoCommitSettings => {
  console.log('Save Auto Commit Settings: savedAutoCommitSettings');
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(result => {
  console.log('Check Updates: result');
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(featuresInfo => {
  console.log('Get Features Info: featuresInfo');
});
```

**16. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url: loginProcessingUrl');
});
```

**17. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(result => {
  console.log('Generate Access Token: result');
});
```

**18. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(mailConfigTemplate => {
  console.log('Get Mail Config Template: mailConfigTemplate');
});
```
