# Notification

```javascript
// Service name: notification
// File: notification.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notification = $injector.get(self.ctx.servicesMap.get('notification'));
```

### **1. getNotifications**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notification.getNotifications(pageLink).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

### **2. deleteNotification**

```javascript
notification.deleteNotification(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **3. markNotificationAsRead**

```javascript
notification.markNotificationAsRead(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **4. markAllNotificationsAsRead**

```javascript
notification.markAllNotificationsAsRead().subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **5. createNotificationRequest**

```javascript
notification.createNotificationRequest(notification).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **6. sendEntitiesLimitIncreaseRequest**

```javascript
notification.sendEntitiesLimitIncreaseRequest(entityType).subscribe(sendEntitiesLimitIncreaseRequest => {
  console.log('Send Entities Limit Increase Request:', sendEntitiesLimitIncreaseRequest);
});
```

### **7. getNotificationRequestById**

```javascript
notification.getNotificationRequestById(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **8. getAvailableDeliveryMethods**

```javascript
notification.getAvailableDeliveryMethods().subscribe(availableDeliveryMethods => {
  console.log('Available Delivery Methods:', availableDeliveryMethods);
});
```

### **9. deleteNotificationRequest**

```javascript
notification.deleteNotificationRequest(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **10. getNotificationRequestPreview**

```javascript
notification.getNotificationRequestPreview(notification).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **11. getNotificationRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notification.getNotificationRequests(pageLink).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

### **12. getNotificationSettings**

```javascript
notification.getNotificationSettings().subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **13. saveNotificationSettings**

```javascript
notification.saveNotificationSettings(notificationSettings).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **14. listSlackConversations**

```javascript
notification.listSlackConversations(type).subscribe(listSlackConversations => {
  console.log('List Slack Conversations:', listSlackConversations);
});
```

### **15. saveNotificationRule**

```javascript
notification.saveNotificationRule(notificationRule).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **16. getNotificationRuleById**

```javascript
notification.getNotificationRuleById(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **17. deleteNotificationRule**

```javascript
notification.deleteNotificationRule(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **18. getNotificationRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notification.getNotificationRules(pageLink).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

### **19. saveNotificationTarget**

```javascript
notification.saveNotificationTarget(notificationTarget).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **20. getNotificationTargetById**

```javascript
notification.getNotificationTargetById(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **21. deleteNotificationTarget**

```javascript
notification.deleteNotificationTarget(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **22. getNotificationTargetsByIds**

```javascript
notification.getNotificationTargetsByIds(ids).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

### **23. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notification.getNotificationTargets(pageLink).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

### **24. getRecipientsForNotificationTargetConfig**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notification.getRecipientsForNotificationTargetConfig(pageLink).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

### **25. saveNotificationTemplate**

```javascript
notification.saveNotificationTemplate(notificationTarget).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **26. getNotificationTemplateById**

```javascript
notification.getNotificationTemplateById(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **27. deleteNotificationTemplate**

```javascript
notification.deleteNotificationTemplate(id).subscribe(notification => {
  console.log('Notification:', notification);
});
```

### **28. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notification.getNotificationTemplates(pageLink).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

### **29. getNotificationUserSettings**

```javascript
notification.getNotificationUserSettings().subscribe(user => {
  console.log('User:', user);
});
```

### **30. saveNotificationUserSettings**

```javascript
notification.saveNotificationUserSettings(settings).subscribe(user => {
  console.log('User:', user);
});
```
