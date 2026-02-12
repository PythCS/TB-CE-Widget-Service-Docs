# ThingsBoard Widget API Documentation

This repository contains comprehensive documentation for all ThingsBoard widget services available in custom widget development and custom actions.

## Quick Start

### Using Services in Widgets

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Device:', device);
});
```

### Using Services in Custom Actions

```javascript
const $injector = widgetContext.$scope.$injector;
const deviceService = $injector.get(widgetContext.servicesMap.get('deviceService'));

deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Device:', device);
});
```

## Documentation Structure

- **[DOCUMENTATION.md](DOCUMENTATION.md)** - Complete reference for all services in one file
- **[docs/](docs/)** - Individual service documentation files

## Available Services

The documentation covers all major ThingsBoard services including:

- **Entity Management**: Device, Asset, Customer, Entity View services
- **Data Operations**: Attribute, Alarm, Event services  
- **Platform Features**: Dashboard, Widget, Rule Chain services
- **Administration**: User, Tenant, Notification services
- **Edge Computing**: Edge service for distributed deployments
- **Security**: OAuth2, API Identifier, Two Factor Authentication services
- **Content Management**: Image, Resource, OTA Package services

## Key Features

- **Copy-paste ready examples** - Every method includes working code snippets
- **Human-readable formatting** - Clear variable names and console output
- **Both injection patterns** - Standard injection and direct context access where available
- **Comprehensive coverage** - All service methods documented with realistic examples
- **PageLink examples** - Proper pagination handling for large datasets

## Notes

- Services use RxJS Observables - always use `.subscribe()` to get results
- Some methods behave differently in Community vs Professional Edition (marked with CE VERSION tag)
- Always handle errors appropriately in production code
- Use PageLink objects for methods that return large datasets to avoid server overload

## Contributing

This documentation follows the ThingsBoard community style guide for developer-friendly API documentation. For questions or improvements, refer to the ThingsBoard GitHub repository.