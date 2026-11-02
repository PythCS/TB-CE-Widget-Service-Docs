# ALARM COMMENT SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

**1. saveAlarmComment**

```javascript
alarmCommentService.saveAlarmComment('your-alarm-id', 'your-alarmcomment-value').subscribe(alarmComment => {
  console.log('Save Alarm Comment:', alarmComment);
});
```

**2. getAlarmComments**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmCommentService.getAlarmComments('your-alarm-id', pageLink).subscribe(alarmComments => {
  console.log('Get Alarm Comments:', alarmComments);
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments('your-alarm-id', 'your-comment-id').subscribe(result => {
  console.log('Delete Alarm Comments:', result);
});
```
