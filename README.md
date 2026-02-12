# ThingsBoard Widget Services Documentation

Complete reference for ThingsBoard Community Edition widget services - 41 services with 459+ methods, all with working code examples.

## What This Is

This documentation covers **every widget service** available in ThingsBoard CE for custom widget development and custom actions. Each method includes copy-paste ready code examples.

## Quick Start

### In Custom Widget Development

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Device:', device);
});
```

### In Custom Actions

```javascript
const $injector = widgetContext.$scope.$injector;
const deviceService = $injector.get(widgetContext.servicesMap.get('deviceService'));

deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Device:', device);
});
```

### Direct Context Access (when available)

Some services provide direct access through the context:

```javascript
// Instead of injecting, use directly
const deviceService = self.ctx.deviceService;
const assetService = self.ctx.assetService;
const attributeService = self.ctx.attributeService;
```

## Service Categories

### **Core Entity Services**
- **DeviceService** - Manage devices, credentials, RPC commands
- **AssetService** - Asset management and relationships  
- **CustomerService** - Customer operations
- **UserService** - User management and authentication
- **DashboardService** - Dashboard operations and sharing

### **Data Services**
- **AttributeService** - Read/write entity attributes and timeseries
- **EntityService** - Generic entity operations and queries
- **EntityRelationService** - Entity relationships and graph queries

### **Rule Engine & Processing**
- **RuleChainService** - Rule chain management and metadata
- **AlarmService** - Alarm creation, management, and querying
- **EventService** - System and debug events

### **Device Management**
- **DeviceProfileService** - Device profiles and LwM2M objects
- **OtaPackageService** - Over-the-air update packages
- **CredentialService** - Device credentials management

### **Asset Management** 
- **AssetProfileService** - Asset profile configurations
- **EntityViewService** - Entity view management

### **UI & Widgets**
- **WidgetService** - Widget bundles and types
- **ImageService** - Image resources and management
- **ResourceService** - JavaScript and other resources

### **Administration**
- **TenantService** - Tenant management
- **AuditLogService** - System audit logging  
- **NotificationService** - Notification rules and delivery
- **QueueService** - Queue management and statistics

## Key Concepts

### PageLinks
Most list methods use PageLink for pagination:

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'ASC');
```

- **10**: Page size (results per page)
- **0**: Page number (starting from 0) 
- **'searchText'**: Filter text (or empty string)
- **'sortProperty'**: Field to sort by
- **'ASC'**: Sort order (ASC or DESC)

### Entity IDs
Entities are referenced with type and ID:

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
```

Common entity types: `DEVICE`, `ASSET`, `CUSTOMER`, `USER`, `DASHBOARD`, etc.

### Observables
All async methods return RxJS Observables - use `.subscribe()`:

```javascript
service.getEntity(id).subscribe(entity => {
  // Handle result
  console.log('Entity:', entity);
});
```

## Documentation Structure

- **[DOCUMENTATION.md](DOCUMENTATION.md)** - Complete reference with all 459+ methods
- **[docs/](docs/)** - Individual service documentation files
- **[README.md](README.md)** - This overview file

## Finding What You Need

1. **Browse by service** in the main [DOCUMENTATION.md](DOCUMENTATION.md)
2. **Search by method name** using Ctrl+F
3. **Check individual service docs** in the [docs/](docs/) folder
4. **Look at the table of contents** for quick navigation

## Best Practices

### Error Handling
Always handle errors in your subscriptions:

```javascript
service.getEntity(id).subscribe(
  entity => {
    console.log('Success:', entity);
  },
  error => {
    console.error('Error:', error);
  }
);
```

### Variable Naming
Use descriptive variable names in callbacks:

```javascript
// Good
userService.getUsers(pageLink).subscribe(users => {
  console.log('Users:', users);
});

// Bad  
userService.getUsers(pageLink).subscribe(getUsersResult => {
  console.log('getUsersResult:', getUsersResult);
});
```

### Memory Management
Unsubscribe from long-running subscriptions to prevent memory leaks:

```javascript
const subscription = service.getData().subscribe(data => {
  // Handle data
});

// Later, when done:
subscription.unsubscribe();
```

## Version Compatibility

This documentation is for **ThingsBoard Community Edition**. Some methods may behave differently in Professional Edition (PE).

Methods marked with **(!!CE VERSION!!)** have known differences between CE and PE versions.

## Contributing

Found an error or missing method? This documentation is auto-generated from the ThingsBoard source code. Issues should be reported to the ThingsBoard project or the documentation maintainer.

## Source

Generated from ThingsBoard CE repository analysis. See the [original GitHub issue](https://github.com/thingsboard/thingsboard/issues/9899) that started this documentation style.

---

**Start exploring:** Check out the complete [DOCUMENTATION.md](DOCUMENTATION.md) file for all services and methods with working examples.