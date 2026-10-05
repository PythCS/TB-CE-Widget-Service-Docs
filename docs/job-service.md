# JOB SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
```

**1. getJobById**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const id = 'your-id';
jobService.getJobById(id).subscribe(jobBy => {
  console.log('Get Job By Id:', jobBy);
});
```

**2. getJobs**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const query = {  // JobQuery object
  // ... set the fields you need
};
jobService.getJobs(query).subscribe(jobs => {
  console.log('List of Jobs:', jobs);
});
```

**3. cancelJob**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const id = 'your-id';
jobService.cancelJob(id).subscribe(cancelJob => {
  console.log('Cancel Job:', cancelJob);
});
```

**4. reprocessJob**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const id = 'your-id';
jobService.reprocessJob(id).subscribe(reprocessJob => {
  console.log('Reprocess Job:', reprocessJob);
});
```

**5. deleteJob**

```javascript
const $injector = self.ctx.$scope.$injector;
const jobService = $injector.get(self.ctx.servicesMap.get('jobService'));
const id = 'your-id';
jobService.deleteJob(id).subscribe(result => {
  console.log('Delete Job result:', result);
});
```
