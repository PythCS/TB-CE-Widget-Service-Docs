# ThingsBoard Widget Service Docs

Auto-generated documentation for ThingsBoard CE frontend widget services.

**Generated:** 2026-04-15  
**Source:** ThingsBoard CE 3.7.x (`widget-services` package)

## What's in here

- `DOCUMENTATION.md` — Full reference for all services (single file, ~1500+ lines)
- `docs/` — Individual pages per service

## Services covered

- AdminService
- AiModelService
- AlarmCommentService
- AlarmRulesService
- AlarmService
- ApiKeyService
- AssetProfileService
- AssetService
- AttributeService
- AuditLogService
- CalculatedFieldsService
- ComponentDescriptorService
- CustomerService
- DashboardService
- DeviceProfileService
- DeviceService
- DomainService
- EdgeService
- EntitiesVersionControlService
- EntityRelationService
- EntityService
- EntityViewService
- EventService
- GitHubService
- ImageService
- MobileAppService
- MobileApplicationService
- NotificationService
- OAuth2Service
- OtaPackageService
- QueueService
- ResourceService
- RuleChainService
- TenantProfileService
- TenantService
- TrendzSettingsService
- TwoFactorAuthenticationService
- UiSettingsService
- UsageInfoService
- UserService
- UserSettingsService
- WidgetService


## Quick start

```javascript
// Inject any service
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Make an API call
deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Device:', device);
});
```

## Contributing

Docs are auto-generated from the ThingsBoard source. Do not edit these files directly — modify the generator instead.
