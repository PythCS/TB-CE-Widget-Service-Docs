# ThingsBoard CE Widget Service Documentation

Auto-generated documentation for all ThingsBoard CE widget services.

Generated from TB CE commit `79bb2b0a659d` on 2026-06-19.

42 services, 453 methods documented.

## Usage

See [DOCUMENTATION.md](DOCUMENTATION.md) for the full documentation with all services.

Individual service docs are available in [docs/](docs/).

## Quick Start

In widget development:
```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));
```

In custom actions:
```javascript
const $injector = widgetContext.$scope.$injector;
const deviceService = $injector.get(widgetContext.servicesMap.get('deviceService'));
```
