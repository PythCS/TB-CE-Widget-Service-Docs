# ThingsBoard CE Widget Services Documentation

*Generated from ThingsBoard CE source code.*

---

## Using Services in Widgets/Custom Actions

Using services in custom actions is slightly different than in custom widget development.

In custom actions you use `widgetContext` — in widget development you use `self.ctx`. Same services, different context variable.

**Example Custom Action:**

```javascript
const $injector = widgetContext.$scope.$injector;
const userService = $injector.get(widgetContext.servicesMap.get('userService'));
```

**Example Widget Development:**

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));
```

---

## Using Page Links

PageLinks are pagination helpers that prevent overloading the ThingsBoard server when you have large datasets. They specify page size and offset.

Create a page link using `self.ctx.pageLink`:

```javascript
// self.ctx.pageLink(pageSize, pageNumber, searchText, sortProperty, sortOrder)
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
```

- `pageSize` — results per page
- `pageNumber` — zero-based page index
- `searchText` — optional text filter
- `sortProperty` — field to sort by (e.g. 'createdTime')
- `sortOrder` — 'ASC' or 'DESC'

---

## Table of Contents

- [AdminService](#admin)
- [AiModelService](#aimodel)
- [AlarmCommentService](#alarmcomment)
- [AlarmRulesService](#alarmrules)
- [AlarmService](#alarm)
- [ApiKeyService](#apikey)
- [AssetProfileService](#assetprofile)
- [AssetService](#asset)
- [AttributeService](#attribute)
- [AuditLogService](#auditlog)
- [CalculatedFieldsService](#calculatedfields)
- [ComponentDescriptorService](#componentdescriptor)
- [CustomerService](#customer)
- [DashboardService](#dashboard)
- [DeviceProfileService](#deviceprofile)
- [DeviceService](#device)
- [DomainService](#domain)
- [EdgeService](#edge)
- [EntitiesVersionControlService](#entitiesversioncontrol)
- [EntityRelationService](#entityrelation)
- [EntityViewService](#entityview)
- [EntityService](#entity)
- [EventService](#event)
- [GitHubService](#github)
- [ImageService](#image)
- [MobileAppService](#mobileapp)
- [MobileApplicationService](#mobileapplication)
- [NotificationService](#notification)
- [OAuth2Service](#oauth2)
- [OtaPackageService](#otapackage)
- [QueueService](#queue)
- [ResourceService](#resource)
- [RuleChainService](#rulechain)
- [TenantProfileService](#tenantprofile)
- [TenantService](#tenant)
- [TrendzSettingsService](#trendzsettings)
- [TwoFactorAuthenticationService](#twofactorauthentication)
- [UiSettingsService](#uisettings)
- [UsageInfoService](#usageinfo)
- [UserSettingsService](#usersettings)
- [UserService](#user)
- [WidgetService](#widget)

---

### **AdminService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('AdminService'));
```

**1. sendTestMail**

