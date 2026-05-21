# NotificationService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('NotificationService'));
```

**1. getNotifications**

```javascript
notificationService.getNotifications(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Notifications result:', result);
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('Operation completed:', result);
});
```

**5. createNotificationRequest**

```javascript
notificationService.createNotificationRequest('your-notification-value').subscribe(result => {
  console.log('create Notification Request result:', result);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest('your-entitytype-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById('your--id').subscribe(result => {
  console.log('Fetched  Notification Request By Id result:', result);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(result => {
  console.log('Fetched  Available Delivery Methods result:', result);
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**10. getNotificationRequestPreview**

```javascript
notificationService.getNotificationRequestPreview('your-notification-value').subscribe(result => {
  console.log('Fetched  Notification Request Preview result:', result);
});
```

**11. getNotificationRequests**

```javascript
notificationService.getNotificationRequests(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Notification Requests result:', result);
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(settings => {
  console.log('Fetched  Notification Settings settings:', settings);
});
```

**13. saveNotificationSettings**

```javascript
notificationService.saveNotificationSettings('your-notificationsettings-value').subscribe(settings => {
  console.log('Saved  Notification Settings settings:', settings);
});
```

**14. listSlackConversations**

```javascript
notificationService.listSlackConversations('your-type-value', 'your-access-token').subscribe(result => {
  console.log('list Slack Conversations result:', result);
});
```

**15. saveNotificationRule**

```javascript
notificationService.saveNotificationRule('your-notificationrule-value').subscribe(rule => {
  console.log('Saved  Notification Rule rule:', rule);
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById('your--id').subscribe(rule => {
  console.log('Fetched  Notification Rule By Id rule:', rule);
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**18. getNotificationRules**

```javascript
notificationService.getNotificationRules(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(rule => {
  console.log('Fetched  Notification Rules rule:', rule);
});
```

**19. saveNotificationTarget**

```javascript
notificationService.saveNotificationTarget('your-notificationtarget-value').subscribe(result => {
  console.log('Saved  Notification Tar Fetched result:', result);
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById('your--id').subscribe(result => {
  console.log('Fetched  Notification Tar Fetched  By Id result:', result);
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds('your-ids-value').subscribe(result => {
  console.log('Fetched  Notification Tar Fetched s By Ids result:', result);
});
```

**23. getNotificationTargets**

```javascript
notificationService.getNotificationTargets(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(result => {
  console.log('Fetched  Notification Tar Fetched s result:', result);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
notificationService.getRecipientsForNotificationTargetConfig('your-notificationtarget-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Recipients For Notification Tar Fetched  Config result:', result);
});
```

**25. saveNotificationTemplate**

```javascript
notificationService.saveNotificationTemplate('your-notificationtarget-value').subscribe(result => {
  console.log('Saved  Notification Template result:', result);
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById('your--id').subscribe(result => {
  console.log('Fetched  Notification Template By Id result:', result);
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**28. getNotificationTemplates**

```javascript
notificationService.getNotificationTemplates(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-notificationtypes-value').subscribe(result => {
  console.log('Fetched  Notification Templates result:', result);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(users => {
  console.log('Fetched  Notification User Settings users:', users);
});
```

**30. saveNotificationUserSettings**

```javascript
notificationService.saveNotificationUserSettings('your-settings-value').subscribe(users => {
  console.log('Saved  Notification User Settings users:', users);
});
```
