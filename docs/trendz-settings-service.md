# TRENDZ SETTINGS SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
trendzSettingsService.getTrendzSettings().subscribe(trendzSettings => {
  console.log('Get Trendz Settings:', trendzSettings);
});
```

**2. saveTrendzSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
const trendzSettings = {  // TrendzSettings object
  // ... set the fields you need
};
trendzSettingsService.saveTrendzSettings(trendzSettings).subscribe(savedTrendzSettings => {
  console.log('Saved Trendz Settings:', savedTrendzSettings);
});
```
