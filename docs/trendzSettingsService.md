# TRENDZ SETTINGS SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
trendzSettingsService.getTrendzSettings().subscribe(trendzSettings => {
  console.log('Get Trendz Settings:', trendzSettings);
});
```

**2. saveTrendzSettings**

```javascript
trendzSettingsService.saveTrendzSettings('your-trendzsettings-value').subscribe(trendzSettings => {
  console.log('Save Trendz Settings:', trendzSettings);
});
```
