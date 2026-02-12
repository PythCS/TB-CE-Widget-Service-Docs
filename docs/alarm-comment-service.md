# ALARM COMMENT

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

## Methods

### saveAlarmComment

```javascript
const alarmId = 'your-alarm-id';
const alarmComment = {
  // your alarmComment object
};

alarmCommentService.saveAlarmComment(alarmId, alarmComment).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### getAlarmComments

```javascript
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

alarmCommentService.getAlarmComments(alarmId, pageLink).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### deleteAlarmComments

```javascript
const alarmId = 'your-alarm-id';
const commentId = 'your-comment-id';

alarmCommentService.deleteAlarmComments(alarmId, commentId).subscribe(result => {
  console.log('Result:', result);
});
```

