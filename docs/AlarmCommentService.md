# AlarmCommentService

### **ALARMCOMMENTSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

**1. saveAlarmComment**

```javascript
alarmCommentService.saveAlarmComment('your-alarm-id', { /* your alarmComment */ }, { /* your config */ }).subscribe(savedAlarmComment => {
  console.log('Saved AlarmComment:', savedAlarmComment);
});
```

**2. getAlarmComments**

```javascript
alarmCommentService.getAlarmComments('your-alarm-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(alarmcomment => {
  console.log('Alarm Comments:', alarmcomment);
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments('your-alarm-id', 'your-comment-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```
