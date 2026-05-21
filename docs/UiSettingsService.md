# UiSettingsService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('UiSettingsService'));
```

**1. getHelpBaseUrl**

```javascript
uiSettingsService.getHelpBaseUrl().subscribe(result => {
  console.log('Fetched  Help Base Url result:', result);
});
```
