# TRENDZ SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzService = $injector.get(self.ctx.servicesMap.get('trendzService'));
```

**1. getTrendzSummary**

```javascript
trendzService.getTrendzSummary().subscribe(trendzSummary => {
  console.log('Get Trendz Summary:', trendzSummary);
});
```

**2. performTrendzHealthcheck**

```javascript
trendzService.performTrendzHealthcheck().subscribe(performTrendzHealthcheck => {
  console.log('Perform Trendz Healthcheck:', performTrendzHealthcheck);
});
```

**3. getTrendzConfig**

```javascript
trendzService.getTrendzConfig().subscribe(trendzConfig => {
  console.log('Get Trendz Config:', trendzConfig);
});
```

**4. saveTrendzConfig**

```javascript
trendzService.saveTrendzConfig('your-trendzconfig-value').subscribe(trendzConfig => {
  console.log('Save Trendz Config:', trendzConfig);
});
```

**5. getTrendzSyncResult**

```javascript
trendzService.getTrendzSyncResult().subscribe(trendzSyncResult => {
  console.log('Get Trendz Sync Result:', trendzSyncResult);
});
```

**6. connectToTrendz**

```javascript
trendzService.connectToTrendz().subscribe(connectToTrendz => {
  console.log('Connect To Trendz:', connectToTrendz);
});
```
