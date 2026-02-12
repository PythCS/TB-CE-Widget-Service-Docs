# AUDIT LOG

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
```

## Methods

### getAuditLogs

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

auditLogService.getAuditLogs(pageLink).subscribe(result => {
  console.log('AuditLogs:', result);
});
```

### getAuditLogsByCustomerId

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

auditLogService.getAuditLogsByCustomerId(customerId, pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### getAuditLogsByUserId

```javascript
const userId = 'your-user-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

auditLogService.getAuditLogsByUserId(userId, pageLink).subscribe(result => {
  console.log('Result:', result);
});
```

### getAuditLogsByEntityId

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-entity-id' };
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

auditLogService.getAuditLogsByEntityId(entityId, pageLink).subscribe(result => {
  console.log('AuditLogsByEntityId:', result);
});
```

