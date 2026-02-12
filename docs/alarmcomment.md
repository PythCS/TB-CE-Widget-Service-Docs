### **ALARM COMMENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmcommentservice = $injector.get(self.ctx.servicesMap.get('alarmcommentservice'));

```

**1. saveAlarmComment**

```javascript
alarmcommentservice.saveAlarmComment('your-alarm-id', alarmComment).subscribe(savealarmcomment => {
  console.log('Savealarmcomment:', savealarmcomment);
});
```

**2. getAlarmComments**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmcommentservice.getAlarmComments(pageLink, 'your-alarm-id').subscribe(alarmcomments => {
  console.log('Alarmcomments:', alarmcomments);
});
```

**3. deleteAlarmComments**

```javascript
alarmcommentservice.deleteAlarmComments('your-alarm-id', 'your-comment-id').subscribe(deletealarmcomments => {
  console.log('Deletealarmcomments:', deletealarmcomments);
});
```

