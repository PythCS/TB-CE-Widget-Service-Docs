### **ADMIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminservice = $injector.get(self.ctx.servicesMap.get('adminservice'));

```

**1. sendTestMail**

```javascript
adminservice.sendTestMail(adminSettings).subscribe(sendtestmail => {
  console.log('Sendtestmail:', sendtestmail);
});
```

**2. sendTestSms**

```javascript
adminservice.sendTestSms(testSmsRequest).subscribe(sendtestsms => {
  console.log('Sendtestsms:', sendtestsms);
});
```

**3. getSecuritySettings**

```javascript
adminservice.getSecuritySettings().subscribe(securitysettings => {
  console.log('Securitysettings:', securitysettings);
});
```

**4. saveSecuritySettings**

```javascript
adminservice.saveSecuritySettings(securitySettings).subscribe(savesecuritysettings => {
  console.log('Savesecuritysettings:', savesecuritysettings);
});
```

**5. getJwtSettings**

```javascript
adminservice.getJwtSettings().subscribe(jwtsettings => {
  console.log('Jwtsettings:', jwtsettings);
});
```

**6. saveJwtSettings**

```javascript
adminservice.saveJwtSettings(jwtSettings).subscribe(savejwtsettings => {
  console.log('Savejwtsettings:', savejwtsettings);
});
```

**7. getRepositorySettings**

```javascript
adminservice.getRepositorySettings().subscribe(repositorysettings => {
  console.log('Repositorysettings:', repositorysettings);
});
```

**8. saveRepositorySettings**

```javascript
adminservice.saveRepositorySettings(repositorySettings).subscribe(saverepositorysettings => {
  console.log('Saverepositorysettings:', saverepositorysettings);
});
```

**9. checkRepositoryAccess**

```javascript
adminservice.checkRepositoryAccess(repositorySettings).subscribe(checkrepositoryaccess => {
  console.log('Checkrepositoryaccess:', checkrepositoryaccess);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminservice.getRepositorySettingsInfo().subscribe(repositorysettingsinfo => {
  console.log('Repositorysettingsinfo:', repositorysettingsinfo);
});
```

**11. getAutoCommitSettings**

```javascript
adminservice.getAutoCommitSettings().subscribe(autocommitsettings => {
  console.log('Autocommitsettings:', autocommitsettings);
});
```

**12. autoCommitSettingsExists**

```javascript
adminservice.autoCommitSettingsExists().subscribe(autocommitsettingsexists => {
  console.log('Autocommitsettingsexists:', autocommitsettingsexists);
});
```

**13. saveAutoCommitSettings**

```javascript
adminservice.saveAutoCommitSettings(autoCommitSettings).subscribe(saveautocommitsettings => {
  console.log('Saveautocommitsettings:', saveautocommitsettings);
});
```

**14. checkUpdates**

```javascript
adminservice.checkUpdates().subscribe(checkupdates => {
  console.log('Checkupdates:', checkupdates);
});
```

**15. getFeaturesInfo**

```javascript
adminservice.getFeaturesInfo().subscribe(featuresinfo => {
  console.log('Featuresinfo:', featuresinfo);
});
```

**16. getLoginProcessingUrl**

```javascript
adminservice.getLoginProcessingUrl().subscribe(loginprocessingurl => {
  console.log('Loginprocessingurl:', loginprocessingurl);
});
```

**17. generateAccessToken**

```javascript
adminservice.generateAccessToken().subscribe(generateaccesstoken => {
  console.log('Generateaccesstoken:', generateaccesstoken);
});
```

**18. getMailConfigTemplate**

```javascript
adminservice.getMailConfigTemplate().subscribe(mailconfigtemplate => {
  console.log('Mailconfigtemplate:', mailconfigtemplate);
});
```

