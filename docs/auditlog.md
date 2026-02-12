### **AUDIT LOG SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditlogservice = $injector.get(self.ctx.servicesMap.get('auditlogservice'));

```

**1. getAuditLogs**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditlogservice.getAuditLogs(pageLink).subscribe(auditlogs => {
  console.log('Auditlogs:', auditlogs);
});
```

**2. getAuditLogsByCustomerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditlogservice.getAuditLogsByCustomerId(pageLink, 'your-customer-id').subscribe(auditlogsbycustomerid => {
  console.log('Auditlogsbycustomerid:', auditlogsbycustomerid);
});
```

**3. getAuditLogsByUserId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditlogservice.getAuditLogsByUserId(pageLink, 'your-user-id').subscribe(auditlogsbyuserid => {
  console.log('Auditlogsbyuserid:', auditlogsbyuserid);
});
```

**4. getAuditLogsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditlogservice.getAuditLogsByEntityId(pageLink, 'your-entity-id').subscribe(auditlogsbyentityid => {
  console.log('Auditlogsbyentityid:', auditlogsbyentityid);
});
```

