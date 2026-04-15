# Audit Log

```javascript
// Service name: auditLog
// File: audit-log.service.ts
```

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLog = $injector.get(self.ctx.servicesMap.get('auditLog'));
```

### **1. getAuditLogs**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLog.getAuditLogs(pageLink).subscribe(auditLog => {
  console.log('Audit Log:', auditLog);
});
```

### **2. getAuditLogsByCustomerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLog.getAuditLogsByCustomerId(pageLink).subscribe(auditLog => {
  console.log('Audit Log:', auditLog);
});
```

### **3. getAuditLogsByUserId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLog.getAuditLogsByUserId(pageLink).subscribe(user => {
  console.log('User:', user);
});
```

### **4. getAuditLogsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLog.getAuditLogsByEntityId(pageLink).subscribe(auditLog => {
  console.log('Audit Log:', auditLog);
});
```
