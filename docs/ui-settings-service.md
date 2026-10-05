# UI SETTINGS SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('uiSettingsService'));
```

**1. getHelpBaseUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('uiSettingsService'));
uiSettingsService.getHelpBaseUrl().subscribe(helpBaseUrl => {
  console.log('Get Help Base Url:', helpBaseUrl);
});
```
