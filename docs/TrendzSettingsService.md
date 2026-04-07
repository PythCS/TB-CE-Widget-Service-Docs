# TrendzSettingsService

### **TRENDZSETTINGSSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
trendzSettingsService.getTrendzSettings({ /* your config */ }).subscribe(trendzetting => {
  console.log('Trendz Settings:', trendzetting);
});
```

**2. saveTrendzSettings**

```javascript
trendzSettingsService.saveTrendzSettings({ /* your trendzSettings */ }, { /* your config */ }).subscribe(savedTrendzSettings => {
  console.log('Saved TrendzSettings:', savedTrendzSettings);
});
```
