### **NOTIFICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationservice = $injector.get(self.ctx.servicesMap.get('notificationservice'));

```

**1. getNotifications**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationservice.getNotifications(pageLink).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
notificationservice.deleteNotification('your-id-id').subscribe(deletenotification => {
  console.log('Deletenotification:', deletenotification);
});
```

**3. markNotificationAsRead**

```javascript
notificationservice.markNotificationAsRead('your-id-id').subscribe(marknotificationasread => {
  console.log('Marknotificationasread:', marknotificationasread);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationservice.markAllNotificationsAsRead().subscribe(markallnotificationsasread => {
  console.log('Markallnotificationsasread:', markallnotificationsasread);
});
```

**5. createNotificationRequest**

```javascript
notificationservice.createNotificationRequest(notification).subscribe(createnotificationrequest => {
  console.log('Createnotificationrequest:', createnotificationrequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationservice.sendEntitiesLimitIncreaseRequest(entityType).subscribe(sendentitieslimitincreaserequest => {
  console.log('Sendentitieslimitincreaserequest:', sendentitieslimitincreaserequest);
});
```

**7. getNotificationRequestById**

```javascript
notificationservice.getNotificationRequestById('your-id-id').subscribe(notificationrequestbyid => {
  console.log('Notificationrequestbyid:', notificationrequestbyid);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationservice.getAvailableDeliveryMethods().subscribe(availabledeliverymethods => {
  console.log('Availabledeliverymethods:', availabledeliverymethods);
});
```

**9. deleteNotificationRequest**

```javascript
notificationservice.deleteNotificationRequest('your-id-id').subscribe(deletenotificationrequest => {
  console.log('Deletenotificationrequest:', deletenotificationrequest);
});
```

**10. getNotificationRequestPreview**

```javascript
notificationservice.getNotificationRequestPreview(notification).subscribe(notificationrequestpreview => {
  console.log('Notificationrequestpreview:', notificationrequestpreview);
});
```

**11. getNotificationRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationservice.getNotificationRequests(pageLink).subscribe(notificationrequests => {
  console.log('Notificationrequests:', notificationrequests);
});
```

**12. getNotificationSettings**

```javascript
notificationservice.getNotificationSettings().subscribe(notificationsettings => {
  console.log('Notificationsettings:', notificationsettings);
});
```

**13. saveNotificationSettings**

```javascript
notificationservice.saveNotificationSettings(notificationSettings).subscribe(savenotificationsettings => {
  console.log('Savenotificationsettings:', savenotificationsettings);
});
```

**14. listSlackConversations**

```javascript
notificationservice.listSlackConversations(type, 'your-token').subscribe(listslackconversations => {
  console.log('Listslackconversations:', listslackconversations);
});
```

**15. saveNotificationRule**

```javascript
notificationservice.saveNotificationRule(notificationRule).subscribe(savenotificationrule => {
  console.log('Savenotificationrule:', savenotificationrule);
});
```

**16. getNotificationRuleById**

```javascript
notificationservice.getNotificationRuleById('your-id-id').subscribe(notificationrulebyid => {
  console.log('Notificationrulebyid:', notificationrulebyid);
});
```

**17. deleteNotificationRule**

```javascript
notificationservice.deleteNotificationRule('your-id-id').subscribe(deletenotificationrule => {
  console.log('Deletenotificationrule:', deletenotificationrule);
});
```

**18. getNotificationRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationservice.getNotificationRules(pageLink).subscribe(notificationrules => {
  console.log('Notificationrules:', notificationrules);
});
```

**19. saveNotificationTarget**

```javascript
notificationservice.saveNotificationTarget(notificationTarget).subscribe(savenotificationtar => {
  console.log('Savenotificationtar:', savenotificationtar);
});
```

**20. getNotificationTargetById**

```javascript
notificationservice.getNotificationTargetById('your-id-id').subscribe(notificationtarbyid => {
  console.log('Notificationtarbyid:', notificationtarbyid);
});
```

**21. deleteNotificationTarget**

```javascript
notificationservice.deleteNotificationTarget('your-id-id').subscribe(deletenotificationtar => {
  console.log('Deletenotificationtar:', deletenotificationtar);
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationservice.getNotificationTargetsByIds('your-ids-id').subscribe(notificationtarsbyids => {
  console.log('Notificationtarsbyids:', notificationtarsbyids);
});
```

**23. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationservice.getNotificationTargets(pageLink).subscribe(notificationtars => {
  console.log('Notificationtars:', notificationtars);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationservice.getRecipientsForNotificationTargetConfig(pageLink, notificationTarget).subscribe(recipientsfornotificationtarconfig => {
  console.log('Recipientsfornotificationtarconfig:', recipientsfornotificationtarconfig);
});
```

**25. saveNotificationTemplate**

```javascript
notificationservice.saveNotificationTemplate(notificationTarget).subscribe(savenotificationtemplate => {
  console.log('Savenotificationtemplate:', savenotificationtemplate);
});
```

**26. getNotificationTemplateById**

```javascript
notificationservice.getNotificationTemplateById('your-id-id').subscribe(notificationtemplatebyid => {
  console.log('Notificationtemplatebyid:', notificationtemplatebyid);
});
```

**27. deleteNotificationTemplate**

```javascript
notificationservice.deleteNotificationTemplate('your-id-id').subscribe(deletenotificationtemplate => {
  console.log('Deletenotificationtemplate:', deletenotificationtemplate);
});
```

**28. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationservice.getNotificationTemplates(pageLink).subscribe(notificationtemplates => {
  console.log('Notificationtemplates:', notificationtemplates);
});
```

**29. getNotificationUserSettings**

```javascript
notificationservice.getNotificationUserSettings().subscribe(notificationusersettings => {
  console.log('Notificationusersettings:', notificationusersettings);
});
```

**30. saveNotificationUserSettings**

```javascript
notificationservice.saveNotificationUserSettings(settings).subscribe(savenotificationusersettings => {
  console.log('Savenotificationusersettings:', savenotificationusersettings);
});
```

