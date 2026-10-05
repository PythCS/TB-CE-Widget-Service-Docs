# TB-CE-Widget-Service-Docs

Human-friendly, copy-paste-ready documentation for all ThingsBoard CE widget services.

- **[DOCUMENTATION.md](DOCUMENTATION.md)** — all services in one file
- **docs/** — one file per service

Every method comes with a working JavaScript example you can paste directly into your
widget code or custom action. Generated from the ThingsBoard CE source
(parsed at commit `79bb2b0a659d`).

## Usage

In widget development:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));
userService.getUsers(pageLink).subscribe(users => {
  console.log('List of Users:', users);
});
```

In custom actions, use `widgetContext` instead of `self.ctx`.
