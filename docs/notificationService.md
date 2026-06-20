# NOTIFICATION SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **NOTIFICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotifications(pageLink).subscribe(notifications => {
  console.log('Get Notifications: notifications');
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification('your-id').subscribe(result => {
  console.log('Delete Notification: result');
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead('your-id').subscribe(result => {
  console.log('Mark Notification As Read: result');
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('Mark All Notifications As Read:result');
});
```

**5. createNotificationRequest**

```javascript
const notification = notification;
notificationService.createNotificationRequest(notification).subscribe(result => {
  console.log('Create Notification Request: result');
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest('type').subscribe(result => {
  console.log('Send Entities Limit Increase Request:result');
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById('your-id').subscribe(notificationRequestById => {
  console.log('Get Notification Request By Id:notificationRequestById');
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(availabledeliverymethods => {
  console.log('Get Available Delivery Methods:availabledeliverymethods');
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest('your-id').subscribe(result => {
  console.log('Delete Notification Request: result');
});
```

**10. getNotificationRequestPreview**

```javascript
const notification = notification;
notificationService.getNotificationRequestPreview(notification).subscribe(notificationRequestPreview => {
  console.log('Get Notification Request Preview:notificationRequestPreview');
});
```

**11. getNotificationRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRequests(pageLink).subscribe(notificationrequests => {
  console.log('Get Notification Requests: notificationrequests');
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(notificationsettings => {
  console.log('Get Notification Settings: notificationsettings');
});
```

**13. saveNotificationSettings**

```javascript
const notificationSettings = notificationSettings;
notificationService.saveNotificationSettings(notificationSettings).subscribe(savedNotificationSettings => {
  console.log('Save Notification Settings: savedNotificationSettings');
});
```

**14. listSlackConversations**

```javascript
const token = token;
notificationService.listSlackConversations('type', token).subscribe(results => {
  console.log('List Slack Conversations: results');
});
```

**15. saveNotificationRule**

```javascript
const notificationRule = notificationRule;
notificationService.saveNotificationRule(notificationRule).subscribe(savedNotificationRule => {
  console.log('Save Notification Rule: savedNotificationRule');
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById('your-id').subscribe(notificationRuleById => {
  console.log('Get Notification Rule By Id: notificationRuleById');
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule('your-id').subscribe(result => {
  console.log('Delete Notification Rule: result');
});
```

**18. getNotificationRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRules(pageLink).subscribe(notificationrules => {
  console.log('Get Notification Rules: notificationrules');
});
```

**19. saveNotificationTarget**

```javascript
const notificationTarget = notificationTarget;
notificationService.saveNotificationTarget(notificationTarget).subscribe(savedNotificationTarget => {
  console.log('Save Notification Target: savedNotificationTarget');
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById('your-id').subscribe(notificationTargetById => {
  console.log('Get Notification Target By Id: notificationTargetById');
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget('your-id').subscribe(result => {
  console.log('Delete Notification Target: result');
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds('your-id').subscribe(notificationtargetsbyids => {
  console.log('Get Notification Targets By Ids:notificationtargetsbyids');
});
```

**23. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTargets(pageLink, 'type').subscribe(notificationtargets => {
  console.log('Get Notification Targets: notificationtargets');
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const notificationTarget = notificationTarget;
notificationService.getRecipientsForNotificationTargetConfig(notificationTarget, pageLink).subscribe(recipientsForNotificationTargetConfig => {
  console.log('Get Recipients For Notification Target Config:recipientsForNotificationTargetConfig');
});
```

**25. saveNotificationTemplate**

```javascript
const notificationTarget = notificationTarget;
notificationService.saveNotificationTemplate(notificationTarget).subscribe(savedNotificationTemplate => {
  console.log('Save Notification Template: savedNotificationTemplate');
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById('your-id').subscribe(notificationTemplateById => {
  console.log('Get Notification Template By Id:notificationTemplateById');
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate('your-id').subscribe(result => {
  console.log('Delete Notification Template: result');
});
```

**28. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTemplates(pageLink, 'type').subscribe(notificationtemplates => {
  console.log('Get Notification Templates: notificationtemplates');
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(notificationusersettings => {
  console.log('Get Notification User Settings:notificationusersettings');
});
```

**30. saveNotificationUserSettings**

```javascript
const settings = settings;
notificationService.saveNotificationUserSettings(settings).subscribe(savedNotificationUserSettings => {
  console.log('Save Notification User Settings:savedNotificationUserSettings');
});
```
