# Admin

```javascript
// Service name: admin
// File: admin.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const admin = $injector.get(self.ctx.servicesMap.get('admin'));
```

### **1. sendTestMail**

```javascript
admin.sendTestMail(adminSettings).subscribe(sendTestMail => {
  console.log('Send Test Mail:', sendTestMail);
});
```

### **2. sendTestSms**

```javascript
admin.sendTestSms(testSmsRequest).subscribe(sendTestSm => {
  console.log('Send Test Sm:', sendTestSm);
});
```

### **3. getSecuritySettings**

```javascript
admin.getSecuritySettings().subscribe(securitySetting => {
  console.log('Security Setting:', securitySetting);
});
```

### **4. saveSecuritySettings**

```javascript
admin.saveSecuritySettings(securitySettings).subscribe(saveSecuritySetting => {
  console.log('Save Security Setting:', saveSecuritySetting);
});
```

### **5. getJwtSettings**

```javascript
admin.getJwtSettings().subscribe(jwtSetting => {
  console.log('Jwt Setting:', jwtSetting);
});
```

### **6. saveJwtSettings**

```javascript
admin.saveJwtSettings(jwtSettings).subscribe(saveJwtSetting => {
  console.log('Save Jwt Setting:', saveJwtSetting);
});
```

### **7. getRepositorySettings**

```javascript
admin.getRepositorySettings().subscribe(repositorySetting => {
  console.log('Repository Setting:', repositorySetting);
});
```

### **8. saveRepositorySettings**

```javascript
admin.saveRepositorySettings(repositorySettings).subscribe(saveRepositorySetting => {
  console.log('Save Repository Setting:', saveRepositorySetting);
});
```

### **9. checkRepositoryAccess**

```javascript
admin.checkRepositoryAccess(repositorySettings).subscribe(checkRepositoryAccess => {
  console.log('Check Repository Access:', checkRepositoryAccess);
});
```

### **10. getRepositorySettingsInfo**

```javascript
admin.getRepositorySettingsInfo().subscribe(repositorySetting => {
  console.log('Repository Setting:', repositorySetting);
});
```

### **11. getAutoCommitSettings**

```javascript
admin.getAutoCommitSettings().subscribe(autoCommitSetting => {
  console.log('Auto Commit Setting:', autoCommitSetting);
});
```

### **12. autoCommitSettingsExists**

```javascript
admin.autoCommitSettingsExists().subscribe(autoCommitSettingsExist => {
  console.log('Auto Commit Settings Exist:', autoCommitSettingsExist);
});
```

### **13. saveAutoCommitSettings**

```javascript
admin.saveAutoCommitSettings(autoCommitSettings).subscribe(saveAutoCommitSetting => {
  console.log('Save Auto Commit Setting:', saveAutoCommitSetting);
});
```

### **14. checkUpdates**

```javascript
admin.checkUpdates().subscribe(checkUpdate => {
  console.log('Check Update:', checkUpdate);
});
```

### **15. getFeaturesInfo**

```javascript
admin.getFeaturesInfo().subscribe(feature => {
  console.log('Feature:', feature);
});
```

### **16. getLoginProcessingUrl**

```javascript
admin.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Login Processing Url:', loginProcessingUrl);
});
```

### **17. generateAccessToken**

```javascript
admin.generateAccessToken().subscribe(generateAccessToken => {
  console.log('Generate Access Token:', generateAccessToken);
});
```

### **18. getMailConfigTemplate**

```javascript
admin.getMailConfigTemplate().subscribe(mailConfigTemplates => {
  console.log('Mail Config Templates:', mailConfigTemplates);
});
```
