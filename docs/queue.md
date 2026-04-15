# Queue

```javascript
// Service name: queue
// File: queue.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queue = $injector.get(self.ctx.servicesMap.get('queue'));
```

### **1. getQueueById**

```javascript
queue.getQueueById(queueId).subscribe(queue => {
  console.log('Queue:', queue);
});
```

### **2. getQueueByName**

```javascript
queue.getQueueByName(queueName).subscribe(queue => {
  console.log('Queue:', queue);
});
```

### **3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queue.getTenantQueuesByServiceType(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **4. saveQueue**

```javascript
queue.saveQueue(queue, serviceType).subscribe(queue => {
  console.log('Queue:', queue);
});
```

### **5. getQueueStatistics**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queue.getQueueStatistics(pageLink).subscribe(queues => {
  console.log('Queues:', queues);
});
```

### **6. getQueueStatisticsById**

```javascript
queue.getQueueStatisticsById(queueStatId).subscribe(queue => {
  console.log('Queue:', queue);
});
```

### **7. getQueueStatisticsByIds**

```javascript
queue.getQueueStatisticsByIds(queueStatIds).subscribe(queues => {
  console.log('Queues:', queues);
});
```
