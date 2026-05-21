# AuditLogService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('AuditLogService'));
```

**1. getAuditLogs**

```javascript
auditLogService.getAuditLogs(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Audit Logs result:', result);
});
```

**2. getAuditLogsByCustomerId**

```javascript
auditLogService.getAuditLogsByCustomerId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Audit Logs By Customer Id result:', result);
});
```

**3. getAuditLogsByUserId**

```javascript
auditLogService.getAuditLogsByUserId('your-user-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  Audit Logs By User Id users:', users);
});
```

**4. getAuditLogsByEntityId**

```javascript
auditLogService.getAuditLogsByEntityId('your-entity-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(entity => {
  console.log('Fetched  Audit Logs By Entity Id entity:', entity);
});
```
