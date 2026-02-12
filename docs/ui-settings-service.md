# UI SETTINGS

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('uiSettingsService'));
```

## Methods

### getHelpBaseUrl

```javascript
uiSettingsService.getHelpBaseUrl().subscribe(url => {
  console.log('URL:', url);
});
```

