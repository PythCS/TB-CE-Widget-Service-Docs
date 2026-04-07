# NotificationService

### **NOTIFICATIONSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
notificationService.getNotifications(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(notification => {
  console.log('Notifications:', notification);
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead('your-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. createNotificationRequest**

```javascript
notificationService.createNotificationRequest({ /* your notification */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest('your-entitytype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById('your-id', { /* your config */ }).subscribe(notificationrequestbyid => {
  console.log('Notification Request By Id:', notificationrequestbyid);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods({ /* your config */ }).subscribe(availabledeliverymethod => {
  console.log('Available Delivery Methods:', availabledeliverymethod);
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**10. getNotificationRequestPreview**

```javascript
notificationService.getNotificationRequestPreview({ /* your notification */ }, { /* your config */ }).subscribe(notificationrequestpreview => {
  console.log('Notification Request Preview:', notificationrequestpreview);
});
```

**11. getNotificationRequests**

```javascript
notificationService.getNotificationRequests(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(notificationrequet => {
  console.log('Notification Requests:', notificationrequet);
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings({ /* your config */ }).subscribe(notificationetting => {
  console.log('Notification Settings:', notificationetting);
});
```

**13. saveNotificationSettings**

```javascript
notificationService.saveNotificationSettings({ /* your notificationSettings */ }, { /* your config */ }).subscribe(savedNotificationSettings => {
  console.log('Saved NotificationSettings:', savedNotificationSettings);
});
```

**14. listSlackConversations**

```javascript
notificationService.listSlackConversations('your-type', 'your-token', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. saveNotificationRule**

```javascript
notificationService.saveNotificationRule({ /* your notificationRule */ }, { /* your config */ }).subscribe(savedNotificationRule => {
  console.log('Saved NotificationRule:', savedNotificationRule);
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById('your-id', { /* your config */ }).subscribe(notificationrulebyid => {
  console.log('Notification Rule By Id:', notificationrulebyid);
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**18. getNotificationRules**

```javascript
notificationService.getNotificationRules(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(notificationrule => {
  console.log('Notification Rules:', notificationrule);
});
```

**19. saveNotificationTarget**

```javascript
notificationService.saveNotificationTarget({ /* your notificationTarget */ }, { /* your config */ }).subscribe(savedNotificationTarget => {
  console.log('Saved NotificationTarget:', savedNotificationTarget);
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById('your-id', { /* your config */ }).subscribe(notificationtargetbyid => {
  console.log('Notification Target By Id:', notificationtargetbyid);
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds(['id1', 'id2'], { /* your config */ }).subscribe(notificationtargetbyid => {
  console.log('Notification Targets By Ids:', notificationtargetbyid);
});
```

**23. getNotificationTargets**

```javascript
notificationService.getNotificationTargets(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(notificationtarget => {
  console.log('Notification Targets:', notificationtarget);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
notificationService.getRecipientsForNotificationTargetConfig({ /* your notificationTarget */ }, self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(recipientsfornotificationtargetconfig => {
  console.log('Recipients For Notification Target Config:', recipientsfornotificationtargetconfig);
});
```

**25. saveNotificationTemplate**

```javascript
notificationService.saveNotificationTemplate({ /* your notificationTarget */ }, { /* your config */ }).subscribe(savedNotificationTemplate => {
  console.log('Saved NotificationTemplate:', savedNotificationTemplate);
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById('your-id', { /* your config */ }).subscribe(notificationtemplatebyid => {
  console.log('Notification Template By Id:', notificationtemplatebyid);
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**28. getNotificationTemplates**

```javascript
notificationService.getNotificationTemplates(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-notificationtypes', { /* your config */ }).subscribe(notificationtemplate => {
  console.log('Notification Templates:', notificationtemplate);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings({ /* your config */ }).subscribe(notificationueretting => {
  console.log('Notification User Settings:', notificationueretting);
});
```

**30. saveNotificationUserSettings**

```javascript
notificationService.saveNotificationUserSettings({ /* your settings */ }, { /* your config */ }).subscribe(savedNotificationUserSettings => {
  console.log('Saved NotificationUserSettings:', savedNotificationUserSettings);
});
```
