# NOTIFICATION SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotifications(pageLink).subscribe(notifications => {
  console.log('Get Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification('your--id').subscribe(result => {
  console.log('Delete Notification:', result);
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead('your--id').subscribe(result => {
  console.log('Mark Notification As Read:', result);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('Mark All Notifications As Read:', result);
});
```

**5. createNotificationRequest**

```javascript
notificationService.createNotificationRequest('your-notification-value').subscribe(notificationRequest => {
  console.log('Create Notification Request:', notificationRequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest('your-entitytype-value').subscribe(result => {
  console.log('Send Entities Limit Increase Request:', result);
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById('your--id').subscribe(notificationRequestById => {
  console.log('Get Notification Request By Id:', notificationRequestById);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(availableDeliveryMethods => {
  console.log('Get Available Delivery Methods:', availableDeliveryMethods);
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest('your--id').subscribe(result => {
  console.log('Delete Notification Request:', result);
});
```

**10. getNotificationRequestPreview**

```javascript
notificationService.getNotificationRequestPreview('your-notification-value').subscribe(notificationRequestPreview => {
  console.log('Get Notification Request Preview:', notificationRequestPreview);
});
```

**11. getNotificationRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRequests(pageLink).subscribe(notificationRequests => {
  console.log('Get Notification Requests:', notificationRequests);
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(notificationSettings => {
  console.log('Get Notification Settings:', notificationSettings);
});
```

**13. saveNotificationSettings**

```javascript
notificationService.saveNotificationSettings('your-notificationsettings-value').subscribe(notificationSettings => {
  console.log('Save Notification Settings:', notificationSettings);
});
```

**14. listSlackConversations**

```javascript
notificationService.listSlackConversations('your-type-value', 'your-access-token').subscribe(slackConversations => {
  console.log('List Slack Conversations:', slackConversations);
});
```

**15. saveNotificationRule**

```javascript
notificationService.saveNotificationRule('your-notificationrule-value').subscribe(notificationRule => {
  console.log('Save Notification Rule:', notificationRule);
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById('your--id').subscribe(notificationRuleById => {
  console.log('Get Notification Rule By Id:', notificationRuleById);
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule('your--id').subscribe(result => {
  console.log('Delete Notification Rule:', result);
});
```

**18. getNotificationRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRules(pageLink).subscribe(rules => {
  console.log('Get Notification Rules:', rules);
});
```

**19. saveNotificationTarget**

```javascript
notificationService.saveNotificationTarget('your-notificationtarget-value').subscribe(notificationTarget => {
  console.log('Save Notification Target:', notificationTarget);
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById('your--id').subscribe(notificationTargetById => {
  console.log('Get Notification Target By Id:', notificationTargetById);
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget('your--id').subscribe(result => {
  console.log('Delete Notification Target:', result);
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds('your-ids-value').subscribe(notificationTargetsByIds => {
  console.log('Get Notification Targets By Ids:', notificationTargetsByIds);
});
```

**23. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTargets(pageLink, 'your-type-value').subscribe(targets => {
  console.log('Get Notification Targets:', targets);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getRecipientsForNotificationTargetConfig('your-notificationtarget-value', pageLink).subscribe(recipientsForNotificationTargetConfig => {
  console.log('Get Recipients For Notification Target Config:', recipientsForNotificationTargetConfig);
});
```

**25. saveNotificationTemplate**

```javascript
notificationService.saveNotificationTemplate('your-notificationtarget-value').subscribe(notificationTemplate => {
  console.log('Save Notification Template:', notificationTemplate);
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById('your--id').subscribe(notificationTemplateById => {
  console.log('Get Notification Template By Id:', notificationTemplateById);
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate('your--id').subscribe(result => {
  console.log('Delete Notification Template:', result);
});
```

**28. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTemplates(pageLink, 'your-notificationtypes-value').subscribe(templates => {
  console.log('Get Notification Templates:', templates);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(notificationUserSettings => {
  console.log('Get Notification User Settings:', notificationUserSettings);
});
```

**30. saveNotificationUserSettings**

```javascript
notificationService.saveNotificationUserSettings('your-settings-value').subscribe(notificationUserSettings => {
  console.log('Save Notification User Settings:', notificationUserSettings);
});
```
