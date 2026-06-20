# ALARM COMMENT SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **ALARM COMMENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

**1. saveAlarmComment**

```javascript
const alarmComment = alarmComment;
alarmCommentService.saveAlarmComment('your-alarm-id', alarmComment).subscribe(savedAlarmComment => {
  console.log('Save Alarm Comment: savedAlarmComment');
});
```

**2. getAlarmComments**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmCommentService.getAlarmComments('your-alarm-id', pageLink).subscribe(alarmcomments => {
  console.log('Get Alarm Comments: alarmcomments');
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments('your-alarm-id', 'your-comment-id').subscribe(result => {
  console.log('Delete Alarm Comments: result');
});
```