```javascript
adminService.sendTestMail('your-adminsettings-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**2. sendTestSms**

```javascript
adminService.sendTestSms('your-testsmsrequest-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings().subscribe(settings => {
  console.log('Fetched  Security Settings settings:', settings);
});
```

**4. saveSecuritySettings**

```javascript
adminService.saveSecuritySettings('your-securitysettings-value').subscribe(settings => {
  console.log('Saved  Security Settings settings:', settings);
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings().subscribe(settings => {
  console.log('Fetched  Jwt Settings settings:', settings);
});
```

**6. saveJwtSettings**

```javascript
adminService.saveJwtSettings('your-jwtsettings-value').subscribe(settings => {
  console.log('Saved  Jwt Settings settings:', settings);
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(settings => {
  console.log('Fetched  Repository Settings settings:', settings);
});
```

**8. saveRepositorySettings**

```javascript
adminService.saveRepositorySettings('your-repositorysettings-value').subscribe(settings => {
  console.log('Saved  Repository Settings settings:', settings);
});
```

**9. checkRepositoryAccess**

```javascript
adminService.checkRepositoryAccess('your-repositorysettings-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(settings => {
  console.log('Fetched  Repository Settings Info settings:', settings);
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(settings => {
  console.log('Fetched  Auto Commit Settings settings:', settings);
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(settings => {
  console.log('auto Commit Settings Exists settings:', settings);
});
```

**13. saveAutoCommitSettings**

```javascript
adminService.saveAutoCommitSettings('your-autocommitsettings-value').subscribe(settings => {
  console.log('Saved  Auto Commit Settings settings:', settings);
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(result => {
  console.log('check Updates result:', result);
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(info => {
  console.log('Fetched  Features Info info:', info);
});
```

**16. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(result => {
  console.log('Fetched  Login Processing Url result:', result);
});
```

**17. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(result => {
  console.log('generate Access Token result:', result);
});
```

**18. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(result => {
  console.log('Fetched  Mail Config Template result:', result);
});
```

---

### **AiModelService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('AiModelService'));
```

**1. saveAiModel**

```javascript
aiModelService.saveAiModel('your-aimodel-value').subscribe(result => {
  console.log('Saved  Ai Model result:', result);
});
```

**2. getAiModels**

```javascript
aiModelService.getAiModels(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Ai Models result:', result);
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById('your-aimodel-id').subscribe(result => {
  console.log('Fetched  Ai Model By Id result:', result);
});
```

**4. checkConnectivity**

```javascript
aiModelService.checkConnectivity('your-aimodelwithusermsg-value').subscribe(result => {
  console.log('check Connectivity result:', result);
});
```

---

### **AlarmCommentService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('AlarmCommentService'));
```

**1. saveAlarmComment**

```javascript
alarmCommentService.saveAlarmComment('your-alarm-id', 'your-alarmcomment-value').subscribe(alarm => {
  console.log('Saved  Alarm Comment alarm:', alarm);
});
```

**2. getAlarmComments**

```javascript
alarmCommentService.getAlarmComments('your-alarm-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(alarm => {
  console.log('Fetched  Alarm Comments alarm:', alarm);
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments('your-alarm-id', 'your-comment-id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

---

### **AlarmRulesService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('AlarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
alarmRulesService.getAlarmRuleById('your-alarmrule-id').subscribe(alarm => {
  console.log('Fetched  Alarm Rule By Id alarm:', alarm);
});
```

**2. saveAlarmRule**

```javascript
alarmRulesService.saveAlarmRule('your-alarmrule-value').subscribe(alarm => {
  console.log('Saved  Alarm Rule alarm:', alarm);
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule('your-alarmrule-id').subscribe(alarm => {
  console.log('Deleted  Alarm Rule alarm:', alarm);
});
```

**4. getAlarmRules**

```javascript
alarmRulesService.getAlarmRules(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-query-value').subscribe(alarm => {
  console.log('Fetched  Alarm Rules alarm:', alarm);
});
```

**5. getAlarmRulesByEntityId**

```javascript
alarmRulesService.getAlarmRulesByEntityId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(alarm => {
  console.log('Fetched  Alarm Rules By Entity Id alarm:', alarm);
});
```

**6. testScript**

```javascript
alarmRulesService.testScript('your-inputparams-value').subscribe(result => {
  console.log('test Script result:', result);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent('your--id').subscribe(alarm => {
  console.log('Fetched  Latest Alarm Rule Debug Event alarm:', alarm);
});
```

**8. getAlarmRuleNames**

```javascript
alarmRulesService.getAlarmRuleNames(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(alarm => {
  console.log('Fetched  Alarm Rule Names alarm:', alarm);
});
```

---

### **AlarmService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('AlarmService'));
```

**1. getAlarm**

```javascript
alarmService.getAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Fetched  Alarm alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo('your-alarm-id').subscribe(alarm => {
  console.log('Fetched  Alarm Info alarm:', alarm);
});
```

**3. saveAlarm**

```javascript
alarmService.saveAlarm('your-alarm-value').subscribe(alarm => {
  console.log('Saved  Alarm alarm:', alarm);
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm('your-alarm-id').subscribe(alarm => {
  console.log('ack Alarm alarm:', alarm);
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm('your-alarm-id').subscribe(alarm => {
  console.log('clear Alarm alarm:', alarm);
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm('your-alarm-id', 'your-assignee-id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm('your-alarm-id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Deleted  Alarm alarm:', alarm);
});
```

**9. getAlarms**

```javascript
alarmService.getAlarms('your-query-value').subscribe(alarm => {
  console.log('Fetched  Alarms alarm:', alarm);
});
```

**10. getAlarmsV2**

```javascript
alarmService.getAlarmsV2('your-query-value').subscribe(alarm => {
  console.log('Fetched  Alarms V2 alarm:', alarm);
});
```

**11. getAllAlarms**

```javascript
alarmService.getAllAlarms('your-query-value').subscribe(alarm => {
  console.log('Fetched  All Alarms alarm:', alarm);
});
```

**12. getAllAlarmsV2**

```javascript
alarmService.getAllAlarmsV2('your-query-value').subscribe(alarm => {
  console.log('Fetched  All Alarms V2 alarm:', alarm);
});
```

**13. getHighestAlarmSeverity**

```javascript
alarmService.getHighestAlarmSeverity('your-entity-id', 'your-alarmsearchstatus-value', 'your-alarmstatus-value').subscribe(alarm => {
  console.log('Fetched  Highest Alarm Severity alarm:', alarm);
});
```

**14. getAlarmTypes**

```javascript
alarmService.getAlarmTypes(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(alarm => {
  console.log('Fetched  Alarm Types alarm:', alarm);
});
```

---

### **ApiKeyService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('ApiKeyService'));
```

**1. saveApiKey**

```javascript
apiKeyService.saveApiKey('your-api-key').subscribe(result => {
  console.log('Saved  Api Key result:', result);
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**3. updateApiKeyDescription**

```javascript
apiKeyService.updateApiKeyDescription('your--id', 'your-description-value').subscribe(result => {
  console.log('update Api Key Description result:', result);
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey('your--id', true).subscribe(result => {
  console.log('enable Api Key result:', result);
});
```

**5. getUserApiKeys**

```javascript
apiKeyService.getUserApiKeys('your-user-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  User Api Keys users:', users);
});
```

---

### **AssetProfileService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('AssetProfileService'));
```

**1. getAssetProfiles**

```javascript
assetProfileService.getAssetProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(profile => {
  console.log('Fetched  Asset Profiles profile:', profile);
});
```

**2. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds('your-assetprofileids-value').subscribe(profile => {
  console.log('Fetched  Asset Profiles By Ids profile:', profile);
});
```

**3. getAssetProfile**

```javascript
assetProfileService.getAssetProfile('your-assetprofile-id').subscribe(profile => {
  console.log('Fetched  Asset Profile profile:', profile);
});
```

**4. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile('your-assetprofile-id').subscribe(profile => {
  console.log('export Asset Profile profile:', profile);
});
```

**5. saveAssetProfile**

```javascript
assetProfileService.saveAssetProfile('your-assetprofile-value').subscribe(profile => {
  console.log('Saved  Asset Profile profile:', profile);
});
```

**6. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile('your-assetprofile-id').subscribe(profile => {
  console.log('set Default Asset Profile profile:', profile);
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(profile => {
  console.log('Fetched  Default Asset Profile Info profile:', profile);
});
```

**8. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo('your-assetprofile-id').subscribe(profile => {
  console.log('Fetched  Asset Profile Info profile:', profile);
});
```

**9. getAssetProfileInfos**

```javascript
assetProfileService.getAssetProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(profile => {
  console.log('Fetched  Asset Profile Infos profile:', profile);
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames('your-activeonly-value').subscribe(profile => {
  console.log('Fetched  Asset Profile Names profile:', profile);
});
```

---

### **AssetService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('AssetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

**1. getTenantAssetInfos**

```javascript
assetService.getTenantAssetInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(tenant => {
  console.log('Fetched  Tenant Asset Infos tenant:', tenant);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
assetService.getTenantAssetInfosByAssetProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-assetprofile-id').subscribe(tenant => {
  console.log('Fetched  Tenant Asset Infos By Asset Profile Id tenant:', tenant);
});
```

**3. getCustomerAssetInfos**

```javascript
assetService.getCustomerAssetInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(info => {
  console.log('Fetched  Customer Asset Infos info:', info);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
assetService.getCustomerAssetInfosByAssetProfileId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-assetprofile-id').subscribe(profile => {
  console.log('Fetched  Customer Asset Infos By Asset Profile Id profile:', profile);
});
```

**5. getAsset**

```javascript
assetService.getAsset('your-asset-id').subscribe(result => {
  console.log('Fetched  Asset result:', result);
});
```

**6. getAssets**

```javascript
assetService.getAssets('your-assetids-value').subscribe(result => {
  console.log('Fetched  Assets result:', result);
});
```

**7. getAssetInfo**

```javascript
assetService.getAssetInfo('your-asset-id').subscribe(info => {
  console.log('Fetched  Asset Info info:', info);
});
```

**8. saveAsset**

```javascript
assetService.saveAsset('your-asset-value').subscribe(result => {
  console.log('Saved  Asset result:', result);
});
```

**9. getAssetTypes**

```javascript
assetService.getAssetTypes().subscribe(result => {
  console.log('Fetched  Asset Types result:', result);
});
```

**10. makeAssetPublic**

```javascript
assetService.makeAssetPublic('your-asset-id').subscribe(result => {
  console.log('make Asset Public result:', result);
});
```

**11. assignAssetToCustomer**

```javascript
assetService.assignAssetToCustomer('your-customer-id', 'your-asset-id').subscribe(result => {
  console.log('assign Asset To Customer result:', result);
});
```

**12. findByQuery**

```javascript
assetService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**13. findByName**

```javascript
assetService.findByName('your-assetname-value').subscribe(result => {
  console.log('find By Name result:', result);
});
```

**14. assignAssetToEdge**

```javascript
assetService.assignAssetToEdge('your-edge-id', 'your-asset-id').subscribe(result => {
  console.log('assign Asset To Edge result:', result);
});
```

**15. getEdgeAssets**

```javascript
assetService.getEdgeAssets('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(result => {
  console.log('Fetched  Edge Assets result:', result);
});
```

**16. bulkImportAssets**

```javascript
assetService.bulkImportAssets('your-entitiesdata-value').subscribe(result => {
  console.log('bulk Import Assets result:', result);
});
```

---

### **AttributeService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('AttributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
attributeService.getEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-api-key').subscribe(entity => {
  console.log('Fetched  Entity Attributes entity:', entity);
});
```

**2. deleteEntityAttributes**

```javascript
attributeService.deleteEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entity => {
  console.log('Deleted  Entity Attributes entity:', entity);
});
```

**3. deleteEntityTimeseries**

```javascript
attributeService.deleteEntityTimeseries('your-entity-id', 'your-timeseries-value', 0, 0).subscribe(entity => {
  console.log('Deleted  Entity Timeseries entity:', entity);
});
```

**4. saveEntityAttributes**

```javascript
attributeService.saveEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entity => {
  console.log('Saved  Entity Attributes entity:', entity);
});
```

**5. saveEntityTimeseries**

```javascript
attributeService.saveEntityTimeseries('your-entity-id', 'your-timeseriesscope-value', 'your-timeseries-value').subscribe(entity => {
  console.log('Saved  Entity Timeseries entity:', entity);
});
```

**6. getEntityTimeseries**

```javascript
attributeService.getEntityTimeseries('your-entity-id', 'your-api-key', 0, 0, 'your-limit-value', 'your-agg-value', 0, 'your-orderby-value', 'your-usestrictdatatypes-value').subscribe(entity => {
  console.log('Fetched  Entity Timeseries entity:', entity);
});
```

**7. getEntityTimeseriesLatest**

```javascript
attributeService.getEntityTimeseriesLatest('your-entity-id', 'your-api-key').subscribe(entity => {
  console.log('Fetched  Entity Timeseries Latest entity:', entity);
});
```

---

### **AuditLogService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('AuditLogService'));
```

**1. getAuditLogs**

```javascript
auditLogService.getAuditLogs(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Audit Logs result:', result);
});
```

**2. getAuditLogsByCustomerId**

```javascript
auditLogService.getAuditLogsByCustomerId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Audit Logs By Customer Id result:', result);
});
```

**3. getAuditLogsByUserId**

```javascript
auditLogService.getAuditLogsByUserId('your-user-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  Audit Logs By User Id users:', users);
});
```

**4. getAuditLogsByEntityId**

```javascript
auditLogService.getAuditLogsByEntityId('your-entity-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(entity => {
  console.log('Fetched  Audit Logs By Entity Id entity:', entity);
});
```

---

### **CalculatedFieldsService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('CalculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
calculatedFieldsService.getCalculatedFieldById('your-calculatedfield-id').subscribe(result => {
  console.log('Fetched  Calculated Field By Id result:', result);
});
```

**2. saveCalculatedField**

```javascript
calculatedFieldsService.saveCalculatedField('your-calculatedfield-value').subscribe(result => {
  console.log('Saved  Calculated Field result:', result);
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField('your-calculatedfield-id').subscribe(result => {
  console.log('Deleted  Calculated Field result:', result);
});
```

**4. getCalculatedFields**

```javascript
calculatedFieldsService.getCalculatedFields(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-query-value').subscribe(result => {
  console.log('Fetched  Calculated Fields result:', result);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
calculatedFieldsService.getCalculatedFieldsByEntityId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(entity => {
  console.log('Fetched  Calculated Fields By Entity Id entity:', entity);
});
```

**6. testScript**

```javascript
calculatedFieldsService.testScript('your-inputparams-value').subscribe(result => {
  console.log('test Script result:', result);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent('your--id').subscribe(result => {
  console.log('Fetched  Latest Calculated Field Debug Event result:', result);
});
```

**8. getCalculatedFieldNames**

```javascript
calculatedFieldsService.getCalculatedFieldNames(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(result => {
  console.log('Fetched  Calculated Field Names result:', result);
});
```

---

### **ComponentDescriptorService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('ComponentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
componentDescriptorService.getComponentDescriptorsByType('your-componenttype-value', 'your-rulechaintype-value').subscribe(result => {
  console.log('Fetched  Component Descriptors By Type result:', result);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes('your-componenttypes-value', 'your-rulechaintype-value').subscribe(result => {
  console.log('Fetched  Component Descriptors By Types result:', result);
});
```

**3. getComponentDescriptorByClazz**

```javascript
componentDescriptorService.getComponentDescriptorByClazz('your-componentdescriptorclazz-value').subscribe(result => {
  console.log('Fetched  Component Descriptor By Clazz result:', result);
});
```

---

### **CustomerService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('CustomerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```

**1. getCustomers**

```javascript
customerService.getCustomers(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Customers result:', result);
});
```

**2. getCustomer**

```javascript
customerService.getCustomer('your-customer-id').subscribe(result => {
  console.log('Fetched  Customer result:', result);
});
```

**3. getCustomersByIds**

```javascript
customerService.getCustomersByIds('your-customerids-value').subscribe(result => {
  console.log('Fetched  Customers By Ids result:', result);
});
```

**4. saveCustomer**

```javascript
customerService.saveCustomer('your-customer-value').subscribe(result => {
  console.log('Saved  Customer result:', result);
});
```

---

### **DashboardService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('DashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

**1. getTenantDashboards**

```javascript
dashboardService.getTenantDashboards(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Dashboards tenant:', tenant);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
dashboardService.getTenantDashboardsByTenantId('your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Dashboards By Tenant Id tenant:', tenant);
});
```

**3. getCustomerDashboards**

```javascript
dashboardService.getCustomerDashboards('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(dashboard => {
  console.log('Fetched  Customer Dashboards dashboard:', dashboard);
});
```

**4. getDashboard**

```javascript
dashboardService.getDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Fetched  Dashboard dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
dashboardService.exportDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('export Dashboard dashboard:', dashboard);
});
```

**6. getDashboardInfo**

```javascript
dashboardService.getDashboardInfo('your-dashboard-id').subscribe(dashboard => {
  console.log('Fetched  Dashboard Info dashboard:', dashboard);
});
```

**7. getDashboards**

```javascript
dashboardService.getDashboards('your-dashboardids-value').subscribe(dashboard => {
  console.log('Fetched  Dashboards dashboard:', dashboard);
});
```

**8. saveDashboard**

```javascript
dashboardService.saveDashboard('your-dashboard-value').subscribe(dashboard => {
  console.log('Saved  Dashboard dashboard:', dashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
dashboardService.assignDashboardToCustomer('your-customer-id', 'your-dashboard-id').subscribe(dashboard => {
  console.log('assign Dashboard To Customer dashboard:', dashboard);
});
```

**10. makeDashboardPublic**

```javascript
dashboardService.makeDashboardPublic('your-dashboard-id').subscribe(dashboard => {
  console.log('make Dashboard Public dashboard:', dashboard);
});
```

**11. makeDashboardPrivate**

```javascript
dashboardService.makeDashboardPrivate('your-dashboard-id').subscribe(dashboard => {
  console.log('make Dashboard Private dashboard:', dashboard);
});
```

**12. updateDashboardCustomers**

```javascript
dashboardService.updateDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboard => {
  console.log('update Dashboard Customers dashboard:', dashboard);
});
```

**13. addDashboardCustomers**

```javascript
dashboardService.addDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboard => {
  console.log('add Dashboard Customers dashboard:', dashboard);
});
```

**14. removeDashboardCustomers**

```javascript
dashboardService.removeDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboard => {
  console.log('remove Dashboard Customers dashboard:', dashboard);
});
```

**15. getHomeDashboard**

```javascript
dashboardService.getHomeDashboard().subscribe(dashboard => {
  console.log('Fetched  Home Dashboard dashboard:', dashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
dashboardService.getTenantHomeDashboardInfo().subscribe(tenant => {
  console.log('Fetched  Tenant Home Dashboard Info tenant:', tenant);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
dashboardService.setTenantHomeDashboardInfo('your-homedashboardinfo-value').subscribe(tenant => {
  console.log('set Tenant Home Dashboard Info tenant:', tenant);
});
```

**18. getPublicDashboardLink**

```javascript
dashboardService.getPublicDashboardLink('your-dashboard-value').subscribe(dashboard => {
  console.log('Fetched  Public Dashboard Link dashboard:', dashboard);
});
```

**19. assignDashboardToEdge**

```javascript
dashboardService.assignDashboardToEdge('your-edge-id', 'your-dashboard-id').subscribe(dashboard => {
  console.log('assign Dashboard To Edge dashboard:', dashboard);
});
```

---

### **DeviceProfileService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('DeviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
deviceProfileService.getDeviceProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(device => {
  console.log('Fetched  Device Profiles device:', device);
});
```

**2. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds('your-deviceprofileids-value').subscribe(device => {
  console.log('Fetched  Device Profiles By Ids device:', device);
});
```

**3. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile('your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Device Profile device:', device);
});
```

**4. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile('your-deviceprofile-id').subscribe(device => {
  console.log('export Device Profile device:', device);
});
```

**5. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects('your-sortorder-value', 'your-objectids-value', 'your-searchtext-value').subscribe(result => {
  console.log('Fetched  Lwm2m Objects result:', result);
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true).subscribe(info => {
  console.log('Fetched  Lwm2m Bootstrap Security Info info:', info);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true).subscribe(info => {
  console.log('Fetched  Lwm2m Bootstrap Security Info By Security Type info:', info);
});
```

**8. getLwm2mObjectsPage**

```javascript
deviceProfileService.getLwm2mObjectsPage(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Lwm2m Objects Page result:', result);
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceProfileService.saveDeviceProfileAndConfirmOtaChange('your-origindeviceprofile-value', 'your-deviceprofile-value').subscribe(device => {
  console.log('Saved  Device Profile And Confirm Ota Change device:', device);
});
```

**10. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(device => {
  console.log('Saved  Device Profile device:', device);
});
```

**11. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile('your-deviceprofile-id').subscribe(device => {
  console.log('set Default Device Profile device:', device);
});
```

**12. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(device => {
  console.log('Fetched  Default Device Profile Info device:', device);
});
```

**13. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo('your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Device Profile Info device:', device);
});
```

**14. getDeviceProfileInfos**

```javascript
deviceProfileService.getDeviceProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-transporttype-value').subscribe(device => {
  console.log('Fetched  Device Profile Infos device:', device);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys('your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Device Profile Devices Attributes Keys device:', device);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys('your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Device Profile Devices Timeseries Keys device:', device);
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames('your-activeonly-value').subscribe(device => {
  console.log('Fetched  Device Profile Names device:', device);
});
```

---

### **DeviceService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('DeviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
deviceService.getDeviceInfosByQuery('your-deviceinfoquery-value').subscribe(device => {
  console.log('Fetched  Device Infos By Query device:', device);
});
```

**2. getTenantDeviceInfos**

```javascript
deviceService.getTenantDeviceInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(device => {
  console.log('Fetched  Tenant Device Infos device:', device);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
deviceService.getTenantDeviceInfosByDeviceProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Tenant Device Infos By Device Profile Id device:', device);
});
```

**4. getCustomerDeviceInfos**

```javascript
deviceService.getCustomerDeviceInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(device => {
  console.log('Fetched  Customer Device Infos device:', device);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
deviceService.getCustomerDeviceInfosByDeviceProfileId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id').subscribe(device => {
  console.log('Fetched  Customer Device Infos By Device Profile Id device:', device);
});
```

**6. getDevice**

```javascript
deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Fetched  Device device:', device);
});
```

**7. getDevices**

```javascript
deviceService.getDevices('your-deviceids-value').subscribe(device => {
  console.log('Fetched  Devices device:', device);
});
```

**8. getDeviceInfo**

```javascript
deviceService.getDeviceInfo('your-device-id').subscribe(device => {
  console.log('Fetched  Device Info device:', device);
});
```

**9. saveDevice**

```javascript
deviceService.saveDevice('your-device-value').subscribe(device => {
  console.log('Saved  Device device:', device);
});
```

**10. saveDeviceWithCredentials**

```javascript
deviceService.saveDeviceWithCredentials('your-device-value', 'your-credentials-value').subscribe(device => {
  console.log('Saved  Device With Credentials device:', device);
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes().subscribe(device => {
  console.log('Fetched  Device Types device:', device);
});
```

**12. getDeviceCredentials**

```javascript
deviceService.getDeviceCredentials('your-device-id', 'your-sync-value').subscribe(device => {
  console.log('Fetched  Device Credentials device:', device);
});
```

**13. saveDeviceCredentials**

```javascript
deviceService.saveDeviceCredentials('your-devicecredentials-value').subscribe(device => {
  console.log('Saved  Device Credentials device:', device);
});
```

**14. makeDevicePublic**

```javascript
deviceService.makeDevicePublic('your-device-id').subscribe(device => {
  console.log('make Device Public device:', device);
});
```

**15. assignDeviceToCustomer**

```javascript
deviceService.assignDeviceToCustomer('your-customer-id', 'your-device-id').subscribe(device => {
  console.log('assign Device To Customer device:', device);
});
```

**16. sendOneWayRpcCommand**

```javascript
deviceService.sendOneWayRpcCommand('your-device-id', 'your-requestbody-value').subscribe(result => {
  console.log('send One Way Rpc Command result:', result);
});
```

**17. sendTwoWayRpcCommand**

```javascript
deviceService.sendTwoWayRpcCommand('your-device-id', 'your-requestbody-value').subscribe(result => {
  console.log('send Two Way Rpc Command result:', result);
});
```

**18. getPersistedRpc**

```javascript
deviceService.getPersistedRpc('your-rpc-id').subscribe(result => {
  console.log('Fetched  Persisted Rpc result:', result);
});
```

**19. getPersistedRpcRequests**

```javascript
deviceService.getPersistedRpcRequests('your-device-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-rpcstatus-value').subscribe(result => {
  console.log('Fetched  Persisted Rpc Requests result:', result);
});
```

**20. findByQuery**

```javascript
deviceService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**21. findByName**

```javascript
deviceService.findByName('your-devicename-value').subscribe(result => {
  console.log('find By Name result:', result);
});
```

**22. claimDevice**

```javascript
deviceService.claimDevice('your-devicename-value', 'your-claimrequest-value').subscribe(device => {
  console.log('claim Device device:', device);
});
```

**23. assignDeviceToEdge**

```javascript
deviceService.assignDeviceToEdge('your-edge-id', 'your-device-id').subscribe(device => {
  console.log('assign Device To Edge device:', device);
});
```

**24. getEdgeDevices**

```javascript
deviceService.getEdgeDevices('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(device => {
  console.log('Fetched  Edge Devices device:', device);
});
```

**25. bulkImportDevices**

```javascript
deviceService.bulkImportDevices('your-entitiesdata-value').subscribe(device => {
  console.log('bulk Import Devices device:', device);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
deviceService.getDevicePublishTelemetryCommands('your-device-id').subscribe(device => {
  console.log('Fetched  Device Publish Telemetry Commands device:', device);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
deviceService.downloadGatewayDockerComposeFile('your-device-id').subscribe(result => {
  console.log('download Gateway Docker Compose File result:', result);
});
```

**28. rebootDevice**

```javascript
deviceService.rebootDevice('your-device-id', true).subscribe(device => {
  console.log('reboot Device device:', device);
});
```

**29. rebootTrigger**

```javascript
deviceService.rebootTrigger('your-device-id', 'your-resourcepath-value').subscribe(result => {
  console.log('reboot Trigger result:', result);
});
```

---

### **DomainService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('DomainService'));
```

**1. saveDomain**

```javascript
domainService.saveDomain('your-domain-value', 'your-oauth2clientids-value').subscribe(result => {
  console.log('Saved  Domain result:', result);
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients('your--id', 'your-oauth2clientids-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**3. getTenantDomainInfos**

```javascript
domainService.getTenantDomainInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Domain Infos tenant:', tenant);
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById('your--id').subscribe(info => {
  console.log('Fetched  Domain Info By Id info:', info);
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

---

### **EdgeService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('EdgeService'));
```

**1. getEdges**

```javascript
edgeService.getEdges('your-edgeids-value').subscribe(result => {
  console.log('Fetched  Edges result:', result);
});
```

**2. getEdge**

```javascript
edgeService.getEdge('your-edge-id').subscribe(result => {
  console.log('Fetched  Edge result:', result);
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo('your-edge-id').subscribe(info => {
  console.log('Fetched  Edge Info info:', info);
});
```

**4. saveEdge**

```javascript
edgeService.saveEdge('your-edge-value').subscribe(result => {
  console.log('Saved  Edge result:', result);
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes().subscribe(result => {
  console.log('Fetched  Edge Types result:', result);
});
```

**6. getCustomerEdgeInfos**

```javascript
edgeService.getCustomerEdgeInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(info => {
  console.log('Fetched  Customer Edge Infos info:', info);
});
```

**7. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer('your-customer-id', 'your-edge-id').subscribe(result => {
  console.log('assign Edge To Customer result:', result);
});
```

**8. makeEdgePublic**

```javascript
edgeService.makeEdgePublic('your-edge-id').subscribe(result => {
  console.log('make Edge Public result:', result);
});
```

**9. getTenantEdgeInfos**

```javascript
edgeService.getTenantEdgeInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(tenant => {
  console.log('Fetched  Tenant Edge Infos tenant:', tenant);
});
```

**10. findByQuery**

```javascript
edgeService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**11. getEdgeEvents**

```javascript
edgeService.getEdgeEvents('your-entity-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Edge Events result:', result);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains('your-edge-id').subscribe(rule => {
  console.log('find Missing To Related Rule Chains rule:', rule);
});
```

**13. findByName**

```javascript
edgeService.findByName('your-edgename-value').subscribe(result => {
  console.log('find By Name result:', result);
});
```

**14. bulkImportEdges**

```javascript
edgeService.bulkImportEdges('your-entitiesdata-value').subscribe(result => {
  console.log('bulk Import Edges result:', result);
});
```

**15. getEdgeInstallInstructions**

```javascript
edgeService.getEdgeInstallInstructions('your-edge-id', 'your-method-value').subscribe(result => {
  console.log('Fetched  Edge Install Instructions result:', result);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
edgeService.getEdgeUpgradeInstructions('your-edgeversion-value', 'your-method-value').subscribe(result => {
  console.log('Fetched  Edge Upgrade Instructions result:', result);
});
```

**17. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable('your-edge-id').subscribe(result => {
  console.log('is Edge Upgrade Available result:', result);
});
```

---

### **EntitiesVersionControlService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('EntitiesVersionControlService'));
```

**1. clearBranchList**

```javascript
entitiesVersionControlService.clearBranchList().subscribe(items => {
  console.log('clear Branch List items:', items);
});
```

**2. listBranches**

```javascript
entitiesVersionControlService.listBranches().subscribe(result => {
  console.log('list Branches result:', result);
});
```

**3. getEntityDataInfo**

```javascript
entitiesVersionControlService.getEntityDataInfo('your-externalentity-id', 'your-version-id').subscribe(entity => {
  console.log('Fetched  Entity Data Info entity:', entity);
});
```

**4. saveEntitiesVersion**

```javascript
entitiesVersionControlService.saveEntitiesVersion('your-request-value').subscribe(entities => {
  console.log('Saved  Entities Version entities:', entities);
});
```

**5. getVersionCreateRequestStatus**

```javascript
entitiesVersionControlService.getVersionCreateRequestStatus('your-request-id').subscribe(result => {
  console.log('Fetched  Version Create Request Status result:', result);
});
```

**6. listEntityVersions**

```javascript
entitiesVersionControlService.listEntityVersions(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-branch-value', 'your-externalentity-id').subscribe(entity => {
  console.log('list Entity Versions entity:', entity);
});
```

**7. listEntityTypeVersions**

```javascript
entitiesVersionControlService.listEntityTypeVersions(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-branch-value', 'your-entitytype-value').subscribe(entity => {
  console.log('list Entity Type Versions entity:', entity);
});
```

**8. listVersions**

```javascript
entitiesVersionControlService.listVersions(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-branch-value').subscribe(result => {
  console.log('list Versions result:', result);
});
```

**9. loadEntitiesVersion**

```javascript
entitiesVersionControlService.loadEntitiesVersion('your-request-value').subscribe(entities => {
  console.log('load Entities Version entities:', entities);
});
```

**10. getVersionLoadRequestStatus**

```javascript
entitiesVersionControlService.getVersionLoadRequestStatus('your-request-id').subscribe(result => {
  console.log('Fetched  Version Load Request Status result:', result);
});
```

**11. compareEntityDataToVersion**

```javascript
entitiesVersionControlService.compareEntityDataToVersion('your-entity-id', 'your-version-id').subscribe(entity => {
  console.log('compare Entity Data To Version entity:', entity);
});
```

**12. entityLoadErrorToMessage**

```javascript
entitiesVersionControlService.entityLoadErrorToMessage('your-entityloaderror-value').subscribe(result => {
  console.log('entity Load Error To Message result:', result);
});
```

---

### **EntityRelationService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('EntityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
entityRelationService.saveRelation('your-relation-value').subscribe(result => {
  console.log('Saved  Relation result:', result);
});
```

**2. getRelation**

```javascript
entityRelationService.getRelation('your-from-id', 'your-relationtype-value', 'your-to-id').subscribe(result => {
  console.log('Fetched  Relation result:', result);
});
```

**3. findByFrom**

```javascript
entityRelationService.findByFrom('your-from-id').subscribe(result => {
  console.log('find By From result:', result);
});
```

**4. findInfoByFrom**

```javascript
entityRelationService.findInfoByFrom('your-from-id').subscribe(info => {
  console.log('find Info By From info:', info);
});
```

**5. findByFromAndType**

```javascript
entityRelationService.findByFromAndType('your-from-id', 'your-relationtype-value').subscribe(result => {
  console.log('find By From And Type result:', result);
});
```

**6. findByTo**

```javascript
entityRelationService.findByTo('your-to-id').subscribe(result => {
  console.log('find By To result:', result);
});
```

**7. findInfoByTo**

```javascript
entityRelationService.findInfoByTo('your-to-id').subscribe(info => {
  console.log('find Info By To info:', info);
});
```

**8. findByToAndType**

```javascript
entityRelationService.findByToAndType('your-to-id', 'your-relationtype-value').subscribe(result => {
  console.log('find By To And Type result:', result);
});
```

**9. findByQuery**

```javascript
entityRelationService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**10. findInfoByQuery**

```javascript
entityRelationService.findInfoByQuery('your-query-value').subscribe(info => {
  console.log('find Info By Query info:', info);
});
```

---

### **EntityViewService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('EntityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

**1. getTenantEntityViewInfos**

```javascript
entityViewService.getTenantEntityViewInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(tenant => {
  console.log('Fetched  Tenant Entity View Infos tenant:', tenant);
});
```

**2. getCustomerEntityViewInfos**

```javascript
entityViewService.getCustomerEntityViewInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(entity => {
  console.log('Fetched  Customer Entity View Infos entity:', entity);
});
```

**3. getEntityView**

```javascript
entityViewService.getEntityView('your-entityview-id').subscribe(entity => {
  console.log('Fetched  Entity View entity:', entity);
});
```

**4. getEntityViews**

```javascript
entityViewService.getEntityViews('your-entityviewids-value').subscribe(entity => {
  console.log('Fetched  Entity Views entity:', entity);
});
```

**5. getEntityViewInfo**

```javascript
entityViewService.getEntityViewInfo('your-entityview-id').subscribe(entity => {
  console.log('Fetched  Entity View Info entity:', entity);
});
```

**6. saveEntityView**

```javascript
entityViewService.saveEntityView('your-entityview-value').subscribe(entity => {
  console.log('Saved  Entity View entity:', entity);
});
```

**7. getEntityViewTypes**

```javascript
entityViewService.getEntityViewTypes().subscribe(entity => {
  console.log('Fetched  Entity View Types entity:', entity);
});
```

**8. makeEntityViewPublic**

```javascript
entityViewService.makeEntityViewPublic('your-entityview-id').subscribe(entity => {
  console.log('make Entity View Public entity:', entity);
});
```

**9. assignEntityViewToCustomer**

```javascript
entityViewService.assignEntityViewToCustomer('your-customer-id', 'your-entityview-id').subscribe(entity => {
  console.log('assign Entity View To Customer entity:', entity);
});
```

**10. findByQuery**

```javascript
entityViewService.findByQuery('your-query-value').subscribe(result => {
  console.log('find By Query result:', result);
});
```

**11. assignEntityViewToEdge**

```javascript
entityViewService.assignEntityViewToEdge('your-edge-id', 'your-entityview-id').subscribe(entity => {
  console.log('assign Entity View To Edge entity:', entity);
});
```

**12. getEdgeEntityViews**

```javascript
entityViewService.getEdgeEntityViews('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(entity => {
  console.log('Fetched  Edge Entity Views entity:', entity);
});
```

---

### **EntityService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('EntityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
entityService.getEntityObservable('your-entitytype-value', 'your-entity-id').subscribe(entity => {
  console.log('Fetched  Entity Observable entity:', entity);
});
```

**2. getEntity**

```javascript
entityService.getEntity('your-entitytype-value', 'your-entity-id').subscribe(entity => {
  console.log('Fetched  Entity entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
entityService.getEntitiesObservable('your-entitytype-value', 'your-entityids-value').subscribe(entities => {
  console.log('Fetched  Entities Observable entities:', entities);
});
```

**4. getEntities**

```javascript
entityService.getEntities('your-entitytype-value', 'your-entityids-value').subscribe(entities => {
  console.log('Fetched  Entities entities:', entities);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
entityService.getSingleTenantByPageLinkObservable(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Single Tenant By Page Link Observable tenant:', tenant);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
entityService.getSingleCustomerByPageLinkObservable(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Single Customer By Page Link Observable result:', result);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
entityService.getEntitiesByPageLinkObservable('your-entitytype-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-subtype-value').subscribe(entities => {
  console.log('Fetched  Entities By Page Link Observable entities:', entities);
});
```

**8. getEntitiesByPageLink**

```javascript
entityService.getEntitiesByPageLink('your-entitytype-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-subtype-value').subscribe(entities => {
  console.log('Fetched  Entities By Page Link entities:', entities);
});
```

**9. getEntitiesByNameFilter**

```javascript
entityService.getEntitiesByNameFilter('your-entitytype-value', 'your-entitynamefilter-value', 0, 'your-subtype-value').subscribe(entities => {
  console.log('Fetched  Entities By Name Filter entities:', entities);
});
```

**10. findEntityDataByQuery**

```javascript
entityService.findEntityDataByQuery('your-query-value').subscribe(entity => {
  console.log('find Entity Data By Query entity:', entity);
});
```

**11. findEntityKeysByQuery**

```javascript
entityService.findEntityKeysByQuery('your-query-value', 'your-scope-value').subscribe(entity => {
  console.log('find Entity Keys By Query entity:', entity);
});
```

**12. findAlarmDataByQuery**

```javascript
entityService.findAlarmDataByQuery('your-query-value').subscribe(alarm => {
  console.log('find Alarm Data By Query alarm:', alarm);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
entityService.findEntityInfosByFilterAndName('your-filter-value', 'your-searchtext-value').subscribe(entity => {
  console.log('find Entity Infos By Filter And Name entity:', entity);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
entityService.findSingleEntityInfoByEntityFilter('your-filter-value').subscribe(entity => {
  console.log('find Single Entity Info By Entity Filter entity:', entity);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
entityService.getAliasFilterTypesByEntityTypes('your-entitytypes-value').subscribe(entity => {
  console.log('Fetched  Alias Filter Types By Entity Types entity:', entity);
});
```

**16. filterAliasByEntityTypes**

```javascript
entityService.filterAliasByEntityTypes('your-entityalias-value', 'your-entitytypes-value').subscribe(entity => {
  console.log('filter Alias By Entity Types entity:', entity);
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
entityService.filterAliasFilterTypeByEntityTypes('your-aliasfiltertype-value', 'your-entitytypes-value').subscribe(entity => {
  console.log('filter Alias Filter Type By Entity Types entity:', entity);
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
entityService.filterAliasFilterTypeByEntityType('your-aliasfiltertype-value', 'your-entitytype-value').subscribe(entity => {
  console.log('filter Alias Filter Type By Entity Type entity:', entity);
});
```

**19. prepareAllowedEntityTypesList**

```javascript
entityService.prepareAllowedEntityTypesList('your-allowedentitytypes-value', true).subscribe(entity => {
  console.log('prepare Allowed Entity Types List entity:', entity);
});
```

**20. getEntityFieldKeys**

```javascript
entityService.getEntityFieldKeys('your-entitytype-value', 'your-searchtext-value').subscribe(entity => {
  console.log('Fetched  Entity Field Keys entity:', entity);
});
```

**21. getAlarmKeys**

```javascript
entityService.getAlarmKeys('your-searchtext-value').subscribe(alarm => {
  console.log('Fetched  Alarm Keys alarm:', alarm);
});
```

**22. getEntityKeys**

```javascript
entityService.getEntityKeys('your-entity-id', 'your-query-value', 'your-type-value').subscribe(entity => {
  console.log('Fetched  Entity Keys entity:', entity);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
entityService.getEntityKeysByEntityFilter('your-filter-value', 'your-types-value', 'your-entitytypes-value').subscribe(entity => {
  console.log('Fetched  Entity Keys By Entity Filter entity:', entity);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
entityService.getEntityKeysByEntityFilterAndScope('your-filter-value', 'your-types-value', 'your-entitytypes-value', 'your-scope-value').subscribe(entity => {
  console.log('Fetched  Entity Keys By Entity Filter And Scope entity:', entity);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
entityService.createDatasourcesFromSubscriptionsInfo('your-subscriptionsinfo-value').subscribe(data => {
  console.log('create Datasources From Subscriptions Info data:', data);
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
entityService.createAlarmSourceFromSubscriptionInfo('your-subscriptioninfo-value').subscribe(alarm => {
  console.log('create Alarm Source From Subscription Info alarm:', alarm);
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
entityService.getAssignedToEdgeEntitiesByType('your-edge-id', 'your-entitytype-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(entities => {
  console.log('Fetched  Assigned To Edge Entities By Type entities:', entities);
});
```

**28. case**

```javascript
entityService.case().subscribe(result => {
  console.log('case result:', result);
});
```

**29. getEntitySubtypesObservable**

```javascript
entityService.getEntitySubtypesObservable('your-entitytype-value').subscribe(entity => {
  console.log('Fetched  Entity Subtypes Observable entity:', entity);
});
```

---

### **EventService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('EventService'));
```

**1. getEvents**

```javascript
eventService.getEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Events result:', result);
});
```

**2. getFilterEvents**

```javascript
eventService.getFilterEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', 'your-filters-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Filter Events result:', result);
});
```

---

### **GitHubService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('GitHubService'));
```

**1. getGitHubStar**

```javascript
gitHubService.getGitHubStar().subscribe(result => {
  console.log('Fetched  Git Hub Star result:', result);
});
```

---

### **ImageService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('ImageService'));
```

**1. uploadImage**

```javascript
imageService.uploadImage('your-file-value', 'your-title-value', 'your-imagesubtype-value').subscribe(result => {
  console.log('upload Image result:', result);
});
```

**2. updateImage**

```javascript
imageService.updateImage('your-type-value', 'your-api-key', 'your-file-value').subscribe(result => {
  console.log('update Image result:', result);
});
```

**3. updateImageInfo**

```javascript
imageService.updateImageInfo('your-imageinfo-value').subscribe(info => {
  console.log('update Image Info info:', info);
});
```

**4. updateImagePublicStatus**

```javascript
imageService.updateImagePublicStatus('your-imageinfo-value', true).subscribe(result => {
  console.log('update Image Public Status result:', result);
});
```

**5. getImages**

```javascript
imageService.getImages(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-imagesubtype-value').subscribe(result => {
  console.log('Fetched  Images result:', result);
});
```

**6. getImageInfo**

```javascript
imageService.getImageInfo('your-type-value', 'your-api-key').subscribe(info => {
  console.log('Fetched  Image Info info:', info);
});
```

**7. getImageDataUrl**

```javascript
imageService.getImageDataUrl('your-imageurl-value').subscribe(data => {
  console.log('Fetched  Image Data Url data:', data);
});
```

**8. loadImageDataUrl**

```javascript
imageService.loadImageDataUrl('your-imagelink-value').subscribe(data => {
  console.log('load Image Data Url data:', data);
});
```

**9. getImageString**

```javascript
imageService.getImageString('your-imageurl-value').subscribe(result => {
  console.log('Fetched  Image String result:', result);
});
```

**10. resolveImageUrl**

```javascript
imageService.resolveImageUrl('your-imageurl-value').subscribe(result => {
  console.log('resolve Image Url result:', result);
});
```

**11. downloadImage**

```javascript
imageService.downloadImage('your-type-value', 'your-api-key').subscribe(result => {
  console.log('download Image result:', result);
});
```

**12. exportImage**

```javascript
imageService.exportImage('your-type-value', 'your-api-key').subscribe(result => {
  console.log('export Image result:', result);
});
```

**13. importImage**

```javascript
imageService.importImage('your-imagedata-value').subscribe(result => {
  console.log('import Image result:', result);
});
```

---

### **MobileAppService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('MobileAppService'));
```

**1. saveMobileApp**

```javascript
mobileAppService.saveMobileApp('your-mobileapp-value').subscribe(result => {
  console.log('Saved  Mobile App result:', result);
});
```

**2. getTenantMobileAppInfos**

```javascript
mobileAppService.getTenantMobileAppInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-platformtype-value').subscribe(tenant => {
  console.log('Fetched  Tenant Mobile App Infos tenant:', tenant);
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById('your--id').subscribe(info => {
  console.log('Fetched  Mobile App Info By Id info:', info);
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
mobileAppService.getTenantMobileAppBundleInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Mobile App Bundle Infos tenant:', tenant);
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById('your--id').subscribe(info => {
  console.log('Fetched  Mobile App Bundle Info By Id info:', info);
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

---

### **MobileApplicationService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('MobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
mobileApplicationService.getMobileAppSettings().subscribe(settings => {
  console.log('Fetched  Mobile App Settings settings:', settings);
});
```

**2. saveMobileAppSettings**

```javascript
mobileApplicationService.saveMobileAppSettings('your-mobileappsettings-value').subscribe(settings => {
  console.log('Saved  Mobile App Settings settings:', settings);
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(result => {
  console.log('Fetched  Mobile App Deep Link result:', result);
});
```

---

### **NotificationService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('NotificationService'));
```

**1. getNotifications**

```javascript
notificationService.getNotifications(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Notifications result:', result);
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('Operation completed:', result);
});
```

**5. createNotificationRequest**

```javascript
notificationService.createNotificationRequest('your-notification-value').subscribe(result => {
  console.log('create Notification Request result:', result);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest('your-entitytype-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById('your--id').subscribe(result => {
  console.log('Fetched  Notification Request By Id result:', result);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(result => {
  console.log('Fetched  Available Delivery Methods result:', result);
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**10. getNotificationRequestPreview**

```javascript
notificationService.getNotificationRequestPreview('your-notification-value').subscribe(result => {
  console.log('Fetched  Notification Request Preview result:', result);
});
```

**11. getNotificationRequests**

```javascript
notificationService.getNotificationRequests(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Notification Requests result:', result);
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(settings => {
  console.log('Fetched  Notification Settings settings:', settings);
});
```

**13. saveNotificationSettings**

```javascript
notificationService.saveNotificationSettings('your-notificationsettings-value').subscribe(settings => {
  console.log('Saved  Notification Settings settings:', settings);
});
```

**14. listSlackConversations**

```javascript
notificationService.listSlackConversations('your-type-value', 'your-access-token').subscribe(result => {
  console.log('list Slack Conversations result:', result);
});
```

**15. saveNotificationRule**

```javascript
notificationService.saveNotificationRule('your-notificationrule-value').subscribe(rule => {
  console.log('Saved  Notification Rule rule:', rule);
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById('your--id').subscribe(rule => {
  console.log('Fetched  Notification Rule By Id rule:', rule);
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**18. getNotificationRules**

```javascript
notificationService.getNotificationRules(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(rule => {
  console.log('Fetched  Notification Rules rule:', rule);
});
```

**19. saveNotificationTarget**

```javascript
notificationService.saveNotificationTarget('your-notificationtarget-value').subscribe(result => {
  console.log('Saved  Notification Tar Fetched result:', result);
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById('your--id').subscribe(result => {
  console.log('Fetched  Notification Tar Fetched  By Id result:', result);
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds('your-ids-value').subscribe(result => {
  console.log('Fetched  Notification Tar Fetched s By Ids result:', result);
});
```

**23. getNotificationTargets**

```javascript
notificationService.getNotificationTargets(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(result => {
  console.log('Fetched  Notification Tar Fetched s result:', result);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
notificationService.getRecipientsForNotificationTargetConfig('your-notificationtarget-value', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Recipients For Notification Tar Fetched  Config result:', result);
});
```

**25. saveNotificationTemplate**

```javascript
notificationService.saveNotificationTemplate('your-notificationtarget-value').subscribe(result => {
  console.log('Saved  Notification Template result:', result);
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById('your--id').subscribe(result => {
  console.log('Fetched  Notification Template By Id result:', result);
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**28. getNotificationTemplates**

```javascript
notificationService.getNotificationTemplates(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-notificationtypes-value').subscribe(result => {
  console.log('Fetched  Notification Templates result:', result);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(users => {
  console.log('Fetched  Notification User Settings users:', users);
});
```

**30. saveNotificationUserSettings**

```javascript
notificationService.saveNotificationUserSettings('your-settings-value').subscribe(users => {
  console.log('Saved  Notification User Settings users:', users);
});
```

---

### **OAuth2Service**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('OAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template().subscribe(result => {
  console.log('Fetched  O Auth2 Template result:', result);
});
```

**2. saveOAuth2Client**

```javascript
oAuth2Service.saveOAuth2Client('your-oauth2client-value').subscribe(result => {
  console.log('Saved  O Auth2 Client result:', result);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
oAuth2Service.findTenantOAuth2ClientInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('find Tenant O Auth2 Client Infos tenant:', tenant);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2Service.findTenantOAuth2ClientInfosByIds('your-clientids-value').subscribe(tenant => {
  console.log('find Tenant O Auth2 Client Infos By Ids tenant:', tenant);
});
```

**5. getOAuth2ClientById**

```javascript
oAuth2Service.getOAuth2ClientById('your--id').subscribe(result => {
  console.log('Fetched  O Auth2 Client By Id result:', result);
});
```

**6. deleteOauth2Client**

```javascript
oAuth2Service.deleteOauth2Client('your--id').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(result => {
  console.log('Fetched  Login Processing Url result:', result);
});
```

---

### **OtaPackageService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('OtaPackageService'));
```

**1. getOtaPackages**

```javascript
otaPackageService.getOtaPackages(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Ota Packages result:', result);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
otaPackageService.getOtaPackagesInfoByDeviceProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id', 'your-type-value').subscribe(device => {
  console.log('Fetched  Ota Packages Info By Device Profile Id device:', device);
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage('your-otapackage-id').subscribe(result => {
  console.log('Fetched  Ota Package result:', result);
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo('your-otapackage-id').subscribe(info => {
  console.log('Fetched  Ota Package Info info:', info);
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage('your-otapackage-id').subscribe(result => {
  console.log('download Ota Package result:', result);
});
```

**6. saveOtaPackage**

```javascript
otaPackageService.saveOtaPackage('your-otapackage-value').subscribe(result => {
  console.log('Saved  Ota Package result:', result);
});
```

**7. saveOtaPackageInfo**

```javascript
otaPackageService.saveOtaPackageInfo('your-otapackageinfo-value').subscribe(info => {
  console.log('Saved  Ota Package Info info:', info);
});
```

**8. uploadOtaPackageFile**

```javascript
otaPackageService.uploadOtaPackageFile('your-otapackage-id', 'your-file-value', 'your-checksumalgorithm-value', 'your-checksum-value').subscribe(result => {
  console.log('upload Ota Package File result:', result);
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage('your-type-value', 'your-entity-id').subscribe(device => {
  console.log('count Update Device After Change Package device:', device);
});
```

**10. confirmDialogUpdatePackage**

```javascript
otaPackageService.confirmDialogUpdatePackage('your-entity-value', 'your-originentity-value').subscribe(result => {
  console.log('confirm Dialog Update Package result:', result);
});
```

---

### **QueueService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('QueueService'));
```

**1. getQueueById**

```javascript
queueService.getQueueById('your-queue-id').subscribe(result => {
  console.log('Fetched  Queue By Id result:', result);
});
```

**2. getQueueByName**

```javascript
queueService.getQueueByName('your-queuename-value').subscribe(result => {
  console.log('Fetched  Queue By Name result:', result);
});
```

**3. getTenantQueuesByServiceType**

```javascript
queueService.getTenantQueuesByServiceType(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-servicetype-value').subscribe(tenant => {
  console.log('Fetched  Tenant Queues By Service Type tenant:', tenant);
});
```

**4. saveQueue**

```javascript
queueService.saveQueue('your-queue-value', 'your-servicetype-value').subscribe(result => {
  console.log('Saved  Queue result:', result);
});
```

**5. getQueueStatistics**

```javascript
queueService.getQueueStatistics(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Queue Statistics result:', result);
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById('your-queuestat-id').subscribe(result => {
  console.log('Fetched  Queue Statistics By Id result:', result);
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds('your-queuestatids-value').subscribe(result => {
  console.log('Fetched  Queue Statistics By Ids result:', result);
});
```

---

### **ResourceService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('ResourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```

**1. getResources**

```javascript
resourceService.getResources(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-resourcetype-value', 'your-resourcesubtype-value').subscribe(result => {
  console.log('Fetched  Resources result:', result);
});
```

**2. getTenantResources**

```javascript
resourceService.getTenantResources(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Resources tenant:', tenant);
});
```

**3. getResource**

```javascript
resourceService.getResource('your-resource-id').subscribe(result => {
  console.log('Fetched  Resource result:', result);
});
```

**4. getResourceInfoById**

```javascript
resourceService.getResourceInfoById('your-resource-id').subscribe(info => {
  console.log('Fetched  Resource Info By Id info:', info);
});
```

**5. getResourceInfo**

```javascript
resourceService.getResourceInfo('your-type-value', 'your-scope-value', 'your-api-key').subscribe(info => {
  console.log('Fetched  Resource Info info:', info);
});
```

**6. downloadResource**

```javascript
resourceService.downloadResource('your-resource-id').subscribe(result => {
  console.log('download Resource result:', result);
});
```

**7. saveResources**

```javascript
resourceService.saveResources('your-resources-value').subscribe(result => {
  console.log('Saved  Resources result:', result);
});
```

**8. saveResource**

```javascript
resourceService.saveResource('your-resource-value').subscribe(result => {
  console.log('Saved  Resource result:', result);
});
```

**9. uploadResources**

```javascript
resourceService.uploadResources('your-resources-value').subscribe(result => {
  console.log('upload Resources result:', result);
});
```

**10. uploadResource**

```javascript
resourceService.uploadResource('your-resource-value').subscribe(result => {
  console.log('upload Resource result:', result);
});
```

**11. updatedResourceInfo**

```javascript
resourceService.updatedResourceInfo('your-resource-id', 'your-updatedresources-value').subscribe(info => {
  console.log('updated Resource Info info:', info);
});
```

**12. updatedResourceData**

```javascript
resourceService.updatedResourceData('your-resource-id', 'your-data-value').subscribe(data => {
  console.log('updated Resource Data data:', data);
});
```

**13. getResourcesByIds**

```javascript
resourceService.getResourcesByIds('your-ids-value').subscribe(result => {
  console.log('Fetched  Resources By Ids result:', result);
});
```

---

### **RuleChainService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('RuleChainService'));
```

**1. getRuleChains**

```javascript
ruleChainService.getRuleChains(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type-value').subscribe(rule => {
  console.log('Fetched  Rule Chains rule:', rule);
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds('your-rulechainids-value').subscribe(rule => {
  console.log('Fetched  Rule Chains By Ids rule:', rule);
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('Fetched  Rule Chain rule:', rule);
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels('your-rulechain-id').subscribe(rule => {
  console.log('Fetched  Rule Chain Output Labels rule:', rule);
});
```

**5. createDefaultRuleChain**

```javascript
ruleChainService.createDefaultRuleChain('your-rulechainname-value').subscribe(rule => {
  console.log('create Default Rule Chain rule:', rule);
});
```

**6. saveRuleChain**

```javascript
ruleChainService.saveRuleChain('your-rulechain-value').subscribe(rule => {
  console.log('Saved  Rule Chain rule:', rule);
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('set Root Rule Chain rule:', rule);
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata('your-rulechain-id').subscribe(rule => {
  console.log('Fetched  Rule Chain Metadata rule:', rule);
});
```

**9. saveRuleChainMetadata**

```javascript
ruleChainService.saveRuleChainMetadata('your-rulechainmetadata-value').subscribe(rule => {
  console.log('Saved  Rule Chain Metadata rule:', rule);
});
```

**10. getRuleNodeComponents**

```javascript
ruleChainService.getRuleNodeComponents('your-modulesmap-value', 'your-rulechaintype-value').subscribe(rule => {
  console.log('Fetched  Rule Node Components rule:', rule);
});
```

**11. getRuleNodeConfigComponent**

```javascript
ruleChainService.getRuleNodeConfigComponent('your-directive-value').subscribe(rule => {
  console.log('Fetched  Rule Node Config Component rule:', rule);
});
```

**12. getRuleNodeComponentByClazz**

```javascript
ruleChainService.getRuleNodeComponentByClazz('your-rulechaintype-value', 'your-clazz-value').subscribe(rule => {
  console.log('Fetched  Rule Node Component By Clazz rule:', rule);
});
```

**13. getRuleNodeSupportedLinks**

```javascript
ruleChainService.getRuleNodeSupportedLinks('your-component-value').subscribe(rule => {
  console.log('Fetched  Rule Node Supported Links rule:', rule);
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
ruleChainService.ruleNodeAllowCustomLinks('your-component-value').subscribe(result => {
  console.log('rule Node Allow Custom Links result:', result);
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
ruleChainService.ruleNodeSourceRuleChainId('your-component-value').subscribe(rule => {
  console.log('rule Node Source Rule Chain Id rule:', rule);
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput('your-rulenode-id').subscribe(rule => {
  console.log('Fetched  Latest Rule Node Debug Input rule:', rule);
});
```

**17. testScript**

```javascript
ruleChainService.testScript('your-inputparams-value', 'your-scriptlang-value').subscribe(result => {
  console.log('test Script result:', result);
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents('your-rulechaintype-value').subscribe(rule => {
  console.log('load Rule Node Components rule:', rule);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentsUiResources('your-components-value', 'your-modulesmap-value').subscribe(rule => {
  console.log('resolve Rule Node Components Ui Resources rule:', rule);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentUiResources('your-component-value', 'your-modulesmap-value').subscribe(rule => {
  console.log('resolve Rule Node Component Ui Resources rule:', rule);
});
```

**21. getEdgeRuleChains**

```javascript
ruleChainService.getEdgeRuleChains('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(rule => {
  console.log('Fetched  Edge Rule Chains rule:', rule);
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge('your-edge-id', 'your-rulechain-id').subscribe(rule => {
  console.log('assign Rule Chain To Edge rule:', rule);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('set Edge Template Root Rule Chain rule:', rule);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('set Auto Assign To Edge Rule Chain rule:', rule);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(rule => {
  console.log('unset Auto Assign To Edge Rule Chain rule:', rule);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(rule => {
  console.log('Fetched  Auto Assign To Edge Rule Chains rule:', rule);
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain('your-edge-id', 'your-rulechain-id').subscribe(rule => {
  console.log('set Edge Root Rule Chain rule:', rule);
});
```

---

### **TenantProfileService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('TenantProfileService'));
```

**1. getTenantProfiles**

```javascript
tenantProfileService.getTenantProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Profiles tenant:', tenant);
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile('your-tenantprofile-id').subscribe(tenant => {
  console.log('Fetched  Tenant Profile tenant:', tenant);
});
```

**3. saveTenantProfile**

```javascript
tenantProfileService.saveTenantProfile('your-tenantprofile-value').subscribe(tenant => {
  console.log('Saved  Tenant Profile tenant:', tenant);
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile('your-tenantprofile-id').subscribe(tenant => {
  console.log('set Default Tenant Profile tenant:', tenant);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(tenant => {
  console.log('Fetched  Default Tenant Profile Info tenant:', tenant);
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo('your-tenantprofile-id').subscribe(tenant => {
  console.log('Fetched  Tenant Profile Info tenant:', tenant);
});
```

**7. getTenantProfileInfos**

```javascript
tenantProfileService.getTenantProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Profile Infos tenant:', tenant);
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds('your-tenantprofileids-value').subscribe(tenant => {
  console.log('Fetched  Tenant Profiles By Ids tenant:', tenant);
});
```

---

### **TenantService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('TenantService'));
```

**1. getTenants**

```javascript
tenantService.getTenants(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenants tenant:', tenant);
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds('your-tenantids-value').subscribe(tenant => {
  console.log('Fetched  Tenants By Ids tenant:', tenant);
});
```

**3. getTenantInfos**

```javascript
tenantService.getTenantInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Infos tenant:', tenant);
});
```

**4. getTenant**

```javascript
tenantService.getTenant('your-tenant-id').subscribe(tenant => {
  console.log('Fetched  Tenant tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo('your-tenant-id').subscribe(tenant => {
  console.log('Fetched  Tenant Info tenant:', tenant);
});
```

**6. saveTenant**

```javascript
tenantService.saveTenant('your-tenant-value').subscribe(tenant => {
  console.log('Saved  Tenant tenant:', tenant);
});
```

---

### **TrendzSettingsService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('TrendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
trendzSettingsService.getTrendzSettings().subscribe(settings => {
  console.log('Fetched  Trendz Settings settings:', settings);
});
```

**2. saveTrendzSettings**

```javascript
trendzSettingsService.saveTrendzSettings('your-trendzsettings-value').subscribe(settings => {
  console.log('Saved  Trendz Settings settings:', settings);
});
```

---

### **TwoFactorAuthenticationService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('TwoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings().subscribe(settings => {
  console.log('Fetched  Two Fa Settings settings:', settings);
});
```

**2. saveTwoFaSettings**

```javascript
twoFactorAuthenticationService.saveTwoFaSettings('your-settings-value').subscribe(settings => {
  console.log('Saved  Two Fa Settings settings:', settings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(result => {
  console.log('Fetched  Available Two Fa Providers result:', result);
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig('your-providertype-value').subscribe(result => {
  console.log('generate Two Fa Account Config result:', result);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(settings => {
  console.log('Fetched  Account Two Fa Settings settings:', settings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig('your-providertype-value', true).subscribe(result => {
  console.log('update Two Fa Account Config result:', result);
});
```

**7. submitTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.submitTwoFaAccountConfig().subscribe(result => {
  console.log('submit Two Fa Account Config result:', result);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(0).subscribe(result => {
  console.log('verify And Save Two Fa Account Config result:', result);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig('your-providertype-value').subscribe(result => {
  console.log('Deleted  Two Fa Account Config result:', result);
});
```

---

### **UiSettingsService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('UiSettingsService'));
```

**1. getHelpBaseUrl**

```javascript
uiSettingsService.getHelpBaseUrl().subscribe(result => {
  console.log('Fetched  Help Base Url result:', result);
});
```

---

### **UsageInfoService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('UsageInfoService'));
```

**1. getUsageInfo**

```javascript
usageInfoService.getUsageInfo().subscribe(info => {
  console.log('Fetched  Usage Info info:', info);
});
```

---

### **UserSettingsService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('UserSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```

**1. loadUserSettings**

```javascript
userSettingsService.loadUserSettings().subscribe(users => {
  console.log('load User Settings users:', users);
});
```

**2. saveUserSettings**

```javascript
userSettingsService.saveUserSettings('your-usersettings-value').subscribe(users => {
  console.log('Saved  User Settings users:', users);
});
```

**3. putUserSettings**

```javascript
userSettingsService.putUserSettings('your-usersettingsdata-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**4. getDocumentationLinks**

```javascript
userSettingsService.getDocumentationLinks().subscribe(result => {
  console.log('Fetched  Documentation Links result:', result);
});
```

**5. updateDocumentationLinks**

```javascript
userSettingsService.updateDocumentationLinks('your-documentationlinks-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**6. getQuickLinks**

```javascript
userSettingsService.getQuickLinks().subscribe(result => {
  console.log('Fetched  Quick Links result:', result);
});
```

**7. updateQuickLinks**

```javascript
userSettingsService.updateQuickLinks('your-quicklinks-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**8. getGettingStarted**

```javascript
userSettingsService.getGettingStarted().subscribe(result => {
  console.log('Fetched  Getting Started result:', result);
});
```

**9. updateGettingStarted**

```javascript
userSettingsService.updateGettingStarted('your-gettingstarted-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**10. getUserDashboardsInfo**

```javascript
userSettingsService.getUserDashboardsInfo().subscribe(users => {
  console.log('Fetched  User Dashboards Info users:', users);
});
```

**11. reportUserDashboardAction**

```javascript
userSettingsService.reportUserDashboardAction('your-dashboard-id', 'your-action-value').subscribe(users => {
  console.log('report User Dashboard Action users:', users);
});
```

---

### **UserService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('UserService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

**1. getUsers**

```javascript
userService.getUsers(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  Users users:', users);
});
```

**2. getTenantAdmins**

```javascript
userService.getTenantAdmins('your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Admins tenant:', tenant);
});
```

**3. getCustomerUsers**

```javascript
userService.getCustomerUsers('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  Customer Users users:', users);
});
```

**4. getUsersForAssign**

```javascript
userService.getUsersForAssign('your-alarm-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  Users For Assign users:', users);
});
```

**5. getUser**

```javascript
userService.getUser('your-user-id').subscribe(users => {
  console.log('Fetched  User users:', users);
});
```

**6. getUsersByIds**

```javascript
userService.getUsersByIds('your-userids-value').subscribe(users => {
  console.log('Fetched  Users By Ids users:', users);
});
```

**7. saveUser**

```javascript
userService.saveUser('your-user-value', 'your-email@example.com').subscribe(users => {
  console.log('Saved  User users:', users);
});
```

**8. getActivationLink**

```javascript
userService.getActivationLink('your-user-id').subscribe(result => {
  console.log('Fetched  Activation Link result:', result);
});
```

**9. getActivationLinkInfo**

```javascript
userService.getActivationLinkInfo('your-user-id').subscribe(info => {
  console.log('Fetched  Activation Link Info info:', info);
});
```

**10. setUserCredentialsEnabled**

```javascript
userService.setUserCredentialsEnabled('your-user-id', true).subscribe(users => {
  console.log('set User Credentials Enabled users:', users);
});
```

**11. findUsersByQuery**

```javascript
userService.findUsersByQuery(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('find Users By Query users:', users);
});
```

---

### **WidgetService**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('WidgetService'));
```

**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(result => {
  console.log('Fetched  Wid Fetched  Scope Variables result:', result);
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(result => {
  console.log('Fetched  All Wid Fetched s Bundles result:', result);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(result => {
  console.log('Fetched  System Wid Fetched s Bundles result:', result);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(tenant => {
  console.log('Fetched  Tenant Wid Fetched s Bundles tenant:', tenant);
});
```

**5. getWidgetBundles**

```javascript
widgetService.getWidgetBundles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(result => {
  console.log('Fetched  Wid Fetched  Bundles result:', result);
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle('your-w-idgetsbundle-id').subscribe(result => {
  console.log('Fetched  Wid Fetched s Bundle result:', result);
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle('your-w-idgetsbundle-id').subscribe(result => {
  console.log('export Wid Fetched s Bundle result:', result);
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle('your-widgetsbundle-value').subscribe(result => {
  console.log('Saved  Wid Fetched s Bundle result:', result);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes('your-w-idgetsbundle-id', 'your-widgettypeids-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns('your-w-idgetsbundle-id', 'your-widgettypefqns-value').subscribe(result => {
  console.log('Operation completed:', result);
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes('your-w-idgetsbundle-id').subscribe(result => {
  console.log('Fetched  Bundle Wid Fetched  Types result:', result);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails('your-w-idgetsbundle-id').subscribe(result => {
  console.log('export Bundle Wid Fetched  Types Details result:', result);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns('your-w-idgetsbundle-id').subscribe(result => {
  console.log('Fetched  Bundle Wid Fetched  Type Fqns result:', result);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList('your-w-idgetsbundle-id').subscribe(info => {
  console.log('Fetched  Bundle Wid Fetched  Type Infos List info:', info);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
widgetService.getBundleWidgetTypeInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-w-idgetsbundle-id', 'your-widgettypes-value').subscribe(info => {
  console.log('Fetched  Bundle Wid Fetched  Type Infos info:', info);
});
```

**16. getWidgetType**

```javascript
widgetService.getWidgetType('your-fullfqn-value').subscribe(result => {
  console.log('Fetched  Wid Fetched  Type result:', result);
});
```

**17. saveWidgetTypeDetails**

```javascript
widgetService.saveWidgetTypeDetails('your-widgetinfo-value', 'your--id', 0, 0).subscribe(result => {
  console.log('Saved  Wid Fetched  Type Details result:', result);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails('your-widgettypedetails-value').subscribe(result => {
  console.log('Saved  Imported Wid Fetched  Type Details result:', result);
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById('your-w-idgettype-id').subscribe(result => {
  console.log('Fetched  Wid Fetched  Type By Id result:', result);
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType('your-w-idgettype-id').subscribe(result => {
  console.log('export Wid Fetched  Type result:', result);
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById('your-w-idgettype-id').subscribe(info => {
  console.log('Fetched  Wid Fetched  Type Info By Id info:', info);
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType('your-widgettypedetails-value').subscribe(result => {
  console.log('Saved  Wid Fetched  Type result:', result);
});
```

**23. getWidgetTypes**

```javascript
widgetService.getWidgetTypes(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-widgettypes-value').subscribe(result => {
  console.log('Fetched  Wid Fetched  Types result:', result);
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate('your-widgettypeparam-value').subscribe(result => {
  console.log('Fetched  Wid Fetched  Template result:', result);
});
```

**25. getWidgetInfoFromCache**

```javascript
widgetService.getWidgetInfoFromCache('your-fullfqn-value').subscribe(info => {
  console.log('Fetched  Wid Fetched  Info From Cache info:', info);
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
widgetService.getBasicWidgetSettingsComponentBySelector('your-selector-value').subscribe(settings => {
  console.log('Fetched  Basic Wid Fetched  Settings Component By Selector settings:', settings);
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
widgetService.getWidgetSettingsComponentTypeBySelector('your-selector-value').subscribe(settings => {
  console.log('Fetched  Wid Fetched  Settings Component Type By Selector settings:', settings);
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated('your-updatedwidgettype-value').subscribe(result => {
  console.log('wid Fetched  Type Updated result:', result);
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds('your-widgetsbundleids-value').subscribe(result => {
  console.log('Fetched  Wid Fetched s Bundles By Ids result:', result);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(result => {
  console.log('load Wid Fetched s Bundle Cache result:', result);
});
```

---
