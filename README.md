# ThingsBoard Widget Services API Documentation

Complete reference for all widget services available in ThingsBoard Community Edition (CE).

## Overview

This documentation provides copy-paste ready examples for using ThingsBoard widget services in your custom widgets and custom actions.

## Quick Start

### Injecting a Service

In custom actions you use `widgetContext` — in widget development you use `self.ctx`. Same services, different context variable.

**Custom Action:**
```javascript
const $injector = widgetContext.$scope.$injector;
const deviceService = $injector.get(widgetContext.servicesMap.get('deviceService'));
```

**Widget Development:**
```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Or use direct context access (when available):
const deviceService = self.ctx.deviceService;
```

### Using a Service

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getTenantDeviceInfos(pageLink, type).subscribe(devices => {
  console.log('Devices:', devices);
});
```

## Full Documentation

See [DOCUMENTATION.md](DOCUMENTATION.md) for the complete API reference with all services and methods.

## CE vs PE Versions

This documentation covers **ThingsBoard Community Edition (CE)**. Some services and methods may behave differently or be unavailable in ThingsBoard Professional Edition (PE). The `getUsers` method in the User Service is known to behave differently between CE and PE versions.

## Available Services

- AI Model Service
- Alarm Comment Service
- Alarm Rules Service
- Alarm Service
- API Key Service
- Asset Profile Service
- Asset Service
- Attribute Service
- Audit Log Service
- Calculated Fields Service
- Component Descriptor Service
- Customer Service
- Dashboard Service
- Device Profile Service
- Device Service
- Domain Service
- Edge Service
- Entities Version Control Service
- Entity Relation Service
- Entity Service
- Entity View Service
- Event Service
- GitHub Service
- Image Service
- Mobile App Service
- Mobile Application Service
- Notification Service
- OAuth2 Service
- OTA Package Service
- Queue Service
- Resource Service
- Rule Chain Service
- Tenant Profile Service
- Tenant Service
- Trendz Settings Service
- Two Factor Authentication Service
- UI Settings Service
- Usage Info Service
- User Service
- User Settings Service
- Widget Service
