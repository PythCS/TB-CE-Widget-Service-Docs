# TRENDZ SETTINGS SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **TRENDZ SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
trendzSettingsService.getTrendzSettings().subscribe(trendzsettings => {
  console.log('Get Trendz Settings: trendzsettings');
});
```

**2. saveTrendzSettings**

```javascript
const trendzSettings = trendzSettings;
trendzSettingsService.saveTrendzSettings(trendzSettings).subscribe(savedTrendzSettings => {
  console.log('Save Trendz Settings: savedTrendzSettings');
});
```
