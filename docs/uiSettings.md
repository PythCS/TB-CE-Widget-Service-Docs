# Ui Settings

```javascript
// Service name: uiSettings
// File: ui-settings.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettings = $injector.get(self.ctx.servicesMap.get('uiSettings'));
```

### **1. getHelpBaseUrl**

```javascript
uiSettings.getHelpBaseUrl().subscribe(helpBaseUrl => {
  console.log('Help Base Url:', helpBaseUrl);
});
```
