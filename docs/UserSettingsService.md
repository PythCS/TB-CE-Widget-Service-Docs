# UserSettingsService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('UserSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```

**1. loadUserSettings**

```javascript
userSettingsService.loadUserSettings().subscribe(users => {
  console.log('load User Settings users:', users);
});
```

**2. saveUserSettings**

```javascript
userSettingsService.saveUserSettings('your-usersettings-value').subscribe(users => {
  console.log('Saved  User Settings users:', users);
});
```

**3. putUserSettings**

```javascript
userSettingsService.putUserSettings('your-usersettingsdata-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**4. getDocumentationLinks**

```javascript
userSettingsService.getDocumentationLinks().subscribe(result => {
  console.log('Fetched  Documentation Links result:', result);
});
```

**5. updateDocumentationLinks**

```javascript
userSettingsService.updateDocumentationLinks('your-documentationlinks-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**6. getQuickLinks**

```javascript
userSettingsService.getQuickLinks().subscribe(result => {
  console.log('Fetched  Quick Links result:', result);
});
```

**7. updateQuickLinks**

```javascript
userSettingsService.updateQuickLinks('your-quicklinks-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**8. getGettingStarted**

```javascript
userSettingsService.getGettingStarted().subscribe(result => {
  console.log('Fetched  Getting Started result:', result);
});
```

**9. updateGettingStarted**

```javascript
userSettingsService.updateGettingStarted('your-gettingstarted-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**10. getUserDashboardsInfo**

```javascript
userSettingsService.getUserDashboardsInfo().subscribe(users => {
  console.log('Fetched  User Dashboards Info users:', users);
});
```

**11. reportUserDashboardAction**

```javascript
userSettingsService.reportUserDashboardAction('your-dashboard-id', 'your-action-value').subscribe(users => {
  console.log('report User Dashboard Action users:', users);
});
```
