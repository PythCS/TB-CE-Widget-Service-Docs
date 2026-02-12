# NOTIFICATION

Notification and messaging system.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

## Methods

### getNotifications

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

notificationService.getNotifications(pageLink).subscribe(result => {
  console.log('Notifications:', result);
});
```

### deleteNotification

```javascript
const id = 'your--id';

notificationService.deleteNotification(id).subscribe(result => {
  console.log('Result:', result);
});
```

### markNotificationAsRead

```javascript
const id = 'your--id';

notificationService.markNotificationAsRead(id).subscribe(result => {
  console.log('Result:', result);
});
```

### markAllNotificationsAsRead

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('Result:', result);
});
```

### createNotificationRequest

```javascript
const notification = {
  // your notification object
};

notificationService.createNotificationRequest(notification).subscribe(result => {
  console.log('createNotificationRequest:', result);
});
```

### sendEntitiesLimitIncreaseRequest

```javascript
const entityType = {
  // your entityType object
};

notificationService.sendEntitiesLimitIncreaseRequest(entityType).subscribe(result => {
  console.log('Result:', result);
});
```

### getNotificationRequestById

```javascript
const id = 'your--id';

notificationService.getNotificationRequestById(id).subscribe(result => {
  console.log('NotificationRequestById:', result);
});
```

### getAvailableDeliveryMethods

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(result => {
  console.log('AvailableDeliveryMethods:', result);
});
```

### deleteNotificationRequest

```javascript
const id = 'your--id';

notificationService.deleteNotificationRequest(id).subscribe(result => {
  console.log('Result:', result);
});
```

### getNotificationRequestPreview

```javascript
const notification = {
  // your notification object
};

notificationService.getNotificationRequestPreview(notification).subscribe(result => {
  console.log('NotificationRequestPreview:', result);
});
```

### getNotificationRequests

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

notificationService.getNotificationRequests(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

### getNotificationSettings

```javascript
notificationService.getNotificationSettings().subscribe(settings => {
  console.log('Settings:', settings);
});
```

### saveNotificationSettings

```javascript
const notificationSettings = {
  // your notificationSettings object
};

notificationService.saveNotificationSettings(notificationSettings).subscribe(settings => {
  console.log('Settings:', settings);
});
```

### listSlackConversations

```javascript
const type = {
  // your type object
};
const token = 'your-token';

notificationService.listSlackConversations(type, token).subscribe(result => {
  console.log('listSlackConversations:', result);
});
```

### saveNotificationRule

```javascript
const notificationRule = {
  // your notificationRule object
};

notificationService.saveNotificationRule(notificationRule).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getNotificationRuleById

```javascript
const id = 'your--id';

notificationService.getNotificationRuleById(id).subscribe(result => {
  console.log('NotificationRuleById:', result);
});
```

### deleteNotificationRule

```javascript
const id = 'your--id';

notificationService.deleteNotificationRule(id).subscribe(result => {
  console.log('Result:', result);
});
```

### getNotificationRules

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

notificationService.getNotificationRules(pageLink).subscribe(result => {
  console.log('NotificationRules:', result);
});
```

### saveNotificationTarget

```javascript
const notificationTarget = {
  // your notificationTarget object
};

notificationService.saveNotificationTarget(notificationTarget).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getNotificationTargetById

```javascript
const id = 'your--id';

notificationService.getNotificationTargetById(id).subscribe(result => {
  console.log('NotificationTarById:', result);
});
```

### deleteNotificationTarget

```javascript
const id = 'your--id';

notificationService.deleteNotificationTarget(id).subscribe(result => {
  console.log('Result:', result);
});
```

### getNotificationTargetsByIds

```javascript
const ids = 'your-s-id';

notificationService.getNotificationTargetsByIds(ids).subscribe(result => {
  console.log('NotificationTarsByIds:', result);
});
```

### getNotificationTargets

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = {
  // your type object
};

notificationService.getNotificationTargets(pageLink, type).subscribe(result => {
  console.log('NotificationTars:', result);
});
```

### getRecipientsForNotificationTargetConfig

```javascript
const notificationTarget = {
  // your notificationTarget object
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

notificationService.getRecipientsForNotificationTargetConfig(notificationTarget, pageLink).subscribe(result => {
  console.log('RecipientsForNotificationTarConfig:', result);
});
```

### saveNotificationTemplate

```javascript
const notificationTarget = {
  // your notificationTarget object
};

notificationService.saveNotificationTemplate(notificationTarget).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getNotificationTemplateById

```javascript
const id = 'your--id';

notificationService.getNotificationTemplateById(id).subscribe(result => {
  console.log('NotificationTemplateById:', result);
});
```

### deleteNotificationTemplate

```javascript
const id = 'your--id';

notificationService.deleteNotificationTemplate(id).subscribe(result => {
  console.log('Result:', result);
});
```

### getNotificationTemplates

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const notificationTypes = {
  // your notificationTypes object
};

notificationService.getNotificationTemplates(pageLink, notificationTypes).subscribe(result => {
  console.log('NotificationTemplates:', result);
});
```

### getNotificationUserSettings

```javascript
notificationService.getNotificationUserSettings().subscribe(settings => {
  console.log('Settings:', settings);
});
```

### saveNotificationUserSettings

```javascript
const settings = {
  // your settings object
};

notificationService.saveNotificationUserSettings(settings).subscribe(settings => {
  console.log('Settings:', settings);
});
```

