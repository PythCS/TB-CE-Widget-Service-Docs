# QUEUE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **QUEUE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

**1. getQueueById**

```javascript
queueService.getQueueById('your-queue-id').subscribe(queueById => {
  console.log('Get Queue By Id: queueById');
});
```

**2. getQueueByName**

```javascript
const queueName = queueName;
queueService.getQueueByName(queueName).subscribe(queueByName => {
  console.log('Get Queue By Name: queueByName');
});
```

**3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getTenantQueuesByServiceType(pageLink, 'type').subscribe(tenantQueuesByServiceType => {
  console.log('Get Tenant Queues By Service Type:tenantQueuesByServiceType');
});
```

**4. saveQueue**

```javascript
const queue = queue;
queueService.saveQueue(queue, 'type').subscribe(savedQueue => {
  console.log('Save Queue: savedQueue');
});
```

**5. getQueueStatistics**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getQueueStatistics(pageLink).subscribe(queuestatistics => {
  console.log('Get Queue Statistics: queuestatistics');
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById('your-id').subscribe(queueStatisticsById => {
  console.log('Get Queue Statistics By Id: queueStatisticsById');
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds('your-id').subscribe(queuestatisticsbyids => {
  console.log('Get Queue Statistics By Ids: queuestatisticsbyids');
});
```
