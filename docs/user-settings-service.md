# USER SETTINGS SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('userSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```

**1. loadUserSettings**

```javascript
self.ctx.userSettingsService.loadUserSettings().subscribe(loadUserSettings => {
  console.log('Load User Settings:', loadUserSettings);
});
```

**2. saveUserSettings**

```javascript
self.ctx.userSettingsService.saveUserSettings('your-usersettings-value').subscribe(userSettings => {
  console.log('Save User Settings:', userSettings);
});
```

**3. putUserSettings**

```javascript
self.ctx.userSettingsService.putUserSettings('your-usersettingsdata-value').subscribe(result => {
  console.log('Put User Settings:', result);
});
```

**4. getDocumentationLinks**

```javascript
self.ctx.userSettingsService.getDocumentationLinks().subscribe(documentationLinks => {
  console.log('Get Documentation Links:', documentationLinks);
});
```

**5. updateDocumentationLinks**

```javascript
self.ctx.userSettingsService.updateDocumentationLinks('your-documentationlinks-value').subscribe(result => {
  console.log('Update Documentation Links:', result);
});
```

**6. getQuickLinks**

```javascript
self.ctx.userSettingsService.getQuickLinks().subscribe(quickLinks => {
  console.log('Get Quick Links:', quickLinks);
});
```

**7. updateQuickLinks**

```javascript
self.ctx.userSettingsService.updateQuickLinks('your-quicklinks-value').subscribe(result => {
  console.log('Update Quick Links:', result);
});
```

**8. getGettingStarted**

```javascript
self.ctx.userSettingsService.getGettingStarted().subscribe(gettingStarted => {
  console.log('Get Getting Started:', gettingStarted);
});
```

**9. updateGettingStarted**

```javascript
self.ctx.userSettingsService.updateGettingStarted('your-gettingstarted-value').subscribe(result => {
  console.log('Update Getting Started:', result);
});
```

**10. getUserDashboardsInfo**

```javascript
self.ctx.userSettingsService.getUserDashboardsInfo().subscribe(userDashboardsInfo => {
  console.log('Get User Dashboards Info:', userDashboardsInfo);
});
```

**11. reportUserDashboardAction**

```javascript
self.ctx.userSettingsService.reportUserDashboardAction('your-dashboard-id', 'your-action-value').subscribe(reportUserDashboardAction => {
  console.log('Report User Dashboard Action:', reportUserDashboardAction);
});
```
