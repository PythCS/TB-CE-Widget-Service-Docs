# AuditLogService

### **AUDITLOGSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
```

**1. getAuditLogs**

```javascript
auditLogService.getAuditLogs(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(auditlog => {
  console.log('Audit Logs:', auditlog);
});
```

**2. getAuditLogsByCustomerId**

```javascript
auditLogService.getAuditLogsByCustomerId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(auditlogsbycustomerid => {
  console.log('Audit Logs By Customer Id:', auditlogsbycustomerid);
});
```

**3. getAuditLogsByUserId**

```javascript
auditLogService.getAuditLogsByUserId('your-user-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(auditlogsbyuserid => {
  console.log('Audit Logs By User Id:', auditlogsbyuserid);
});
```

**4. getAuditLogsByEntityId**

```javascript
auditLogService.getAuditLogsByEntityId('your-entity-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(auditlogsbyentityid => {
  console.log('Audit Logs By Entity Id:', auditlogsbyentityid);
});
```
