# QUEUE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

**1. getQueueById**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queueId = 'your-queue-id';
queueService.getQueueById(queueId).subscribe(queueBy => {
  console.log('Get Queue By Id:', queueBy);
});
```

**2. getQueueByName**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queueName = 'your-queue-name';
queueService.getQueueByName(queueName).subscribe(queueByName => {
  console.log('Get Queue By Name:', queueByName);
});
```

**3. getTenantQueuesByServiceType**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const serviceType = {  // ServiceType object
  // ... set the fields you need
};
queueService.getTenantQueuesByServiceType(pageLink, serviceType).subscribe(tenantQueuesByServiceTypes => {
  console.log('List of Tenant Queues By Service Types:', tenantQueuesByServiceTypes);
});
```

**4. saveQueue**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queue = {  // QueueInfo object
  // ... set the fields you need
};
const serviceType = {  // ServiceType object
  // ... set the fields you need
};
queueService.saveQueue(queue, serviceType).subscribe(savedQueue => {
  console.log('Saved Queue:', savedQueue);
});
```

**5. getQueueStatistics**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getQueueStatistics(pageLink).subscribe(queueStatistics => {
  console.log('List of Queue Statistics:', queueStatistics);
});
```

**6. getQueueStatisticsById**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queueStatId = 'your-queue-stat-id';
queueService.getQueueStatisticsById(queueStatId).subscribe(queueStatisticsBy => {
  console.log('Get Queue Statistics By Id:', queueStatisticsBy);
});
```

**7. getQueueStatisticsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
const queueStatIds = ['your-queue-stat-i-1', 'your-queue-stat-i-2'];
queueService.getQueueStatisticsByIds(queueStatIds).subscribe(queueStatisticsBys => {
  console.log('List of Queue Statistics By Ids:', queueStatisticsBys);
});
```
