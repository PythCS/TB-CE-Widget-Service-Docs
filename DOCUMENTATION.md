# ThingsBoard Widget Services API

Complete reference for all widget services available in ThingsBoard CE.

## Table of Contents

- [Using Services in Widgets/Custom Actions](#using-services-in-widgetscustom-actions)
- [Using Page Links](#using-page-links)
- [AdminService](#admin-service)
- [AiModelService](#aimodel-service)
- [AlarmCommentService](#alarmcomment-service)
- [AlarmRulesService](#alarmrules-service)
- [AlarmService](#alarm-service)
- [ApiKeyService](#apikey-service)
- [AssetProfileService](#assetprofile-service)
- [AssetService](#asset-service)
- [AttributeService](#attribute-service)
- [AuditLogService](#auditlog-service)
- [CalculatedFieldsService](#calculatedfields-service)
- [ComponentDescriptorService](#componentdescriptor-service)
- [CustomerService](#customer-service)
- [DashboardService](#dashboard-service)
- [DeviceProfileService](#deviceprofile-service)
- [DeviceService](#device-service)
- [DomainService](#domain-service)
- [EdgeService](#edge-service)
- [EntitiesVersionControlService](#entitiesversioncontrol-service)
- [EntityRelationService](#entityrelation-service)
- [EntityService](#entity-service)
- [EntityViewService](#entityview-service)
- [EventService](#event-service)
- [GitHubService](#github-service)
- [ImageService](#image-service)
- [MobileAppService](#mobileapp-service)
- [MobileApplicationService](#mobileapplication-service)
- [NotificationService](#notification-service)
- [OAuth2Service](#oauth2-service)
- [OtaPackageService](#otapackage-service)
- [QueueService](#queue-service)
- [ResourceService](#resource-service)
- [RuleChainService](#rulechain-service)
- [TenantProfileService](#tenantprofile-service)
- [TenantService](#tenant-service)
- [TrendzSettingsService](#trendzsettings-service)
- [TwoFactorAuthenticationService](#twofactorauthentication-service)
- [UiSettingsService](#uisettings-service)
- [UsageInfoService](#usageinfo-service)
- [UserService](#user-service)
- [UserSettingsService](#usersettings-service)
- [WidgetService](#widget-service)

## Using Services in Widgets/Custom Actions

Using services in custom actions is slightly different than in custom widget development.

In custom actions you use `widgetContext` — in widget development you use `self.ctx`. Same services, different context variable.

Example Custom Action:

```javascript
const $injector = widgetContext.$scope.$injector;
const userService = $injector.get(widgetContext.servicesMap.get('userService'));
```

Example Widget Development:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));
```

## Using Page Links

Page links are used for pagination to avoid overloading the server when dealing with large datasets (1000+ results). They control how many items to fetch per request and which page to retrieve.

Create a page link like this:

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
```

Parameters:
- `pageSize` (number): How many items to return per page (e.g., 10, 20, 50)
- `page` (number): Zero-based page index (0 = first page, 1 = second page, etc.)
- `searchText` (string): Optional text to filter results
- `sortProperty` (string): Property name to sort by
- `sortOrder` (string): 'ASC' or 'DESC'

The response from paginated methods includes:
- `data`: Array of items for the current page
- `totalPages`: Total number of pages
- `totalElements`: Total number of items across all pages
- `hasNext`: Boolean indicating if more pages exist

### **ADMINSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
adminService.sendTestMail({ /* your adminSettings */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**2. sendTestSms**

```javascript
adminService.sendTestSms({ /* your testSmsRequest */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings({ /* your config */ }).subscribe(ecurityetting => {
  console.log('Security Settings:', ecurityetting);
});
```

**4. saveSecuritySettings**

```javascript
adminService.saveSecuritySettings({ /* your securitySettings */ }, { /* your config */ }).subscribe(savedSecuritySettings => {
  console.log('Saved SecuritySettings:', savedSecuritySettings);
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings({ /* your config */ }).subscribe(jwtetting => {
  console.log('Jwt Settings:', jwtetting);
});
```

**6. saveJwtSettings**

```javascript
adminService.saveJwtSettings({ /* your jwtSettings */ }, { /* your config */ }).subscribe(savedJwtSettings => {
  console.log('Saved JwtSettings:', savedJwtSettings);
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings({ /* your config */ }).subscribe(repoitoryetting => {
  console.log('Repository Settings:', repoitoryetting);
});
```

**8. saveRepositorySettings**

```javascript
adminService.saveRepositorySettings({ /* your repositorySettings */ }, { /* your config */ }).subscribe(savedRepositorySettings => {
  console.log('Saved RepositorySettings:', savedRepositorySettings);
});
```

**9. checkRepositoryAccess**

```javascript
adminService.checkRepositoryAccess({ /* your repositorySettings */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo({ /* your config */ }).subscribe(repositorysettingsinfo => {
  console.log('Repository Settings Info:', repositorysettingsinfo);
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings({ /* your config */ }).subscribe(autocommitetting => {
  console.log('Auto Commit Settings:', autocommitetting);
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. saveAutoCommitSettings**

```javascript
adminService.saveAutoCommitSettings({ /* your autoCommitSettings */ }, { /* your config */ }).subscribe(savedAutoCommitSettings => {
  console.log('Saved AutoCommitSettings:', savedAutoCommitSettings);
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo({ /* your config */ }).subscribe(featuresinfo => {
  console.log('Features Info:', featuresinfo);
});
```

**16. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl({ /* your config */ }).subscribe(loginprocessingurl => {
  console.log('Login Processing Url:', loginprocessingurl);
});
```

**17. generateAccessToken**

```javascript
adminService.generateAccessToken({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**18. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate({ /* your config */ }).subscribe(mailconfigtemplate => {
  console.log('Mail Config Template:', mailconfigtemplate);
});
```

### **AIMODELSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

**1. saveAiModel**

```javascript
aiModelService.saveAiModel({ /* your aiModel */ }, { /* your config */ }).subscribe(savedAiModel => {
  console.log('Saved AiModel:', savedAiModel);
});
```

**2. getAiModels**

```javascript
aiModelService.getAiModels(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(aimodel => {
  console.log('Ai Models:', aimodel);
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById('your-aimodel-id', { /* your config */ }).subscribe(aimodelbyid => {
  console.log('Ai Model By Id:', aimodelbyid);
});
```

**4. checkConnectivity**

```javascript
aiModelService.checkConnectivity({ /* your aiModelWithUserMsg */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **ALARMCOMMENTSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

**1. saveAlarmComment**

```javascript
alarmCommentService.saveAlarmComment('your-alarm-id', { /* your alarmComment */ }, { /* your config */ }).subscribe(savedAlarmComment => {
  console.log('Saved AlarmComment:', savedAlarmComment);
});
```

**2. getAlarmComments**

```javascript
alarmCommentService.getAlarmComments('your-alarm-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(alarmcomment => {
  console.log('Alarm Comments:', alarmcomment);
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments('your-alarm-id', 'your-comment-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

### **ALARMRULESSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
alarmRulesService.getAlarmRuleById('your-alarmrule-id', { /* your config */ }).subscribe(alarmrulebyid => {
  console.log('Alarm Rule By Id:', alarmrulebyid);
});
```

**2. saveAlarmRule**

```javascript
alarmRulesService.saveAlarmRule({ /* your alarmRule */ }, { /* your config */ }).subscribe(savedAlarmRule => {
  console.log('Saved AlarmRule:', savedAlarmRule);
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule('your-alarmrule-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**4. getAlarmRules**

```javascript
alarmRulesService.getAlarmRules(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your query */ }, { /* your config */ }).subscribe(alarmrule => {
  console.log('Alarm Rules:', alarmrule);
});
```

**5. getAlarmRulesByEntityId**

```javascript
alarmRulesService.getAlarmRulesByEntityId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(alarmrulesbyentityid => {
  console.log('Alarm Rules By Entity Id:', alarmrulesbyentityid);
});
```

**6. testScript**

```javascript
alarmRulesService.testScript({ /* your inputParams */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent('your-id', { /* your config */ }).subscribe(latestalarmruledebugevent => {
  console.log('Latest Alarm Rule Debug Event:', latestalarmruledebugevent);
});
```

**8. getAlarmRuleNames**

```javascript
alarmRulesService.getAlarmRuleNames(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(alarmrulename => {
  console.log('Alarm Rule Names:', alarmrulename);
});
```

### **ALARMSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

**1. getAlarm**

```javascript
alarmService.getAlarm('your-alarm-id', { /* your config */ }).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo('your-alarm-id', { /* your config */ }).subscribe(alarminfo => {
  console.log('Alarm Info:', alarminfo);
});
```

**3. saveAlarm**

```javascript
alarmService.saveAlarm({ /* your alarm object */ }, { /* your config */ }).subscribe(savedAlarm => {
  console.log('Saved Alarm:', savedAlarm);
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm('your-alarm-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm('your-alarm-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm('your-alarm-id', 'your-assignee-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm('your-alarm-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm('your-alarm-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**9. getAlarms**

```javascript
alarmService.getAlarms({ /* your query */ }, { /* your config */ }).subscribe(alarm => {
  console.log('Alarms:', alarm);
});
```

**10. getAlarmsV2**

```javascript
alarmService.getAlarmsV2({ /* your query */ }, { /* your config */ }).subscribe(alarmsv2 => {
  console.log('Alarms V2:', alarmsv2);
});
```

**11. getAllAlarms**

```javascript
alarmService.getAllAlarms({ /* your query */ }, { /* your config */ }).subscribe(allalarm => {
  console.log('All Alarms:', allalarm);
});
```

**12. getAllAlarmsV2**

```javascript
alarmService.getAllAlarmsV2({ /* your query */ }, { /* your config */ }).subscribe(allalarmsv2 => {
  console.log('All Alarms V2:', allalarmsv2);
});
```

**13. getHighestAlarmSeverity**

```javascript
alarmService.getHighestAlarmSeverity('your-entity-id', { /* your alarmSearchStatus */ }, { /* your alarmStatus */ }, { /* your config */ }).subscribe(highestalarmseverity => {
  console.log('Highest Alarm Severity:', highestalarmseverity);
});
```

**14. getAlarmTypes**

```javascript
alarmService.getAlarmTypes(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(alarmtype => {
  console.log('Alarm Types:', alarmtype);
});
```

### **APIKEYSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
apiKeyService.saveApiKey({ /* your apiKey */ }, { /* your config */ }).subscribe(savedApiKey => {
  console.log('Saved ApiKey:', savedApiKey);
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**3. updateApiKeyDescription**

```javascript
apiKeyService.updateApiKeyDescription('your-id', 'your-description', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey('your-id', true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getUserApiKeys**

```javascript
apiKeyService.getUserApiKeys('your-user-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(uerapikey => {
  console.log('User Api Keys:', uerapikey);
});
```

### **ASSETPROFILESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
assetProfileService.getAssetProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(aetprofile => {
  console.log('Asset Profiles:', aetprofile);
});
```

**2. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds(['id1', 'id2'], { /* your config */ }).subscribe(aetprofilebyid => {
  console.log('Asset Profiles By Ids:', aetprofilebyid);
});
```

**3. getAssetProfile**

```javascript
assetProfileService.getAssetProfile('your-assetprofile-id', { /* your config */ }).subscribe(assetprofile => {
  console.log('Asset Profile:', assetprofile);
});
```

**4. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile('your-assetprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. saveAssetProfile**

```javascript
assetProfileService.saveAssetProfile({ /* your assetProfile */ }, { /* your config */ }).subscribe(savedAssetProfile => {
  console.log('Saved AssetProfile:', savedAssetProfile);
});
```

**6. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile('your-assetprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo({ /* your config */ }).subscribe(defaultassetprofileinfo => {
  console.log('Default Asset Profile Info:', defaultassetprofileinfo);
});
```

**8. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo('your-assetprofile-id', { /* your config */ }).subscribe(assetprofileinfo => {
  console.log('Asset Profile Info:', assetprofileinfo);
});
```

**9. getAssetProfileInfos**

```javascript
assetProfileService.getAssetProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(aetprofileinfo => {
  console.log('Asset Profile Infos:', aetprofileinfo);
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames({ /* your activeOnly */ }, { /* your config */ }).subscribe(aetprofilename => {
  console.log('Asset Profile Names:', aetprofilename);
});
```

### **ASSETSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('assetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

**1. getTenantAssetInfos**

```javascript
assetService.getTenantAssetInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(tenantaetinfo => {
  console.log('Tenant Asset Infos:', tenantaetinfo);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
assetService.getTenantAssetInfosByAssetProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-assetprofile-id', { /* your config */ }).subscribe(tenantaetinfobyaetprofileid => {
  console.log('Tenant Asset Infos By Asset Profile Id:', tenantaetinfobyaetprofileid);
});
```

**3. getCustomerAssetInfos**

```javascript
assetService.getCustomerAssetInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(cutomeraetinfo => {
  console.log('Customer Asset Infos:', cutomeraetinfo);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
assetService.getCustomerAssetInfosByAssetProfileId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-assetprofile-id', { /* your config */ }).subscribe(cutomeraetinfobyaetprofileid => {
  console.log('Customer Asset Infos By Asset Profile Id:', cutomeraetinfobyaetprofileid);
});
```

**5. getAsset**

```javascript
assetService.getAsset('your-asset-id', { /* your config */ }).subscribe(asset => {
  console.log('Asset:', asset);
});
```

**6. getAssets**

```javascript
assetService.getAssets(['id1', 'id2'], { /* your config */ }).subscribe(aet => {
  console.log('Assets:', aet);
});
```

**7. getAssetInfo**

```javascript
assetService.getAssetInfo('your-asset-id', { /* your config */ }).subscribe(assetinfo => {
  console.log('Asset Info:', assetinfo);
});
```

**8. saveAsset**

```javascript
assetService.saveAsset({ /* your asset object */ }, { /* your config */ }).subscribe(savedAsset => {
  console.log('Saved Asset:', savedAsset);
});
```

**9. getAssetTypes**

```javascript
assetService.getAssetTypes({ /* your config */ }).subscribe(aettype => {
  console.log('Asset Types:', aettype);
});
```

**10. makeAssetPublic**

```javascript
assetService.makeAssetPublic('your-asset-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. assignAssetToCustomer**

```javascript
assetService.assignAssetToCustomer('your-customer-id', 'your-asset-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. findByQuery**

```javascript
assetService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. findByName**

```javascript
assetService.findByName('your-assetName', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**14. assignAssetToEdge**

```javascript
assetService.assignAssetToEdge('your-edge-id', 'your-asset-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getEdgeAssets**

```javascript
assetService.getEdgeAssets('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(edgeaet => {
  console.log('Edge Assets:', edgeaet);
});
```

**16. bulkImportAssets**

```javascript
assetService.bulkImportAssets({ /* your entitiesData */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **ATTRIBUTESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
attributeService.getEntityAttributes('your-entity-id', { /* your attributeScope */ }, ['id1', 'id2'], { /* your config */ }).subscribe(entityattribute => {
  console.log('Entity Attributes:', entityattribute);
});
```

**2. deleteEntityAttributes**

```javascript
attributeService.deleteEntityAttributes('your-entity-id', { /* your attributeScope */ }, ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**3. deleteEntityTimeseries**

```javascript
attributeService.deleteEntityTimeseries('your-entity-id', ['id1', 'id2'], 100, 100, { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**4. saveEntityAttributes**

```javascript
attributeService.saveEntityAttributes('your-entity-id', { /* your attributeScope */ }, ['id1', 'id2'], { /* your config */ }).subscribe(savedEntityAttributes => {
  console.log('Saved EntityAttributes:', savedEntityAttributes);
});
```

**5. saveEntityTimeseries**

```javascript
attributeService.saveEntityTimeseries('your-entity-id', 'your-timeseriesScope', ['id1', 'id2'], { /* your config */ }).subscribe(savedEntityTimeseries => {
  console.log('Saved EntityTimeseries:', savedEntityTimeseries);
});
```

**6. getEntityTimeseries**

```javascript
attributeService.getEntityTimeseries('your-entity-id', ['id1', 'id2'], 100, 100, { /* your limit */ }, { /* your agg */ }, 100, { /* your orderBy */ }, 'your-usestrictdatatypes', { /* your config */ }).subscribe(entitytimeery => {
  console.log('Entity Timeseries:', entitytimeery);
});
```

**7. getEntityTimeseriesLatest**

```javascript
attributeService.getEntityTimeseriesLatest('your-entity-id', ['id1', 'id2'], { /* your config */ }).subscribe(entitytimeserieslatest => {
  console.log('Entity Timeseries Latest:', entitytimeserieslatest);
});
```

### **AUDITLOGSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
```

**1. getAuditLogs**

```javascript
auditLogService.getAuditLogs(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(auditlog => {
  console.log('Audit Logs:', auditlog);
});
```

**2. getAuditLogsByCustomerId**

```javascript
auditLogService.getAuditLogsByCustomerId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(auditlogsbycustomerid => {
  console.log('Audit Logs By Customer Id:', auditlogsbycustomerid);
});
```

**3. getAuditLogsByUserId**

```javascript
auditLogService.getAuditLogsByUserId('your-user-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(auditlogsbyuserid => {
  console.log('Audit Logs By User Id:', auditlogsbyuserid);
});
```

**4. getAuditLogsByEntityId**

```javascript
auditLogService.getAuditLogsByEntityId('your-entity-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(auditlogsbyentityid => {
  console.log('Audit Logs By Entity Id:', auditlogsbyentityid);
});
```

### **CALCULATEDFIELDSSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
calculatedFieldsService.getCalculatedFieldById('your-calculatedfield-id', { /* your config */ }).subscribe(calculatedfieldbyid => {
  console.log('Calculated Field By Id:', calculatedfieldbyid);
});
```

**2. saveCalculatedField**

```javascript
calculatedFieldsService.saveCalculatedField({ /* your calculatedField */ }, { /* your config */ }).subscribe(savedCalculatedField => {
  console.log('Saved CalculatedField:', savedCalculatedField);
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField('your-calculatedfield-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**4. getCalculatedFields**

```javascript
calculatedFieldsService.getCalculatedFields(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your query */ }, { /* your config */ }).subscribe(calculatedfield => {
  console.log('Calculated Fields:', calculatedfield);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
calculatedFieldsService.getCalculatedFieldsByEntityId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(calculatedfieldsbyentityid => {
  console.log('Calculated Fields By Entity Id:', calculatedfieldsbyentityid);
});
```

**6. testScript**

```javascript
calculatedFieldsService.testScript({ /* your inputParams */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent('your-id', { /* your config */ }).subscribe(latestcalculatedfielddebugevent => {
  console.log('Latest Calculated Field Debug Event:', latestcalculatedfielddebugevent);
});
```

**8. getCalculatedFieldNames**

```javascript
calculatedFieldsService.getCalculatedFieldNames(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(calculatedfieldname => {
  console.log('Calculated Field Names:', calculatedfieldname);
});
```

### **COMPONENTDESCRIPTORSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
componentDescriptorService.getComponentDescriptorsByType('your-componenttype', 'your-rulechaintype', { /* your config */ }).subscribe(componentdescriptorsbytype => {
  console.log('Component Descriptors By Type:', componentdescriptorsbytype);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes('your-componenttypes', 'your-rulechaintype', { /* your config */ }).subscribe(componentdecriptorbytype => {
  console.log('Component Descriptors By Types:', componentdecriptorbytype);
});
```

**3. getComponentDescriptorByClazz**

```javascript
componentDescriptorService.getComponentDescriptorByClazz('your-componentDescriptorClazz', { /* your config */ }).subscribe(componentdescriptorbyclazz => {
  console.log('Component Descriptor By Clazz:', componentdescriptorbyclazz);
});
```

### **CUSTOMERSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('customerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```

**1. getCustomers**

```javascript
customerService.getCustomers(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(cutomer => {
  console.log('Customers:', cutomer);
});
```

**2. getCustomer**

```javascript
customerService.getCustomer('your-customer-id', { /* your config */ }).subscribe(customer => {
  console.log('Customer:', customer);
});
```

**3. getCustomersByIds**

```javascript
customerService.getCustomersByIds(['id1', 'id2'], { /* your config */ }).subscribe(cutomerbyid => {
  console.log('Customers By Ids:', cutomerbyid);
});
```

**4. saveCustomer**

```javascript
customerService.saveCustomer({ /* your customer object */ }, { /* your config */ }).subscribe(savedCustomer => {
  console.log('Saved Customer:', savedCustomer);
});
```

### **DASHBOARDSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

**1. getTenantDashboards**

```javascript
dashboardService.getTenantDashboards(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantdahboard => {
  console.log('Tenant Dashboards:', tenantdahboard);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
dashboardService.getTenantDashboardsByTenantId('your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantdashboardsbytenantid => {
  console.log('Tenant Dashboards By Tenant Id:', tenantdashboardsbytenantid);
});
```

**3. getCustomerDashboards**

```javascript
dashboardService.getCustomerDashboards('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(cutomerdahboard => {
  console.log('Customer Dashboards:', cutomerdahboard);
});
```

**4. getDashboard**

```javascript
dashboardService.getDashboard('your-dashboard-id', { /* your config */ }).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
dashboardService.exportDashboard('your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. getDashboardInfo**

```javascript
dashboardService.getDashboardInfo('your-dashboard-id', { /* your config */ }).subscribe(dashboardinfo => {
  console.log('Dashboard Info:', dashboardinfo);
});
```

**7. getDashboards**

```javascript
dashboardService.getDashboards(['id1', 'id2'], { /* your config */ }).subscribe(dahboard => {
  console.log('Dashboards:', dahboard);
});
```

**8. saveDashboard**

```javascript
dashboardService.saveDashboard({ /* your dashboard object */ }, { /* your config */ }).subscribe(savedDashboard => {
  console.log('Saved Dashboard:', savedDashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
dashboardService.assignDashboardToCustomer('your-customer-id', 'your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. makeDashboardPublic**

```javascript
dashboardService.makeDashboardPublic('your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. makeDashboardPrivate**

```javascript
dashboardService.makeDashboardPrivate('your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. updateDashboardCustomers**

```javascript
dashboardService.updateDashboardCustomers('your-dashboard-id', ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. addDashboardCustomers**

```javascript
dashboardService.addDashboardCustomers('your-dashboard-id', ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**14. removeDashboardCustomers**

```javascript
dashboardService.removeDashboardCustomers('your-dashboard-id', ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getHomeDashboard**

```javascript
dashboardService.getHomeDashboard({ /* your config */ }).subscribe(homedashboard => {
  console.log('Home Dashboard:', homedashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
dashboardService.getTenantHomeDashboardInfo({ /* your config */ }).subscribe(tenanthomedashboardinfo => {
  console.log('Tenant Home Dashboard Info:', tenanthomedashboardinfo);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
dashboardService.setTenantHomeDashboardInfo({ /* your homeDashboardInfo */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**18. getPublicDashboardLink**

```javascript
dashboardService.getPublicDashboardLink({ /* your dashboard object */ }).subscribe(publicdashboardlink => {
  console.log('Public Dashboard Link:', publicdashboardlink);
});
```

**19. assignDashboardToEdge**

```javascript
dashboardService.assignDashboardToEdge('your-edge-id', 'your-dashboard-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **DEVICEPROFILESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
deviceProfileService.getDeviceProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(deviceprofile => {
  console.log('Device Profiles:', deviceprofile);
});
```

**2. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds(['id1', 'id2'], { /* your config */ }).subscribe(deviceprofilebyid => {
  console.log('Device Profiles By Ids:', deviceprofilebyid);
});
```

**3. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile('your-deviceprofile-id', { /* your config */ }).subscribe(deviceprofile => {
  console.log('Device Profile:', deviceprofile);
});
```

**4. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile('your-deviceprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects({ /* your sortOrder */ }, ['id1', 'id2'], 'your-searchText', { /* your config */ }).subscribe(lwm2mobject => {
  console.log('Lwm2m Objects:', lwm2mobject);
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true, { /* your config */ }).subscribe(lwm2mbootstrapsecurityinfo => {
  console.log('Lwm2m Bootstrap Security Info:', lwm2mbootstrapsecurityinfo);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true, { /* your config */ }).subscribe(lwm2mbootstrapsecurityinfobysecuritytype => {
  console.log('Lwm2m Bootstrap Security Info By Security Type:', lwm2mbootstrapsecurityinfobysecuritytype);
});
```

**8. getLwm2mObjectsPage**

```javascript
deviceProfileService.getLwm2mObjectsPage(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(lwm2mobjectspage => {
  console.log('Lwm2m Objects Page:', lwm2mobjectspage);
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceProfileService.saveDeviceProfileAndConfirmOtaChange({ /* your originDeviceProfile */ }, { /* your deviceProfile */ }, { /* your config */ }).subscribe(savedDeviceProfileAndConfirmOtaChange => {
  console.log('Saved DeviceProfileAndConfirmOtaChange:', savedDeviceProfileAndConfirmOtaChange);
});
```

**10. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(savedDeviceProfile => {
  console.log('Saved DeviceProfile:', savedDeviceProfile);
});
```

**11. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile('your-deviceprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo({ /* your config */ }).subscribe(defaultdeviceprofileinfo => {
  console.log('Default Device Profile Info:', defaultdeviceprofileinfo);
});
```

**13. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo('your-deviceprofile-id', { /* your config */ }).subscribe(deviceprofileinfo => {
  console.log('Device Profile Info:', deviceprofileinfo);
});
```

**14. getDeviceProfileInfos**

```javascript
deviceProfileService.getDeviceProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-transporttype', { /* your config */ }).subscribe(deviceprofileinfo => {
  console.log('Device Profile Infos:', deviceprofileinfo);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys('your-deviceprofile-id', { /* your config */ }).subscribe(deviceprofiledeviceattributekey => {
  console.log('Device Profile Devices Attributes Keys:', deviceprofiledeviceattributekey);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys('your-deviceprofile-id', { /* your config */ }).subscribe(deviceprofiledevicetimeeriekey => {
  console.log('Device Profile Devices Timeseries Keys:', deviceprofiledevicetimeeriekey);
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames({ /* your activeOnly */ }, { /* your config */ }).subscribe(deviceprofilename => {
  console.log('Device Profile Names:', deviceprofilename);
});
```

### **DEVICESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
deviceService.getDeviceInfosByQuery({ /* your deviceInfoQuery */ }, { /* your config */ }).subscribe(deviceinfobyquery => {
  console.log('Device Infos By Query:', deviceinfobyquery);
});
```

**2. getTenantDeviceInfos**

```javascript
deviceService.getTenantDeviceInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(tenantdeviceinfo => {
  console.log('Tenant Device Infos:', tenantdeviceinfo);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
deviceService.getTenantDeviceInfosByDeviceProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id', { /* your config */ }).subscribe(tenantdeviceinfobydeviceprofileid => {
  console.log('Tenant Device Infos By Device Profile Id:', tenantdeviceinfobydeviceprofileid);
});
```

**4. getCustomerDeviceInfos**

```javascript
deviceService.getCustomerDeviceInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(cutomerdeviceinfo => {
  console.log('Customer Device Infos:', cutomerdeviceinfo);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
deviceService.getCustomerDeviceInfosByDeviceProfileId('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id', { /* your config */ }).subscribe(cutomerdeviceinfobydeviceprofileid => {
  console.log('Customer Device Infos By Device Profile Id:', cutomerdeviceinfobydeviceprofileid);
});
```

**6. getDevice**

```javascript
deviceService.getDevice('your-device-id', { /* your config */ }).subscribe(device => {
  console.log('Device:', device);
});
```

**7. getDevices**

```javascript
deviceService.getDevices(['id1', 'id2'], { /* your config */ }).subscribe(device => {
  console.log('Devices:', device);
});
```

**8. getDeviceInfo**

```javascript
deviceService.getDeviceInfo('your-device-id', { /* your config */ }).subscribe(deviceinfo => {
  console.log('Device Info:', deviceinfo);
});
```

**9. saveDevice**

```javascript
deviceService.saveDevice({ /* your device object */ }, { /* your config */ }).subscribe(savedDevice => {
  console.log('Saved Device:', savedDevice);
});
```

**10. saveDeviceWithCredentials**

```javascript
deviceService.saveDeviceWithCredentials({ /* your device object */ }, { /* your credentials */ }, { /* your config */ }).subscribe(savedDeviceWithCredentials => {
  console.log('Saved DeviceWithCredentials:', savedDeviceWithCredentials);
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes({ /* your config */ }).subscribe(devicetype => {
  console.log('Device Types:', devicetype);
});
```

**12. getDeviceCredentials**

```javascript
deviceService.getDeviceCredentials('your-device-id', { /* your sync */ }, { /* your config */ }).subscribe(devicecredential => {
  console.log('Device Credentials:', devicecredential);
});
```

**13. saveDeviceCredentials**

```javascript
deviceService.saveDeviceCredentials({ /* your deviceCredentials */ }, { /* your config */ }).subscribe(savedDeviceCredentials => {
  console.log('Saved DeviceCredentials:', savedDeviceCredentials);
});
```

**14. makeDevicePublic**

```javascript
deviceService.makeDevicePublic('your-device-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. assignDeviceToCustomer**

```javascript
deviceService.assignDeviceToCustomer('your-customer-id', 'your-device-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**16. sendOneWayRpcCommand**

```javascript
deviceService.sendOneWayRpcCommand('your-device-id', { /* your requestBody */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**17. sendTwoWayRpcCommand**

```javascript
deviceService.sendTwoWayRpcCommand('your-device-id', { /* your requestBody */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**18. getPersistedRpc**

```javascript
deviceService.getPersistedRpc('your-rpc-id', { /* your config */ }).subscribe(persistedrpc => {
  console.log('Persisted Rpc:', persistedrpc);
});
```

**19. getPersistedRpcRequests**

```javascript
deviceService.getPersistedRpcRequests('your-device-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your rpcStatus */ }, { /* your config */ }).subscribe(peritedrpcrequet => {
  console.log('Persisted Rpc Requests:', peritedrpcrequet);
});
```

**20. findByQuery**

```javascript
deviceService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**21. findByName**

```javascript
deviceService.findByName('your-deviceName', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**22. claimDevice**

```javascript
deviceService.claimDevice('your-deviceName', { /* your claimRequest */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**23. assignDeviceToEdge**

```javascript
deviceService.assignDeviceToEdge('your-edge-id', 'your-device-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**24. getEdgeDevices**

```javascript
deviceService.getEdgeDevices('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(edgedevice => {
  console.log('Edge Devices:', edgedevice);
});
```

**25. bulkImportDevices**

```javascript
deviceService.bulkImportDevices({ /* your entitiesData */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
deviceService.getDevicePublishTelemetryCommands('your-device-id', { /* your config */ }).subscribe(devicepublihtelemetrycommand => {
  console.log('Device Publish Telemetry Commands:', devicepublihtelemetrycommand);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
deviceService.downloadGatewayDockerComposeFile('your-device-id').subscribe(result => {
  console.log('Result:', result);
});
```

**28. rebootDevice**

```javascript
deviceService.rebootDevice('your-device-id', true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**29. rebootTrigger**

```javascript
deviceService.rebootTrigger('your-device-id', 'your-resourcePath', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **DOMAINSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
domainService.saveDomain({ /* your domain */ }, ['id1', 'id2'], { /* your config */ }).subscribe(savedDomain => {
  console.log('Saved Domain:', savedDomain);
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients('your-id', ['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**3. getTenantDomainInfos**

```javascript
domainService.getTenantDomainInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantdomaininfo => {
  console.log('Tenant Domain Infos:', tenantdomaininfo);
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById('your-id', { /* your config */ }).subscribe(domaininfobyid => {
  console.log('Domain Info By Id:', domaininfobyid);
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

### **EDGESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

**1. getEdges**

```javascript
edgeService.getEdges(['id1', 'id2'], { /* your config */ }).subscribe(edge => {
  console.log('Edges:', edge);
});
```

**2. getEdge**

```javascript
edgeService.getEdge('your-edge-id', { /* your config */ }).subscribe(edge => {
  console.log('Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo('your-edge-id', { /* your config */ }).subscribe(edgeinfo => {
  console.log('Edge Info:', edgeinfo);
});
```

**4. saveEdge**

```javascript
edgeService.saveEdge({ /* your edge object */ }, { /* your config */ }).subscribe(savedEdge => {
  console.log('Saved Edge:', savedEdge);
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes({ /* your config */ }).subscribe(edgetype => {
  console.log('Edge Types:', edgetype);
});
```

**6. getCustomerEdgeInfos**

```javascript
edgeService.getCustomerEdgeInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(cutomeredgeinfo => {
  console.log('Customer Edge Infos:', cutomeredgeinfo);
});
```

**7. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer('your-customer-id', 'your-edge-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. makeEdgePublic**

```javascript
edgeService.makeEdgePublic('your-edge-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. getTenantEdgeInfos**

```javascript
edgeService.getTenantEdgeInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(tenantedgeinfo => {
  console.log('Tenant Edge Infos:', tenantedgeinfo);
});
```

**10. findByQuery**

```javascript
edgeService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. getEdgeEvents**

```javascript
edgeService.getEdgeEvents('your-entity-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(edgeevent => {
  console.log('Edge Events:', edgeevent);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains('your-edge-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. findByName**

```javascript
edgeService.findByName('your-edgeName', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**14. bulkImportEdges**

```javascript
edgeService.bulkImportEdges({ /* your entitiesData */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getEdgeInstallInstructions**

```javascript
edgeService.getEdgeInstallInstructions('your-edge-id', { /* your method */ }, { /* your config */ }).subscribe(edgeintallintruction => {
  console.log('Edge Install Instructions:', edgeintallintruction);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
edgeService.getEdgeUpgradeInstructions('your-edgeVersion', { /* your method */ }, { /* your config */ }).subscribe(edgeupgradeintruction => {
  console.log('Edge Upgrade Instructions:', edgeupgradeintruction);
});
```

**17. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable('your-edge-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **ENTITIESVERSIONCONTROLSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
```

**1. clearBranchList**

```javascript
entitiesVersionControlService.clearBranchList().subscribe(result => {
  console.log('Result:', result);
});
```

**2. listBranches**

```javascript
entitiesVersionControlService.listBranches().subscribe(result => {
  console.log('Result:', result);
});
```

**3. getEntityDataInfo**

```javascript
entitiesVersionControlService.getEntityDataInfo('your-externalentity-id', 'your-version-id', { /* your config */ }).subscribe(entitydatainfo => {
  console.log('Entity Data Info:', entitydatainfo);
});
```

**4. saveEntitiesVersion**

```javascript
entitiesVersionControlService.saveEntitiesVersion({ /* your request */ }, { /* your config */ }).subscribe(savedEntitiesVersion => {
  console.log('Saved EntitiesVersion:', savedEntitiesVersion);
});
```

**5. getVersionCreateRequestStatus**

```javascript
entitiesVersionControlService.getVersionCreateRequestStatus('your-request-id', { /* your config */ }).subscribe(verioncreaterequettatu => {
  console.log('Version Create Request Status:', verioncreaterequettatu);
});
```

**6. listEntityVersions**

```javascript
entitiesVersionControlService.listEntityVersions(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-branch', 'your-externalentity-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. listEntityTypeVersions**

```javascript
entitiesVersionControlService.listEntityTypeVersions(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-branch', 'your-entitytype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. listVersions**

```javascript
entitiesVersionControlService.listVersions(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-branch', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. loadEntitiesVersion**

```javascript
entitiesVersionControlService.loadEntitiesVersion({ /* your request */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. getVersionLoadRequestStatus**

```javascript
entitiesVersionControlService.getVersionLoadRequestStatus('your-request-id', { /* your config */ }).subscribe(verionloadrequettatu => {
  console.log('Version Load Request Status:', verionloadrequettatu);
});
```

**11. compareEntityDataToVersion**

```javascript
entitiesVersionControlService.compareEntityDataToVersion('your-entity-id', 'your-version-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. entityLoadErrorToMessage**

```javascript
entitiesVersionControlService.entityLoadErrorToMessage({ /* your entityLoadError */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **ENTITYRELATIONSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('entityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
entityRelationService.saveRelation({ /* your relation */ }, { /* your config */ }).subscribe(savedRelation => {
  console.log('Saved Relation:', savedRelation);
});
```

**2. getRelation**

```javascript
entityRelationService.getRelation('your-from-id', 'your-relationtype', 'your-to-id', { /* your config */ }).subscribe(relation => {
  console.log('Relation:', relation);
});
```

**3. findByFrom**

```javascript
entityRelationService.findByFrom('your-from-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. findInfoByFrom**

```javascript
entityRelationService.findInfoByFrom('your-from-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. findByFromAndType**

```javascript
entityRelationService.findByFromAndType('your-from-id', 'your-relationtype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. findByTo**

```javascript
entityRelationService.findByTo('your-to-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. findInfoByTo**

```javascript
entityRelationService.findInfoByTo('your-to-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. findByToAndType**

```javascript
entityRelationService.findByToAndType('your-to-id', 'your-relationtype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. findByQuery**

```javascript
entityRelationService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. findInfoByQuery**

```javascript
entityRelationService.findInfoByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **ENTITYSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
entityService.getEntityObservable('your-entitytype', 'your-entity-id', { /* your config */ }).subscribe(entityobservable => {
  console.log('Entity Observable:', entityobservable);
});
```

**2. getEntity**

```javascript
entityService.getEntity('your-entitytype', 'your-entity-id', { /* your config */ }).subscribe(entity => {
  console.log('Entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
entityService.getEntitiesObservable('your-entitytype', 'your-entitys-id', { /* your config */ }).subscribe(entitiesobservable => {
  console.log('Entities Observable:', entitiesobservable);
});
```

**4. getEntities**

```javascript
entityService.getEntities('your-entitytype', 'your-entitys-id', { /* your config */ }).subscribe(entity => {
  console.log('Entities:', entity);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
entityService.getSingleTenantByPageLinkObservable(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(singletenantbypagelinkobservable => {
  console.log('Single Tenant By Page Link Observable:', singletenantbypagelinkobservable);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
entityService.getSingleCustomerByPageLinkObservable(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(singlecustomerbypagelinkobservable => {
  console.log('Single Customer By Page Link Observable:', singlecustomerbypagelinkobservable);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
entityService.getEntitiesByPageLinkObservable('your-entitytype', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-subtype', { /* your config */ }).subscribe(entitiesbypagelinkobservable => {
  console.log('Entities By Page Link Observable:', entitiesbypagelinkobservable);
});
```

**8. getEntitiesByPageLink**

```javascript
entityService.getEntitiesByPageLink('your-entitytype', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-subtype', { /* your config */ }).subscribe(entitiesbypagelink => {
  console.log('Entities By Page Link:', entitiesbypagelink);
});
```

**9. getEntitiesByNameFilter**

```javascript
entityService.getEntitiesByNameFilter('your-entitytype', 'your-entityNameFilter', 100, 'your-subtype', { /* your config */ }).subscribe(entitiesbynamefilter => {
  console.log('Entities By Name Filter:', entitiesbynamefilter);
});
```

**10. findEntityDataByQuery**

```javascript
entityService.findEntityDataByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. findEntityKeysByQuery**

```javascript
entityService.findEntityKeysByQuery({ /* your query */ }, { /* your scope */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. findAlarmDataByQuery**

```javascript
entityService.findAlarmDataByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
entityService.findEntityInfosByFilterAndName({ /* your filter */ }, 'your-searchText', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
entityService.findSingleEntityInfoByEntityFilter({ /* your filter */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
entityService.getAliasFilterTypesByEntityTypes('your-entitytypes').subscribe(aliafiltertypebyentitytype => {
  console.log('Alias Filter Types By Entity Types:', aliafiltertypebyentitytype);
});
```

**16. filterAliasByEntityTypes**

```javascript
entityService.filterAliasByEntityTypes({ /* your entityAlias */ }, 'your-entitytypes').subscribe(result => {
  console.log('Result:', result);
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
entityService.filterAliasFilterTypeByEntityTypes('your-aliasfiltertype', 'your-entitytypes').subscribe(result => {
  console.log('Result:', result);
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
entityService.filterAliasFilterTypeByEntityType('your-aliasfiltertype', 'your-entitytype').subscribe(result => {
  console.log('Result:', result);
});
```

**19. prepareAllowedEntityTypesList**

```javascript
entityService.prepareAllowedEntityTypesList('your-allowedentitytypes', 'your-usealiasentitytypes').subscribe(result => {
  console.log('Result:', result);
});
```

**20. getEntityFieldKeys**

```javascript
entityService.getEntityFieldKeys('your-entitytype', { /* your searchText */ }).subscribe(entityfieldkey => {
  console.log('Entity Field Keys:', entityfieldkey);
});
```

**21. getAlarmKeys**

```javascript
entityService.getAlarmKeys({ /* your searchText */ }).subscribe(alarmkey => {
  console.log('Alarm Keys:', alarmkey);
});
```

**22. getEntityKeys**

```javascript
entityService.getEntityKeys('your-entity-id', { /* your query */ }, 'your-type', { /* your config */ }).subscribe(entitykey => {
  console.log('Entity Keys:', entitykey);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
entityService.getEntityKeysByEntityFilter({ /* your filter */ }, 'your-types', 'your-entitytypes', { /* your config */ }).subscribe(entitykeysbyentityfilter => {
  console.log('Entity Keys By Entity Filter:', entitykeysbyentityfilter);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
entityService.getEntityKeysByEntityFilterAndScope({ /* your filter */ }, 'your-types', 'your-entitytypes', { /* your scope */ }, { /* your config */ }).subscribe(entitykeysbyentityfilterandscope => {
  console.log('Entity Keys By Entity Filter And Scope:', entitykeysbyentityfilterandscope);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
entityService.createDatasourcesFromSubscriptionsInfo({ /* your subscriptionsInfo */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
entityService.createAlarmSourceFromSubscriptionInfo({ /* your subscriptionInfo */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
entityService.getAssignedToEdgeEntitiesByType('your-edge-id', 'your-entitytype', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(assignedtoedgeentitiesbytype => {
  console.log('Assigned To Edge Entities By Type:', assignedtoedgeentitiesbytype);
});
```

**28. case**

```javascript
entityService.case().subscribe(result => {
  console.log('Result:', result);
});
```

**29. getEntitySubtypesObservable**

```javascript
entityService.getEntitySubtypesObservable('your-entitytype').subscribe(entitysubtypesobservable => {
  console.log('Entity Subtypes Observable:', entitysubtypesobservable);
});
```

### **ENTITYVIEWSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('entityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

**1. getTenantEntityViewInfos**

```javascript
entityViewService.getTenantEntityViewInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(tenantentityviewinfo => {
  console.log('Tenant Entity View Infos:', tenantentityviewinfo);
});
```

**2. getCustomerEntityViewInfos**

```javascript
entityViewService.getCustomerEntityViewInfos('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(cutomerentityviewinfo => {
  console.log('Customer Entity View Infos:', cutomerentityviewinfo);
});
```

**3. getEntityView**

```javascript
entityViewService.getEntityView('your-entityview-id', { /* your config */ }).subscribe(entityview => {
  console.log('Entity View:', entityview);
});
```

**4. getEntityViews**

```javascript
entityViewService.getEntityViews('your-entityviews-id', { /* your config */ }).subscribe(entityview => {
  console.log('Entity Views:', entityview);
});
```

**5. getEntityViewInfo**

```javascript
entityViewService.getEntityViewInfo('your-entityview-id', { /* your config */ }).subscribe(entityviewinfo => {
  console.log('Entity View Info:', entityviewinfo);
});
```

**6. saveEntityView**

```javascript
entityViewService.saveEntityView({ /* your entityView */ }, { /* your config */ }).subscribe(savedEntityView => {
  console.log('Saved EntityView:', savedEntityView);
});
```

**7. getEntityViewTypes**

```javascript
entityViewService.getEntityViewTypes({ /* your config */ }).subscribe(entityviewtype => {
  console.log('Entity View Types:', entityviewtype);
});
```

**8. makeEntityViewPublic**

```javascript
entityViewService.makeEntityViewPublic('your-entityview-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. assignEntityViewToCustomer**

```javascript
entityViewService.assignEntityViewToCustomer('your-customer-id', 'your-entityview-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. findByQuery**

```javascript
entityViewService.findByQuery({ /* your query */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. assignEntityViewToEdge**

```javascript
entityViewService.assignEntityViewToEdge('your-edge-id', 'your-entityview-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. getEdgeEntityViews**

```javascript
entityViewService.getEdgeEntityViews('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(edgeentityview => {
  console.log('Edge Entity Views:', edgeentityview);
});
```

### **EVENTSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
eventService.getEvents('your-entity-id', 'your-eventtype', 'your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(event => {
  console.log('Events:', event);
});
```

**2. getFilterEvents**

```javascript
eventService.getFilterEvents('your-entity-id', 'your-eventtype', 'your-tenant-id', { /* your filters */ }, self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(filterevent => {
  console.log('Filter Events:', filterevent);
});
```

### **GITHUBSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
```

**1. getGitHubStar**

```javascript
gitHubService.getGitHubStar({ /* your config */ }).subscribe(githubstar => {
  console.log('Git Hub Star:', githubstar);
});
```

### **IMAGESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
```

**1. uploadImage**

```javascript
imageService.uploadImage({ /* your file */ }, 'your-title', 'your-imagesubtype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**2. updateImage**

```javascript
imageService.updateImage('your-type', 'your-key', { /* your file */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**3. updateImageInfo**

```javascript
imageService.updateImageInfo({ /* your imageInfo */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. updateImagePublicStatus**

```javascript
imageService.updateImagePublicStatus({ /* your imageInfo */ }, true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getImages**

```javascript
imageService.getImages(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-imagesubtype', { /* your config */ }).subscribe(image => {
  console.log('Images:', image);
});
```

**6. getImageInfo**

```javascript
imageService.getImageInfo('your-type', 'your-key', { /* your config */ }).subscribe(imageinfo => {
  console.log('Image Info:', imageinfo);
});
```

**7. getImageDataUrl**

```javascript
imageService.getImageDataUrl('your-imageUrl').subscribe(imagedataurl => {
  console.log('Image Data Url:', imagedataurl);
});
```

**8. loadImageDataUrl**

```javascript
imageService.loadImageDataUrl('your-imageLink').subscribe(result => {
  console.log('Result:', result);
});
```

**9. getImageString**

```javascript
imageService.getImageString('your-imageUrl').subscribe(imagestring => {
  console.log('Image String:', imagestring);
});
```

**10. resolveImageUrl**

```javascript
imageService.resolveImageUrl('your-imageUrl').subscribe(result => {
  console.log('Result:', result);
});
```

**11. downloadImage**

```javascript
imageService.downloadImage('your-type', 'your-key').subscribe(result => {
  console.log('Result:', result);
});
```

**12. exportImage**

```javascript
imageService.exportImage('your-type', 'your-key', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. importImage**

```javascript
imageService.importImage({ /* your imageData */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **MOBILEAPPSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
mobileAppService.saveMobileApp({ /* your mobileApp */ }, { /* your config */ }).subscribe(savedMobileApp => {
  console.log('Saved MobileApp:', savedMobileApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
mobileAppService.getTenantMobileAppInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-platformtype', { /* your config */ }).subscribe(tenantmobileappinfo => {
  console.log('Tenant Mobile App Infos:', tenantmobileappinfo);
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById('your-id', { /* your config */ }).subscribe(mobileappinfobyid => {
  console.log('Mobile App Info By Id:', mobileappinfobyid);
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
mobileAppService.getTenantMobileAppBundleInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantmobileappbundleinfo => {
  console.log('Tenant Mobile App Bundle Infos:', tenantmobileappbundleinfo);
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById('your-id', { /* your config */ }).subscribe(mobileappbundleinfobyid => {
  console.log('Mobile App Bundle Info By Id:', mobileappbundleinfobyid);
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

### **MOBILEAPPLICATIONSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
mobileApplicationService.getMobileAppSettings({ /* your config */ }).subscribe(mobileappetting => {
  console.log('Mobile App Settings:', mobileappetting);
});
```

**2. saveMobileAppSettings**

```javascript
mobileApplicationService.saveMobileAppSettings({ /* your mobileAppSettings */ }, { /* your config */ }).subscribe(savedMobileAppSettings => {
  console.log('Saved MobileAppSettings:', savedMobileAppSettings);
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink({ /* your config */ }).subscribe(mobileappdeeplink => {
  console.log('Mobile App Deep Link:', mobileappdeeplink);
});
```

### **NOTIFICATIONSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
notificationService.getNotifications(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(notification => {
  console.log('Notifications:', notification);
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead('your-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. createNotificationRequest**

```javascript
notificationService.createNotificationRequest({ /* your notification */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest('your-entitytype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById('your-id', { /* your config */ }).subscribe(notificationrequestbyid => {
  console.log('Notification Request By Id:', notificationrequestbyid);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods({ /* your config */ }).subscribe(availabledeliverymethod => {
  console.log('Available Delivery Methods:', availabledeliverymethod);
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**10. getNotificationRequestPreview**

```javascript
notificationService.getNotificationRequestPreview({ /* your notification */ }, { /* your config */ }).subscribe(notificationrequestpreview => {
  console.log('Notification Request Preview:', notificationrequestpreview);
});
```

**11. getNotificationRequests**

```javascript
notificationService.getNotificationRequests(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(notificationrequet => {
  console.log('Notification Requests:', notificationrequet);
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings({ /* your config */ }).subscribe(notificationetting => {
  console.log('Notification Settings:', notificationetting);
});
```

**13. saveNotificationSettings**

```javascript
notificationService.saveNotificationSettings({ /* your notificationSettings */ }, { /* your config */ }).subscribe(savedNotificationSettings => {
  console.log('Saved NotificationSettings:', savedNotificationSettings);
});
```

**14. listSlackConversations**

```javascript
notificationService.listSlackConversations('your-type', 'your-token', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. saveNotificationRule**

```javascript
notificationService.saveNotificationRule({ /* your notificationRule */ }, { /* your config */ }).subscribe(savedNotificationRule => {
  console.log('Saved NotificationRule:', savedNotificationRule);
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById('your-id', { /* your config */ }).subscribe(notificationrulebyid => {
  console.log('Notification Rule By Id:', notificationrulebyid);
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**18. getNotificationRules**

```javascript
notificationService.getNotificationRules(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(notificationrule => {
  console.log('Notification Rules:', notificationrule);
});
```

**19. saveNotificationTarget**

```javascript
notificationService.saveNotificationTarget({ /* your notificationTarget */ }, { /* your config */ }).subscribe(savedNotificationTarget => {
  console.log('Saved NotificationTarget:', savedNotificationTarget);
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById('your-id', { /* your config */ }).subscribe(notificationtargetbyid => {
  console.log('Notification Target By Id:', notificationtargetbyid);
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds(['id1', 'id2'], { /* your config */ }).subscribe(notificationtargetbyid => {
  console.log('Notification Targets By Ids:', notificationtargetbyid);
});
```

**23. getNotificationTargets**

```javascript
notificationService.getNotificationTargets(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(notificationtarget => {
  console.log('Notification Targets:', notificationtarget);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
notificationService.getRecipientsForNotificationTargetConfig({ /* your notificationTarget */ }, self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(recipientsfornotificationtargetconfig => {
  console.log('Recipients For Notification Target Config:', recipientsfornotificationtargetconfig);
});
```

**25. saveNotificationTemplate**

```javascript
notificationService.saveNotificationTemplate({ /* your notificationTarget */ }, { /* your config */ }).subscribe(savedNotificationTemplate => {
  console.log('Saved NotificationTemplate:', savedNotificationTemplate);
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById('your-id', { /* your config */ }).subscribe(notificationtemplatebyid => {
  console.log('Notification Template By Id:', notificationtemplatebyid);
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**28. getNotificationTemplates**

```javascript
notificationService.getNotificationTemplates(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-notificationtypes', { /* your config */ }).subscribe(notificationtemplate => {
  console.log('Notification Templates:', notificationtemplate);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings({ /* your config */ }).subscribe(notificationueretting => {
  console.log('Notification User Settings:', notificationueretting);
});
```

**30. saveNotificationUserSettings**

```javascript
notificationService.saveNotificationUserSettings({ /* your settings */ }, { /* your config */ }).subscribe(savedNotificationUserSettings => {
  console.log('Saved NotificationUserSettings:', savedNotificationUserSettings);
});
```

### **OAUTH2SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template({ /* your config */ }).subscribe(oauth2template => {
  console.log('O Auth2 Template:', oauth2template);
});
```

**2. saveOAuth2Client**

```javascript
oAuth2Service.saveOAuth2Client({ /* your oAuth2Client */ }, { /* your config */ }).subscribe(savedOAuth2Client => {
  console.log('Saved OAuth2Client:', savedOAuth2Client);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
oAuth2Service.findTenantOAuth2ClientInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2Service.findTenantOAuth2ClientInfosByIds(['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getOAuth2ClientById**

```javascript
oAuth2Service.getOAuth2ClientById('your-id', { /* your config */ }).subscribe(oauth2clientbyid => {
  console.log('O Auth2 Client By Id:', oauth2clientbyid);
});
```

**6. deleteOauth2Client**

```javascript
oAuth2Service.deleteOauth2Client('your-id', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl({ /* your config */ }).subscribe(loginprocessingurl => {
  console.log('Login Processing Url:', loginprocessingurl);
});
```

### **OTAPACKAGESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
otaPackageService.getOtaPackages(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(otapackage => {
  console.log('Ota Packages:', otapackage);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
otaPackageService.getOtaPackagesInfoByDeviceProfileId(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-deviceprofile-id', 'your-type', { /* your config */ }).subscribe(otapackagesinfobydeviceprofileid => {
  console.log('Ota Packages Info By Device Profile Id:', otapackagesinfobydeviceprofileid);
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage('your-otapackage-id', { /* your config */ }).subscribe(otapackage => {
  console.log('Ota Package:', otapackage);
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo('your-otapackage-id', { /* your config */ }).subscribe(otapackageinfo => {
  console.log('Ota Package Info:', otapackageinfo);
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage('your-otapackage-id').subscribe(result => {
  console.log('Result:', result);
});
```

**6. saveOtaPackage**

```javascript
otaPackageService.saveOtaPackage({ /* your otaPackage */ }, { /* your config */ }).subscribe(savedOtaPackage => {
  console.log('Saved OtaPackage:', savedOtaPackage);
});
```

**7. saveOtaPackageInfo**

```javascript
otaPackageService.saveOtaPackageInfo({ /* your otaPackageInfo */ }, { /* your config */ }).subscribe(savedOtaPackageInfo => {
  console.log('Saved OtaPackageInfo:', savedOtaPackageInfo);
});
```

**8. uploadOtaPackageFile**

```javascript
otaPackageService.uploadOtaPackageFile('your-otapackage-id', { /* your file */ }, { /* your checksumAlgorithm */ }, 'your-checksum', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage('your-type', 'your-entity-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. confirmDialogUpdatePackage**

```javascript
otaPackageService.confirmDialogUpdatePackage({ /* your entity */ }, { /* your originEntity */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **QUEUESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

**1. getQueueById**

```javascript
queueService.getQueueById('your-queue-id', { /* your config */ }).subscribe(queuebyid => {
  console.log('Queue By Id:', queuebyid);
});
```

**2. getQueueByName**

```javascript
queueService.getQueueByName('your-queueName', { /* your config */ }).subscribe(queuebyname => {
  console.log('Queue By Name:', queuebyname);
});
```

**3. getTenantQueuesByServiceType**

```javascript
queueService.getTenantQueuesByServiceType(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-servicetype', { /* your config */ }).subscribe(tenantqueuesbyservicetype => {
  console.log('Tenant Queues By Service Type:', tenantqueuesbyservicetype);
});
```

**4. saveQueue**

```javascript
queueService.saveQueue({ /* your queue */ }, 'your-servicetype', { /* your config */ }).subscribe(savedQueue => {
  console.log('Saved Queue:', savedQueue);
});
```

**5. getQueueStatistics**

```javascript
queueService.getQueueStatistics(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(queuetatitic => {
  console.log('Queue Statistics:', queuetatitic);
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById('your-queuestat-id', { /* your config */ }).subscribe(queuestatisticsbyid => {
  console.log('Queue Statistics By Id:', queuestatisticsbyid);
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds(['id1', 'id2'], { /* your config */ }).subscribe(queuetatiticbyid => {
  console.log('Queue Statistics By Ids:', queuetatiticbyid);
});
```

### **RESOURCESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('resourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```

**1. getResources**

```javascript
resourceService.getResources(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-resourcetype', 'your-resourcesubtype', { /* your config */ }).subscribe(reource => {
  console.log('Resources:', reource);
});
```

**2. getTenantResources**

```javascript
resourceService.getTenantResources(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantreource => {
  console.log('Tenant Resources:', tenantreource);
});
```

**3. getResource**

```javascript
resourceService.getResource('your-resource-id', { /* your config */ }).subscribe(resource => {
  console.log('Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
resourceService.getResourceInfoById('your-resource-id', { /* your config */ }).subscribe(resourceinfobyid => {
  console.log('Resource Info By Id:', resourceinfobyid);
});
```

**5. getResourceInfo**

```javascript
resourceService.getResourceInfo('your-type', { /* your scope */ }, 'your-key', { /* your config */ }).subscribe(resourceinfo => {
  console.log('Resource Info:', resourceinfo);
});
```

**6. downloadResource**

```javascript
resourceService.downloadResource('your-resource-id').subscribe(result => {
  console.log('Result:', result);
});
```

**7. saveResources**

```javascript
resourceService.saveResources(['id1', 'id2'], { /* your config */ }).subscribe(savedResources => {
  console.log('Saved Resources:', savedResources);
});
```

**8. saveResource**

```javascript
resourceService.saveResource({ /* your resource */ }, { /* your config */ }).subscribe(savedResource => {
  console.log('Saved Resource:', savedResource);
});
```

**9. uploadResources**

```javascript
resourceService.uploadResources(['id1', 'id2'], { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. uploadResource**

```javascript
resourceService.uploadResource({ /* your resource */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. updatedResourceInfo**

```javascript
resourceService.updatedResourceInfo('your-resource-id', { /* your updatedResources */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**12. updatedResourceData**

```javascript
resourceService.updatedResourceData('your-resource-id', { /* your data */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. getResourcesByIds**

```javascript
resourceService.getResourcesByIds(['id1', 'id2'], { /* your config */ }).subscribe(reourcebyid => {
  console.log('Resources By Ids:', reourcebyid);
});
```

### **RULECHAINSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
ruleChainService.getRuleChains(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-type', { /* your config */ }).subscribe(rulechain => {
  console.log('Rule Chains:', rulechain);
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds(['id1', 'id2'], { /* your config */ }).subscribe(rulechainbyid => {
  console.log('Rule Chains By Ids:', rulechainbyid);
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain('your-rulechain-id', { /* your config */ }).subscribe(rulechain => {
  console.log('Rule Chain:', rulechain);
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels('your-rulechain-id', { /* your config */ }).subscribe(rulechainoutputlabel => {
  console.log('Rule Chain Output Labels:', rulechainoutputlabel);
});
```

**5. createDefaultRuleChain**

```javascript
ruleChainService.createDefaultRuleChain('your-ruleChainName', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. saveRuleChain**

```javascript
ruleChainService.saveRuleChain({ /* your ruleChain */ }, { /* your config */ }).subscribe(savedRuleChain => {
  console.log('Saved RuleChain:', savedRuleChain);
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain('your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata('your-rulechain-id', { /* your config */ }).subscribe(rulechainmetadata => {
  console.log('Rule Chain Metadata:', rulechainmetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
ruleChainService.saveRuleChainMetadata({ /* your ruleChainMetaData */ }, { /* your config */ }).subscribe(savedRuleChainMetadata => {
  console.log('Saved RuleChainMetadata:', savedRuleChainMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
ruleChainService.getRuleNodeComponents({ /* your modulesMap */ }, 'your-rulechaintype', { /* your config */ }).subscribe(rulenodecomponent => {
  console.log('Rule Node Components:', rulenodecomponent);
});
```

**11. getRuleNodeConfigComponent**

```javascript
ruleChainService.getRuleNodeConfigComponent('your-directive').subscribe(rulenodeconfigcomponent => {
  console.log('Rule Node Config Component:', rulenodeconfigcomponent);
});
```

**12. getRuleNodeComponentByClazz**

```javascript
ruleChainService.getRuleNodeComponentByClazz('your-rulechaintype', 'your-clazz').subscribe(rulenodecomponentbyclazz => {
  console.log('Rule Node Component By Clazz:', rulenodecomponentbyclazz);
});
```

**13. getRuleNodeSupportedLinks**

```javascript
ruleChainService.getRuleNodeSupportedLinks({ /* your component */ }).subscribe(rulenodeupportedlink => {
  console.log('Rule Node Supported Links:', rulenodeupportedlink);
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
ruleChainService.ruleNodeAllowCustomLinks({ /* your component */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
ruleChainService.ruleNodeSourceRuleChainId({ /* your component */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput('your-rulenode-id', { /* your config */ }).subscribe(latestrulenodedebuginput => {
  console.log('Latest Rule Node Debug Input:', latestrulenodedebuginput);
});
```

**17. testScript**

```javascript
ruleChainService.testScript({ /* your inputParams */ }, { /* your scriptLang */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents('your-rulechaintype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentsUiResources(['id1', 'id2'], { /* your modulesMap */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentUiResources({ /* your component */ }, { /* your modulesMap */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**21. getEdgeRuleChains**

```javascript
ruleChainService.getEdgeRuleChains('your-edge-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(edgerulechain => {
  console.log('Edge Rule Chains:', edgerulechain);
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge('your-edge-id', 'your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain('your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain('your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain('your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains({ /* your config */ }).subscribe(autoaigntoedgerulechain => {
  console.log('Auto Assign To Edge Rule Chains:', autoaigntoedgerulechain);
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain('your-edge-id', 'your-rulechain-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **TENANTPROFILESERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
tenantProfileService.getTenantProfiles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantprofile => {
  console.log('Tenant Profiles:', tenantprofile);
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile('your-tenantprofile-id', { /* your config */ }).subscribe(tenantprofile => {
  console.log('Tenant Profile:', tenantprofile);
});
```

**3. saveTenantProfile**

```javascript
tenantProfileService.saveTenantProfile({ /* your tenantProfile */ }, { /* your config */ }).subscribe(savedTenantProfile => {
  console.log('Saved TenantProfile:', savedTenantProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile('your-tenantprofile-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo({ /* your config */ }).subscribe(defaulttenantprofileinfo => {
  console.log('Default Tenant Profile Info:', defaulttenantprofileinfo);
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo('your-tenantprofile-id', { /* your config */ }).subscribe(tenantprofileinfo => {
  console.log('Tenant Profile Info:', tenantprofileinfo);
});
```

**7. getTenantProfileInfos**

```javascript
tenantProfileService.getTenantProfileInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantprofileinfo => {
  console.log('Tenant Profile Infos:', tenantprofileinfo);
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds(['id1', 'id2'], { /* your config */ }).subscribe(tenantprofilebyid => {
  console.log('Tenant Profiles By Ids:', tenantprofilebyid);
});
```

### **TENANTSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
tenantService.getTenants(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenant => {
  console.log('Tenants:', tenant);
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds(['id1', 'id2'], { /* your config */ }).subscribe(tenantbyid => {
  console.log('Tenants By Ids:', tenantbyid);
});
```

**3. getTenantInfos**

```javascript
tenantService.getTenantInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantinfo => {
  console.log('Tenant Infos:', tenantinfo);
});
```

**4. getTenant**

```javascript
tenantService.getTenant('your-tenant-id', { /* your config */ }).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo('your-tenant-id', { /* your config */ }).subscribe(tenantinfo => {
  console.log('Tenant Info:', tenantinfo);
});
```

**6. saveTenant**

```javascript
tenantService.saveTenant({ /* your tenant object */ }, { /* your config */ }).subscribe(savedTenant => {
  console.log('Saved Tenant:', savedTenant);
});
```

### **TRENDZSETTINGSSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
trendzSettingsService.getTrendzSettings({ /* your config */ }).subscribe(trendzetting => {
  console.log('Trendz Settings:', trendzetting);
});
```

**2. saveTrendzSettings**

```javascript
trendzSettingsService.saveTrendzSettings({ /* your trendzSettings */ }, { /* your config */ }).subscribe(savedTrendzSettings => {
  console.log('Saved TrendzSettings:', savedTrendzSettings);
});
```

### **TWOFACTORAUTHENTICATIONSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings({ /* your config */ }).subscribe(twofaetting => {
  console.log('Two Fa Settings:', twofaetting);
});
```

**2. saveTwoFaSettings**

```javascript
twoFactorAuthenticationService.saveTwoFaSettings({ /* your settings */ }, { /* your config */ }).subscribe(savedTwoFaSettings => {
  console.log('Saved TwoFaSettings:', savedTwoFaSettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders({ /* your config */ }).subscribe(availabletwofaprovider => {
  console.log('Available Two Fa Providers:', availabletwofaprovider);
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig('your-providertype', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings({ /* your config */ }).subscribe(accounttwofaetting => {
  console.log('Account Two Fa Settings:', accounttwofaetting);
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig('your-providertype', true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**7. submitTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.submitTwoFaAccountConfig({ /* your authConfig */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig({ /* your authConfig */ }, 100, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig('your-providertype', { /* your config */ }).subscribe(result => {
  console.log('Delete Result:', result);
});
```

### **UISETTINGSSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('uiSettingsService'));
```

**1. getHelpBaseUrl**

```javascript
uiSettingsService.getHelpBaseUrl().subscribe(helpbaseurl => {
  console.log('Help Base Url:', helpbaseurl);
});
```

### **USAGEINFOSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('usageInfoService'));
```

**1. getUsageInfo**

```javascript
usageInfoService.getUsageInfo({ /* your config */ }).subscribe(usageinfo => {
  console.log('Usage Info:', usageinfo);
});
```

### **USERSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

**1. getUsers**

```javascript
userService.getUsers(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(uer => {
  console.log('Users:', uer);
});
```

**2. getTenantAdmins**

```javascript
userService.getTenantAdmins('your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantadmin => {
  console.log('Tenant Admins:', tenantadmin);
});
```

**3. getCustomerUsers**

```javascript
userService.getCustomerUsers('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(cutomeruer => {
  console.log('Customer Users:', cutomeruer);
});
```

**4. getUsersForAssign**

```javascript
userService.getUsersForAssign('your-alarm-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(usersforassign => {
  console.log('Users For Assign:', usersforassign);
});
```

**5. getUser**

```javascript
userService.getUser('your-user-id', { /* your config */ }).subscribe(user => {
  console.log('User:', user);
});
```

**6. getUsersByIds**

```javascript
userService.getUsersByIds(['id1', 'id2'], { /* your config */ }).subscribe(uerbyid => {
  console.log('Users By Ids:', uerbyid);
});
```

**7. saveUser**

```javascript
userService.saveUser({ /* your user object */ }, { /* your sendActivationMail */ }, { /* your config */ }).subscribe(savedUser => {
  console.log('Saved User:', savedUser);
});
```

**8. getActivationLink**

```javascript
userService.getActivationLink('your-user-id', { /* your config */ }).subscribe(activationlink => {
  console.log('Activation Link:', activationlink);
});
```

**9. getActivationLinkInfo**

```javascript
userService.getActivationLinkInfo('your-user-id', { /* your config */ }).subscribe(activationlinkinfo => {
  console.log('Activation Link Info:', activationlinkinfo);
});
```

**10. setUserCredentialsEnabled**

```javascript
userService.setUserCredentialsEnabled('your-user-id', true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. findUsersByQuery**

```javascript
userService.findUsersByQuery(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **USERSETTINGSSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('userSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```

**1. loadUserSettings**

```javascript
userSettingsService.loadUserSettings().subscribe(result => {
  console.log('Result:', result);
});
```

**2. saveUserSettings**

```javascript
userSettingsService.saveUserSettings({ /* your userSettings */ }).subscribe(savedUserSettings => {
  console.log('Saved UserSettings:', savedUserSettings);
});
```

**3. putUserSettings**

```javascript
userSettingsService.putUserSettings({ /* your userSettingsData */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**4. getDocumentationLinks**

```javascript
userSettingsService.getDocumentationLinks({ /* your config */ }).subscribe(documentationlink => {
  console.log('Documentation Links:', documentationlink);
});
```

**5. updateDocumentationLinks**

```javascript
userSettingsService.updateDocumentationLinks({ /* your documentationLinks */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**6. getQuickLinks**

```javascript
userSettingsService.getQuickLinks({ /* your config */ }).subscribe(quicklink => {
  console.log('Quick Links:', quicklink);
});
```

**7. updateQuickLinks**

```javascript
userSettingsService.updateQuickLinks({ /* your quickLinks */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. getGettingStarted**

```javascript
userSettingsService.getGettingStarted({ /* your config */ }).subscribe(gettingstarted => {
  console.log('Getting Started:', gettingstarted);
});
```

**9. updateGettingStarted**

```javascript
userSettingsService.updateGettingStarted({ /* your gettingStarted */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. getUserDashboardsInfo**

```javascript
userSettingsService.getUserDashboardsInfo({ /* your config */ }).subscribe(userdashboardsinfo => {
  console.log('User Dashboards Info:', userdashboardsinfo);
});
```

**11. reportUserDashboardAction**

```javascript
userSettingsService.reportUserDashboardAction('your-dashboard-id', { /* your action */ }, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

### **WIDGETSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(widgetcopevariable => {
  console.log('Widget Scope Variables:', widgetcopevariable);
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles({ /* your config */ }).subscribe(allwidgetbundle => {
  console.log('All Widgets Bundles:', allwidgetbundle);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles({ /* your config */ }).subscribe(ytemwidgetbundle => {
  console.log('System Widgets Bundles:', ytemwidgetbundle);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles({ /* your config */ }).subscribe(tenantwidgetbundle => {
  console.log('Tenant Widgets Bundles:', tenantwidgetbundle);
});
```

**5. getWidgetBundles**

```javascript
widgetService.getWidgetBundles(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(widgetbundle => {
  console.log('Widget Bundles:', widgetbundle);
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle('your-widgetsbundle-id', { /* your config */ }).subscribe(widgetsbundle => {
  console.log('Widgets Bundle:', widgetsbundle);
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle('your-widgetsbundle-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle({ /* your widgetsBundle */ }, { /* your config */ }).subscribe(savedWidgetsBundle => {
  console.log('Saved WidgetsBundle:', savedWidgetsBundle);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes('your-widgetsbundle-id', 'your-widgettypeids', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns('your-widgetsbundle-id', 'your-widgettypefqns', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes('your-widgetsbundle-id', { /* your config */ }).subscribe(bundlewidgettype => {
  console.log('Bundle Widget Types:', bundlewidgettype);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails('your-widgetsbundle-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns('your-widgetsbundle-id', { /* your config */ }).subscribe(bundlewidgettypefqn => {
  console.log('Bundle Widget Type Fqns:', bundlewidgettypefqn);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList('your-widgetsbundle-id', { /* your config */ }).subscribe(bundlewidgettypeinfolit => {
  console.log('Bundle Widget Type Infos List:', bundlewidgettypeinfolit);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
widgetService.getBundleWidgetTypeInfos(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-widgetsbundle-id', 'your-widgettypes', { /* your config */ }).subscribe(bundlewidgettypeinfo => {
  console.log('Bundle Widget Type Infos:', bundlewidgettypeinfo);
});
```

**16. getWidgetType**

```javascript
widgetService.getWidgetType('your-fullFqn', { /* your config */ }).subscribe(widgettype => {
  console.log('Widget Type:', widgettype);
});
```

**17. saveWidgetTypeDetails**

```javascript
widgetService.saveWidgetTypeDetails({ /* your widgetInfo */ }, { /* your id */ }, 100, 100, { /* your config */ }).subscribe(savedWidgetTypeDetails => {
  console.log('Saved WidgetTypeDetails:', savedWidgetTypeDetails);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails('your-widgettypedetails', { /* your config */ }).subscribe(savedImportedWidgetTypeDetails => {
  console.log('Saved ImportedWidgetTypeDetails:', savedImportedWidgetTypeDetails);
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById('your-widgettype-id', { /* your config */ }).subscribe(widgettypebyid => {
  console.log('Widget Type By Id:', widgettypebyid);
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType('your-widgettype-id', { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById('your-widgettype-id', { /* your config */ }).subscribe(widgettypeinfobyid => {
  console.log('Widget Type Info By Id:', widgettypeinfobyid);
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType('your-widgettypedetails', { /* your config */ }).subscribe(savedWidgetType => {
  console.log('Saved WidgetType:', savedWidgetType);
});
```

**23. getWidgetTypes**

```javascript
widgetService.getWidgetTypes(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-widgettypes', { /* your config */ }).subscribe(widgettype => {
  console.log('Widget Types:', widgettype);
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate('your-widgettypeparam', { /* your config */ }).subscribe(widgettemplate => {
  console.log('Widget Template:', widgettemplate);
});
```

**25. getWidgetInfoFromCache**

```javascript
widgetService.getWidgetInfoFromCache('your-fullFqn').subscribe(widgetinfofromcache => {
  console.log('Widget Info From Cache:', widgetinfofromcache);
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
widgetService.getBasicWidgetSettingsComponentBySelector('your-selector').subscribe(basicwidgetsettingscomponentbyselector => {
  console.log('Basic Widget Settings Component By Selector:', basicwidgetsettingscomponentbyselector);
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
widgetService.getWidgetSettingsComponentTypeBySelector('your-selector').subscribe(widgetsettingscomponenttypebyselector => {
  console.log('Widget Settings Component Type By Selector:', widgetsettingscomponenttypebyselector);
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated('your-updatedwidgettype').subscribe(result => {
  console.log('Result:', result);
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds(['id1', 'id2'], { /* your config */ }).subscribe(widgetbundlebyid => {
  console.log('Widgets Bundles By Ids:', widgetbundlebyid);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache({ /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
