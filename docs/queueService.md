# QUEUE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

**1. getQueueById**

```javascript
queueService.getQueueById('your-queue-id').subscribe(queueById => {
  console.log('Get Queue By Id:', queueById);
});
```

**2. getQueueByName**

```javascript
queueService.getQueueByName('your-queuename-value').subscribe(queueByName => {
  console.log('Get Queue By Name:', queueByName);
});
```

**3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getTenantQueuesByServiceType(pageLink, 'your-servicetype-value').subscribe(tenantQueuesByServiceType => {
  console.log('Get Tenant Queues By Service Type:', tenantQueuesByServiceType);
});
```

**4. saveQueue**

```javascript
queueService.saveQueue('your-queue-value', 'your-servicetype-value').subscribe(queue => {
  console.log('Save Queue:', queue);
});
```

**5. getQueueStatistics**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getQueueStatistics(pageLink).subscribe(queueStatistics => {
  console.log('Get Queue Statistics:', queueStatistics);
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById('your-queuestat-id').subscribe(queueStatisticsById => {
  console.log('Get Queue Statistics By Id:', queueStatisticsById);
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds('your-queuestatids-value').subscribe(queueStatisticsByIds => {
  console.log('Get Queue Statistics By Ids:', queueStatisticsByIds);
});
```
