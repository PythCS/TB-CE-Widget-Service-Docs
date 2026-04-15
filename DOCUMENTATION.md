# ThingsBoard CE Widget Service Reference

Complete reference for all ThingsBoard frontend services available in widget development and custom actions. All methods return RxJS Observables — call `.subscribe()` to get results.

Auto-generated from ThingsBoard CE 3.7.x source (widget-services).

---

## USING SERVICES IN WIDGETS/CUSTOM ACTIONS

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

## USING PAGE LINKS

`PageLink` handles pagination — tell the server how many results (`limit`) and where to start (`offset`). Use `self.ctx.pageLink(limit, offset, searchText, sortProperty, sortOrder)` to build one.

```javascript
const pageLink = self.ctx.pageLink(10, 0, null, 'name', 'ASC');
userService.getUsers(pageLink).subscribe(users => {
  console.log('Users:', users);
});
```

`TimePageLink` adds time-range filtering — use it for audit logs, events, etc. that need a start/end timestamp.

---

## SERVICE REFERENCE

- [AdminService](#adminservice)
- [AiModelService](#aimodelservice)
- [AlarmCommentService](#alarmcommentservice)
- [AlarmRulesService](#alarmrulesservice)
- [AlarmService](#alarmservice)
- [ApiKeyService](#apikeyservice)
- [AssetProfileService](#assetprofileservice)
- [AssetService](#assetservice)
- [AttributeService](#attributeservice)
- [AuditLogService](#auditlogservice)
- [CalculatedFieldsService](#calculatedfieldsservice)
- [ComponentDescriptorService](#componentdescriptorservice)
- [CustomerService](#customerservice)
- [DashboardService](#dashboardservice)
- [DeviceProfileService](#deviceprofileservice)
- [DeviceService](#deviceservice)
- [DomainService](#domainservice)
- [EdgeService](#edgeservice)
- [EntitiesVersionControlService](#entitiesversioncontrolservice)
- [EntityRelationService](#entityrelationservice)
- [EntityService](#entityservice)
- [EntityViewService](#entityviewservice)
- [EventService](#eventservice)
- [GitHubService](#githubservice)
- [ImageService](#imageservice)
- [MobileAppService](#mobileappservice)
- [MobileApplicationService](#mobileapplicationservice)
- [NotificationService](#notificationservice)
- [OAuth2Service](#oauth2service)
- [OtaPackageService](#otapackageservice)
- [QueueService](#queueservice)
- [ResourceService](#resourceservice)
- [RuleChainService](#rulechainservice)
- [TenantProfileService](#tenantprofileservice)
- [TenantService](#tenantservice)
- [TrendzSettingsService](#trendzsettingsservice)
- [TwoFactorAuthenticationService](#twofactorauthenticationservice)
- [UiSettingsService](#uisettingsservice)
- [UsageInfoService](#usageinfoservice)
- [UserService](#userservice)
- [UserSettingsService](#usersettingsservice)
- [WidgetService](#widgetservice)

---

### **ADMINSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
adminService.sendTestMail(/* adminSettings */ null).subscribe(testMail => {
  console.log('sendTestMail:', testMail);
});
```

**2. sendTestSms**

```javascript
adminService.sendTestSms(/* testSmsRequest */ null).subscribe(testSms => {
  console.log('sendTestSms:', testSms);
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings().subscribe(securitySettings => {
  console.log('SecuritySettings:', securitySettings);
});
```

**4. saveSecuritySettings**

```javascript
adminService.saveSecuritySettings(/* securitySettings */ null).subscribe(securitySettings => {
  console.log('SecuritySettings:', securitySettings);
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings().subscribe(jwtSettings => {
  console.log('JwtSettings:', jwtSettings);
});
```

**6. saveJwtSettings**

```javascript
adminService.saveJwtSettings(/* jwtSettings */ null).subscribe(jwtSettings => {
  console.log('JwtSettings:', jwtSettings);
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(repositorySettings => {
  console.log('RepositorySettings:', repositorySettings);
});
```

**8. saveRepositorySettings**

```javascript
adminService.saveRepositorySettings(/* repositorySettings */ null).subscribe(repositorySettings => {
  console.log('RepositorySettings:', repositorySettings);
});
```

**9. checkRepositoryAccess**

```javascript
adminService.checkRepositoryAccess(/* repositorySettings */ null).subscribe(checkRepositoryAccess => {
  console.log('checkRepositoryAccess:', checkRepositoryAccess);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(repositorySettingsInfo => {
  console.log('RepositorySettings:', repositorySettingsInfo);
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(autoCommitSettings => {
  console.log('AutoCommitSettings:', autoCommitSettings);
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(autoCommitSettingsExists => {
  console.log('autoCommitSettingsExists:', autoCommitSettingsExists);
});
```

**13. saveAutoCommitSettings**

```javascript
adminService.saveAutoCommitSettings(/* autoCommitSettings */ null).subscribe(autoCommitSettings => {
  console.log('AutoCommitSettings:', autoCommitSettings);
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(checkUpdates => {
  console.log('checkUpdates:', checkUpdates);
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(featuresInfo => {
  console.log('Features:', featuresInfo);
});
```

**16. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('LoginProcessingUrl:', loginProcessingUrl);
});
```

**17. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(accessToken => {
  console.log('generateAccessToken:', accessToken);
});
```

**18. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(mailConfigTemplate => {
  console.log('MailConfigTemplate:', mailConfigTemplate);
});
```

---
### **AIMODELSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

**1. saveAiModel**

```javascript
aiModelService.saveAiModel(/* aiModel */ null).subscribe(aiModel => {
  console.log('AiModel:', aiModel);
});
```

**2. getAiModels**

```javascript
aiModelService.getAiModels(self.ctx.pageLink(10, 0, null, null, null)).subscribe(aiModels => {
  console.log('AiModels:', aiModels);
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById(/* aiModelId */ null).subscribe(aiModelById => {
  console.log('AiModelById:', aiModelById);
});
```

**4. checkConnectivity**

```javascript
aiModelService.checkConnectivity(/* aiModelWithUserMsg */ null).subscribe(checkConnectivity => {
  console.log('checkConnectivity:', checkConnectivity);
});
```

---
### **ALARMCOMMENTSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

**1. saveAlarmComment**

```javascript
alarmCommentService.saveAlarmComment(/* alarmId */ null, /* alarmComment */ null).subscribe(alarmComment => {
  console.log('AlarmComment:', alarmComment);
});
```

**2. getAlarmComments**

```javascript
alarmCommentService.getAlarmComments(/* alarmId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(alarmComments => {
  console.log('AlarmComments:', alarmComments);
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments(/* alarmId */ null, /* commentId */ null).subscribe(alarmComments => {
  console.log('AlarmComments:', alarmComments);
});
```

---
### **ALARMRULESSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
alarmRulesService.getAlarmRuleById(/* alarmRuleId */ null).subscribe(alarmRuleById => {
  console.log('AlarmRuleById:', alarmRuleById);
});
```

**2. saveAlarmRule**

```javascript
alarmRulesService.saveAlarmRule(/* alarmRule */ null).subscribe(alarmRule => {
  console.log('AlarmRule:', alarmRule);
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule(/* alarmRuleId */ null).subscribe(alarmRule => {
  console.log('AlarmRule:', alarmRule);
});
```

**4. getAlarmRules**

```javascript
alarmRulesService.getAlarmRules(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(alarmRules => {
  console.log('AlarmRules:', alarmRules);
});
```

**5. getAlarmRulesByEntityId**

```javascript
alarmRulesService.getAlarmRulesByEntityId(self.ctx.pageLink(10, 0, null, null, null)).subscribe(alarmRulesByEntityId => {
  console.log('AlarmRulesByEntityId:', alarmRulesByEntityId);
});
```

**6. testScript**

```javascript
alarmRulesService.testScript(/* inputParams */ null).subscribe(script => {
  console.log('testScript:', script);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent(/* id */ null).subscribe(laAlarmRuleDebugEvent => {
  console.log('LatestAlarmRuleDebugEvent:', laAlarmRuleDebugEvent);
});
```

**8. getAlarmRuleNames**

```javascript
alarmRulesService.getAlarmRuleNames(self.ctx.pageLink(10, 0, null, null, null)).subscribe(alarmRuleNames => {
  console.log('AlarmRuleNames:', alarmRuleNames);
});
```

---
### **ALARMSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

**1. getAlarm**

```javascript
alarmService.getAlarm(/* alarmId */ null).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo(/* alarmId */ null).subscribe(alarmInfo => {
  console.log('Alarm:', alarmInfo);
});
```

**3. saveAlarm**

```javascript
alarmService.saveAlarm(/* alarm */ null).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm(/* alarmId */ null).subscribe(alarm => {
  console.log('ackAlarm:', alarm);
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm(/* alarmId */ null).subscribe(alarm => {
  console.log('clearAlarm:', alarm);
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm(/* alarmId */ null, /* assigneeId */ null).subscribe(alarm => {
  console.log('assignAlarm:', alarm);
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm(/* alarmId */ null).subscribe(unAlarm => {
  console.log('unassignAlarm:', unAlarm);
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm(/* alarmId */ null).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

**9. getAlarms**

```javascript
alarmService.getAlarms(null).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

**10. getAlarmsV2**

```javascript
alarmService.getAlarmsV2(null).subscribe(alarmsV2 => {
  console.log('Alarms v2:', alarmsV2);
});
```

**11. getAllAlarms**

```javascript
alarmService.getAllAlarms(null).subscribe(allAlarms => {
  console.log('AllAlarms:', allAlarms);
});
```

**12. getAllAlarmsV2**

```javascript
alarmService.getAllAlarmsV2(null).subscribe(allAlarmsV2 => {
  console.log('AllAlarms v2:', allAlarmsV2);
});
```

**13. getHighestAlarmSeverity**

```javascript
alarmService.getHighestAlarmSeverity(entityId, /* alarmSearchStatus */ null, /* alarmStatus */ null).subscribe(highestAlarmSeverity => {
  console.log('HighestAlarmSeverity:', highestAlarmSeverity);
});
```

**14. getAlarmTypes**

```javascript
alarmService.getAlarmTypes(self.ctx.pageLink(10, 0, null, null, null)).subscribe(alarmTypes => {
  console.log('AlarmTypes:', alarmTypes);
});
```

---
### **APIKEYSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
apiKeyService.saveApiKey(/* apiKey */ null).subscribe(apiKey => {
  console.log('ApiKey:', apiKey);
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey(/* id */ null).subscribe(apiKey => {
  console.log('ApiKey:', apiKey);
});
```

**3. updateApiKeyDescription**

```javascript
apiKeyService.updateApiKeyDescription(/* id */ null, /* description */ null).subscribe(apiKeyDescription => {
  console.log('updateApiKeyDescription:', apiKeyDescription);
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey(/* id */ null, true).subscribe(enableApiKey => {
  console.log('enableApiKey:', enableApiKey);
});
```

**5. getUserApiKeys**

```javascript
apiKeyService.getUserApiKeys(/* userId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(userApiKeys => {
  console.log('UserApiKeys:', userApiKeys);
});
```

---
### **ASSETPROFILESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
assetProfileService.getAssetProfiles(self.ctx.pageLink(10, 0, null, null, null)).subscribe(asProfiles => {
  console.log('AssetProfiles:', asProfiles);
});
```

**2. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds(['id1', 'id2']).subscribe(asProfilesByIds => {
  console.log('AssetProfilesByIds:', asProfilesByIds);
});
```

**3. getAssetProfile**

```javascript
assetProfileService.getAssetProfile(/* assetProfileId */ null).subscribe(asProfile => {
  console.log('AssetProfile:', asProfile);
});
```

**4. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile(/* assetProfileId */ null).subscribe(exportAsProfile => {
  console.log('exportAssetProfile:', exportAsProfile);
});
```

**5. saveAssetProfile**

```javascript
assetProfileService.saveAssetProfile(/* assetProfile */ null).subscribe(asProfile => {
  console.log('AssetProfile:', asProfile);
});
```

**6. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile(/* assetProfileId */ null).subscribe(defaultAsProfile => {
  console.log('setDefaultAssetProfile:', defaultAsProfile);
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(defaultAsProfileInfo => {
  console.log('DefaultAssetProfile:', defaultAsProfileInfo);
});
```

**8. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo(/* assetProfileId */ null).subscribe(asProfileInfo => {
  console.log('AssetProfile:', asProfileInfo);
});
```

**9. getAssetProfileInfos**

```javascript
assetProfileService.getAssetProfileInfos(self.ctx.pageLink(10, 0, null, null, null)).subscribe(asProfileInfos => {
  console.log('AssetProfile infos:', asProfileInfos);
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames(null).subscribe(asProfileNames => {
  console.log('AssetProfileNames:', asProfileNames);
});
```

---
### **ASSETSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('assetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```


**1. getTenantAssetInfos**

```javascript
assetService.getTenantAssetInfos(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantAsInfos => {
  console.log('TenantAsset infos:', tenantAsInfos);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
assetService.getTenantAssetInfosByAssetProfileId(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantAsInfosByAsProfileId => {
  console.log('TenantAsset infosByAssetProfileId:', tenantAsInfosByAsProfileId);
});
```

**3. getCustomerAssetInfos**

```javascript
assetService.getCustomerAssetInfos(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(customerAsInfos => {
  console.log('CustomerAsset infos:', customerAsInfos);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
assetService.getCustomerAssetInfosByAssetProfileId(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(customerAsInfosByAsProfileId => {
  console.log('CustomerAsset infosByAssetProfileId:', customerAsInfosByAsProfileId);
});
```

**5. getAsset**

```javascript
assetService.getAsset(/* assetId */ null).subscribe(as => {
  console.log('Asset:', as);
});
```

**6. getAssets**

```javascript
assetService.getAssets(['id1', 'id2']).subscribe(ass => {
  console.log('Assets:', ass);
});
```

**7. getAssetInfo**

```javascript
assetService.getAssetInfo(/* assetId */ null).subscribe(asInfo => {
  console.log('Asset:', asInfo);
});
```

**8. saveAsset**

```javascript
assetService.saveAsset(/* asset */ null).subscribe(as => {
  console.log('Asset:', as);
});
```

**9. getAssetTypes**

```javascript
assetService.getAssetTypes().subscribe(asTypes => {
  console.log('AssetTypes:', asTypes);
});
```

**10. makeAssetPublic**

```javascript
assetService.makeAssetPublic(/* assetId */ null).subscribe(asPublic => {
  console.log('makeAssetPublic:', asPublic);
});
```

**11. assignAssetToCustomer**

```javascript
assetService.assignAssetToCustomer(/* customerId */ null, /* assetId */ null).subscribe(asToCustomer => {
  console.log('assignAssetToCustomer:', asToCustomer);
});
```

**12. findByQuery**

```javascript
assetService.findByQuery(null).subscribe(byQuery => {
  console.log('ByQuery:', byQuery);
});
```

**13. findByName**

```javascript
assetService.findByName(/* assetName */ null).subscribe(byName => {
  console.log('ByName:', byName);
});
```

**14. assignAssetToEdge**

```javascript
assetService.assignAssetToEdge(/* edgeId */ null, /* assetId */ null).subscribe(asToEdge => {
  console.log('assignAssetToEdge:', asToEdge);
});
```

**15. getEdgeAssets**

```javascript
assetService.getEdgeAssets(/* edgeId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(edgeAss => {
  console.log('EdgeAssets:', edgeAss);
});
```

**16. bulkImportAssets**

```javascript
assetService.bulkImportAssets(/* entitiesData */ null).subscribe(bulkImportAss => {
  console.log('bulkImportAssets:', bulkImportAss);
});
```

---
### **ATTRIBUTESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```


**1. getEntityAttributes**

```javascript
attributeService.getEntityAttributes(entityId, null, ['id1', 'id2']).subscribe(entityAttributes => {
  console.log('EntityAttributes:', entityAttributes);
});
```

**2. deleteEntityAttributes**

```javascript
attributeService.deleteEntityAttributes(entityId, null, /* attributes */ null).subscribe(entityAttributes => {
  console.log('EntityAttributes:', entityAttributes);
});
```

**3. deleteEntityTimeseries**

```javascript
attributeService.deleteEntityTimeseries(entityId, /* timeseries */ null, 0, 0).subscribe(entityTimeseries => {
  console.log('EntityTimeseries:', entityTimeseries);
});
```

**4. saveEntityAttributes**

```javascript
attributeService.saveEntityAttributes(entityId, null, /* attributes */ null).subscribe(entityAttributes => {
  console.log('EntityAttributes:', entityAttributes);
});
```

**5. saveEntityTimeseries**

```javascript
attributeService.saveEntityTimeseries(entityId, /* timeseriesScope */ null, /* timeseries */ null).subscribe(entityTimeseries => {
  console.log('EntityTimeseries:', entityTimeseries);
});
```

**6. getEntityTimeseries**

```javascript
attributeService.getEntityTimeseries(entityId, ['id1', 'id2'], 0, 0, null, null, 0, null, null).subscribe(entityTimeseries => {
  console.log('EntityTimeseries:', entityTimeseries);
});
```

**7. getEntityTimeseriesLatest**

```javascript
attributeService.getEntityTimeseriesLatest(entityId, ['id1', 'id2']).subscribe(entityTimeseriesLa => {
  console.log('EntityTimeseriesLatest:', entityTimeseriesLa);
});
```

---
### **AUDITLOGSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
```

**1. getAuditLogs**

```javascript
auditLogService.getAuditLogs(self.ctx.pageLink(10, 0, null, null, null)).subscribe(auditLogs => {
  console.log('AuditLogs:', auditLogs);
});
```

**2. getAuditLogsByCustomerId**

```javascript
auditLogService.getAuditLogsByCustomerId(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(auditLogsByCustomerId => {
  console.log('AuditLogsByCustomerId:', auditLogsByCustomerId);
});
```

**3. getAuditLogsByUserId**

```javascript
auditLogService.getAuditLogsByUserId(/* userId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(auditLogsByUserId => {
  console.log('AuditLogsByUserId:', auditLogsByUserId);
});
```

**4. getAuditLogsByEntityId**

```javascript
auditLogService.getAuditLogsByEntityId(entityId, self.ctx.pageLink(10, 0, null, null, null)).subscribe(auditLogsByEntityId => {
  console.log('AuditLogsByEntityId:', auditLogsByEntityId);
});
```

---
### **CALCULATEDFIELDSSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
calculatedFieldsService.getCalculatedFieldById(/* calculatedFieldId */ null).subscribe(calculatedFieldById => {
  console.log('CalculatedFieldById:', calculatedFieldById);
});
```

**2. saveCalculatedField**

```javascript
calculatedFieldsService.saveCalculatedField(/* calculatedField */ null).subscribe(calculatedField => {
  console.log('CalculatedField:', calculatedField);
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField(/* calculatedFieldId */ null).subscribe(calculatedField => {
  console.log('CalculatedField:', calculatedField);
});
```

**4. getCalculatedFields**

```javascript
calculatedFieldsService.getCalculatedFields(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(calculatedFields => {
  console.log('CalculatedFields:', calculatedFields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
calculatedFieldsService.getCalculatedFieldsByEntityId(self.ctx.pageLink(10, 0, null, null, null), /* type */ null).subscribe(calculatedFieldsByEntityId => {
  console.log('CalculatedFieldsByEntityId:', calculatedFieldsByEntityId);
});
```

**6. testScript**

```javascript
calculatedFieldsService.testScript(/* inputParams */ null).subscribe(script => {
  console.log('testScript:', script);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent(/* id */ null).subscribe(laCalculatedFieldDebugEvent => {
  console.log('LatestCalculatedFieldDebugEvent:', laCalculatedFieldDebugEvent);
});
```

**8. getCalculatedFieldNames**

```javascript
calculatedFieldsService.getCalculatedFieldNames(self.ctx.pageLink(10, 0, null, null, null), /* type */ null).subscribe(calculatedFieldNames => {
  console.log('CalculatedFieldNames:', calculatedFieldNames);
});
```

---
### **COMPONENTDESCRIPTORSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
componentDescriptorService.getComponentDescriptorsByType(null, null).subscribe(componentDescriptorsByType => {
  console.log('ComponentDescriptorsByType:', componentDescriptorsByType);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes(/* componentTypes */ null, null).subscribe(componentDescriptorsByTypes => {
  console.log('ComponentDescriptorsByTypes:', componentDescriptorsByTypes);
});
```

**3. getComponentDescriptorByClazz**

```javascript
componentDescriptorService.getComponentDescriptorByClazz(/* componentDescriptorClazz */ null).subscribe(componentDescriptorByClazz => {
  console.log('ComponentDescriptorByClazz:', componentDescriptorByClazz);
});
```

---
### **CUSTOMERSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('customerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```


**1. getCustomers**

```javascript
customerService.getCustomers(self.ctx.pageLink(10, 0, null, null, null)).subscribe(customers => {
  console.log('Customers:', customers);
});
```

**2. getCustomer**

```javascript
customerService.getCustomer(/* customerId */ null).subscribe(customer => {
  console.log('Customer:', customer);
});
```

**3. getCustomersByIds**

```javascript
customerService.getCustomersByIds(['id1', 'id2']).subscribe(customersByIds => {
  console.log('CustomersByIds:', customersByIds);
});
```

**4. saveCustomer**

```javascript
customerService.saveCustomer(/* customer */ null).subscribe(customer => {
  console.log('Customer:', customer);
});
```

---
### **DASHBOARDSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```


**1. getTenantDashboards**

```javascript
dashboardService.getTenantDashboards(self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantDashboards => {
  console.log('TenantDashboards:', tenantDashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
dashboardService.getTenantDashboardsByTenantId(/* tenantId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantDashboardsByTenantId => {
  console.log('TenantDashboardsByTenantId:', tenantDashboardsByTenantId);
});
```

**3. getCustomerDashboards**

```javascript
dashboardService.getCustomerDashboards(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(customerDashboards => {
  console.log('CustomerDashboards:', customerDashboards);
});
```

**4. getDashboard**

```javascript
dashboardService.getDashboard(/* dashboardId */ null).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
dashboardService.exportDashboard(/* dashboardId */ null).subscribe(exportDashboard => {
  console.log('exportDashboard:', exportDashboard);
});
```

**6. getDashboardInfo**

```javascript
dashboardService.getDashboardInfo(/* dashboardId */ null).subscribe(dashboardInfo => {
  console.log('Dashboard:', dashboardInfo);
});
```

**7. getDashboards**

```javascript
dashboardService.getDashboards(['id1', 'id2']).subscribe(dashboards => {
  console.log('Dashboards:', dashboards);
});
```

**8. saveDashboard**

```javascript
dashboardService.saveDashboard(/* dashboard */ null).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
dashboardService.assignDashboardToCustomer(/* customerId */ null, /* dashboardId */ null).subscribe(dashboardToCustomer => {
  console.log('assignDashboardToCustomer:', dashboardToCustomer);
});
```

**10. makeDashboardPublic**

```javascript
dashboardService.makeDashboardPublic(/* dashboardId */ null).subscribe(dashboardPublic => {
  console.log('makeDashboardPublic:', dashboardPublic);
});
```

**11. makeDashboardPrivate**

```javascript
dashboardService.makeDashboardPrivate(/* dashboardId */ null).subscribe(dashboardPrivate => {
  console.log('makeDashboardPrivate:', dashboardPrivate);
});
```

**12. updateDashboardCustomers**

```javascript
dashboardService.updateDashboardCustomers(/* dashboardId */ null, ['id1', 'id2']).subscribe(dashboardCustomers => {
  console.log('updateDashboardCustomers:', dashboardCustomers);
});
```

**13. addDashboardCustomers**

```javascript
dashboardService.addDashboardCustomers(/* dashboardId */ null, ['id1', 'id2']).subscribe(addDashboardCustomers => {
  console.log('addDashboardCustomers:', addDashboardCustomers);
});
```

**14. removeDashboardCustomers**

```javascript
dashboardService.removeDashboardCustomers(/* dashboardId */ null, ['id1', 'id2']).subscribe(removeDashboardCustomers => {
  console.log('removeDashboardCustomers:', removeDashboardCustomers);
});
```

**15. getHomeDashboard**

```javascript
dashboardService.getHomeDashboard().subscribe(homeDashboard => {
  console.log('HomeDashboard:', homeDashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
dashboardService.getTenantHomeDashboardInfo().subscribe(tenantHomeDashboardInfo => {
  console.log('TenantHomeDashboard:', tenantHomeDashboardInfo);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
dashboardService.setTenantHomeDashboardInfo(/* homeDashboardInfo */ null).subscribe(tenantHomeDashboardInfo => {
  console.log('setTenantHomeDashboard:', tenantHomeDashboardInfo);
});
```

**18. getPublicDashboardLink**

```javascript
dashboardService.getPublicDashboardLink(/* dashboard */ null).subscribe(publicDashboardLink => {
  console.log('PublicDashboardLink:', publicDashboardLink);
});
```

**19. assignDashboardToEdge**

```javascript
dashboardService.assignDashboardToEdge(/* edgeId */ null, /* dashboardId */ null).subscribe(dashboardToEdge => {
  console.log('assignDashboardToEdge:', dashboardToEdge);
});
```

---
### **DEVICEPROFILESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
deviceProfileService.getDeviceProfiles(self.ctx.pageLink(10, 0, null, null, null)).subscribe(deviceProfiles => {
  console.log('DeviceProfiles:', deviceProfiles);
});
```

**2. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds(['id1', 'id2']).subscribe(deviceProfilesByIds => {
  console.log('DeviceProfilesByIds:', deviceProfilesByIds);
});
```

**3. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile(/* deviceProfileId */ null).subscribe(deviceProfile => {
  console.log('DeviceProfile:', deviceProfile);
});
```

**4. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile(/* deviceProfileId */ null).subscribe(exportDeviceProfile => {
  console.log('exportDeviceProfile:', exportDeviceProfile);
});
```

**5. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects(null, ['id1', 'id2'], /* searchText */ null).subscribe(lwm2mObjects => {
  console.log('Lwm2mObjects:', lwm2mObjects);
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true).subscribe(lwm2mBootstrapSecurityInfo => {
  console.log('Lwm2mBootstrapSecurity:', lwm2mBootstrapSecurityInfo);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true).subscribe(lwm2mBootstrapSecurityInfoBySecurityType => {
  console.log('Lwm2mBootstrapSecurity infoBySecurityType:', lwm2mBootstrapSecurityInfoBySecurityType);
});
```

**8. getLwm2mObjectsPage**

```javascript
deviceProfileService.getLwm2mObjectsPage(self.ctx.pageLink(10, 0, null, null, null)).subscribe(lwm2mObjectsPage => {
  console.log('Lwm2mObjectsPage:', lwm2mObjectsPage);
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceProfileService.saveDeviceProfileAndConfirmOtaChange(/* originDeviceProfile */ null, /* deviceProfile */ null).subscribe(deviceProfileAndConfirmOtaChange => {
  console.log('DeviceProfile ConfirmOtaChange:', deviceProfileAndConfirmOtaChange);
});
```

**10. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(deviceProfile => {
  console.log('DeviceProfile:', deviceProfile);
});
```

**11. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile(/* deviceProfileId */ null).subscribe(defaultDeviceProfile => {
  console.log('setDefaultDeviceProfile:', defaultDeviceProfile);
});
```

**12. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(defaultDeviceProfileInfo => {
  console.log('DefaultDeviceProfile:', defaultDeviceProfileInfo);
});
```

**13. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo(/* deviceProfileId */ null).subscribe(deviceProfileInfo => {
  console.log('DeviceProfile:', deviceProfileInfo);
});
```

**14. getDeviceProfileInfos**

```javascript
deviceProfileService.getDeviceProfileInfos(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(deviceProfileInfos => {
  console.log('DeviceProfile infos:', deviceProfileInfos);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys(/* deviceProfileId */ null).subscribe(deviceProfileDevicesAttributesKeys => {
  console.log('DeviceProfileDevicesAttributesKeys:', deviceProfileDevicesAttributesKeys);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys(/* deviceProfileId */ null).subscribe(deviceProfileDevicesTimeseriesKeys => {
  console.log('DeviceProfileDevicesTimeseriesKeys:', deviceProfileDevicesTimeseriesKeys);
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames(null).subscribe(deviceProfileNames => {
  console.log('DeviceProfileNames:', deviceProfileNames);
});
```

---
### **DEVICESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```


**1. getDeviceInfosByQuery**

```javascript
deviceService.getDeviceInfosByQuery(null).subscribe(deviceInfosByQuery => {
  console.log('Device infosByQuery:', deviceInfosByQuery);
});
```

**2. getTenantDeviceInfos**

```javascript
deviceService.getTenantDeviceInfos(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantDeviceInfos => {
  console.log('TenantDevice infos:', tenantDeviceInfos);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
deviceService.getTenantDeviceInfosByDeviceProfileId(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantDeviceInfosByDeviceProfileId => {
  console.log('TenantDevice infosByDeviceProfileId:', tenantDeviceInfosByDeviceProfileId);
});
```

**4. getCustomerDeviceInfos**

```javascript
deviceService.getCustomerDeviceInfos(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(customerDeviceInfos => {
  console.log('CustomerDevice infos:', customerDeviceInfos);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
deviceService.getCustomerDeviceInfosByDeviceProfileId(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(customerDeviceInfosByDeviceProfileId => {
  console.log('CustomerDevice infosByDeviceProfileId:', customerDeviceInfosByDeviceProfileId);
});
```

**6. getDevice**

```javascript
deviceService.getDevice(/* deviceId */ null).subscribe(device => {
  console.log('Device:', device);
});
```

**7. getDevices**

```javascript
deviceService.getDevices(['id1', 'id2']).subscribe(devices => {
  console.log('Devices:', devices);
});
```

**8. getDeviceInfo**

```javascript
deviceService.getDeviceInfo(/* deviceId */ null).subscribe(deviceInfo => {
  console.log('Device:', deviceInfo);
});
```

**9. saveDevice**

```javascript
deviceService.saveDevice(/* device */ null).subscribe(device => {
  console.log('Device:', device);
});
```

**10. saveDeviceWithCredentials**

```javascript
deviceService.saveDeviceWithCredentials(/* device */ null, /* credentials */ null).subscribe(deviceWithCredentials => {
  console.log('DeviceWithCredentials:', deviceWithCredentials);
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes().subscribe(deviceTypes => {
  console.log('DeviceTypes:', deviceTypes);
});
```

**12. getDeviceCredentials**

```javascript
deviceService.getDeviceCredentials(/* deviceId */ null, null).subscribe(deviceCredentials => {
  console.log('DeviceCredentials:', deviceCredentials);
});
```

**13. saveDeviceCredentials**

```javascript
deviceService.saveDeviceCredentials(/* deviceCredentials */ null).subscribe(deviceCredentials => {
  console.log('DeviceCredentials:', deviceCredentials);
});
```

**14. makeDevicePublic**

```javascript
deviceService.makeDevicePublic(/* deviceId */ null).subscribe(devicePublic => {
  console.log('makeDevicePublic:', devicePublic);
});
```

**15. assignDeviceToCustomer**

```javascript
deviceService.assignDeviceToCustomer(/* customerId */ null, /* deviceId */ null).subscribe(deviceToCustomer => {
  console.log('assignDeviceToCustomer:', deviceToCustomer);
});
```

**16. sendOneWayRpcCommand**

```javascript
deviceService.sendOneWayRpcCommand(/* deviceId */ null, /* requestBody */ null).subscribe(oneWayRpcCommand => {
  console.log('sendOneWayRpcCommand:', oneWayRpcCommand);
});
```

**17. sendTwoWayRpcCommand**

```javascript
deviceService.sendTwoWayRpcCommand(/* deviceId */ null, /* requestBody */ null).subscribe(twoWayRpcCommand => {
  console.log('sendTwoWayRpcCommand:', twoWayRpcCommand);
});
```

**18. getPersistedRpc**

```javascript
deviceService.getPersistedRpc(/* rpcId */ null).subscribe(persistedRpc => {
  console.log('PersistedRpc:', persistedRpc);
});
```

**19. getPersistedRpcRequests**

```javascript
deviceService.getPersistedRpcRequests(/* deviceId */ null, self.ctx.pageLink(10, 0, null, null, null), /* rpcStatus */ null).subscribe(persistedRpcRequests => {
  console.log('PersistedRpcRequests:', persistedRpcRequests);
});
```

**20. findByQuery**

```javascript
deviceService.findByQuery(null).subscribe(byQuery => {
  console.log('ByQuery:', byQuery);
});
```

**21. findByName**

```javascript
deviceService.findByName(/* deviceName */ null).subscribe(byName => {
  console.log('ByName:', byName);
});
```

**22. claimDevice**

```javascript
deviceService.claimDevice(/* deviceName */ null, /* claimRequest */ null).subscribe(claimDevice => {
  console.log('claimDevice:', claimDevice);
});
```

**23. assignDeviceToEdge**

```javascript
deviceService.assignDeviceToEdge(/* edgeId */ null, /* deviceId */ null).subscribe(deviceToEdge => {
  console.log('assignDeviceToEdge:', deviceToEdge);
});
```

**24. getEdgeDevices**

```javascript
deviceService.getEdgeDevices(/* edgeId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(edgeDevices => {
  console.log('EdgeDevices:', edgeDevices);
});
```

**25. bulkImportDevices**

```javascript
deviceService.bulkImportDevices(/* entitiesData */ null).subscribe(bulkImportDevices => {
  console.log('bulkImportDevices:', bulkImportDevices);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
deviceService.getDevicePublishTelemetryCommands(/* deviceId */ null).subscribe(devicePublishTelemetryCommands => {
  console.log('DevicePublishTelemetryCommands:', devicePublishTelemetryCommands);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
deviceService.downloadGatewayDockerComposeFile(/* deviceId */ null).subscribe(downGatewayDockerComposeFile => {
  console.log('downloadGatewayDockerComposeFile:', downGatewayDockerComposeFile);
});
```

**28. rebootDevice**

```javascript
deviceService.rebootDevice(/* deviceId */ null, true).subscribe(rebootDevice => {
  console.log('rebootDevice:', rebootDevice);
});
```

**29. rebootTrigger**

```javascript
deviceService.rebootTrigger(/* deviceId */ null, /* resourcePath */ null).subscribe(rebootTrigger => {
  console.log('rebootTrigger:', rebootTrigger);
});
```

---
### **DOMAINSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
domainService.saveDomain(/* domain */ null, ['id1', 'id2']).subscribe(domain => {
  console.log('Domain:', domain);
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients(/* id */ null, ['id1', 'id2']).subscribe(oauth2Clients => {
  console.log('updateOauth2Clients:', oauth2Clients);
});
```

**3. getTenantDomainInfos**

```javascript
domainService.getTenantDomainInfos(self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantDomainInfos => {
  console.log('TenantDomain infos:', tenantDomainInfos);
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById(/* id */ null).subscribe(domainInfoById => {
  console.log('Domain infoById:', domainInfoById);
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain(/* id */ null).subscribe(domain => {
  console.log('Domain:', domain);
});
```

---
### **EDGESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

**1. getEdges**

```javascript
edgeService.getEdges(['id1', 'id2']).subscribe(edges => {
  console.log('Edges:', edges);
});
```

**2. getEdge**

```javascript
edgeService.getEdge(/* edgeId */ null).subscribe(edge => {
  console.log('Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo(/* edgeId */ null).subscribe(edgeInfo => {
  console.log('Edge:', edgeInfo);
});
```

**4. saveEdge**

```javascript
edgeService.saveEdge(/* edge */ null).subscribe(edge => {
  console.log('Edge:', edge);
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes().subscribe(edgeTypes => {
  console.log('EdgeTypes:', edgeTypes);
});
```

**6. getCustomerEdgeInfos**

```javascript
edgeService.getCustomerEdgeInfos(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(customerEdgeInfos => {
  console.log('CustomerEdge infos:', customerEdgeInfos);
});
```

**7. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer(/* customerId */ null, /* edgeId */ null).subscribe(edgeToCustomer => {
  console.log('assignEdgeToCustomer:', edgeToCustomer);
});
```

**8. makeEdgePublic**

```javascript
edgeService.makeEdgePublic(/* edgeId */ null).subscribe(edgePublic => {
  console.log('makeEdgePublic:', edgePublic);
});
```

**9. getTenantEdgeInfos**

```javascript
edgeService.getTenantEdgeInfos(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantEdgeInfos => {
  console.log('TenantEdge infos:', tenantEdgeInfos);
});
```

**10. findByQuery**

```javascript
edgeService.findByQuery(null).subscribe(byQuery => {
  console.log('ByQuery:', byQuery);
});
```

**11. getEdgeEvents**

```javascript
edgeService.getEdgeEvents(entityId, self.ctx.pageLink(10, 0, null, null, null)).subscribe(edgeEvents => {
  console.log('EdgeEvents:', edgeEvents);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains(/* edgeId */ null).subscribe(missingToRelatedRuleChains => {
  console.log('MissingToRelatedRuleChains:', missingToRelatedRuleChains);
});
```

**13. findByName**

```javascript
edgeService.findByName(/* edgeName */ null).subscribe(byName => {
  console.log('ByName:', byName);
});
```

**14. bulkImportEdges**

```javascript
edgeService.bulkImportEdges(/* entitiesData */ null).subscribe(bulkImportEdges => {
  console.log('bulkImportEdges:', bulkImportEdges);
});
```

**15. getEdgeInstallInstructions**

```javascript
edgeService.getEdgeInstallInstructions(/* edgeId */ null, null).subscribe(edgeInstallInstructions => {
  console.log('EdgeInstallInstructions:', edgeInstallInstructions);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
edgeService.getEdgeUpgradeInstructions(/* edgeVersion */ null, null).subscribe(edgeUpgradeInstructions => {
  console.log('EdgeUpgradeInstructions:', edgeUpgradeInstructions);
});
```

**17. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable(/* edgeId */ null).subscribe(isEdgeUpgradeAvailable => {
  console.log('isEdgeUpgradeAvailable:', isEdgeUpgradeAvailable);
});
```

---
### **ENTITIESVERSIONCONTROLSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
```

**1. clearBranchList**

```javascript
entitiesVersionControlService.clearBranchList().subscribe(branchList => {
  console.log('clearBranchList:', branchList);
});
```

**2. listBranches**

```javascript
entitiesVersionControlService.listBranches().subscribe(branches => {
  console.log('listBranches:', branches);
});
```

**3. getEntityDataInfo**

```javascript
entitiesVersionControlService.getEntityDataInfo(entityId, /* versionId */ null).subscribe(entityDataInfo => {
  console.log('EntityData:', entityDataInfo);
});
```

**4. saveEntitiesVersion**

```javascript
entitiesVersionControlService.saveEntitiesVersion(/* request */ null).subscribe(entitiesVersion => {
  console.log('EntitiesVersion:', entitiesVersion);
});
```

**5. getVersionCreateRequestStatus**

```javascript
entitiesVersionControlService.getVersionCreateRequestStatus(/* requestId */ null).subscribe(versionCreateRequestStatus => {
  console.log('VersionCreateRequestStatus:', versionCreateRequestStatus);
});
```

**6. listEntityVersions**

```javascript
entitiesVersionControlService.listEntityVersions(self.ctx.pageLink(10, 0, null, null, null), /* branch */ null, entityId).subscribe(entityVersions => {
  console.log('listEntityVersions:', entityVersions);
});
```

**7. listEntityTypeVersions**

```javascript
entitiesVersionControlService.listEntityTypeVersions(self.ctx.pageLink(10, 0, null, null, null), /* branch */ null, null).subscribe(entityTypeVersions => {
  console.log('listEntityTypeVersions:', entityTypeVersions);
});
```

**8. listVersions**

```javascript
entitiesVersionControlService.listVersions(self.ctx.pageLink(10, 0, null, null, null), /* branch */ null).subscribe(versions => {
  console.log('listVersions:', versions);
});
```

**9. loadEntitiesVersion**

```javascript
entitiesVersionControlService.loadEntitiesVersion(/* request */ null).subscribe(entitiesVersion => {
  console.log('loadEntitiesVersion:', entitiesVersion);
});
```

**10. getVersionLoadRequestStatus**

```javascript
entitiesVersionControlService.getVersionLoadRequestStatus(/* requestId */ null).subscribe(versionLoadRequestStatus => {
  console.log('VersionLoadRequestStatus:', versionLoadRequestStatus);
});
```

**11. compareEntityDataToVersion**

```javascript
entitiesVersionControlService.compareEntityDataToVersion(entityId, /* versionId */ null).subscribe(entityDataToVersion => {
  console.log('compareEntityDataToVersion:', entityDataToVersion);
});
```

**12. entityLoadErrorToMessage**

```javascript
entitiesVersionControlService.entityLoadErrorToMessage(/* entityLoadError */ null).subscribe(entityLoadErrorToMessage => {
  console.log('entityLoadErrorToMessage:', entityLoadErrorToMessage);
});
```

---
### **ENTITYRELATIONSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('entityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```


**1. saveRelation**

```javascript
entityRelationService.saveRelation(/* relation */ null).subscribe(relation => {
  console.log('Relation:', relation);
});
```

**2. getRelation**

```javascript
entityRelationService.getRelation(entityId, /* relationType */ null, entityId).subscribe(relation => {
  console.log('Relation:', relation);
});
```

**3. findByFrom**

```javascript
entityRelationService.findByFrom(entityId).subscribe(byFrom => {
  console.log('ByFrom:', byFrom);
});
```

**4. findInfoByFrom**

```javascript
entityRelationService.findInfoByFrom(entityId).subscribe(infoByFrom => {
  console.log('infoByFrom:', infoByFrom);
});
```

**5. findByFromAndType**

```javascript
entityRelationService.findByFromAndType(entityId, /* relationType */ null).subscribe(byFromAndType => {
  console.log('ByFrom Type:', byFromAndType);
});
```

**6. findByTo**

```javascript
entityRelationService.findByTo(entityId).subscribe(byTo => {
  console.log('ByTo:', byTo);
});
```

**7. findInfoByTo**

```javascript
entityRelationService.findInfoByTo(entityId).subscribe(infoByTo => {
  console.log('infoByTo:', infoByTo);
});
```

**8. findByToAndType**

```javascript
entityRelationService.findByToAndType(entityId, /* relationType */ null).subscribe(byToAndType => {
  console.log('ByTo Type:', byToAndType);
});
```

**9. findByQuery**

```javascript
entityRelationService.findByQuery(null).subscribe(byQuery => {
  console.log('ByQuery:', byQuery);
});
```

**10. findInfoByQuery**

```javascript
entityRelationService.findInfoByQuery(null).subscribe(infoByQuery => {
  console.log('infoByQuery:', infoByQuery);
});
```

---
### **ENTITYVIEWSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('entityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```


**1. getTenantEntityViewInfos**

```javascript
entityViewService.getTenantEntityViewInfos(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantEntityViewInfos => {
  console.log('TenantEntityView infos:', tenantEntityViewInfos);
});
```

**2. getCustomerEntityViewInfos**

```javascript
entityViewService.getCustomerEntityViewInfos(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(customerEntityViewInfos => {
  console.log('CustomerEntityView infos:', customerEntityViewInfos);
});
```

**3. getEntityView**

```javascript
entityViewService.getEntityView(/* entityViewId */ null).subscribe(entityView => {
  console.log('EntityView:', entityView);
});
```

**4. getEntityViews**

```javascript
entityViewService.getEntityViews(['id1', 'id2']).subscribe(entityViews => {
  console.log('EntityViews:', entityViews);
});
```

**5. getEntityViewInfo**

```javascript
entityViewService.getEntityViewInfo(/* entityViewId */ null).subscribe(entityViewInfo => {
  console.log('EntityView:', entityViewInfo);
});
```

**6. saveEntityView**

```javascript
entityViewService.saveEntityView(/* entityView */ null).subscribe(entityView => {
  console.log('EntityView:', entityView);
});
```

**7. getEntityViewTypes**

```javascript
entityViewService.getEntityViewTypes().subscribe(entityViewTypes => {
  console.log('EntityViewTypes:', entityViewTypes);
});
```

**8. makeEntityViewPublic**

```javascript
entityViewService.makeEntityViewPublic(/* entityViewId */ null).subscribe(entityViewPublic => {
  console.log('makeEntityViewPublic:', entityViewPublic);
});
```

**9. assignEntityViewToCustomer**

```javascript
entityViewService.assignEntityViewToCustomer(/* customerId */ null, /* entityViewId */ null).subscribe(entityViewToCustomer => {
  console.log('assignEntityViewToCustomer:', entityViewToCustomer);
});
```

**10. findByQuery**

```javascript
entityViewService.findByQuery(null).subscribe(byQuery => {
  console.log('ByQuery:', byQuery);
});
```

**11. assignEntityViewToEdge**

```javascript
entityViewService.assignEntityViewToEdge(/* edgeId */ null, /* entityViewId */ null).subscribe(entityViewToEdge => {
  console.log('assignEntityViewToEdge:', entityViewToEdge);
});
```

**12. getEdgeEntityViews**

```javascript
entityViewService.getEdgeEntityViews(/* edgeId */ null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(edgeEntityViews => {
  console.log('EdgeEntityViews:', edgeEntityViews);
});
```

---
### **ENTITYSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```


**1. getEntityObservable**

```javascript
entityService.getEntityObservable(null, /* entityId */ null).subscribe(entityObservable => {
  console.log('EntityObservable:', entityObservable);
});
```

**2. getEntity**

```javascript
entityService.getEntity(null, /* entityId */ null).subscribe(entity => {
  console.log('Entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
entityService.getEntitiesObservable(null, ['id1', 'id2']).subscribe(entitiesObservable => {
  console.log('EntitiesObservable:', entitiesObservable);
});
```

**4. getEntities**

```javascript
entityService.getEntities(null, ['id1', 'id2']).subscribe(entities => {
  console.log('Entities:', entities);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
entityService.getSingleTenantByPageLinkObservable(self.ctx.pageLink(10, 0, null, null, null)).subscribe(singleTenantByPageLinkObservable => {
  console.log('SingleTenantByPageLinkObservable:', singleTenantByPageLinkObservable);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
entityService.getSingleCustomerByPageLinkObservable(self.ctx.pageLink(10, 0, null, null, null)).subscribe(singleCustomerByPageLinkObservable => {
  console.log('SingleCustomerByPageLinkObservable:', singleCustomerByPageLinkObservable);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
entityService.getEntitiesByPageLinkObservable(null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(entitiesByPageLinkObservable => {
  console.log('EntitiesByPageLinkObservable:', entitiesByPageLinkObservable);
});
```

**8. getEntitiesByPageLink**

```javascript
entityService.getEntitiesByPageLink(null, self.ctx.pageLink(10, 0, null, null, null), null).subscribe(entitiesByPageLink => {
  console.log('EntitiesByPageLink:', entitiesByPageLink);
});
```

**9. getEntitiesByNameFilter**

```javascript
entityService.getEntitiesByNameFilter(null, /* entityNameFilter */ null, 0, null).subscribe(entitiesByNameFilter => {
  console.log('EntitiesByNameFilter:', entitiesByNameFilter);
});
```

**10. findEntityDataByQuery**

```javascript
entityService.findEntityDataByQuery(null).subscribe(entityDataByQuery => {
  console.log('EntityDataByQuery:', entityDataByQuery);
});
```

**11. findEntityKeysByQuery**

```javascript
entityService.findEntityKeysByQuery(null, null).subscribe(entityKeysByQuery => {
  console.log('EntityKeysByQuery:', entityKeysByQuery);
});
```

**12. findAlarmDataByQuery**

```javascript
entityService.findAlarmDataByQuery(null).subscribe(alarmDataByQuery => {
  console.log('AlarmDataByQuery:', alarmDataByQuery);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
entityService.findEntityInfosByFilterAndName(entityFilter, /* searchText */ null).subscribe(entityInfosByFilterAndName => {
  console.log('Entity infosByFilter Name:', entityInfosByFilterAndName);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
entityService.findSingleEntityInfoByEntityFilter(entityFilter).subscribe(singleEntityInfoByEntityFilter => {
  console.log('SingleEntity infoByEntityFilter:', singleEntityInfoByEntityFilter);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
entityService.getAliasFilterTypesByEntityTypes(/* entityTypes */ null).subscribe(aliasFilterTypesByEntityTypes => {
  console.log('AliasFilterTypesByEntityTypes:', aliasFilterTypesByEntityTypes);
});
```

**16. filterAliasByEntityTypes**

```javascript
entityService.filterAliasByEntityTypes(/* entityAlias */ null, /* entityTypes */ null).subscribe(filterAliasByEntityTypes => {
  console.log('filterAliasByEntityTypes:', filterAliasByEntityTypes);
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
entityService.filterAliasFilterTypeByEntityTypes(/* aliasFilterType */ null, /* entityTypes */ null).subscribe(filterAliasFilterTypeByEntityTypes => {
  console.log('filterAliasFilterTypeByEntityTypes:', filterAliasFilterTypeByEntityTypes);
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
entityService.filterAliasFilterTypeByEntityType(/* aliasFilterType */ null, /* entityType */ null).subscribe(filterAliasFilterTypeByEntityType => {
  console.log('filterAliasFilterTypeByEntityType:', filterAliasFilterTypeByEntityType);
});
```

**19. prepareAllowedEntityTypesList**

```javascript
entityService.prepareAllowedEntityTypesList(/* allowedEntityTypes */ null, false).subscribe(prepareAllowedEntityTypesList => {
  console.log('prepareAllowedEntityTypesList:', prepareAllowedEntityTypesList);
});
```

**20. getEntityFieldKeys**

```javascript
entityService.getEntityFieldKeys(null, null).subscribe(entityFieldKeys => {
  console.log('EntityFieldKeys:', entityFieldKeys);
});
```

**21. getAlarmKeys**

```javascript
entityService.getAlarmKeys(null).subscribe(alarmKeys => {
  console.log('AlarmKeys:', alarmKeys);
});
```

**22. getEntityKeys**

```javascript
entityService.getEntityKeys(entityId, /* query */ null, null).subscribe(entityKeys => {
  console.log('EntityKeys:', entityKeys);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
entityService.getEntityKeysByEntityFilter(entityFilter, /* types */ null, /* entityTypes */ null).subscribe(entityKeysByEntityFilter => {
  console.log('EntityKeysByEntityFilter:', entityKeysByEntityFilter);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
entityService.getEntityKeysByEntityFilterAndScope(entityFilter, /* types */ null, /* entityTypes */ null, null).subscribe(entityKeysByEntityFilterAndScope => {
  console.log('EntityKeysByEntityFilter Scope:', entityKeysByEntityFilterAndScope);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
entityService.createDatasourcesFromSubscriptionsInfo(/* subscriptionsInfo */ null).subscribe(datasourcesFromSubscriptionsInfo => {
  console.log('createDatasourcesFromSubscriptions:', datasourcesFromSubscriptionsInfo);
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
entityService.createAlarmSourceFromSubscriptionInfo(/* subscriptionInfo */ null).subscribe(alarmSourceFromSubscriptionInfo => {
  console.log('createAlarmSourceFromSubscription:', alarmSourceFromSubscriptionInfo);
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
entityService.getAssignedToEdgeEntitiesByType(/* edgeId */ null, null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(assignedToEdgeEntitiesByType => {
  console.log('AssignedToEdgeEntitiesByType:', assignedToEdgeEntitiesByType);
});
```

**28. case**

```javascript
entityService.case().subscribe(case => {
  console.log('case:', case);
});
```

**29. getEntitySubtypesObservable**

```javascript
entityService.getEntitySubtypesObservable(null).subscribe(entitySubtypesObservable => {
  console.log('EntitySubtypesObservable:', entitySubtypesObservable);
});
```

---
### **EVENTSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
eventService.getEvents(entityId, /* eventType */ null, /* tenantId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(events => {
  console.log('Events:', events);
});
```

**2. getFilterEvents**

```javascript
eventService.getFilterEvents(entityId, /* eventType */ null, /* tenantId */ null, /* filters */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(filterEvents => {
  console.log('FilterEvents:', filterEvents);
});
```

---
### **GITHUBSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
```

**1. getGitHubStar**

```javascript
gitHubService.getGitHubStar().subscribe(gitHubStar => {
  console.log('GitHubStar:', gitHubStar);
});
```

---
### **IMAGESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
```

**1. uploadImage**

```javascript
imageService.uploadImage(/* file */ null, /* title */ null, null).subscribe(upImage => {
  console.log('uploadImage:', upImage);
});
```

**2. updateImage**

```javascript
imageService.updateImage(null, /* key */ null, /* file */ null).subscribe(image => {
  console.log('updateImage:', image);
});
```

**3. updateImageInfo**

```javascript
imageService.updateImageInfo(/* imageInfo */ null).subscribe(imageInfo => {
  console.log('updateImage:', imageInfo);
});
```

**4. updateImagePublicStatus**

```javascript
imageService.updateImagePublicStatus(/* imageInfo */ null, true).subscribe(imagePublicStatus => {
  console.log('updateImagePublicStatus:', imagePublicStatus);
});
```

**5. getImages**

```javascript
imageService.getImages(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(images => {
  console.log('Images:', images);
});
```

**6. getImageInfo**

```javascript
imageService.getImageInfo(null, /* key */ null).subscribe(imageInfo => {
  console.log('Image:', imageInfo);
});
```

**7. getImageDataUrl**

```javascript
imageService.getImageDataUrl(/* imageUrl */ null).subscribe(imageDataUrl => {
  console.log('ImageDataUrl:', imageDataUrl);
});
```

**8. loadImageDataUrl**

```javascript
imageService.loadImageDataUrl(/* imageLink */ null).subscribe(imageDataUrl => {
  console.log('loadImageDataUrl:', imageDataUrl);
});
```

**9. getImageString**

```javascript
imageService.getImageString(/* imageUrl */ null).subscribe(imageString => {
  console.log('ImageString:', imageString);
});
```

**10. resolveImageUrl**

```javascript
imageService.resolveImageUrl(/* imageUrl */ null).subscribe(imageUrl => {
  console.log('resolveImageUrl:', imageUrl);
});
```

**11. downloadImage**

```javascript
imageService.downloadImage(null, /* key */ null).subscribe(downImage => {
  console.log('downloadImage:', downImage);
});
```

**12. exportImage**

```javascript
imageService.exportImage(null, /* key */ null).subscribe(exportImage => {
  console.log('exportImage:', exportImage);
});
```

**13. importImage**

```javascript
imageService.importImage(/* imageData */ null).subscribe(importImage => {
  console.log('importImage:', importImage);
});
```

---
### **MOBILEAPPSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
mobileAppService.saveMobileApp(/* mobileApp */ null).subscribe(mobileApp => {
  console.log('MobileApp:', mobileApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
mobileAppService.getTenantMobileAppInfos(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantMobileAppInfos => {
  console.log('TenantMobileApp infos:', tenantMobileAppInfos);
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById(/* id */ null).subscribe(mobileAppInfoById => {
  console.log('MobileApp infoById:', mobileAppInfoById);
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp(/* id */ null).subscribe(mobileApp => {
  console.log('MobileApp:', mobileApp);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
mobileAppService.getTenantMobileAppBundleInfos(self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantMobileAppBundleInfos => {
  console.log('TenantMobileAppBundle infos:', tenantMobileAppBundleInfos);
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById(/* id */ null).subscribe(mobileAppBundleInfoById => {
  console.log('MobileAppBundle infoById:', mobileAppBundleInfoById);
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle(/* id */ null).subscribe(mobileAppBundle => {
  console.log('MobileAppBundle:', mobileAppBundle);
});
```

---
### **MOBILEAPPLICATIONSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
mobileApplicationService.getMobileAppSettings().subscribe(mobileAppSettings => {
  console.log('MobileAppSettings:', mobileAppSettings);
});
```

**2. saveMobileAppSettings**

```javascript
mobileApplicationService.saveMobileAppSettings(/* mobileAppSettings */ null).subscribe(mobileAppSettings => {
  console.log('MobileAppSettings:', mobileAppSettings);
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(mobileAppDeepLink => {
  console.log('MobileAppDeepLink:', mobileAppDeepLink);
});
```

---
### **NOTIFICATIONSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
notificationService.getNotifications(self.ctx.pageLink(10, 0, null, null, null)).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification(/* id */ null).subscribe(notification => {
  console.log('Notification:', notification);
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead(/* id */ null).subscribe(markNotificationAsRead => {
  console.log('markNotificationAsRead:', markNotificationAsRead);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(markAllNotificationsAsRead => {
  console.log('markAllNotificationsAsRead:', markAllNotificationsAsRead);
});
```

**5. createNotificationRequest**

```javascript
notificationService.createNotificationRequest(/* notification */ null).subscribe(notificationRequest => {
  console.log('createNotificationRequest:', notificationRequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest(null).subscribe(entitiesLimitIncreaseRequest => {
  console.log('sendEntitiesLimitIncreaseRequest:', entitiesLimitIncreaseRequest);
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById(/* id */ null).subscribe(notificationRequestById => {
  console.log('NotificationRequestById:', notificationRequestById);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(availableDeliveryMethods => {
  console.log('AvailableDeliveryMethods:', availableDeliveryMethods);
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest(/* id */ null).subscribe(notificationRequest => {
  console.log('NotificationRequest:', notificationRequest);
});
```

**10. getNotificationRequestPreview**

```javascript
notificationService.getNotificationRequestPreview(/* notification */ null).subscribe(notificationRequestPreview => {
  console.log('NotificationRequestPreview:', notificationRequestPreview);
});
```

**11. getNotificationRequests**

```javascript
notificationService.getNotificationRequests(self.ctx.pageLink(10, 0, null, null, null)).subscribe(notificationRequests => {
  console.log('NotificationRequests:', notificationRequests);
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(notificationSettings => {
  console.log('NotificationSettings:', notificationSettings);
});
```

**13. saveNotificationSettings**

```javascript
notificationService.saveNotificationSettings(/* notificationSettings */ null).subscribe(notificationSettings => {
  console.log('NotificationSettings:', notificationSettings);
});
```

**14. listSlackConversations**

```javascript
notificationService.listSlackConversations(null, /* token */ null).subscribe(slConversations => {
  console.log('listSlackConversations:', slConversations);
});
```

**15. saveNotificationRule**

```javascript
notificationService.saveNotificationRule(/* notificationRule */ null).subscribe(notificationRule => {
  console.log('NotificationRule:', notificationRule);
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById(/* id */ null).subscribe(notificationRuleById => {
  console.log('NotificationRuleById:', notificationRuleById);
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule(/* id */ null).subscribe(notificationRule => {
  console.log('NotificationRule:', notificationRule);
});
```

**18. getNotificationRules**

```javascript
notificationService.getNotificationRules(self.ctx.pageLink(10, 0, null, null, null)).subscribe(notificationRules => {
  console.log('NotificationRules:', notificationRules);
});
```

**19. saveNotificationTarget**

```javascript
notificationService.saveNotificationTarget(/* notificationTarget */ null).subscribe(notificationTar => {
  console.log('NotificationTarget:', notificationTar);
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById(/* id */ null).subscribe(notificationTarById => {
  console.log('NotificationTarget ById:', notificationTarById);
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget(/* id */ null).subscribe(notificationTar => {
  console.log('NotificationTarget:', notificationTar);
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds(['id1', 'id2']).subscribe(notificationTarsByIds => {
  console.log('NotificationTarget sByIds:', notificationTarsByIds);
});
```

**23. getNotificationTargets**

```javascript
notificationService.getNotificationTargets(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(notificationTars => {
  console.log('NotificationTarget s:', notificationTars);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
notificationService.getRecipientsForNotificationTargetConfig(/* notificationTarget */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(recipientsForNotificationTarConfig => {
  console.log('RecipientsForNotificationTarget Config:', recipientsForNotificationTarConfig);
});
```

**25. saveNotificationTemplate**

```javascript
notificationService.saveNotificationTemplate(/* notificationTarget */ null).subscribe(notificationTemplate => {
  console.log('NotificationTemplate:', notificationTemplate);
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById(/* id */ null).subscribe(notificationTemplateById => {
  console.log('NotificationTemplateById:', notificationTemplateById);
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate(/* id */ null).subscribe(notificationTemplate => {
  console.log('NotificationTemplate:', notificationTemplate);
});
```

**28. getNotificationTemplates**

```javascript
notificationService.getNotificationTemplates(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(notificationTemplates => {
  console.log('NotificationTemplates:', notificationTemplates);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(notificationUserSettings => {
  console.log('NotificationUserSettings:', notificationUserSettings);
});
```

**30. saveNotificationUserSettings**

```javascript
notificationService.saveNotificationUserSettings(/* settings */ null).subscribe(notificationUserSettings => {
  console.log('NotificationUserSettings:', notificationUserSettings);
});
```

---
### **OAUTH2SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oauth2Service = $injector.get(self.ctx.servicesMap.get('oauth2Service'));
```

**1. getOAuth2Template**

```javascript
oauth2Service.getOAuth2Template().subscribe(oAuth2Template => {
  console.log('OAuth2Template:', oAuth2Template);
});
```

**2. saveOAuth2Client**

```javascript
oauth2Service.saveOAuth2Client(/* oAuth2Client */ null).subscribe(oAuth2Client => {
  console.log('OAuth2Client:', oAuth2Client);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
oauth2Service.findTenantOAuth2ClientInfos(self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantOAuth2ClientInfos => {
  console.log('TenantOAuth2Client infos:', tenantOAuth2ClientInfos);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oauth2Service.findTenantOAuth2ClientInfosByIds(['id1', 'id2']).subscribe(tenantOAuth2ClientInfosByIds => {
  console.log('TenantOAuth2Client infosByIds:', tenantOAuth2ClientInfosByIds);
});
```

**5. getOAuth2ClientById**

```javascript
oauth2Service.getOAuth2ClientById(/* id */ null).subscribe(oAuth2ClientById => {
  console.log('OAuth2ClientById:', oAuth2ClientById);
});
```

**6. deleteOauth2Client**

```javascript
oauth2Service.deleteOauth2Client(/* id */ null).subscribe(oauth2Client => {
  console.log('Oauth2Client:', oauth2Client);
});
```

**7. getLoginProcessingUrl**

```javascript
oauth2Service.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('LoginProcessingUrl:', loginProcessingUrl);
});
```

---
### **OTAPACKAGESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
otaPackageService.getOtaPackages(self.ctx.pageLink(10, 0, null, null, null)).subscribe(otaPages => {
  console.log('OtaPackages:', otaPages);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
otaPackageService.getOtaPackagesInfoByDeviceProfileId(self.ctx.pageLink(10, 0, null, null, null), /* deviceProfileId */ null, null).subscribe(otaPagesInfoByDeviceProfileId => {
  console.log('OtaPackages infoByDeviceProfileId:', otaPagesInfoByDeviceProfileId);
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage(/* otaPackageId */ null).subscribe(otaPage => {
  console.log('OtaPackage:', otaPage);
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo(/* otaPackageId */ null).subscribe(otaPageInfo => {
  console.log('OtaPackage:', otaPageInfo);
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage(/* otaPackageId */ null).subscribe(downOtaPage => {
  console.log('downloadOtaPackage:', downOtaPage);
});
```

**6. saveOtaPackage**

```javascript
otaPackageService.saveOtaPackage(/* otaPackage */ null).subscribe(otaPage => {
  console.log('OtaPackage:', otaPage);
});
```

**7. saveOtaPackageInfo**

```javascript
otaPackageService.saveOtaPackageInfo(/* otaPackageInfo */ null).subscribe(otaPageInfo => {
  console.log('OtaPackage:', otaPageInfo);
});
```

**8. uploadOtaPackageFile**

```javascript
otaPackageService.uploadOtaPackageFile(/* otaPackageId */ null, /* file */ null, null, /* checksum */ null).subscribe(upOtaPageFile => {
  console.log('uploadOtaPackageFile:', upOtaPageFile);
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage(null, entityId).subscribe(updateDeviceAfterChangePage => {
  console.log('countUpdateDeviceAfterChangePackage:', updateDeviceAfterChangePage);
});
```

**10. confirmDialogUpdatePackage**

```javascript
otaPackageService.confirmDialogUpdatePackage(/* entity */ null, /* originEntity */ null).subscribe(dialogUpdatePage => {
  console.log('confirmDialogUpdatePackage:', dialogUpdatePage);
});
```

---
### **QUEUESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

**1. getQueueById**

```javascript
queueService.getQueueById(/* queueId */ null).subscribe(queueById => {
  console.log('QueueById:', queueById);
});
```

**2. getQueueByName**

```javascript
queueService.getQueueByName(/* queueName */ null).subscribe(queueByName => {
  console.log('QueueByName:', queueByName);
});
```

**3. getTenantQueuesByServiceType**

```javascript
queueService.getTenantQueuesByServiceType(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(tenantQueuesByServiceType => {
  console.log('TenantQueuesByServiceType:', tenantQueuesByServiceType);
});
```

**4. saveQueue**

```javascript
queueService.saveQueue(/* queue */ null, null).subscribe(queue => {
  console.log('Queue:', queue);
});
```

**5. getQueueStatistics**

```javascript
queueService.getQueueStatistics(self.ctx.pageLink(10, 0, null, null, null)).subscribe(queueStatistics => {
  console.log('QueueStatistics:', queueStatistics);
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById(/* queueStatId */ null).subscribe(queueStatisticsById => {
  console.log('QueueStatisticsById:', queueStatisticsById);
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds(['id1', 'id2']).subscribe(queueStatisticsByIds => {
  console.log('QueueStatisticsByIds:', queueStatisticsByIds);
});
```

---
### **RESOURCESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('resourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```


**1. getResources**

```javascript
resourceService.getResources(self.ctx.pageLink(10, 0, null, null, null), null, null).subscribe(resources => {
  console.log('Resources:', resources);
});
```

**2. getTenantResources**

```javascript
resourceService.getTenantResources(self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantResources => {
  console.log('TenantResources:', tenantResources);
});
```

**3. getResource**

```javascript
resourceService.getResource(/* resourceId */ null).subscribe(resource => {
  console.log('Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
resourceService.getResourceInfoById(/* resourceId */ null).subscribe(resourceInfoById => {
  console.log('Resource infoById:', resourceInfoById);
});
```

**5. getResourceInfo**

```javascript
resourceService.getResourceInfo(null, null, /* key */ null).subscribe(resourceInfo => {
  console.log('Resource:', resourceInfo);
});
```

**6. downloadResource**

```javascript
resourceService.downloadResource(/* resourceId */ null).subscribe(downResource => {
  console.log('downloadResource:', downResource);
});
```

**7. saveResources**

```javascript
resourceService.saveResources(/* resources */ null).subscribe(resources => {
  console.log('Resources:', resources);
});
```

**8. saveResource**

```javascript
resourceService.saveResource(/* resource */ null).subscribe(resource => {
  console.log('Resource:', resource);
});
```

**9. uploadResources**

```javascript
resourceService.uploadResources(/* resources */ null).subscribe(upResources => {
  console.log('uploadResources:', upResources);
});
```

**10. uploadResource**

```javascript
resourceService.uploadResource(/* resource */ null).subscribe(upResource => {
  console.log('uploadResource:', upResource);
});
```

**11. updatedResourceInfo**

```javascript
resourceService.updatedResourceInfo(/* resourceId */ null, /* updatedResources */ null).subscribe(dResourceInfo => {
  console.log('updatedResource:', dResourceInfo);
});
```

**12. updatedResourceData**

```javascript
resourceService.updatedResourceData(/* resourceId */ null, /* data */ null).subscribe(dResourceData => {
  console.log('updatedResourceData:', dResourceData);
});
```

**13. getResourcesByIds**

```javascript
resourceService.getResourcesByIds(['id1', 'id2']).subscribe(resourcesByIds => {
  console.log('ResourcesByIds:', resourcesByIds);
});
```

---
### **RULECHAINSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
ruleChainService.getRuleChains(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(ruleChains => {
  console.log('RuleChains:', ruleChains);
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds(['id1', 'id2']).subscribe(ruleChainsByIds => {
  console.log('RuleChainsByIds:', ruleChainsByIds);
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain(/* ruleChainId */ null).subscribe(ruleChain => {
  console.log('RuleChain:', ruleChain);
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels(/* ruleChainId */ null).subscribe(ruleChainOutputLabels => {
  console.log('RuleChainOutputLabels:', ruleChainOutputLabels);
});
```

**5. createDefaultRuleChain**

```javascript
ruleChainService.createDefaultRuleChain(/* ruleChainName */ null).subscribe(defaultRuleChain => {
  console.log('createDefaultRuleChain:', defaultRuleChain);
});
```

**6. saveRuleChain**

```javascript
ruleChainService.saveRuleChain(/* ruleChain */ null).subscribe(ruleChain => {
  console.log('RuleChain:', ruleChain);
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain(/* ruleChainId */ null).subscribe(rootRuleChain => {
  console.log('setRootRuleChain:', rootRuleChain);
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata(/* ruleChainId */ null).subscribe(ruleChainMetadata => {
  console.log('RuleChainMetadata:', ruleChainMetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
ruleChainService.saveRuleChainMetadata(/* ruleChainMetaData */ null).subscribe(ruleChainMetadata => {
  console.log('RuleChainMetadata:', ruleChainMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
ruleChainService.getRuleNodeComponents(/* modulesMap */ null, null).subscribe(ruleNodeComponents => {
  console.log('RuleNodeComponents:', ruleNodeComponents);
});
```

**11. getRuleNodeConfigComponent**

```javascript
ruleChainService.getRuleNodeConfigComponent(/* directive */ null).subscribe(ruleNodeConfigComponent => {
  console.log('RuleNodeConfigComponent:', ruleNodeConfigComponent);
});
```

**12. getRuleNodeComponentByClazz**

```javascript
ruleChainService.getRuleNodeComponentByClazz(null, /* clazz */ null).subscribe(ruleNodeComponentByClazz => {
  console.log('RuleNodeComponentByClazz:', ruleNodeComponentByClazz);
});
```

**13. getRuleNodeSupportedLinks**

```javascript
ruleChainService.getRuleNodeSupportedLinks(/* component */ null).subscribe(ruleNodeSupportedLinks => {
  console.log('RuleNodeSupportedLinks:', ruleNodeSupportedLinks);
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
ruleChainService.ruleNodeAllowCustomLinks(/* component */ null).subscribe(ruleNodeAllowCustomLinks => {
  console.log('ruleNodeAllowCustomLinks:', ruleNodeAllowCustomLinks);
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
ruleChainService.ruleNodeSourceRuleChainId(/* component */ null).subscribe(ruleNodeSourceRuleChainId => {
  console.log('ruleNodeSourceRuleChainId:', ruleNodeSourceRuleChainId);
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput(/* ruleNodeId */ null).subscribe(laRuleNodeDebugInput => {
  console.log('LatestRuleNodeDebugInput:', laRuleNodeDebugInput);
});
```

**17. testScript**

```javascript
ruleChainService.testScript(/* inputParams */ null, null).subscribe(script => {
  console.log('testScript:', script);
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents(null).subscribe(ruleNodeComponents => {
  console.log('loadRuleNodeComponents:', ruleNodeComponents);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentsUiResources(/* components */ null, /* modulesMap */ null).subscribe(ruleNodeComponentsUiResources => {
  console.log('resolveRuleNodeComponentsUiResources:', ruleNodeComponentsUiResources);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentUiResources(/* component */ null, /* modulesMap */ null).subscribe(ruleNodeComponentUiResources => {
  console.log('resolveRuleNodeComponentUiResources:', ruleNodeComponentUiResources);
});
```

**21. getEdgeRuleChains**

```javascript
ruleChainService.getEdgeRuleChains(/* edgeId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(edgeRuleChains => {
  console.log('EdgeRuleChains:', edgeRuleChains);
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge(/* edgeId */ null, /* ruleChainId */ null).subscribe(ruleChainToEdge => {
  console.log('assignRuleChainToEdge:', ruleChainToEdge);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain(/* ruleChainId */ null).subscribe(edgeTemplateRootRuleChain => {
  console.log('setEdgeTemplateRootRuleChain:', edgeTemplateRootRuleChain);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain(/* ruleChainId */ null).subscribe(autoAssignToEdgeRuleChain => {
  console.log('setAutoAssignToEdgeRuleChain:', autoAssignToEdgeRuleChain);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain(/* ruleChainId */ null).subscribe(unAutoAssignToEdgeRuleChain => {
  console.log('unsetAutoAssignToEdgeRuleChain:', unAutoAssignToEdgeRuleChain);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoAssignToEdgeRuleChains => {
  console.log('AutoAssignToEdgeRuleChains:', autoAssignToEdgeRuleChains);
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain(/* edgeId */ null, /* ruleChainId */ null).subscribe(edgeRootRuleChain => {
  console.log('setEdgeRootRuleChain:', edgeRootRuleChain);
});
```

---
### **TENANTPROFILESERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
tenantProfileService.getTenantProfiles(self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantProfiles => {
  console.log('TenantProfiles:', tenantProfiles);
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile(/* tenantProfileId */ null).subscribe(tenantProfile => {
  console.log('TenantProfile:', tenantProfile);
});
```

**3. saveTenantProfile**

```javascript
tenantProfileService.saveTenantProfile(/* tenantProfile */ null).subscribe(tenantProfile => {
  console.log('TenantProfile:', tenantProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile(/* tenantProfileId */ null).subscribe(defaultTenantProfile => {
  console.log('setDefaultTenantProfile:', defaultTenantProfile);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(defaultTenantProfileInfo => {
  console.log('DefaultTenantProfile:', defaultTenantProfileInfo);
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo(/* tenantProfileId */ null).subscribe(tenantProfileInfo => {
  console.log('TenantProfile:', tenantProfileInfo);
});
```

**7. getTenantProfileInfos**

```javascript
tenantProfileService.getTenantProfileInfos(self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantProfileInfos => {
  console.log('TenantProfile infos:', tenantProfileInfos);
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds(['id1', 'id2']).subscribe(tenantProfilesByIds => {
  console.log('TenantProfilesByIds:', tenantProfilesByIds);
});
```

---
### **TENANTSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
tenantService.getTenants(self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds(['id1', 'id2']).subscribe(tenantsByIds => {
  console.log('TenantsByIds:', tenantsByIds);
});
```

**3. getTenantInfos**

```javascript
tenantService.getTenantInfos(self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantInfos => {
  console.log('Tenant infos:', tenantInfos);
});
```

**4. getTenant**

```javascript
tenantService.getTenant(/* tenantId */ null).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo(/* tenantId */ null).subscribe(tenantInfo => {
  console.log('Tenant:', tenantInfo);
});
```

**6. saveTenant**

```javascript
tenantService.saveTenant(/* tenant */ null).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

---
### **TRENDZSETTINGSSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
trendzSettingsService.getTrendzSettings().subscribe(trendzSettings => {
  console.log('TrendzSettings:', trendzSettings);
});
```

**2. saveTrendzSettings**

```javascript
trendzSettingsService.saveTrendzSettings(/* trendzSettings */ null).subscribe(trendzSettings => {
  console.log('TrendzSettings:', trendzSettings);
});
```

---
### **TWOFACTORAUTHENTICATIONSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings().subscribe(twoFaSettings => {
  console.log('TwoFaSettings:', twoFaSettings);
});
```

**2. saveTwoFaSettings**

```javascript
twoFactorAuthenticationService.saveTwoFaSettings(/* settings */ null).subscribe(twoFaSettings => {
  console.log('TwoFaSettings:', twoFaSettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(availableTwoFaProviders => {
  console.log('AvailableTwoFaProviders:', availableTwoFaProviders);
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig(null).subscribe(twoFaAcConfig => {
  console.log('generateTwoFaAccountConfig:', twoFaAcConfig);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(acTwoFaSettings => {
  console.log('AccountTwoFaSettings:', acTwoFaSettings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig(null, true).subscribe(twoFaAcConfig => {
  console.log('updateTwoFaAccountConfig:', twoFaAcConfig);
});
```

**7. submitTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.submitTwoFaAccountConfig(/* authConfig */ null).subscribe(twoFaAcConfig => {
  console.log('submitTwoFaAccountConfig:', twoFaAcConfig);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(/* authConfig */ null, 0).subscribe(andSaveTwoFaAcConfig => {
  console.log('verify SaveTwoFaAccountConfig:', andSaveTwoFaAcConfig);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig(null).subscribe(twoFaAcConfig => {
  console.log('TwoFaAccountConfig:', twoFaAcConfig);
});
```

---
### **UISETTINGSSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('uiSettingsService'));
```

**1. getHelpBaseUrl**

```javascript
uiSettingsService.getHelpBaseUrl().subscribe(helpBaseUrl => {
  console.log('HelpBaseUrl:', helpBaseUrl);
});
```

---
### **USAGEINFOSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('usageInfoService'));
```

**1. getUsageInfo**

```javascript
usageInfoService.getUsageInfo().subscribe(usageInfo => {
  console.log('Usage:', usageInfo);
});
```

---
### **USERSETTINGSSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('userSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```


**1. loadUserSettings**

```javascript
userSettingsService.loadUserSettings().subscribe(userSettings => {
  console.log('loadUserSettings:', userSettings);
});
```

**2. saveUserSettings**

```javascript
userSettingsService.saveUserSettings(/* userSettings */ null).subscribe(userSettings => {
  console.log('UserSettings:', userSettings);
});
```

**3. putUserSettings**

```javascript
userSettingsService.putUserSettings(/* userSettingsData */ null).subscribe(putUserSettings => {
  console.log('putUserSettings:', putUserSettings);
});
```

**4. getDocumentationLinks**

```javascript
userSettingsService.getDocumentationLinks().subscribe(documentationLinks => {
  console.log('DocumentationLinks:', documentationLinks);
});
```

**5. updateDocumentationLinks**

```javascript
userSettingsService.updateDocumentationLinks(/* documentationLinks */ null).subscribe(documentationLinks => {
  console.log('updateDocumentationLinks:', documentationLinks);
});
```

**6. getQuickLinks**

```javascript
userSettingsService.getQuickLinks().subscribe(quickLinks => {
  console.log('QuickLinks:', quickLinks);
});
```

**7. updateQuickLinks**

```javascript
userSettingsService.updateQuickLinks(/* quickLinks */ null).subscribe(quickLinks => {
  console.log('updateQuickLinks:', quickLinks);
});
```

**8. getGettingStarted**

```javascript
userSettingsService.getGettingStarted().subscribe(gettingStarted => {
  console.log('GettingStarted:', gettingStarted);
});
```

**9. updateGettingStarted**

```javascript
userSettingsService.updateGettingStarted(/* gettingStarted */ null).subscribe(gettingStarted => {
  console.log('updateGettingStarted:', gettingStarted);
});
```

**10. getUserDashboardsInfo**

```javascript
userSettingsService.getUserDashboardsInfo().subscribe(userDashboardsInfo => {
  console.log('UserDashboards:', userDashboardsInfo);
});
```

**11. reportUserDashboardAction**

```javascript
userSettingsService.reportUserDashboardAction(/* dashboardId */ null, null).subscribe(reportUserDashboardAction => {
  console.log('reportUserDashboardAction:', reportUserDashboardAction);
});
```

---
### **USERSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```


**1. getUsers**

```javascript
userService.getUsers(self.ctx.pageLink(10, 0, null, null, null)).subscribe(users => {
  console.log('Users:', users);
});
```

**2. getTenantAdmins**

```javascript
userService.getTenantAdmins(/* tenantId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(tenantAdmins => {
  console.log('TenantAdmins:', tenantAdmins);
});
```

**3. getCustomerUsers**

```javascript
userService.getCustomerUsers(/* customerId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(customerUsers => {
  console.log('CustomerUsers:', customerUsers);
});
```

**4. getUsersForAssign**

```javascript
userService.getUsersForAssign(/* alarmId */ null, self.ctx.pageLink(10, 0, null, null, null)).subscribe(usersForAssign => {
  console.log('UsersForAssign:', usersForAssign);
});
```

**5. getUser**

```javascript
userService.getUser(/* userId */ null).subscribe(user => {
  console.log('User:', user);
});
```

**6. getUsersByIds**

```javascript
userService.getUsersByIds(['id1', 'id2']).subscribe(usersByIds => {
  console.log('UsersByIds:', usersByIds);
});
```

**7. saveUser**

```javascript
userService.saveUser(/* user */ null, null).subscribe(user => {
  console.log('User:', user);
});
```

**8. getActivationLink**

```javascript
userService.getActivationLink(/* userId */ null).subscribe(activationLink => {
  console.log('ActivationLink:', activationLink);
});
```

**9. getActivationLinkInfo**

```javascript
userService.getActivationLinkInfo(/* userId */ null).subscribe(activationLinkInfo => {
  console.log('ActivationLink:', activationLinkInfo);
});
```

**10. setUserCredentialsEnabled**

```javascript
userService.setUserCredentialsEnabled(/* userId */ null, false).subscribe(userCredentialsEnabled => {
  console.log('setUserCredentialsEnabled:', userCredentialsEnabled);
});
```

**11. findUsersByQuery**

```javascript
userService.findUsersByQuery(self.ctx.pageLink(10, 0, null, null, null)).subscribe(usersByQuery => {
  console.log('UsersByQuery:', usersByQuery);
});
```

---
### **WIDGETSERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(widScopeVariables => {
  console.log('Widget ScopeVariables:', widScopeVariables);
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(allWidsBundles => {
  console.log('AllWidget sBundles:', allWidsBundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(systemWidsBundles => {
  console.log('SystemWidget sBundles:', systemWidsBundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(tenantWidsBundles => {
  console.log('TenantWidget sBundles:', tenantWidsBundles);
});
```

**5. getWidgetBundles**

```javascript
widgetService.getWidgetBundles(self.ctx.pageLink(10, 0, null, null, null)).subscribe(widBundles => {
  console.log('Widget Bundles:', widBundles);
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle(/* widgetsBundleId */ null).subscribe(widsBundle => {
  console.log('Widget sBundle:', widsBundle);
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle(/* widgetsBundleId */ null).subscribe(exportWidsBundle => {
  console.log('exportWidget sBundle:', exportWidsBundle);
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle(/* widgetsBundle */ null).subscribe(widsBundle => {
  console.log('Widget sBundle:', widsBundle);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes(/* widgetsBundleId */ null, ['id1', 'id2']).subscribe(widsBundleWidTypes => {
  console.log('updateWidget sBundleWidget Types:', widsBundleWidTypes);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns(/* widgetsBundleId */ null, ['id1', 'id2']).subscribe(widsBundleWidFqns => {
  console.log('updateWidget sBundleWidget Fqns:', widsBundleWidFqns);
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes(/* widgetsBundleId */ null).subscribe(bundleWidTypes => {
  console.log('BundleWidget Types:', bundleWidTypes);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails(/* widgetsBundleId */ null).subscribe(exportBundleWidTypesDetails => {
  console.log('exportBundleWidget TypesDetails:', exportBundleWidTypesDetails);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns(/* widgetsBundleId */ null).subscribe(bundleWidTypeFqns => {
  console.log('BundleWidget TypeFqns:', bundleWidTypeFqns);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList(/* widgetsBundleId */ null).subscribe(bundleWidTypeInfosList => {
  console.log('BundleWidget Type infosList:', bundleWidTypeInfosList);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
widgetService.getBundleWidgetTypeInfos(self.ctx.pageLink(10, 0, null, null, null), /* widgetsBundleId */ null, null).subscribe(bundleWidTypeInfos => {
  console.log('BundleWidget Type infos:', bundleWidTypeInfos);
});
```

**16. getWidgetType**

```javascript
widgetService.getWidgetType(/* fullFqn */ null).subscribe(widType => {
  console.log('Widget Type:', widType);
});
```

**17. saveWidgetTypeDetails**

```javascript
widgetService.saveWidgetTypeDetails(/* widgetInfo */ null, /* id */ null, 0, 0).subscribe(widTypeDetails => {
  console.log('Widget TypeDetails:', widTypeDetails);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails(/* widgetTypeDetails */ null).subscribe(importedWidTypeDetails => {
  console.log('ImportedWidget TypeDetails:', importedWidTypeDetails);
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById(/* widgetTypeId */ null).subscribe(widTypeById => {
  console.log('Widget TypeById:', widTypeById);
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType(/* widgetTypeId */ null).subscribe(exportWidType => {
  console.log('exportWidget Type:', exportWidType);
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById(/* widgetTypeId */ null).subscribe(widTypeInfoById => {
  console.log('Widget Type infoById:', widTypeInfoById);
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType(/* widgetTypeDetails */ null).subscribe(widType => {
  console.log('Widget Type:', widType);
});
```

**23. getWidgetTypes**

```javascript
widgetService.getWidgetTypes(self.ctx.pageLink(10, 0, null, null, null), null).subscribe(widTypes => {
  console.log('Widget Types:', widTypes);
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate(/* widgetTypeParam */ null).subscribe(widTemplate => {
  console.log('Widget Template:', widTemplate);
});
```

**25. getWidgetInfoFromCache**

```javascript
widgetService.getWidgetInfoFromCache(/* fullFqn */ null).subscribe(widInfoFromCache => {
  console.log('Widget infoFromCache:', widInfoFromCache);
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
widgetService.getBasicWidgetSettingsComponentBySelector(/* selector */ null).subscribe(basicWidSettingsComponentBySelector => {
  console.log('BasicWidget SettingsComponentBySelector:', basicWidSettingsComponentBySelector);
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
widgetService.getWidgetSettingsComponentTypeBySelector(/* selector */ null).subscribe(widSettingsComponentTypeBySelector => {
  console.log('Widget SettingsComponentTypeBySelector:', widSettingsComponentTypeBySelector);
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated(/* updatedWidgetType */ null).subscribe(widTypeUpdated => {
  console.log('widget TypeUpdated:', widTypeUpdated);
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds(['id1', 'id2']).subscribe(widsBundlesByIds => {
  console.log('Widget sBundlesByIds:', widsBundlesByIds);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(widsBundleCache => {
  console.log('loadWidget sBundleCache:', widsBundleCache);
});
```

---
