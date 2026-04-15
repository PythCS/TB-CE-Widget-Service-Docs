# Trendz Settings

```javascript
// Service name: trendzSettings
// File: trendz-settings.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettings = $injector.get(self.ctx.servicesMap.get('trendzSettings'));
```

### **1. getTrendzSettings**

```javascript
trendzSettings.getTrendzSettings().subscribe(trendzSetting => {
  console.log('Trendz Setting:', trendzSetting);
});
```

### **2. saveTrendzSettings**

```javascript
trendzSettings.saveTrendzSettings(trendzSettings).subscribe(trendzSetting => {
  console.log('Trendz Setting:', trendzSetting);
});
```
