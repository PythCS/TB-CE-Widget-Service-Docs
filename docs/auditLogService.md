# AUDIT LOG SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **AUDIT LOG SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
```

**1. getAuditLogs**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogs(pageLink).subscribe(auditlogs => {
  console.log('Get Audit Logs: auditlogs');
});
```

**2. getAuditLogsByCustomerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByCustomerId('your-customer-id', pageLink).subscribe(auditLogsByCustomerId => {
  console.log('Get Audit Logs By Customer Id: auditLogsByCustomerId');
});
```

**3. getAuditLogsByUserId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByUserId('your-user-id', pageLink).subscribe(auditLogsByUserId => {
  console.log('Get Audit Logs By User Id: auditLogsByUserId');
});
```

**4. getAuditLogsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByEntityId('your-entity-id', pageLink).subscribe(auditLogsByEntityId => {
  console.log('Get Audit Logs By Entity Id: auditLogsByEntityId');
});
```
