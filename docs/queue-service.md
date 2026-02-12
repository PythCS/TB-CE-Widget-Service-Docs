# QUEUE

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

## Methods

### getQueueById

```javascript
const queueId = 'your-queue-id';

queueService.getQueueById(queueId).subscribe(info => {
  console.log('Info:', info);
});
```

### getQueueByName

```javascript
const queueName = 'your-queuename';

queueService.getQueueByName(queueName).subscribe(info => {
  console.log('Info:', info);
});
```

### getTenantQueuesByServiceType

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const serviceType = {
  // your serviceType object
};

queueService.getTenantQueuesByServiceType(pageLink, serviceType).subscribe(info => {
  console.log('Info:', info);
});
```

### saveQueue

```javascript
const queue = {
  // your queue object
};
const serviceType = {
  // your serviceType object
};

queueService.saveQueue(queue, serviceType).subscribe(info => {
  console.log('Info:', info);
});
```

### getQueueStatistics

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

queueService.getQueueStatistics(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

### getQueueStatisticsById

```javascript
const queueStatId = 'your-queuestat-id';

queueService.getQueueStatisticsById(queueStatId).subscribe(info => {
  console.log('Info:', info);
});
```

### getQueueStatisticsByIds

```javascript
const queueStatIds = 'your-queuestats-id';

queueService.getQueueStatisticsByIds(queueStatIds).subscribe(info => {
  console.log('Info:', info);
});
```

