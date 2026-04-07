# AdminService

### **ADMINSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
adminService.sendTestMail({ /* your adminSettings */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**2. sendTestSms**

```javascript
adminService.sendTestSms({ /* your testSmsRequest */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings({ /* your config */ }).subscribe(ecurityetting => {
  console.log('Security Settings:', ecurityetting);
});
```

**4. saveSecuritySettings**

```javascript
adminService.saveSecuritySettings({ /* your securitySettings */ }, { /* your config */ }).subscribe(savedSecuritySettings => {
  console.log('Saved SecuritySettings:', savedSecuritySettings);
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings({ /* your config */ }).subscribe(jwtetting => {
  console.log('Jwt Settings:', jwtetting);
});
```

**6. saveJwtSettings**

```javascript
adminService.saveJwtSettings({ /* your jwtSettings */ }, { /* your config */ }).subscribe(savedJwtSettings => {
  console.log('Saved JwtSettings:', savedJwtSettings);
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings({ /* your config */ }).subscribe(repoitoryetting => {
  console.log('Repository Settings:', repoitoryetting);
});
```

**8. saveRepositorySettings**

```javascript
adminService.saveRepositorySettings({ /* your repositorySettings */ }, { /* your config */ }).subscribe(savedRepositorySettings => {
  console.log('Saved RepositorySettings:', savedRepositorySettings);
});
```

**9. checkRepositoryAccess**

```javascript
adminService.checkRepositoryAccess({ /* your repositorySettings */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo({ /* your config */ }).subscribe(repositorysettingsinfo => {
  console.log('Repository Settings Info:', repositorysettingsinfo);
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings({ /* your config */ }).subscribe(autocommitetting => {
  console.log('Auto Commit Settings:', autocommitetting);
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. saveAutoCommitSettings**

```javascript
adminService.saveAutoCommitSettings({ /* your autoCommitSettings */ }, { /* your config */ }).subscribe(savedAutoCommitSettings => {
  console.log('Saved AutoCommitSettings:', savedAutoCommitSettings);
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo({ /* your config */ }).subscribe(featuresinfo => {
  console.log('Features Info:', featuresinfo);
});
```

**16. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl({ /* your config */ }).subscribe(loginprocessingurl => {
  console.log('Login Processing Url:', loginprocessingurl);
});
```

**17. generateAccessToken**

```javascript
adminService.generateAccessToken({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**18. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate({ /* your config */ }).subscribe(mailconfigtemplate => {
  console.log('Mail Config Template:', mailconfigtemplate);
});
```
