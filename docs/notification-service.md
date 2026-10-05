# NOTIFICATION SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotifications(pageLink).subscribe(notifications => {
  console.log('List of Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotification(id).subscribe(result => {
  console.log('Delete Notification result:', result);
});
```

**3. markNotificationAsRead**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.markNotificationAsRead(id).subscribe(markNotificationAsRead => {
  console.log('Mark Notification As Read:', markNotificationAsRead);
});
```

**4. markAllNotificationsAsRead**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
notificationService.markAllNotificationsAsRead().subscribe(markAllNotificationsAsRead => {
  console.log('Mark All Notifications As Read:', markAllNotificationsAsRead);
});
```

**5. createNotificationRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notification = {  // NotificationRequest object
  // ... set the fields you need
};
notificationService.createNotificationRequest(notification).subscribe(createNotificationRequest => {
  console.log('Create Notification Request:', createNotificationRequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
notificationService.sendEntitiesLimitIncreaseRequest(entityType).subscribe(sendEntitiesLimitIncreaseRequest => {
  console.log('Send Entities Limit Increase Request:', sendEntitiesLimitIncreaseRequest);
});
```

**7. sendAddonAccessRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const addonType = {  // AddonType object
  // ... set the fields you need
};
notificationService.sendAddonAccessRequest(addonType).subscribe(sendAddonAccessRequest => {
  console.log('Send Addon Access Request:', sendAddonAccessRequest);
});
```

**8. sendPlanUpgradeRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const planName = 'your-plan-name';
notificationService.sendPlanUpgradeRequest(planName).subscribe(sendPlanUpgradeRequest => {
  console.log('Send Plan Upgrade Request:', sendPlanUpgradeRequest);
});
```

**9. getNotificationRequestById**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.getNotificationRequestById(id).subscribe(notificationRequestBy => {
  console.log('Get Notification Request By Id:', notificationRequestBy);
});
```

**10. getAvailableDeliveryMethods**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
notificationService.getAvailableDeliveryMethods().subscribe(availableDeliveryMethods => {
  console.log('List of Available Delivery Methods:', availableDeliveryMethods);
});
```

**11. deleteNotificationRequest**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotificationRequest(id).subscribe(result => {
  console.log('Delete Notification Request result:', result);
});
```

**12. getNotificationRequestPreview**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notification = {  // NotificationRequest object
  // ... set the fields you need
};
notificationService.getNotificationRequestPreview(notification).subscribe(notificationRequestPreview => {
  console.log('Get Notification Request Preview:', notificationRequestPreview);
});
```

**13. getNotificationRequests**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRequests(pageLink).subscribe(notificationRequests => {
  console.log('List of Notification Requests:', notificationRequests);
});
```

**14. getNotificationSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
notificationService.getNotificationSettings().subscribe(notificationSettings => {
  console.log('Get Notification Settings:', notificationSettings);
});
```

**15. saveNotificationSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationSettings = {  // NotificationSettings object
  // ... set the fields you need
};
notificationService.saveNotificationSettings(notificationSettings).subscribe(savedNotificationSettings => {
  console.log('Saved Notification Settings:', savedNotificationSettings);
});
```

**16. listSlackConversations**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const type = {  // SlackChanelType object
  // ... set the fields you need
};
const token = 'your-token';
notificationService.listSlackConversations(type, token).subscribe(listSlackConversations => {
  console.log('List Slack Conversations:', listSlackConversations);
});
```

**17. saveNotificationRule**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationRule = {  // NotificationRule object
  // ... set the fields you need
};
notificationService.saveNotificationRule(notificationRule).subscribe(savedNotificationRule => {
  console.log('Saved Notification Rule:', savedNotificationRule);
});
```

**18. getNotificationRuleById**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.getNotificationRuleById(id).subscribe(notificationRuleBy => {
  console.log('Get Notification Rule By Id:', notificationRuleBy);
});
```

**19. deleteNotificationRule**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotificationRule(id).subscribe(result => {
  console.log('Delete Notification Rule result:', result);
});
```

**20. getNotificationRules**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRules(pageLink).subscribe(notificationRules => {
  console.log('List of Notification Rules:', notificationRules);
});
```

**21. saveNotificationTarget**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationTarget = {  // NotificationTarget object
  // ... set the fields you need
};
notificationService.saveNotificationTarget(notificationTarget).subscribe(savedNotificationTarget => {
  console.log('Saved Notification Target:', savedNotificationTarget);
});
```

**22. getNotificationTargetById**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.getNotificationTargetById(id).subscribe(notificationTargetBy => {
  console.log('Get Notification Target By Id:', notificationTargetBy);
});
```

**23. deleteNotificationTarget**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotificationTarget(id).subscribe(result => {
  console.log('Delete Notification Target result:', result);
});
```

**24. getNotificationTargetsByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const ids = [];  // e.g. array of ids values
notificationService.getNotificationTargetsByIds(ids).subscribe(notificationTargetsBys => {
  console.log('List of Notification Targets By Ids:', notificationTargetsBys);
});
```

**25. getNotificationTargets**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {  // NotificationType object
  // ... set the fields you need
};
notificationService.getNotificationTargets(pageLink, type).subscribe(notificationTargets => {
  console.log('List of Notification Targets:', notificationTargets);
});
```

**26. getRecipientsForNotificationTargetConfig**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationTarget = {  // NotificationTarget object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getRecipientsForNotificationTargetConfig(notificationTarget, pageLink).subscribe(recipientsForNotificationTargetConfigs => {
  console.log('List of Recipients For Notification Target Configs:', recipientsForNotificationTargetConfigs);
});
```

**27. saveNotificationTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const notificationTarget = {  // NotificationTemplate object
  // ... set the fields you need
};
notificationService.saveNotificationTemplate(notificationTarget).subscribe(savedNotificationTemplate => {
  console.log('Saved Notification Template:', savedNotificationTemplate);
});
```

**28. getNotificationTemplateById**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.getNotificationTemplateById(id).subscribe(notificationTemplateBy => {
  console.log('Get Notification Template By Id:', notificationTemplateBy);
});
```

**29. deleteNotificationTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const id = 'your-id';
notificationService.deleteNotificationTemplate(id).subscribe(result => {
  console.log('Delete Notification Template result:', result);
});
```

**30. getNotificationTemplates**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const notificationTypes = {  // NotificationType object
  // ... set the fields you need
};
notificationService.getNotificationTemplates(pageLink, notificationTypes).subscribe(notificationTemplates => {
  console.log('List of Notification Templates:', notificationTemplates);
});
```

**31. getNotificationUserSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
notificationService.getNotificationUserSettings().subscribe(notificationUserSettings => {
  console.log('Get Notification User Settings:', notificationUserSettings);
});
```

**32. saveNotificationUserSettings**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const settings = {  // NotificationUserSettings object
  // ... set the fields you need
};
notificationService.saveNotificationUserSettings(settings).subscribe(savedNotificationUserSettings => {
  console.log('Saved Notification User Settings:', savedNotificationUserSettings);
});
```

**33. sendAddonAccessError**

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
const addonType = {  // AddonType object
  // ... set the fields you need
};
notificationService.sendAddonAccessError(addonType).subscribe(sendAddonAccessError => {
  console.log('Send Addon Access Error:', sendAddonAccessError);
});
```
