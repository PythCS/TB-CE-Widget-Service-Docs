# NotificationService

**Source:** `notification.service.ts`  
**Direct context access:** `none`

---

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```
**1. getNotifications**

```javascript
notificationService.getNotifications(self.ctx.pageLink(10, 0, null, null, null)).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification(/* id */ null).subscribe(notification => {
  console.log('Notification:', notification);
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead(/* id */ null).subscribe(markNotificationAsRead => {
  console.log('markNotificationAsRead:', markNotificationAsRead);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(markAllNotificationsAsRead => {
  console.log('markAllNotificationsAsRead:', markAllNotificationsAsRead);
});
```

**5. createNotificationRequest**

```javascript
notificationService.createNotificationRequest(/* notification */ null).subscribe(notificationRequest => {
  console.log('createNotificationRequest:', notificationRequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest(null).subscribe(entitiesLimitIncreaseRequest => {
  console.log('sendEntitiesLimitIncreaseRequest:', entitiesLimitIncreaseRequest);
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById(/* id */ null).subscribe(notificationRequestById => {
  console.log('NotificationRequestById:', notificationRequestById);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(availableDeliveryMethods => {
  console.log('AvailableDeliveryMethods:', availableDeliveryMethods);
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest(/* id */ null).subscribe(notificationRequest => {
  console.log('NotificationRequest:', notificationRequest);
});
```

**10. getNotificationRequestPreview**

```javascript
notificationService.getNotificationRequestPreview(/* notification */ null).subscribe(notificationRequestPreview => {
  console.log('NotificationRequestPreview:', notificationRequestPreview);
});
```

**11. getNotificationRequests**

```javascript
notificationService.getNotificationRequests(self.ctx.pageLink(10, 0, null, null, null)).subscribe(notificationRequests => {
  console.log('NotificationRequests:', notificationRequests);
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(notificationSettings => {
  console.log('NotificationSettings:', notificationSettings);
});
```

**13. saveNotificationSettings**

```javascript
notificationService.saveNotificationSettings(/* notificationSettings */ null).subscribe(notificationSettings => {
  console.log('NotificationSettings:', notificationSettings);
});
```

**14. listSlackConversations**

```javascript
notificationService.listSlackConversations(null, /* token */ null).subscribe(slConversations => {
  console.log('listSlackConversations:', slConversations);
});
```

**15. saveNotificationRule**

```javascript
notificationService.saveNotificationRule(/* notificationRule */ null).subscribe(notificationRule => {
  console.log('NotificationRule:', notificationRule);
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById(/* id */ null).subscribe(notificationRuleById => {
  console.log('NotificationRuleById:', notificationRuleById);
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule(/* id */ null).subscribe(notificationRule => {
  console.log('NotificationRule:', notificationRule);
});
```

**18. getNotificationRules**

```javascript
notificationService.getNotificationRules(self.ctx.pageLink(10, 0, null, null, null)).subscribe(notificationRules => {
  console.log('NotificationRules:', notificationRules);
});
```

**19. saveNotificationTarget**

```javascript
notificationService.saveNotificationTarget(/* notificationTarget */ null).subscribe(notificationTar => {
  console.log('NotificationTarget:', notificationTar);
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById(/* id */ null).subscribe(notificationTarById => {
  console.log('NotificationTarget ById:', notificationTarById);
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget(/* id */ null).subscribe(notificationTar => {
  console.log('NotificationTarget:', notificationTar);
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds(['id1', 'id2']).subscribe(notificationTarsByIds => {
  console.log('NotificationTarget sByIds:', notificationTarsByIds);
});
```

**23. getNotificationTargets**

```javascript
notificationService.getNotificationTargets(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(notificationTars => {
  console.log('NotificationTarget s:', notificationTars);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
notificationService.getRecipientsForNotificationTargetConfig(/* notificationTarget */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(recipientsForNotificationTarConfig => {
  console.log('RecipientsForNotificationTarget Config:', recipientsForNotificationTarConfig);
});
```

**25. saveNotificationTemplate**

```javascript
notificationService.saveNotificationTemplate(/* notificationTarget */ null).subscribe(notificationTemplate => {
  console.log('NotificationTemplate:', notificationTemplate);
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById(/* id */ null).subscribe(notificationTemplateById => {
  console.log('NotificationTemplateById:', notificationTemplateById);
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate(/* id */ null).subscribe(notificationTemplate => {
  console.log('NotificationTemplate:', notificationTemplate);
});
```

**28. getNotificationTemplates**

```javascript
notificationService.getNotificationTemplates(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(notificationTemplates => {
  console.log('NotificationTemplates:', notificationTemplates);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(notificationUserSettings => {
  console.log('NotificationUserSettings:', notificationUserSettings);
});
```

**30. saveNotificationUserSettings**

```javascript
notificationService.saveNotificationUserSettings(/* settings */ null).subscribe(notificationUserSettings => {
  console.log('NotificationUserSettings:', notificationUserSettings);
});
```

---

*Auto-generated by ThingsBoardDocUpdater*