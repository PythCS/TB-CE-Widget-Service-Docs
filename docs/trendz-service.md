# TRENDZ SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
```

**1. getTrendzSummary**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.getTrendzSummary().subscribe(trendzSummary => {
  console.log('Get Trendz Summary:', trendzSummary);
});
```

**2. performTrendzHealthcheck**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.performTrendzHealthcheck().subscribe(performTrendzHealthcheck => {
  console.log('Perform Trendz Healthcheck:', performTrendzHealthcheck);
});
```

**3. getTrendzConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.getTrendzConfig().subscribe(trendzConfig => {
  console.log('Get Trendz Config:', trendzConfig);
});
```

**4. saveTrendzConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
const trendzConfig = {  // TrendzConfiguration object
  // ... set the fields you need
};
trendzService.saveTrendzConfig(trendzConfig).subscribe(savedTrendzConfig => {
  console.log('Saved Trendz Config:', savedTrendzConfig);
});
```

**5. getTrendzSyncResult**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.getTrendzSyncResult().subscribe(trendzSyncResult => {
  console.log('Get Trendz Sync Result:', trendzSyncResult);
});
```

**6. connectToTrendz**

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
trendzService.connectToTrendz().subscribe(connectToTrendz => {
  console.log('Connect To Trendz:', connectToTrendz);
});
```
