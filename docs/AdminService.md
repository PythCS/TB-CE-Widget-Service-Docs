# AdminService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('AdminService'));
```

**1. sendTestMail**

```javascript
adminService.sendTestMail('your-adminsettings-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**2. sendTestSms**

```javascript
adminService.sendTestSms('your-testsmsrequest-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings().subscribe(settings => {
  console.log('Fetched  Security Settings settings:', settings);
});
```

**4. saveSecuritySettings**

```javascript
adminService.saveSecuritySettings('your-securitysettings-value').subscribe(settings => {
  console.log('Saved  Security Settings settings:', settings);
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings().subscribe(settings => {
  console.log('Fetched  Jwt Settings settings:', settings);
});
```

**6. saveJwtSettings**

```javascript
adminService.saveJwtSettings('your-jwtsettings-value').subscribe(settings => {
  console.log('Saved  Jwt Settings settings:', settings);
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(settings => {
  console.log('Fetched  Repository Settings settings:', settings);
});
```

**8. saveRepositorySettings**

```javascript
adminService.saveRepositorySettings('your-repositorysettings-value').subscribe(settings => {
  console.log('Saved  Repository Settings settings:', settings);
});
```

**9. checkRepositoryAccess**

```javascript
adminService.checkRepositoryAccess('your-repositorysettings-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(settings => {
  console.log('Fetched  Repository Settings Info settings:', settings);
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(settings => {
  console.log('Fetched  Auto Commit Settings settings:', settings);
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(settings => {
  console.log('auto Commit Settings Exists settings:', settings);
});
```

**13. saveAutoCommitSettings**

```javascript
adminService.saveAutoCommitSettings('your-autocommitsettings-value').subscribe(settings => {
  console.log('Saved  Auto Commit Settings settings:', settings);
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(result => {
  console.log('check Updates result:', result);
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(info => {
  console.log('Fetched  Features Info info:', info);
});
```

**16. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(result => {
  console.log('Fetched  Login Processing Url result:', result);
});
```

**17. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(result => {
  console.log('generate Access Token result:', result);
});
```

**18. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(result => {
  console.log('Fetched  Mail Config Template result:', result);
});
```
