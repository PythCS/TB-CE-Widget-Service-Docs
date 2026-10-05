# ALARM COMMENT SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

**1. saveAlarmComment**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
const alarmId = 'your-alarm-id';
const alarmComment = {  // AlarmComment object
  // ... set the fields you need
};
alarmCommentService.saveAlarmComment(alarmId, alarmComment).subscribe(savedAlarmComment => {
  console.log('Saved Alarm Comment:', savedAlarmComment);
});
```

**2. getAlarmComments**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmCommentService.getAlarmComments(alarmId, pageLink).subscribe(alarmComments => {
  console.log('List of Alarm Comments:', alarmComments);
});
```

**3. deleteAlarmComments**

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
const alarmId = 'your-alarm-id';
const commentId = 'your-comment-id';
alarmCommentService.deleteAlarmComments(alarmId, commentId).subscribe(result => {
  console.log('Delete Alarm Comments result:', result);
});
```
