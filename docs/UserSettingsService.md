# UserSettingsService

### **USERSETTINGSSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('userSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```

**1. loadUserSettings**

```javascript
userSettingsService.loadUserSettings().subscribe(result => {
  console.log('Result:', result);
});
```

**2. saveUserSettings**

```javascript
userSettingsService.saveUserSettings({ /* your userSettings */ }).subscribe(savedUserSettings => {
  console.log('Saved UserSettings:', savedUserSettings);
});
```

**3. putUserSettings**

```javascript
userSettingsService.putUserSettings({ /* your userSettingsData */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. getDocumentationLinks**

```javascript
userSettingsService.getDocumentationLinks({ /* your config */ }).subscribe(documentationlink => {
  console.log('Documentation Links:', documentationlink);
});
```

**5. updateDocumentationLinks**

```javascript
userSettingsService.updateDocumentationLinks({ /* your documentationLinks */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. getQuickLinks**

```javascript
userSettingsService.getQuickLinks({ /* your config */ }).subscribe(quicklink => {
  console.log('Quick Links:', quicklink);
});
```

**7. updateQuickLinks**

```javascript
userSettingsService.updateQuickLinks({ /* your quickLinks */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. getGettingStarted**

```javascript
userSettingsService.getGettingStarted({ /* your config */ }).subscribe(gettingstarted => {
  console.log('Getting Started:', gettingstarted);
});
```

**9. updateGettingStarted**

```javascript
userSettingsService.updateGettingStarted({ /* your gettingStarted */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. getUserDashboardsInfo**

```javascript
userSettingsService.getUserDashboardsInfo({ /* your config */ }).subscribe(userdashboardsinfo => {
  console.log('User Dashboards Info:', userdashboardsinfo);
});
```

**11. reportUserDashboardAction**

```javascript
userSettingsService.reportUserDashboardAction('your-dashboard-id', { /* your action */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
