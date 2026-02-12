### **USER SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usersettingsservice = $injector.get(self.ctx.servicesMap.get('usersettingsservice'));

// Alternative: Direct context access
const usersettingsservice = self.ctx.userSettingsService;
```

**1. loadUserSettings**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.loadUserSettings().subscribe(usersettings => {
  console.log('Usersettings:', usersettings);
});
```

**2. saveUserSettings**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.saveUserSettings(userSettings).subscribe(saveusersettings => {
  console.log('Saveusersettings:', saveusersettings);
});
```

**3. putUserSettings**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.putUserSettings(userSettingsData).subscribe(putusersettings => {
  console.log('Putusersettings:', putusersettings);
});
```

**4. getDocumentationLinks**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.getDocumentationLinks().subscribe(documentationlinks => {
  console.log('Documentationlinks:', documentationlinks);
});
```

**5. updateDocumentationLinks**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.updateDocumentationLinks(documentationLinks).subscribe(updatedocumentationlinks => {
  console.log('Updatedocumentationlinks:', updatedocumentationlinks);
});
```

**6. getQuickLinks**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.getQuickLinks().subscribe(quicklinks => {
  console.log('Quicklinks:', quicklinks);
});
```

**7. updateQuickLinks**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.updateQuickLinks(quickLinks).subscribe(updatequicklinks => {
  console.log('Updatequicklinks:', updatequicklinks);
});
```

**8. getGettingStarted**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.getGettingStarted().subscribe(gettingstarted => {
  console.log('Gettingstarted:', gettingstarted);
});
```

**9. updateGettingStarted**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.updateGettingStarted(gettingStarted).subscribe(updategettingstarted => {
  console.log('Updategettingstarted:', updategettingstarted);
});
```

**10. getUserDashboardsInfo**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.getUserDashboardsInfo().subscribe(userdashboardsinfo => {
  console.log('Userdashboardsinfo:', userdashboardsinfo);
});
```

**11. reportUserDashboardAction**

```javascript
const usersettingsservice = self.ctx.userSettingsService;
usersettingsservice.reportUserDashboardAction('your-dashboard-id', action).subscribe(reportuserdashboardaction => {
  console.log('Reportuserdashboardaction:', reportuserdashboardaction);
});
```

