# USER SETTINGS SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('userSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```

**1. loadUserSettings**

```javascript
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.loadUserSettings().subscribe(userSettings => {
  console.log('Load User Settings:', userSettings);
});
```

**2. saveUserSettings**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const userSettings = {  // UserSettings object
  // ... set the fields you need
};
userSettingsService.saveUserSettings(userSettings).subscribe(savedUserSettings => {
  console.log('Saved User Settings:', savedUserSettings);
});
```

**3. putUserSettings**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const userSettingsData = {  // Partial<UserSettings> object
  // ... set the fields you need
};
userSettingsService.putUserSettings(userSettingsData).subscribe(putUserSettings => {
  console.log('Put User Settings:', putUserSettings);
});
```

**4. getDocumentationLinks**

```javascript
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.getDocumentationLinks().subscribe(documentationLinks => {
  console.log('Get Documentation Links:', documentationLinks);
});
```

**5. updateDocumentationLinks**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const documentationLinks = {  // DocumentationLinks object
  // ... set the fields you need
};
userSettingsService.updateDocumentationLinks(documentationLinks).subscribe(savedDocumentationLinks => {
  console.log('Saved Documentation Links:', savedDocumentationLinks);
});
```

**6. getQuickLinks**

```javascript
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.getQuickLinks().subscribe(quickLinks => {
  console.log('Get Quick Links:', quickLinks);
});
```

**7. updateQuickLinks**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const quickLinks = {  // QuickLinks object
  // ... set the fields you need
};
userSettingsService.updateQuickLinks(quickLinks).subscribe(savedQuickLinks => {
  console.log('Saved Quick Links:', savedQuickLinks);
});
```

**8. getGettingStarted**

```javascript
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.getGettingStarted().subscribe(gettingStarted => {
  console.log('Get Getting Started:', gettingStarted);
});
```

**9. updateGettingStarted**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const gettingStarted = {  // GettingStarted object
  // ... set the fields you need
};
userSettingsService.updateGettingStarted(gettingStarted).subscribe(savedGettingStarted => {
  console.log('Saved Getting Started:', savedGettingStarted);
});
```

**10. getUserDashboardsInfo**

```javascript
const userSettingsService = self.ctx.userSettingsService;
userSettingsService.getUserDashboardsInfo().subscribe(userDashboardsInfo => {
  console.log('Get User Dashboards Info:', userDashboardsInfo);
});
```

**11. reportUserDashboardAction**

```javascript
const userSettingsService = self.ctx.userSettingsService;
const dashboardId = 'your-dashboard-id';
const action = {  // UserDashboardAction object
  // ... set the fields you need
};
userSettingsService.reportUserDashboardAction(dashboardId, action).subscribe(reportUserDashboardAction => {
  console.log('Report User Dashboard Action:', reportUserDashboardAction);
});
```
