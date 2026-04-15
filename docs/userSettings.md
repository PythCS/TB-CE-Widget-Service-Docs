# User Settings

```javascript
// Service name: userSettings
// File: user-settings.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const userSettings = self.ctx.userSettingsService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const userSettings = $injector.get(self.ctx.servicesMap.get('userSettings'));
```

### **1. loadUserSettings**

```javascript
userSettings.loadUserSettings().subscribe(user => {
  console.log('User:', user);
});
```

### **2. saveUserSettings**

```javascript
userSettings.saveUserSettings(userSettings).subscribe(user => {
  console.log('User:', user);
});
```

### **3. putUserSettings**

```javascript
userSettings.putUserSettings(userSettingsData).subscribe(user => {
  console.log('User:', user);
});
```

### **4. getDocumentationLinks**

```javascript
userSettings.getDocumentationLinks().subscribe(documentationLink => {
  console.log('Documentation Link:', documentationLink);
});
```

### **5. updateDocumentationLinks**

```javascript
userSettings.updateDocumentationLinks(documentationLinks).subscribe(updateDocumentationLink => {
  console.log('Update Documentation Link:', updateDocumentationLink);
});
```

### **6. getQuickLinks**

```javascript
userSettings.getQuickLinks().subscribe(quickLink => {
  console.log('Quick Link:', quickLink);
});
```

### **7. updateQuickLinks**

```javascript
userSettings.updateQuickLinks(quickLinks).subscribe(updateQuickLink => {
  console.log('Update Quick Link:', updateQuickLink);
});
```

### **8. getGettingStarted**

```javascript
userSettings.getGettingStarted().subscribe(gettingStarted => {
  console.log('Getting Started:', gettingStarted);
});
```

### **9. updateGettingStarted**

```javascript
userSettings.updateGettingStarted(gettingStarted).subscribe(updateGettingStarted => {
  console.log('Update Getting Started:', updateGettingStarted);
});
```

### **10. getUserDashboardsInfo**

```javascript
userSettings.getUserDashboardsInfo().subscribe(user => {
  console.log('User:', user);
});
```

### **11. reportUserDashboardAction**

```javascript
userSettings.reportUserDashboardAction(dashboardId, action).subscribe(user => {
  console.log('User:', user);
});
```
