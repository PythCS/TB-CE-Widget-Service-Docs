# USER SETTINGS

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('userSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```

## Methods

### loadUserSettings

```javascript
userSettingsService.loadUserSettings().subscribe(settings => {
  console.log('Settings:', settings);
});
```

### saveUserSettings

```javascript
const userSettings = {
  // your userSettings object
};

userSettingsService.saveUserSettings(userSettings).subscribe(settings => {
  console.log('Settings:', settings);
});
```

### putUserSettings

```javascript
const userSettingsData = {
  // your userSettingsData object
};

userSettingsService.putUserSettings(userSettingsData).subscribe(result => {
  console.log('Result:', result);
});
```

### getDocumentationLinks

```javascript
userSettingsService.getDocumentationLinks().subscribe(result => {
  console.log('DocumentationLinks:', result);
});
```

### updateDocumentationLinks

```javascript
const documentationLinks = {
  // your documentationLinks object
};

userSettingsService.updateDocumentationLinks(documentationLinks).subscribe(result => {
  console.log('Result:', result);
});
```

### getQuickLinks

```javascript
userSettingsService.getQuickLinks().subscribe(result => {
  console.log('QuickLinks:', result);
});
```

### updateQuickLinks

```javascript
const quickLinks = {
  // your quickLinks object
};

userSettingsService.updateQuickLinks(quickLinks).subscribe(result => {
  console.log('Result:', result);
});
```

### getGettingStarted

```javascript
userSettingsService.getGettingStarted().subscribe(result => {
  console.log('tingStarted:', result);
});
```

### updateGettingStarted

```javascript
const gettingStarted = {
  // your gettingStarted object
};

userSettingsService.updateGettingStarted(gettingStarted).subscribe(result => {
  console.log('Result:', result);
});
```

### getUserDashboardsInfo

```javascript
userSettingsService.getUserDashboardsInfo().subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

### reportUserDashboardAction

```javascript
const dashboardId = 'your-dashboard-id';
const action = {
  // your action object
};

userSettingsService.reportUserDashboardAction(dashboardId, action).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

