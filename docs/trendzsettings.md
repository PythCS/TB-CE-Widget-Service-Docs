### **TRENDZ SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzsettingsservice = $injector.get(self.ctx.servicesMap.get('trendzsettingsservice'));

```

**1. getTrendzSettings**

```javascript
trendzsettingsservice.getTrendzSettings().subscribe(trendzsettings => {
  console.log('Trendzsettings:', trendzsettings);
});
```

**2. saveTrendzSettings**

```javascript
trendzsettingsservice.saveTrendzSettings(trendzSettings).subscribe(savetrendzsettings => {
  console.log('Savetrendzsettings:', savetrendzsettings);
});
```

