# QueueService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('QueueService'));
```

**1. getQueueById**

```javascript
queueService.getQueueById('your-queue-id').subscribe(result => {
  console.log('Fetched  Queue By Id result:', result);
});
```

**2. getQueueByName**

```javascript
queueService.getQueueByName('your-queuename-value').subscribe(result => {
  console.log('Fetched  Queue By Name result:', result);
});
```

**3. getTenantQueuesByServiceType**

```javascript
queueService.getTenantQueuesByServiceType(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-servicetype-value').subscribe(tenant => {
  console.log('Fetched  Tenant Queues By Service Type tenant:', tenant);
});
```

**4. saveQueue**

```javascript
queueService.saveQueue('your-queue-value', 'your-servicetype-value').subscribe(result => {
  console.log('Saved  Queue result:', result);
});
```

**5. getQueueStatistics**

```javascript
queueService.getQueueStatistics(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Queue Statistics result:', result);
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById('your-queuestat-id').subscribe(result => {
  console.log('Fetched  Queue Statistics By Id result:', result);
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds('your-queuestatids-value').subscribe(result => {
  console.log('Fetched  Queue Statistics By Ids result:', result);
});
```
