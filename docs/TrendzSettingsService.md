# TrendzSettingsService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('TrendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
trendzSettingsService.getTrendzSettings().subscribe(settings => {
  console.log('Fetched  Trendz Settings settings:', settings);
});
```

**2. saveTrendzSettings**

```javascript
trendzSettingsService.saveTrendzSettings('your-trendzsettings-value').subscribe(settings => {
  console.log('Saved  Trendz Settings settings:', settings);
});
```
