# TRENDZ SETTINGS

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

## Methods

### getTrendzSettings

```javascript
trendzSettingsService.getTrendzSettings().subscribe(settings => {
  console.log('Settings:', settings);
});
```

### saveTrendzSettings

```javascript
const trendzSettings = {
  // your trendzSettings object
};

trendzSettingsService.saveTrendzSettings(trendzSettings).subscribe(settings => {
  console.log('Settings:', settings);
});
```

