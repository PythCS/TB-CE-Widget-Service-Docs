# USER SETTINGS SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **USER SETTINGS SERVICE**

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
  console.log('Load User Settings: result');
});
```

**2. saveUserSettings**

```javascript
const userSettings = userSettings;
userSettingsService.saveUserSettings(userSettings).subscribe(savedUserSettings => {
  console.log('Save User Settings: savedUserSettings');
});
```

**3. putUserSettings**

```javascript
const userSettingsData = userSettingsData;
userSettingsService.putUserSettings(userSettingsData).subscribe(result => {
  console.log('Put User Settings: result');
});
```

**4. getDocumentationLinks**

```javascript
userSettingsService.getDocumentationLinks().subscribe(documentationlinks => {
  console.log('Get Documentation Links: documentationlinks');
});
```

**5. updateDocumentationLinks**

```javascript
const documentationLinks = documentationLinks;
userSettingsService.updateDocumentationLinks(documentationLinks).subscribe(result => {
  console.log('Update Documentation Links: result');
});
```

**6. getQuickLinks**

```javascript
userSettingsService.getQuickLinks().subscribe(quicklinks => {
  console.log('Get Quick Links: quicklinks');
});
```

**7. updateQuickLinks**

```javascript
const quickLinks = quickLinks;
userSettingsService.updateQuickLinks(quickLinks).subscribe(result => {
  console.log('Update Quick Links: result');
});
```

**8. getGettingStarted**

```javascript
userSettingsService.getGettingStarted().subscribe(gettingStarted => {
  console.log('Get Getting Started: gettingStarted');
});
```

**9. updateGettingStarted**

```javascript
const gettingStarted = gettingStarted;
userSettingsService.updateGettingStarted(gettingStarted).subscribe(result => {
  console.log('Update Getting Started: result');
});
```

**10. getUserDashboardsInfo**

```javascript
userSettingsService.getUserDashboardsInfo().subscribe(userDashboardsInfo => {
  console.log('Get User Dashboards Info: userDashboardsInfo');
});
```

**11. reportUserDashboardAction**

```javascript
const action = action;
userSettingsService.reportUserDashboardAction('your-dashboard-id', action).subscribe(result => {
  console.log('Report User Dashboard Action: result');
});
```
