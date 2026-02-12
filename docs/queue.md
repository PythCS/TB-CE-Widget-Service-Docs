### **QUEUE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueservice = $injector.get(self.ctx.servicesMap.get('queueservice'));

```

**1. getQueueById**

```javascript
queueservice.getQueueById('your-queue-id').subscribe(queuebyid => {
  console.log('Queuebyid:', queuebyid);
});
```

**2. getQueueByName**

```javascript
queueservice.getQueueByName('Device Name').subscribe(queuebyname => {
  console.log('Queuebyname:', queuebyname);
});
```

**3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueservice.getTenantQueuesByServiceType(pageLink, serviceType).subscribe(tenantqueuesbyservicetype => {
  console.log('Tenantqueuesbyservicetype:', tenantqueuesbyservicetype);
});
```

**4. saveQueue**

```javascript
queueservice.saveQueue(queue, serviceType).subscribe(savequeue => {
  console.log('Savequeue:', savequeue);
});
```

**5. getQueueStatistics**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueservice.getQueueStatistics(pageLink).subscribe(queuestatistics => {
  console.log('Queuestatistics:', queuestatistics);
});
```

**6. getQueueStatisticsById**

```javascript
queueservice.getQueueStatisticsById('your-queuestat-id').subscribe(queuestatisticsbyid => {
  console.log('Queuestatisticsbyid:', queuestatisticsbyid);
});
```

**7. getQueueStatisticsByIds**

```javascript
queueservice.getQueueStatisticsByIds('your-queuestats-id').subscribe(queuestatisticsbyids => {
  console.log('Queuestatisticsbyids:', queuestatisticsbyids);
});
```

