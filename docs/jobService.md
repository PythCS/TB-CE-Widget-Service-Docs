# JOB SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
```

**1. getJobById**

```javascript
jobService.getJobById('your--id').subscribe(jobById => {
  console.log('Get Job By Id:', jobById);
});
```

**2. getJobs**

```javascript
jobService.getJobs('your-query-value').subscribe(jobs => {
  console.log('Get Jobs:', jobs);
});
```

**3. cancelJob**

```javascript
jobService.cancelJob('your--id').subscribe(result => {
  console.log('Cancel Job:', result);
});
```

**4. reprocessJob**

```javascript
jobService.reprocessJob('your--id').subscribe(result => {
  console.log('Reprocess Job:', result);
});
```

**5. deleteJob**

```javascript
jobService.deleteJob('your--id').subscribe(result => {
  console.log('Delete Job:', result);
});
```
