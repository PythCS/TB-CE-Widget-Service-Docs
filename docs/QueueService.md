# QueueService

### **QUEUESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

**1. getQueueById**

```javascript
queueService.getQueueById('your-queue-id', { /* your config */ }).subscribe(queuebyid => {
  console.log('Queue By Id:', queuebyid);
});
```

**2. getQueueByName**

```javascript
queueService.getQueueByName('your-queueName', { /* your config */ }).subscribe(queuebyname => {
  console.log('Queue By Name:', queuebyname);
});
```

**3. getTenantQueuesByServiceType**

```javascript
queueService.getTenantQueuesByServiceType(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-servicetype', { /* your config */ }).subscribe(tenantqueuesbyservicetype => {
  console.log('Tenant Queues By Service Type:', tenantqueuesbyservicetype);
});
```

**4. saveQueue**

```javascript
queueService.saveQueue({ /* your queue */ }, 'your-servicetype', { /* your config */ }).subscribe(savedQueue => {
  console.log('Saved Queue:', savedQueue);
});
```

**5. getQueueStatistics**

```javascript
queueService.getQueueStatistics(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(queuetatitic => {
  console.log('Queue Statistics:', queuetatitic);
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById('your-queuestat-id', { /* your config */ }).subscribe(queuestatisticsbyid => {
  console.log('Queue Statistics By Id:', queuestatisticsbyid);
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds(['id1', 'id2'], { /* your config */ }).subscribe(queuetatiticbyid => {
  console.log('Queue Statistics By Ids:', queuetatiticbyid);
});
```
