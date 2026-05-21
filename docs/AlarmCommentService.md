# AlarmCommentService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('AlarmCommentService'));
```

**1. saveAlarmComment**

```javascript
alarmCommentService.saveAlarmComment('your-alarm-id', 'your-alarmcomment-value').subscribe(alarm => {
  console.log('Saved  Alarm Comment alarm:', alarm);
});
```

**2. getAlarmComments**

```javascript
alarmCommentService.getAlarmComments('your-alarm-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(alarm => {
  console.log('Fetched  Alarm Comments alarm:', alarm);
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments('your-alarm-id', 'your-comment-id').subscribe(result => {
  console.log('Operation completed:', result);
});
```
