# Alarm Comment

```javascript
// Service name: alarmComment
// File: alarm-comment.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmComment = $injector.get(self.ctx.servicesMap.get('alarmComment'));
```

### **1. saveAlarmComment**

```javascript
alarmComment.saveAlarmComment(alarmId, alarmComment).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

### **2. getAlarmComments**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmComment.getAlarmComments(pageLink).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

### **3. deleteAlarmComments**

```javascript
alarmComment.deleteAlarmComments(alarmId, commentId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```
