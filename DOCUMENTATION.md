# ThingsBoard CE Widget Services Documentation

*Generated from ThingsBoard CE source code. Copy-paste ready examples.*

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

PageLinks are pagination helpers that prevent overloading the ThingsBoard server when you have 1000+ results. They specify page size and offset.

Create a page link using `self.ctx.pageLink`:

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
```

- `pageSize` (10) — results per page
- `pageNumber` (0) — zero-based page index
- `searchText` — optional text filter
- `sortProperty` — field to sort by
- `sortOrder` — 'ASC' or 'DESC'

---

## Table of Contents

- [ADMIN SERVICE](#admin-service)
- [AI MODEL SERVICE](#ai-model-service)
- [ALARM COMMENT SERVICE](#alarm-comment-service)
- [ALARM RULES SERVICE](#alarm-rules-service)
- [ALARM SERVICE](#alarm-service)
- [API KEY SERVICE](#api-key-service)
- [ASSET PROFILE SERVICE](#asset-profile-service)
- [ASSET SERVICE](#asset-service)
- [ATTRIBUTE SERVICE](#attribute-service)
- [AUDIT LOG SERVICE](#audit-log-service)
- [CALCULATED FIELDS SERVICE](#calculated-fields-service)
- [COMPONENT DESCRIPTOR SERVICE](#component-descriptor-service)
- [CUSTOMER SERVICE](#customer-service)
- [DASHBOARD SERVICE](#dashboard-service)
- [DEVICE PROFILE SERVICE](#device-profile-service)
- [DEVICE SERVICE](#device-service)
- [DOMAIN SERVICE](#domain-service)
- [EDGE SERVICE](#edge-service)
- [ENTITIES VERSION CONTROL SERVICE](#entities-version-control-service)
- [ENTITY RELATION SERVICE](#entity-relation-service)
- [ENTITY SERVICE](#entity-service)
- [ENTITY VIEW SERVICE](#entity-view-service)
- [EVENT SERVICE](#event-service)
- [GIT HUB SERVICE](#git-hub-service)
- [IMAGE SERVICE](#image-service)
- [MOBILE APP SERVICE](#mobile-app-service)
- [MOBILE APPLICATION SERVICE](#mobile-application-service)
- [NOTIFICATION SERVICE](#notification-service)
- [O AUTH 2 SERVICE](#o-auth-2-service)
- [OTA PACKAGE SERVICE](#ota-package-service)
- [QUEUE SERVICE](#queue-service)
- [RESOURCE SERVICE](#resource-service)
- [RULE CHAIN SERVICE](#rule-chain-service)
- [TENANT PROFILE SERVICE](#tenant-profile-service)
- [TENANT SERVICE](#tenant-service)
- [TRENDZ SETTINGS SERVICE](#trendz-settings-service)
- [TWO FACTOR AUTHENTICATION SERVICE](#two-factor-authentication-service)
- [UI SETTINGS SERVICE](#ui-settings-service)
- [USAGE INFO SERVICE](#usage-info-service)
- [USER SERVICE](#user-service)
- [USER SETTINGS SERVICE](#user-settings-service)
- [WIDGET SERVICE](#widget-service)

---

### **ADMIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
adminService.sendTestMail('your-adminsettings-value').subscribe(result => {
  console.log('Send Test Mail:', result);
});
```

**2. sendTestSms**

```javascript
adminService.sendTestSms('your-testsmsrequest-value').subscribe(result => {
  console.log('Send Test Sms:', result);
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings().subscribe(securitySettings => {
  console.log('Get Security Settings:', securitySettings);
});
```

**4. saveSecuritySettings**

```javascript
adminService.saveSecuritySettings('your-securitysettings-value').subscribe(securitySettings => {
  console.log('Save Security Settings:', securitySettings);
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings().subscribe(jwtSettings => {
  console.log('Get Jwt Settings:', jwtSettings);
});
```

**6. saveJwtSettings**

```javascript
adminService.saveJwtSettings('your-jwtsettings-value').subscribe(jwtSettings => {
  console.log('Save Jwt Settings:', jwtSettings);
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(repositorySettings => {
  console.log('Get Repository Settings:', repositorySettings);
});
```

**8. saveRepositorySettings**

```javascript
adminService.saveRepositorySettings('your-repositorysettings-value').subscribe(repositorySettings => {
  console.log('Save Repository Settings:', repositorySettings);
});
```

**9. checkRepositoryAccess**

```javascript
adminService.checkRepositoryAccess('your-repositorysettings-value').subscribe(result => {
  console.log('Check Repository Access:', result);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(repositorySettingsInfo => {
  console.log('Get Repository Settings Info:', repositorySettingsInfo);
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(autoCommitSettings => {
  console.log('Get Auto Commit Settings:', autoCommitSettings);
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(autoCommitSettingsExists => {
  console.log('Auto Commit Settings Exists:', autoCommitSettingsExists);
});
```

**13. saveAutoCommitSettings**

```javascript
adminService.saveAutoCommitSettings('your-autocommitsettings-value').subscribe(autoCommitSettings => {
  console.log('Save Auto Commit Settings:', autoCommitSettings);
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(updates => {
  console.log('Check Updates:', updates);
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(featuresInfo => {
  console.log('Get Features Info:', featuresInfo);
});
```

**16. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```

**17. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(accessToken => {
  console.log('Generate Access Token:', accessToken);
});
```

**18. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(mailConfigTemplate => {
  console.log('Get Mail Config Template:', mailConfigTemplate);
});
```

---

### **AI MODEL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiModelService = $injector.get(self.ctx.servicesMap.get('aiModelService'));
```

**1. saveAiModel**

```javascript
aiModelService.saveAiModel('your-aimodel-value').subscribe(aiModel => {
  console.log('Save Ai Model:', aiModel);
});
```

**2. getAiModels**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aiModelService.getAiModels(pageLink).subscribe(aiModels => {
  console.log('Get Ai Models:', aiModels);
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById('your-aimodel-id').subscribe(aiModelById => {
  console.log('Get Ai Model By Id:', aiModelById);
});
```

**4. checkConnectivity**

```javascript
aiModelService.checkConnectivity('your-aimodelwithusermsg-value').subscribe(connectivity => {
  console.log('Check Connectivity:', connectivity);
});
```

---

### **ALARM COMMENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmCommentService = $injector.get(self.ctx.servicesMap.get('alarmCommentService'));
```

**1. saveAlarmComment**

```javascript
alarmCommentService.saveAlarmComment('your-alarm-id', 'your-alarmcomment-value').subscribe(alarmComment => {
  console.log('Save Alarm Comment:', alarmComment);
});
```

**2. getAlarmComments**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmCommentService.getAlarmComments('your-alarm-id', pageLink).subscribe(alarmComments => {
  console.log('Get Alarm Comments:', alarmComments);
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments('your-alarm-id', 'your-comment-id').subscribe(result => {
  console.log('Delete Alarm Comments:', result);
});
```

---

### **ALARM RULES SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmRulesService = $injector.get(self.ctx.servicesMap.get('alarmRulesService'));
```

**1. getAlarmRuleById**

```javascript
alarmRulesService.getAlarmRuleById('your-alarmrule-id').subscribe(alarmRuleById => {
  console.log('Get Alarm Rule By Id:', alarmRuleById);
});
```

**2. saveAlarmRule**

```javascript
alarmRulesService.saveAlarmRule('your-alarmrule-value').subscribe(alarmRule => {
  console.log('Save Alarm Rule:', alarmRule);
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule('your-alarmrule-id').subscribe(alarmRule => {
  console.log('Delete Alarm Rule:', alarmRule);
});
```

**4. getAlarmRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRules(pageLink, 'your-query-value').subscribe(alarmRules => {
  console.log('Get Alarm Rules:', alarmRules);
});
```

**5. getAlarmRulesByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRulesByEntityId(pageLink).subscribe(alarmRulesByEntityId => {
  console.log('Get Alarm Rules By Entity Id:', alarmRulesByEntityId);
});
```

**6. testScript**

```javascript
alarmRulesService.testScript('your-inputparams-value').subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent('your--id').subscribe(latestAlarmRuleDebugEvent => {
  console.log('Get Latest Alarm Rule Debug Event:', latestAlarmRuleDebugEvent);
});
```

**8. getAlarmRuleNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRuleNames(pageLink).subscribe(alarmRuleNames => {
  console.log('Get Alarm Rule Names:', alarmRuleNames);
});
```

---

### **ALARM SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const alarmService = $injector.get(self.ctx.servicesMap.get('alarmService'));
```

**1. getAlarm**

```javascript
alarmService.getAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Get Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo('your-alarm-id').subscribe(alarmInfo => {
  console.log('Get Alarm Info:', alarmInfo);
});
```

**3. saveAlarm**

```javascript
alarmService.saveAlarm('your-alarm-value').subscribe(alarm => {
  console.log('Save Alarm:', alarm);
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Ack Alarm:', alarm);
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Clear Alarm:', alarm);
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm('your-alarm-id', 'your-assignee-id').subscribe(result => {
  console.log('Assign Alarm:', result);
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm('your-alarm-id').subscribe(result => {
  console.log('Unassign Alarm:', result);
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm('your-alarm-id').subscribe(alarm => {
  console.log('Delete Alarm:', alarm);
});
```

**9. getAlarms**

```javascript
alarmService.getAlarms('your-query-value').subscribe(alarms => {
  console.log('Get Alarms:', alarms);
});
```

**10. getAlarmsV2**

```javascript
alarmService.getAlarmsV2('your-query-value').subscribe(alarmsV2 => {
  console.log('Get Alarms V 2:', alarmsV2);
});
```

**11. getAllAlarms**

```javascript
alarmService.getAllAlarms('your-query-value').subscribe(allAlarms => {
  console.log('Get All Alarms:', allAlarms);
});
```

**12. getAllAlarmsV2**

```javascript
alarmService.getAllAlarmsV2('your-query-value').subscribe(allAlarmsV2 => {
  console.log('Get All Alarms V 2:', allAlarmsV2);
});
```

**13. getHighestAlarmSeverity**

```javascript
alarmService.getHighestAlarmSeverity('your-entity-id', 'your-alarmsearchstatus-value', 'your-alarmstatus-value').subscribe(highestAlarmSeverity => {
  console.log('Get Highest Alarm Severity:', highestAlarmSeverity);
});
```

**14. getAlarmTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmService.getAlarmTypes(pageLink).subscribe(alarmTypes => {
  console.log('Get Alarm Types:', alarmTypes);
});
```

---

### **API KEY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
apiKeyService.saveApiKey('your-api-key').subscribe(apiKey => {
  console.log('Save Api Key:', apiKey);
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey('your--id').subscribe(result => {
  console.log('Delete Api Key:', result);
});
```

**3. updateApiKeyDescription**

```javascript
apiKeyService.updateApiKeyDescription('your--id', 'your-description-value').subscribe(apiKeyDescription => {
  console.log('Update Api Key Description:', apiKeyDescription);
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey('your--id', true).subscribe(enableApiKey => {
  console.log('Enable Api Key:', enableApiKey);
});
```

**5. getUserApiKeys**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apiKeyService.getUserApiKeys('your-user-id', pageLink).subscribe(userApiKeys => {
  console.log('Get User Api Keys:', userApiKeys);
});
```

---

### **ASSET PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfiles(pageLink).subscribe(assetProfiles => {
  console.log('Get Asset Profiles:', assetProfiles);
});
```

**2. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds('your-assetprofileids-value').subscribe(assetProfilesByIds => {
  console.log('Get Asset Profiles By Ids:', assetProfilesByIds);
});
```

**3. getAssetProfile**

```javascript
assetProfileService.getAssetProfile('your-assetprofile-id').subscribe(assetProfile => {
  console.log('Get Asset Profile:', assetProfile);
});
```

**4. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile('your-assetprofile-id').subscribe(assetProfile => {
  console.log('Export Asset Profile:', assetProfile);
});
```

**5. saveAssetProfile**

```javascript
assetProfileService.saveAssetProfile('your-assetprofile-value').subscribe(assetProfile => {
  console.log('Save Asset Profile:', assetProfile);
});
```

**6. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile('your-assetprofile-id').subscribe(defaultAssetProfile => {
  console.log('Set Default Asset Profile:', defaultAssetProfile);
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(defaultAssetProfileInfo => {
  console.log('Get Default Asset Profile Info:', defaultAssetProfileInfo);
});
```

**8. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo('your-assetprofile-id').subscribe(assetProfileInfo => {
  console.log('Get Asset Profile Info:', assetProfileInfo);
});
```

**9. getAssetProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(assetProfileInfos => {
  console.log('Get Asset Profile Infos:', assetProfileInfos);
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames('your-activeonly-value').subscribe(assetProfileNames => {
  console.log('Get Asset Profile Names:', assetProfileNames);
});
```

---

### **ASSET SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetService = $injector.get(self.ctx.servicesMap.get('assetService'));

// Alternative: Direct context access
const assetService = self.ctx.assetService;
```

**1. getTenantAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getTenantAssetInfos(pageLink, 'your-type-value').subscribe(tenantAssetInfos => {
  console.log('Get Tenant Asset Infos:', tenantAssetInfos);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getTenantAssetInfosByAssetProfileId(pageLink, 'your-assetprofile-id').subscribe(tenantAssetInfosByAssetProfileId => {
  console.log('Get Tenant Asset Infos By Asset Profile Id:', tenantAssetInfosByAssetProfileId);
});
```

**3. getCustomerAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getCustomerAssetInfos('your-customer-id', pageLink, 'your-type-value').subscribe(customerAssetInfos => {
  console.log('Get Customer Asset Infos:', customerAssetInfos);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getCustomerAssetInfosByAssetProfileId('your-customer-id', pageLink, 'your-assetprofile-id').subscribe(customerAssetInfosByAssetProfileId => {
  console.log('Get Customer Asset Infos By Asset Profile Id:', customerAssetInfosByAssetProfileId);
});
```

**5. getAsset**

```javascript
self.ctx.assetService.getAsset('your-asset-id').subscribe(asset => {
  console.log('Get Asset:', asset);
});
```

**6. getAssets**

```javascript
self.ctx.assetService.getAssets('your-assetids-value').subscribe(assets => {
  console.log('Get Assets:', assets);
});
```

**7. getAssetInfo**

```javascript
self.ctx.assetService.getAssetInfo('your-asset-id').subscribe(assetInfo => {
  console.log('Get Asset Info:', assetInfo);
});
```

**8. saveAsset**

```javascript
self.ctx.assetService.saveAsset('your-asset-value').subscribe(asset => {
  console.log('Save Asset:', asset);
});
```

**9. getAssetTypes**

```javascript
self.ctx.assetService.getAssetTypes().subscribe(assetTypes => {
  console.log('Get Asset Types:', assetTypes);
});
```

**10. makeAssetPublic**

```javascript
self.ctx.assetService.makeAssetPublic('your-asset-id').subscribe(makeAssetPublic => {
  console.log('Make Asset Public:', makeAssetPublic);
});
```

**11. assignAssetToCustomer**

```javascript
self.ctx.assetService.assignAssetToCustomer('your-customer-id', 'your-asset-id').subscribe(assetToCustomer => {
  console.log('Assign Asset To Customer:', assetToCustomer);
});
```

**12. findByQuery**

```javascript
self.ctx.assetService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**13. findByName**

```javascript
self.ctx.assetService.findByName('your-assetname-value').subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**14. assignAssetToEdge**

```javascript
self.ctx.assetService.assignAssetToEdge('your-edge-id', 'your-asset-id').subscribe(assetToEdge => {
  console.log('Assign Asset To Edge:', assetToEdge);
});
```

**15. getEdgeAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.assetService.getEdgeAssets('your-edge-id', pageLink, 'your-type-value').subscribe(edgeAssets => {
  console.log('Get Edge Assets:', edgeAssets);
});
```

**16. bulkImportAssets**

```javascript
self.ctx.assetService.bulkImportAssets('your-entitiesdata-value').subscribe(bulkImportAssets => {
  console.log('Bulk Import Assets:', bulkImportAssets);
});
```

---

### **ATTRIBUTE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const attributeService = $injector.get(self.ctx.servicesMap.get('attributeService'));

// Alternative: Direct context access
const attributeService = self.ctx.attributeService;
```

**1. getEntityAttributes**

```javascript
self.ctx.attributeService.getEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-keys-value').subscribe(entityAttributes => {
  console.log('Get Entity Attributes:', entityAttributes);
});
```

**2. deleteEntityAttributes**

```javascript
self.ctx.attributeService.deleteEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entityAttributes => {
  console.log('Delete Entity Attributes:', entityAttributes);
});
```

**3. deleteEntityTimeseries**

```javascript
self.ctx.attributeService.deleteEntityTimeseries('your-entity-id', 'your-timeseries-value', 0, 0).subscribe(entityTimeseries => {
  console.log('Delete Entity Timeseries:', entityTimeseries);
});
```

**4. saveEntityAttributes**

```javascript
self.ctx.attributeService.saveEntityAttributes('your-entity-id', 'your-attributescope-value', 'your-attributes-value').subscribe(entityAttributes => {
  console.log('Save Entity Attributes:', entityAttributes);
});
```

**5. saveEntityTimeseries**

```javascript
self.ctx.attributeService.saveEntityTimeseries('your-entity-id', 'your-timeseriesscope-value', 'your-timeseries-value').subscribe(entityTimeseries => {
  console.log('Save Entity Timeseries:', entityTimeseries);
});
```

**6. getEntityTimeseries**

```javascript
self.ctx.attributeService.getEntityTimeseries('your-entity-id', 'your-keys-value', 0, 0, 'your-limit-value', 'your-agg-value', 0, 'your-orderby-value', 'your-usestrictdatatypes-value').subscribe(entityTimeseries => {
  console.log('Get Entity Timeseries:', entityTimeseries);
});
```

**7. getEntityTimeseriesLatest**

```javascript
self.ctx.attributeService.getEntityTimeseriesLatest('your-entity-id', 'your-keys-value').subscribe(entityTimeseriesLatest => {
  console.log('Get Entity Timeseries Latest:', entityTimeseriesLatest);
});
```

---

### **AUDIT LOG SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
```

**1. getAuditLogs**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogs(pageLink).subscribe(auditLogs => {
  console.log('Get Audit Logs:', auditLogs);
});
```

**2. getAuditLogsByCustomerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByCustomerId('your-customer-id', pageLink).subscribe(auditLogsByCustomerId => {
  console.log('Get Audit Logs By Customer Id:', auditLogsByCustomerId);
});
```

**3. getAuditLogsByUserId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByUserId('your-user-id', pageLink).subscribe(auditLogsByUserId => {
  console.log('Get Audit Logs By User Id:', auditLogsByUserId);
});
```

**4. getAuditLogsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByEntityId('your-entity-id', pageLink).subscribe(auditLogsByEntityId => {
  console.log('Get Audit Logs By Entity Id:', auditLogsByEntityId);
});
```

---

### **CALCULATED FIELDS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const calculatedFieldsService = $injector.get(self.ctx.servicesMap.get('calculatedFieldsService'));
```

**1. getCalculatedFieldById**

```javascript
calculatedFieldsService.getCalculatedFieldById('your-calculatedfield-id').subscribe(field => {
  console.log('Get Calculated Field By Id:', field);
});
```

**2. saveCalculatedField**

```javascript
calculatedFieldsService.saveCalculatedField('your-calculatedfield-value').subscribe(calculatedField => {
  console.log('Save Calculated Field:', calculatedField);
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField('your-calculatedfield-id').subscribe(calculatedField => {
  console.log('Delete Calculated Field:', calculatedField);
});
```

**4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFields(pageLink, 'your-query-value').subscribe(fields => {
  console.log('Get Calculated Fields:', fields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, 'your-type-value').subscribe(calculatedFieldsByEntityId => {
  console.log('Get Calculated Fields By Entity Id:', calculatedFieldsByEntityId);
});
```

**6. testScript**

```javascript
calculatedFieldsService.testScript('your-inputparams-value').subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent('your--id').subscribe(latestCalculatedFieldDebugEvent => {
  console.log('Get Latest Calculated Field Debug Event:', latestCalculatedFieldDebugEvent);
});
```

**8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldNames(pageLink, 'your-type-value').subscribe(calculatedFieldNames => {
  console.log('Get Calculated Field Names:', calculatedFieldNames);
});
```

---

### **COMPONENT DESCRIPTOR SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const componentDescriptorService = $injector.get(self.ctx.servicesMap.get('componentDescriptorService'));
```

**1. getComponentDescriptorsByType**

```javascript
componentDescriptorService.getComponentDescriptorsByType('your-componenttype-value', 'your-rulechaintype-value').subscribe(componentDescriptorsByType => {
  console.log('Get Component Descriptors By Type:', componentDescriptorsByType);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes('your-componenttypes-value', 'your-rulechaintype-value').subscribe(componentDescriptorsByTypes => {
  console.log('Get Component Descriptors By Types:', componentDescriptorsByTypes);
});
```

**3. getComponentDescriptorByClazz**

```javascript
componentDescriptorService.getComponentDescriptorByClazz('your-componentdescriptorclazz-value').subscribe(componentDescriptorByClazz => {
  console.log('Get Component Descriptor By Clazz:', componentDescriptorByClazz);
});
```

---

### **CUSTOMER SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const customerService = $injector.get(self.ctx.servicesMap.get('customerService'));

// Alternative: Direct context access
const customerService = self.ctx.customerService;
```

**1. getCustomers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.customerService.getCustomers(pageLink).subscribe(customers => {
  console.log('Get Customers:', customers);
});
```

**2. getCustomer**

```javascript
self.ctx.customerService.getCustomer('your-customer-id').subscribe(customer => {
  console.log('Get Customer:', customer);
});
```

**3. getCustomersByIds**

```javascript
self.ctx.customerService.getCustomersByIds('your-customerids-value').subscribe(customersByIds => {
  console.log('Get Customers By Ids:', customersByIds);
});
```

**4. saveCustomer**

```javascript
self.ctx.customerService.saveCustomer('your-customer-value').subscribe(customer => {
  console.log('Save Customer:', customer);
});
```

---

### **DASHBOARD SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const dashboardService = $injector.get(self.ctx.servicesMap.get('dashboardService'));

// Alternative: Direct context access
const dashboardService = self.ctx.dashboardService;
```

**1. getTenantDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getTenantDashboards(pageLink).subscribe(tenantDashboards => {
  console.log('Get Tenant Dashboards:', tenantDashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getTenantDashboardsByTenantId('your-tenant-id', pageLink).subscribe(tenantDashboardsByTenantId => {
  console.log('Get Tenant Dashboards By Tenant Id:', tenantDashboardsByTenantId);
});
```

**3. getCustomerDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.dashboardService.getCustomerDashboards('your-customer-id', pageLink).subscribe(customerDashboards => {
  console.log('Get Customer Dashboards:', customerDashboards);
});
```

**4. getDashboard**

```javascript
self.ctx.dashboardService.getDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Get Dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
self.ctx.dashboardService.exportDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Export Dashboard:', dashboard);
});
```

**6. getDashboardInfo**

```javascript
self.ctx.dashboardService.getDashboardInfo('your-dashboard-id').subscribe(dashboardInfo => {
  console.log('Get Dashboard Info:', dashboardInfo);
});
```

**7. getDashboards**

```javascript
self.ctx.dashboardService.getDashboards('your-dashboardids-value').subscribe(dashboards => {
  console.log('Get Dashboards:', dashboards);
});
```

**8. saveDashboard**

```javascript
self.ctx.dashboardService.saveDashboard('your-dashboard-value').subscribe(dashboard => {
  console.log('Save Dashboard:', dashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
self.ctx.dashboardService.assignDashboardToCustomer('your-customer-id', 'your-dashboard-id').subscribe(dashboardToCustomer => {
  console.log('Assign Dashboard To Customer:', dashboardToCustomer);
});
```

**10. makeDashboardPublic**

```javascript
self.ctx.dashboardService.makeDashboardPublic('your-dashboard-id').subscribe(makeDashboardPublic => {
  console.log('Make Dashboard Public:', makeDashboardPublic);
});
```

**11. makeDashboardPrivate**

```javascript
self.ctx.dashboardService.makeDashboardPrivate('your-dashboard-id').subscribe(makeDashboardPrivate => {
  console.log('Make Dashboard Private:', makeDashboardPrivate);
});
```

**12. updateDashboardCustomers**

```javascript
self.ctx.dashboardService.updateDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboardCustomers => {
  console.log('Update Dashboard Customers:', dashboardCustomers);
});
```

**13. addDashboardCustomers**

```javascript
self.ctx.dashboardService.addDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(addDashboardCustomers => {
  console.log('Add Dashboard Customers:', addDashboardCustomers);
});
```

**14. removeDashboardCustomers**

```javascript
self.ctx.dashboardService.removeDashboardCustomers('your-dashboard-id', 'your-customerids-value').subscribe(dashboardCustomers => {
  console.log('Remove Dashboard Customers:', dashboardCustomers);
});
```

**15. getHomeDashboard**

```javascript
self.ctx.dashboardService.getHomeDashboard().subscribe(homeDashboard => {
  console.log('Get Home Dashboard:', homeDashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
self.ctx.dashboardService.getTenantHomeDashboardInfo().subscribe(tenantHomeDashboardInfo => {
  console.log('Get Tenant Home Dashboard Info:', tenantHomeDashboardInfo);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
self.ctx.dashboardService.setTenantHomeDashboardInfo('your-homedashboardinfo-value').subscribe(tenantHomeDashboardInfo => {
  console.log('Set Tenant Home Dashboard Info:', tenantHomeDashboardInfo);
});
```

**18. getPublicDashboardLink**

```javascript
self.ctx.dashboardService.getPublicDashboardLink('your-dashboard-value').subscribe(publicDashboardLink => {
  console.log('Get Public Dashboard Link:', publicDashboardLink);
});
```

**19. assignDashboardToEdge**

```javascript
self.ctx.dashboardService.assignDashboardToEdge('your-edge-id', 'your-dashboard-id').subscribe(dashboardToEdge => {
  console.log('Assign Dashboard To Edge:', dashboardToEdge);
});
```

---

### **DEVICE PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfiles(pageLink).subscribe(deviceProfiles => {
  console.log('Get Device Profiles:', deviceProfiles);
});
```

**2. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds('your-deviceprofileids-value').subscribe(deviceProfilesByIds => {
  console.log('Get Device Profiles By Ids:', deviceProfilesByIds);
});
```

**3. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile('your-deviceprofile-id').subscribe(deviceProfile => {
  console.log('Get Device Profile:', deviceProfile);
});
```

**4. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile('your-deviceprofile-id').subscribe(deviceProfile => {
  console.log('Export Device Profile:', deviceProfile);
});
```

**5. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects('your-sortorder-value', 'your-objectids-value', 'your-searchtext-value').subscribe(lwm2mObjects => {
  console.log('Get Lwm 2 m Objects:', lwm2mObjects);
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true).subscribe(lwm2mBootstrapSecurityInfo => {
  console.log('Get Lwm 2 m Bootstrap Security Info:', lwm2mBootstrapSecurityInfo);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true).subscribe(lwm2mBootstrapSecurityInfoBySecurityType => {
  console.log('Get Lwm 2 m Bootstrap Security Info By Security Type:', lwm2mBootstrapSecurityInfoBySecurityType);
});
```

**8. getLwm2mObjectsPage**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(lwm2mObjectsPage => {
  console.log('Get Lwm 2 m Objects Page:', lwm2mObjectsPage);
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
deviceProfileService.saveDeviceProfileAndConfirmOtaChange('your-origindeviceprofile-value', 'your-deviceprofile-value').subscribe(deviceProfileAndConfirmOtaChange => {
  console.log('Save Device Profile And Confirm Ota Change:', deviceProfileAndConfirmOtaChange);
});
```

**10. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(deviceProfile => {
  console.log('Save Device Profile:', deviceProfile);
});
```

**11. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile('your-deviceprofile-id').subscribe(defaultDeviceProfile => {
  console.log('Set Default Device Profile:', defaultDeviceProfile);
});
```

**12. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(defaultDeviceProfileInfo => {
  console.log('Get Default Device Profile Info:', defaultDeviceProfileInfo);
});
```

**13. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo('your-deviceprofile-id').subscribe(info => {
  console.log('Get Device Profile Info:', info);
});
```

**14. getDeviceProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfileInfos(pageLink, 'your-transporttype-value').subscribe(deviceProfileInfos => {
  console.log('Get Device Profile Infos:', deviceProfileInfos);
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys('your-deviceprofile-id').subscribe(deviceProfileDevicesAttributesKeys => {
  console.log('Get Device Profile Devices Attributes Keys:', deviceProfileDevicesAttributesKeys);
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys('your-deviceprofile-id').subscribe(deviceProfileDevicesTimeseriesKeys => {
  console.log('Get Device Profile Devices Timeseries Keys:', deviceProfileDevicesTimeseriesKeys);
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames('your-activeonly-value').subscribe(deviceProfileNames => {
  console.log('Get Device Profile Names:', deviceProfileNames);
});
```

---

### **DEVICE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceService = $injector.get(self.ctx.servicesMap.get('deviceService'));

// Alternative: Direct context access
const deviceService = self.ctx.deviceService;
```

**1. getDeviceInfosByQuery**

```javascript
self.ctx.deviceService.getDeviceInfosByQuery('your-deviceinfoquery-value').subscribe(deviceInfosByQuery => {
  console.log('Get Device Infos By Query:', deviceInfosByQuery);
});
```

**2. getTenantDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getTenantDeviceInfos(pageLink, 'your-type-value').subscribe(tenantDeviceInfos => {
  console.log('Get Tenant Device Infos:', tenantDeviceInfos);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getTenantDeviceInfosByDeviceProfileId(pageLink, 'your-deviceprofile-id').subscribe(tenantDeviceInfosByDeviceProfileId => {
  console.log('Get Tenant Device Infos By Device Profile Id:', tenantDeviceInfosByDeviceProfileId);
});
```

**4. getCustomerDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getCustomerDeviceInfos('your-customer-id', pageLink, 'your-type-value').subscribe(customerDeviceInfos => {
  console.log('Get Customer Device Infos:', customerDeviceInfos);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getCustomerDeviceInfosByDeviceProfileId('your-customer-id', pageLink, 'your-deviceprofile-id').subscribe(customerDeviceInfosByDeviceProfileId => {
  console.log('Get Customer Device Infos By Device Profile Id:', customerDeviceInfosByDeviceProfileId);
});
```

**6. getDevice**

```javascript
self.ctx.deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Get Device:', device);
});
```

**7. getDevices**

```javascript
self.ctx.deviceService.getDevices('your-deviceids-value').subscribe(devices => {
  console.log('Get Devices:', devices);
});
```

**8. getDeviceInfo**

```javascript
self.ctx.deviceService.getDeviceInfo('your-device-id').subscribe(deviceInfo => {
  console.log('Get Device Info:', deviceInfo);
});
```

**9. saveDevice**

```javascript
self.ctx.deviceService.saveDevice('your-device-value').subscribe(device => {
  console.log('Save Device:', device);
});
```

**10. saveDeviceWithCredentials**

```javascript
self.ctx.deviceService.saveDeviceWithCredentials('your-device-value', 'your-credentials-value').subscribe(deviceWithCredentials => {
  console.log('Save Device With Credentials:', deviceWithCredentials);
});
```

**11. getDeviceTypes**

```javascript
self.ctx.deviceService.getDeviceTypes().subscribe(deviceTypes => {
  console.log('Get Device Types:', deviceTypes);
});
```

**12. getDeviceCredentials**

```javascript
self.ctx.deviceService.getDeviceCredentials('your-device-id', true).subscribe(deviceCredentials => {
  console.log('Get Device Credentials:', deviceCredentials);
});
```

**13. saveDeviceCredentials**

```javascript
self.ctx.deviceService.saveDeviceCredentials('your-devicecredentials-value').subscribe(deviceCredentials => {
  console.log('Save Device Credentials:', deviceCredentials);
});
```

**14. makeDevicePublic**

```javascript
self.ctx.deviceService.makeDevicePublic('your-device-id').subscribe(makeDevicePublic => {
  console.log('Make Device Public:', makeDevicePublic);
});
```

**15. assignDeviceToCustomer**

```javascript
self.ctx.deviceService.assignDeviceToCustomer('your-customer-id', 'your-device-id').subscribe(deviceToCustomer => {
  console.log('Assign Device To Customer:', deviceToCustomer);
});
```

**16. sendOneWayRpcCommand**

```javascript
self.ctx.deviceService.sendOneWayRpcCommand('your-device-id', 'your-requestbody-value').subscribe(oneWayRpcCommand => {
  console.log('Send One Way Rpc Command:', oneWayRpcCommand);
});
```

**17. sendTwoWayRpcCommand**

```javascript
self.ctx.deviceService.sendTwoWayRpcCommand('your-device-id', 'your-requestbody-value').subscribe(twoWayRpcCommand => {
  console.log('Send Two Way Rpc Command:', twoWayRpcCommand);
});
```

**18. getPersistedRpc**

```javascript
self.ctx.deviceService.getPersistedRpc('your-rpc-id').subscribe(persistedRpc => {
  console.log('Get Persisted Rpc:', persistedRpc);
});
```

**19. getPersistedRpcRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getPersistedRpcRequests('your-device-id', pageLink, 'your-rpcstatus-value').subscribe(persistedRpcRequests => {
  console.log('Get Persisted Rpc Requests:', persistedRpcRequests);
});
```

**20. findByQuery**

```javascript
self.ctx.deviceService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**21. findByName**

```javascript
self.ctx.deviceService.findByName('your-devicename-value').subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**22. claimDevice**

```javascript
self.ctx.deviceService.claimDevice('your-devicename-value', 'your-claimrequest-value').subscribe(claimDevice => {
  console.log('Claim Device:', claimDevice);
});
```

**23. assignDeviceToEdge**

```javascript
self.ctx.deviceService.assignDeviceToEdge('your-edge-id', 'your-device-id').subscribe(deviceToEdge => {
  console.log('Assign Device To Edge:', deviceToEdge);
});
```

**24. getEdgeDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.deviceService.getEdgeDevices('your-edge-id', pageLink, 'your-type-value').subscribe(edgeDevices => {
  console.log('Get Edge Devices:', edgeDevices);
});
```

**25. bulkImportDevices**

```javascript
self.ctx.deviceService.bulkImportDevices('your-entitiesdata-value').subscribe(bulkImportDevices => {
  console.log('Bulk Import Devices:', bulkImportDevices);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
self.ctx.deviceService.getDevicePublishTelemetryCommands('your-device-id').subscribe(devicePublishTelemetryCommands => {
  console.log('Get Device Publish Telemetry Commands:', devicePublishTelemetryCommands);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
self.ctx.deviceService.downloadGatewayDockerComposeFile('your-device-id').subscribe(downloadGatewayDockerComposeFile => {
  console.log('Download Gateway Docker Compose File:', downloadGatewayDockerComposeFile);
});
```

**28. rebootDevice**

```javascript
self.ctx.deviceService.rebootDevice('your-device-id', true).subscribe(rebootDevice => {
  console.log('Reboot Device:', rebootDevice);
});
```

**29. rebootTrigger**

```javascript
self.ctx.deviceService.rebootTrigger('your-device-id', 'your-resourcepath-value').subscribe(rebootTrigger => {
  console.log('Reboot Trigger:', rebootTrigger);
});
```

---

### **DOMAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
domainService.saveDomain('your-domain-value', 'your-oauth2clientids-value').subscribe(domain => {
  console.log('Save Domain:', domain);
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients('your--id', 'your-oauth2clientids-value').subscribe(result => {
  console.log('Update Oauth 2 Clients:', result);
});
```

**3. getTenantDomainInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domainService.getTenantDomainInfos(pageLink).subscribe(tenantDomainInfos => {
  console.log('Get Tenant Domain Infos:', tenantDomainInfos);
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById('your--id').subscribe(domainInfoById => {
  console.log('Get Domain Info By Id:', domainInfoById);
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain('your--id').subscribe(result => {
  console.log('Delete Domain:', result);
});
```

---

### **EDGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const edgeService = $injector.get(self.ctx.servicesMap.get('edgeService'));
```

**1. getEdges**

```javascript
edgeService.getEdges('your-edgeids-value').subscribe(edges => {
  console.log('Get Edges:', edges);
});
```

**2. getEdge**

```javascript
edgeService.getEdge('your-edge-id').subscribe(edge => {
  console.log('Get Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo('your-edge-id').subscribe(info => {
  console.log('Get Edge Info:', info);
});
```

**4. saveEdge**

```javascript
edgeService.saveEdge('your-edge-value').subscribe(edge => {
  console.log('Save Edge:', edge);
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes().subscribe(edgeTypes => {
  console.log('Get Edge Types:', edgeTypes);
});
```

**6. getCustomerEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getCustomerEdgeInfos('your-customer-id', pageLink, 'your-type-value').subscribe(customerEdgeInfos => {
  console.log('Get Customer Edge Infos:', customerEdgeInfos);
});
```

**7. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer('your-customer-id', 'your-edge-id').subscribe(edgeToCustomer => {
  console.log('Assign Edge To Customer:', edgeToCustomer);
});
```

**8. makeEdgePublic**

```javascript
edgeService.makeEdgePublic('your-edge-id').subscribe(makeEdgePublic => {
  console.log('Make Edge Public:', makeEdgePublic);
});
```

**9. getTenantEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getTenantEdgeInfos(pageLink, 'your-type-value').subscribe(tenantEdgeInfos => {
  console.log('Get Tenant Edge Infos:', tenantEdgeInfos);
});
```

**10. findByQuery**

```javascript
edgeService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**11. getEdgeEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getEdgeEvents('your-entity-id', pageLink).subscribe(edgeEvents => {
  console.log('Get Edge Events:', edgeEvents);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains('your-edge-id').subscribe(missingToRelatedRuleChains => {
  console.log('Find Missing To Related Rule Chains:', missingToRelatedRuleChains);
});
```

**13. findByName**

```javascript
edgeService.findByName('your-edgename-value').subscribe(byName => {
  console.log('Find By Name:', byName);
});
```

**14. bulkImportEdges**

```javascript
edgeService.bulkImportEdges('your-entitiesdata-value').subscribe(bulkImportEdges => {
  console.log('Bulk Import Edges:', bulkImportEdges);
});
```

**15. getEdgeInstallInstructions**

```javascript
edgeService.getEdgeInstallInstructions('your-edge-id', 'your-method-value').subscribe(edgeInstallInstructions => {
  console.log('Get Edge Install Instructions:', edgeInstallInstructions);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
edgeService.getEdgeUpgradeInstructions('your-edgeversion-value', 'your-method-value').subscribe(edgeUpgradeInstructions => {
  console.log('Get Edge Upgrade Instructions:', edgeUpgradeInstructions);
});
```

**17. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable('your-edge-id').subscribe(isEdgeUpgradeAvailable => {
  console.log('Is Edge Upgrade Available:', isEdgeUpgradeAvailable);
});
```

---

### **ENTITIES VERSION CONTROL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
```

**1. clearBranchList**

```javascript
entitiesVersionControlService.clearBranchList().subscribe(branchList => {
  console.log('Clear Branch List:', branchList);
});
```

**2. listBranches**

```javascript
entitiesVersionControlService.listBranches().subscribe(branches => {
  console.log('List Branches:', branches);
});
```

**3. getEntityDataInfo**

```javascript
entitiesVersionControlService.getEntityDataInfo('your-externalentity-id', 'your-version-id').subscribe(entityDataInfo => {
  console.log('Get Entity Data Info:', entityDataInfo);
});
```

**4. saveEntitiesVersion**

```javascript
entitiesVersionControlService.saveEntitiesVersion('your-request-value').subscribe(entitiesVersion => {
  console.log('Save Entities Version:', entitiesVersion);
});
```

**5. getVersionCreateRequestStatus**

```javascript
entitiesVersionControlService.getVersionCreateRequestStatus('your-request-id').subscribe(versionCreateRequestStatus => {
  console.log('Get Version Create Request Status:', versionCreateRequestStatus);
});
```

**6. listEntityVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entitiesVersionControlService.listEntityVersions(pageLink, 'your-branch-value', 'your-externalentity-id').subscribe(entityVersions => {
  console.log('List Entity Versions:', entityVersions);
});
```

**7. listEntityTypeVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entitiesVersionControlService.listEntityTypeVersions(pageLink, 'your-branch-value', 'your-entitytype-value').subscribe(entityTypeVersions => {
  console.log('List Entity Type Versions:', entityTypeVersions);
});
```

**8. listVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entitiesVersionControlService.listVersions(pageLink, 'your-branch-value').subscribe(versions => {
  console.log('List Versions:', versions);
});
```

**9. loadEntitiesVersion**

```javascript
entitiesVersionControlService.loadEntitiesVersion('your-request-value').subscribe(loadEntitiesVersion => {
  console.log('Load Entities Version:', loadEntitiesVersion);
});
```

**10. getVersionLoadRequestStatus**

```javascript
entitiesVersionControlService.getVersionLoadRequestStatus('your-request-id').subscribe(versionLoadRequestStatus => {
  console.log('Get Version Load Request Status:', versionLoadRequestStatus);
});
```

**11. compareEntityDataToVersion**

```javascript
entitiesVersionControlService.compareEntityDataToVersion('your-entity-id', 'your-version-id').subscribe(compareEntityDataToVersion => {
  console.log('Compare Entity Data To Version:', compareEntityDataToVersion);
});
```

**12. entityLoadErrorToMessage**

```javascript
entitiesVersionControlService.entityLoadErrorToMessage('your-entityloaderror-value').subscribe(entityLoadErrorToMessage => {
  console.log('Entity Load Error To Message:', entityLoadErrorToMessage);
});
```

---

### **ENTITY RELATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityRelationService = $injector.get(self.ctx.servicesMap.get('entityRelationService'));

// Alternative: Direct context access
const entityRelationService = self.ctx.entityRelationService;
```

**1. saveRelation**

```javascript
self.ctx.entityRelationService.saveRelation('your-relation-value').subscribe(relation => {
  console.log('Save Relation:', relation);
});
```

**2. getRelation**

```javascript
self.ctx.entityRelationService.getRelation('your-from-id', 'your-relationtype-value', 'your-to-id').subscribe(relation => {
  console.log('Get Relation:', relation);
});
```

**3. findByFrom**

```javascript
self.ctx.entityRelationService.findByFrom('your-from-id').subscribe(byFrom => {
  console.log('Find By From:', byFrom);
});
```

**4. findInfoByFrom**

```javascript
self.ctx.entityRelationService.findInfoByFrom('your-from-id').subscribe(infoByFrom => {
  console.log('Find Info By From:', infoByFrom);
});
```

**5. findByFromAndType**

```javascript
self.ctx.entityRelationService.findByFromAndType('your-from-id', 'your-relationtype-value').subscribe(byFromAndType => {
  console.log('Find By From And Type:', byFromAndType);
});
```

**6. findByTo**

```javascript
self.ctx.entityRelationService.findByTo('your-to-id').subscribe(byTo => {
  console.log('Find By To:', byTo);
});
```

**7. findInfoByTo**

```javascript
self.ctx.entityRelationService.findInfoByTo('your-to-id').subscribe(infoByTo => {
  console.log('Find Info By To:', infoByTo);
});
```

**8. findByToAndType**

```javascript
self.ctx.entityRelationService.findByToAndType('your-to-id', 'your-relationtype-value').subscribe(byToAndType => {
  console.log('Find By To And Type:', byToAndType);
});
```

**9. findByQuery**

```javascript
self.ctx.entityRelationService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**10. findInfoByQuery**

```javascript
self.ctx.entityRelationService.findInfoByQuery('your-query-value').subscribe(infoByQuery => {
  console.log('Find Info By Query:', infoByQuery);
});
```

---

### **ENTITY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityService = $injector.get(self.ctx.servicesMap.get('entityService'));

// Alternative: Direct context access
const entityService = self.ctx.entityService;
```

**1. getEntityObservable**

```javascript
self.ctx.entityService.getEntityObservable('your-entitytype-value', 'your-entity-id').subscribe(entityObservable => {
  console.log('Get Entity Observable:', entityObservable);
});
```

**2. getEntity**

```javascript
self.ctx.entityService.getEntity('your-entitytype-value', 'your-entity-id').subscribe(entity => {
  console.log('Get Entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
self.ctx.entityService.getEntitiesObservable('your-entitytype-value', 'your-entityids-value').subscribe(entitiesObservable => {
  console.log('Get Entities Observable:', entitiesObservable);
});
```

**4. getEntities**

```javascript
self.ctx.entityService.getEntities('your-entitytype-value', 'your-entityids-value').subscribe(entities => {
  console.log('Get Entities:', entities);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(singleTenantByPageLinkObservable => {
  console.log('Get Single Tenant By Page Link Observable:', singleTenantByPageLinkObservable);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getSingleCustomerByPageLinkObservable(pageLink).subscribe(singleCustomerByPageLinkObservable => {
  console.log('Get Single Customer By Page Link Observable:', singleCustomerByPageLinkObservable);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getEntitiesByPageLinkObservable('your-entitytype-value', pageLink, 'your-subtype-value').subscribe(entitiesByPageLinkObservable => {
  console.log('Get Entities By Page Link Observable:', entitiesByPageLinkObservable);
});
```

**8. getEntitiesByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getEntitiesByPageLink('your-entitytype-value', pageLink, 'your-subtype-value').subscribe(entitiesByPageLink => {
  console.log('Get Entities By Page Link:', entitiesByPageLink);
});
```

**9. getEntitiesByNameFilter**

```javascript
self.ctx.entityService.getEntitiesByNameFilter('your-entitytype-value', 'your-entitynamefilter-value', 0, 'your-subtype-value').subscribe(entitiesByNameFilter => {
  console.log('Get Entities By Name Filter:', entitiesByNameFilter);
});
```

**10. findEntityDataByQuery**

```javascript
self.ctx.entityService.findEntityDataByQuery('your-query-value').subscribe(entityDataByQuery => {
  console.log('Find Entity Data By Query:', entityDataByQuery);
});
```

**11. findEntityKeysByQuery**

```javascript
self.ctx.entityService.findEntityKeysByQuery('your-query-value', 'your-scope-value').subscribe(entityKeysByQuery => {
  console.log('Find Entity Keys By Query:', entityKeysByQuery);
});
```

**12. findAlarmDataByQuery**

```javascript
self.ctx.entityService.findAlarmDataByQuery('your-query-value').subscribe(alarmDataByQuery => {
  console.log('Find Alarm Data By Query:', alarmDataByQuery);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
self.ctx.entityService.findEntityInfosByFilterAndName('your-filter-value', 'your-searchtext-value').subscribe(entityInfosByFilterAndName => {
  console.log('Find Entity Infos By Filter And Name:', entityInfosByFilterAndName);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
self.ctx.entityService.findSingleEntityInfoByEntityFilter('your-filter-value').subscribe(singleEntityInfoByEntityFilter => {
  console.log('Find Single Entity Info By Entity Filter:', singleEntityInfoByEntityFilter);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
self.ctx.entityService.getAliasFilterTypesByEntityTypes('your-entitytypes-value').subscribe(aliasFilterTypesByEntityTypes => {
  console.log('Get Alias Filter Types By Entity Types:', aliasFilterTypesByEntityTypes);
});
```

**16. filterAliasByEntityTypes**

```javascript
self.ctx.entityService.filterAliasByEntityTypes('your-entityalias-value', 'your-entitytypes-value').subscribe(filterAliasByEntityTypes => {
  console.log('Filter Alias By Entity Types:', filterAliasByEntityTypes);
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
self.ctx.entityService.filterAliasFilterTypeByEntityTypes('your-aliasfiltertype-value', 'your-entitytypes-value').subscribe(filterAliasFilterTypeByEntityTypes => {
  console.log('Filter Alias Filter Type By Entity Types:', filterAliasFilterTypeByEntityTypes);
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
self.ctx.entityService.filterAliasFilterTypeByEntityType('your-aliasfiltertype-value', 'your-entitytype-value').subscribe(filterAliasFilterTypeByEntityType => {
  console.log('Filter Alias Filter Type By Entity Type:', filterAliasFilterTypeByEntityType);
});
```

**19. prepareAllowedEntityTypesList**

```javascript
self.ctx.entityService.prepareAllowedEntityTypesList('your-allowedentitytypes-value', true).subscribe(prepareAllowedEntityTypesList => {
  console.log('Prepare Allowed Entity Types List:', prepareAllowedEntityTypesList);
});
```

**20. getEntityFieldKeys**

```javascript
self.ctx.entityService.getEntityFieldKeys('your-entitytype-value', 'your-searchtext-value').subscribe(entityFieldKeys => {
  console.log('Get Entity Field Keys:', entityFieldKeys);
});
```

**21. getAlarmKeys**

```javascript
self.ctx.entityService.getAlarmKeys('your-searchtext-value').subscribe(alarmKeys => {
  console.log('Get Alarm Keys:', alarmKeys);
});
```

**22. getEntityKeys**

```javascript
self.ctx.entityService.getEntityKeys('your-entity-id', 'your-query-value', 'your-type-value').subscribe(entityKeys => {
  console.log('Get Entity Keys:', entityKeys);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
self.ctx.entityService.getEntityKeysByEntityFilter('your-filter-value', 'your-types-value', 'your-entitytypes-value').subscribe(entityKeysByEntityFilter => {
  console.log('Get Entity Keys By Entity Filter:', entityKeysByEntityFilter);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
self.ctx.entityService.getEntityKeysByEntityFilterAndScope('your-filter-value', 'your-types-value', 'your-entitytypes-value', 'your-scope-value').subscribe(entityKeysByEntityFilterAndScope => {
  console.log('Get Entity Keys By Entity Filter And Scope:', entityKeysByEntityFilterAndScope);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
self.ctx.entityService.createDatasourcesFromSubscriptionsInfo('your-subscriptionsinfo-value').subscribe(datasourcesFromSubscriptionsInfo => {
  console.log('Create Datasources From Subscriptions Info:', datasourcesFromSubscriptionsInfo);
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
self.ctx.entityService.createAlarmSourceFromSubscriptionInfo('your-subscriptioninfo-value').subscribe(alarmSourceFromSubscriptionInfo => {
  console.log('Create Alarm Source From Subscription Info:', alarmSourceFromSubscriptionInfo);
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityService.getAssignedToEdgeEntitiesByType('your-edge-id', 'your-entitytype-value', pageLink).subscribe(assignedToEdgeEntitiesByType => {
  console.log('Get Assigned To Edge Entities By Type:', assignedToEdgeEntitiesByType);
});
```

**28. case**

```javascript
self.ctx.entityService.case().subscribe(case => {
  console.log('Case:', case);
});
```

**29. getEntitySubtypesObservable**

```javascript
self.ctx.entityService.getEntitySubtypesObservable('your-entitytype-value').subscribe(entitySubtypesObservable => {
  console.log('Get Entity Subtypes Observable:', entitySubtypesObservable);
});
```

---

### **ENTITY VIEW SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entityViewService = $injector.get(self.ctx.servicesMap.get('entityViewService'));

// Alternative: Direct context access
const entityViewService = self.ctx.entityViewService;
```

**1. getTenantEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getTenantEntityViewInfos(pageLink, 'your-type-value').subscribe(tenantEntityViewInfos => {
  console.log('Get Tenant Entity View Infos:', tenantEntityViewInfos);
});
```

**2. getCustomerEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getCustomerEntityViewInfos('your-customer-id', pageLink, 'your-type-value').subscribe(customerEntityViewInfos => {
  console.log('Get Customer Entity View Infos:', customerEntityViewInfos);
});
```

**3. getEntityView**

```javascript
self.ctx.entityViewService.getEntityView('your-entityview-id').subscribe(entityView => {
  console.log('Get Entity View:', entityView);
});
```

**4. getEntityViews**

```javascript
self.ctx.entityViewService.getEntityViews('your-entityviewids-value').subscribe(entityViews => {
  console.log('Get Entity Views:', entityViews);
});
```

**5. getEntityViewInfo**

```javascript
self.ctx.entityViewService.getEntityViewInfo('your-entityview-id').subscribe(entityViewInfo => {
  console.log('Get Entity View Info:', entityViewInfo);
});
```

**6. saveEntityView**

```javascript
self.ctx.entityViewService.saveEntityView('your-entityview-value').subscribe(entityView => {
  console.log('Save Entity View:', entityView);
});
```

**7. getEntityViewTypes**

```javascript
self.ctx.entityViewService.getEntityViewTypes().subscribe(entityViewTypes => {
  console.log('Get Entity View Types:', entityViewTypes);
});
```

**8. makeEntityViewPublic**

```javascript
self.ctx.entityViewService.makeEntityViewPublic('your-entityview-id').subscribe(makeEntityViewPublic => {
  console.log('Make Entity View Public:', makeEntityViewPublic);
});
```

**9. assignEntityViewToCustomer**

```javascript
self.ctx.entityViewService.assignEntityViewToCustomer('your-customer-id', 'your-entityview-id').subscribe(entityViewToCustomer => {
  console.log('Assign Entity View To Customer:', entityViewToCustomer);
});
```

**10. findByQuery**

```javascript
self.ctx.entityViewService.findByQuery('your-query-value').subscribe(byQuery => {
  console.log('Find By Query:', byQuery);
});
```

**11. assignEntityViewToEdge**

```javascript
self.ctx.entityViewService.assignEntityViewToEdge('your-edge-id', 'your-entityview-id').subscribe(entityViewToEdge => {
  console.log('Assign Entity View To Edge:', entityViewToEdge);
});
```

**12. getEdgeEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.entityViewService.getEdgeEntityViews('your-edge-id', pageLink, 'your-type-value').subscribe(edgeEntityViews => {
  console.log('Get Edge Entity Views:', edgeEntityViews);
});
```

---

### **EVENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', pageLink).subscribe(events => {
  console.log('Get Events:', events);
});
```

**2. getFilterEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
eventService.getFilterEvents('your-entity-id', 'your-eventtype-value', 'your-tenant-id', 'your-filters-value', pageLink).subscribe(filterEvents => {
  console.log('Get Filter Events:', filterEvents);
});
```

---

### **GIT HUB SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
```

**1. getGitHubStar**

```javascript
gitHubService.getGitHubStar().subscribe(gitHubStar => {
  console.log('Get Git Hub Star:', gitHubStar);
});
```

---

### **IMAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
```

**1. uploadImage**

```javascript
imageService.uploadImage('your-file-value', 'your-title-value', 'your-imagesubtype-value').subscribe(uploadImage => {
  console.log('Upload Image:', uploadImage);
});
```

**2. updateImage**

```javascript
imageService.updateImage('your-type-value', 'your-key-value', 'your-file-value').subscribe(image => {
  console.log('Update Image:', image);
});
```

**3. updateImageInfo**

```javascript
imageService.updateImageInfo('your-imageinfo-value').subscribe(imageInfo => {
  console.log('Update Image Info:', imageInfo);
});
```

**4. updateImagePublicStatus**

```javascript
imageService.updateImagePublicStatus('your-imageinfo-value', true).subscribe(imagePublicStatus => {
  console.log('Update Image Public Status:', imagePublicStatus);
});
```

**5. getImages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
imageService.getImages(pageLink, 'your-imagesubtype-value').subscribe(images => {
  console.log('Get Images:', images);
});
```

**6. getImageInfo**

```javascript
imageService.getImageInfo('your-type-value', 'your-key-value').subscribe(imageInfo => {
  console.log('Get Image Info:', imageInfo);
});
```

**7. getImageDataUrl**

```javascript
imageService.getImageDataUrl('your-imageurl-value').subscribe(imageDataUrl => {
  console.log('Get Image Data Url:', imageDataUrl);
});
```

**8. loadImageDataUrl**

```javascript
imageService.loadImageDataUrl('your-imagelink-value').subscribe(loadImageDataUrl => {
  console.log('Load Image Data Url:', loadImageDataUrl);
});
```

**9. getImageString**

```javascript
imageService.getImageString('your-imageurl-value').subscribe(imageString => {
  console.log('Get Image String:', imageString);
});
```

**10. resolveImageUrl**

```javascript
imageService.resolveImageUrl('your-imageurl-value').subscribe(resolveImageUrl => {
  console.log('Resolve Image Url:', resolveImageUrl);
});
```

**11. downloadImage**

```javascript
imageService.downloadImage('your-type-value', 'your-key-value').subscribe(downloadImage => {
  console.log('Download Image:', downloadImage);
});
```

**12. exportImage**

```javascript
imageService.exportImage('your-type-value', 'your-key-value').subscribe(image => {
  console.log('Export Image:', image);
});
```

**13. importImage**

```javascript
imageService.importImage('your-imagedata-value').subscribe(image => {
  console.log('Import Image:', image);
});
```

---

### **MOBILE APP SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
mobileAppService.saveMobileApp('your-mobileapp-value').subscribe(mobileApp => {
  console.log('Save Mobile App:', mobileApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppInfos(pageLink, 'your-platformtype-value').subscribe(tenantMobileAppInfos => {
  console.log('Get Tenant Mobile App Infos:', tenantMobileAppInfos);
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById('your--id').subscribe(mobileAppInfoById => {
  console.log('Get Mobile App Info By Id:', mobileAppInfoById);
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp('your--id').subscribe(result => {
  console.log('Delete Mobile App:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(tenantMobileAppBundleInfos => {
  console.log('Get Tenant Mobile App Bundle Infos:', tenantMobileAppBundleInfos);
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById('your--id').subscribe(mobileAppBundleInfoById => {
  console.log('Get Mobile App Bundle Info By Id:', mobileAppBundleInfoById);
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle('your--id').subscribe(result => {
  console.log('Delete Mobile App Bundle:', result);
});
```

---

### **MOBILE APPLICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileApplicationService = $injector.get(self.ctx.servicesMap.get('mobileApplicationService'));
```

**1. getMobileAppSettings**

```javascript
mobileApplicationService.getMobileAppSettings().subscribe(settings => {
  console.log('Get Mobile App Settings:', settings);
});
```

**2. saveMobileAppSettings**

```javascript
mobileApplicationService.saveMobileAppSettings('your-mobileappsettings-value').subscribe(mobileAppSettings => {
  console.log('Save Mobile App Settings:', mobileAppSettings);
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(mobileAppDeepLink => {
  console.log('Get Mobile App Deep Link:', mobileAppDeepLink);
});
```

---

### **NOTIFICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotifications(pageLink).subscribe(notifications => {
  console.log('Get Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification('your--id').subscribe(result => {
  console.log('Delete Notification:', result);
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead('your--id').subscribe(result => {
  console.log('Mark Notification As Read:', result);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('Mark All Notifications As Read:', result);
});
```

**5. createNotificationRequest**

```javascript
notificationService.createNotificationRequest('your-notification-value').subscribe(notificationRequest => {
  console.log('Create Notification Request:', notificationRequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest('your-entitytype-value').subscribe(result => {
  console.log('Send Entities Limit Increase Request:', result);
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById('your--id').subscribe(notificationRequestById => {
  console.log('Get Notification Request By Id:', notificationRequestById);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(availableDeliveryMethods => {
  console.log('Get Available Delivery Methods:', availableDeliveryMethods);
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest('your--id').subscribe(result => {
  console.log('Delete Notification Request:', result);
});
```

**10. getNotificationRequestPreview**

```javascript
notificationService.getNotificationRequestPreview('your-notification-value').subscribe(notificationRequestPreview => {
  console.log('Get Notification Request Preview:', notificationRequestPreview);
});
```

**11. getNotificationRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRequests(pageLink).subscribe(notificationRequests => {
  console.log('Get Notification Requests:', notificationRequests);
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(notificationSettings => {
  console.log('Get Notification Settings:', notificationSettings);
});
```

**13. saveNotificationSettings**

```javascript
notificationService.saveNotificationSettings('your-notificationsettings-value').subscribe(notificationSettings => {
  console.log('Save Notification Settings:', notificationSettings);
});
```

**14. listSlackConversations**

```javascript
notificationService.listSlackConversations('your-type-value', 'your-access-token').subscribe(slackConversations => {
  console.log('List Slack Conversations:', slackConversations);
});
```

**15. saveNotificationRule**

```javascript
notificationService.saveNotificationRule('your-notificationrule-value').subscribe(notificationRule => {
  console.log('Save Notification Rule:', notificationRule);
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById('your--id').subscribe(notificationRuleById => {
  console.log('Get Notification Rule By Id:', notificationRuleById);
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule('your--id').subscribe(result => {
  console.log('Delete Notification Rule:', result);
});
```

**18. getNotificationRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRules(pageLink).subscribe(rules => {
  console.log('Get Notification Rules:', rules);
});
```

**19. saveNotificationTarget**

```javascript
notificationService.saveNotificationTarget('your-notificationtarget-value').subscribe(notificationTarget => {
  console.log('Save Notification Target:', notificationTarget);
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById('your--id').subscribe(notificationTargetById => {
  console.log('Get Notification Target By Id:', notificationTargetById);
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget('your--id').subscribe(result => {
  console.log('Delete Notification Target:', result);
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds('your-ids-value').subscribe(notificationTargetsByIds => {
  console.log('Get Notification Targets By Ids:', notificationTargetsByIds);
});
```

**23. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTargets(pageLink, 'your-type-value').subscribe(targets => {
  console.log('Get Notification Targets:', targets);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getRecipientsForNotificationTargetConfig('your-notificationtarget-value', pageLink).subscribe(recipientsForNotificationTargetConfig => {
  console.log('Get Recipients For Notification Target Config:', recipientsForNotificationTargetConfig);
});
```

**25. saveNotificationTemplate**

```javascript
notificationService.saveNotificationTemplate('your-notificationtarget-value').subscribe(notificationTemplate => {
  console.log('Save Notification Template:', notificationTemplate);
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById('your--id').subscribe(notificationTemplateById => {
  console.log('Get Notification Template By Id:', notificationTemplateById);
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate('your--id').subscribe(result => {
  console.log('Delete Notification Template:', result);
});
```

**28. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTemplates(pageLink, 'your-notificationtypes-value').subscribe(templates => {
  console.log('Get Notification Templates:', templates);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(notificationUserSettings => {
  console.log('Get Notification User Settings:', notificationUserSettings);
});
```

**30. saveNotificationUserSettings**

```javascript
notificationService.saveNotificationUserSettings('your-settings-value').subscribe(notificationUserSettings => {
  console.log('Save Notification User Settings:', notificationUserSettings);
});
```

---

### **O AUTH 2 SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template().subscribe(oAuth2Template => {
  console.log('Get O Auth 2 Template:', oAuth2Template);
});
```

**2. saveOAuth2Client**

```javascript
oAuth2Service.saveOAuth2Client('your-oauth2client-value').subscribe(oAuth2Client => {
  console.log('Save O Auth 2 Client:', oAuth2Client);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(tenantOAuth2ClientInfos => {
  console.log('Find Tenant O Auth 2 Client Infos:', tenantOAuth2ClientInfos);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2Service.findTenantOAuth2ClientInfosByIds('your-clientids-value').subscribe(tenantOAuth2ClientInfosByIds => {
  console.log('Find Tenant O Auth 2 Client Infos By Ids:', tenantOAuth2ClientInfosByIds);
});
```

**5. getOAuth2ClientById**

```javascript
oAuth2Service.getOAuth2ClientById('your--id').subscribe(oAuth2ClientById => {
  console.log('Get O Auth 2 Client By Id:', oAuth2ClientById);
});
```

**6. deleteOauth2Client**

```javascript
oAuth2Service.deleteOauth2Client('your--id').subscribe(result => {
  console.log('Delete Oauth 2 Client:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url:', loginProcessingUrl);
});
```

---

### **OTA PACKAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackages(pageLink).subscribe(otaPackages => {
  console.log('Get Ota Packages:', otaPackages);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, 'your-deviceprofile-id', 'your-type-value').subscribe(otaPackagesInfoByDeviceProfileId => {
  console.log('Get Ota Packages Info By Device Profile Id:', otaPackagesInfoByDeviceProfileId);
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage('your-otapackage-id').subscribe(otaPackage => {
  console.log('Get Ota Package:', otaPackage);
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo('your-otapackage-id').subscribe(otaPackageInfo => {
  console.log('Get Ota Package Info:', otaPackageInfo);
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage('your-otapackage-id').subscribe(downloadOtaPackage => {
  console.log('Download Ota Package:', downloadOtaPackage);
});
```

**6. saveOtaPackage**

```javascript
otaPackageService.saveOtaPackage('your-otapackage-value').subscribe(otaPackage => {
  console.log('Save Ota Package:', otaPackage);
});
```

**7. saveOtaPackageInfo**

```javascript
otaPackageService.saveOtaPackageInfo('your-otapackageinfo-value').subscribe(otaPackageInfo => {
  console.log('Save Ota Package Info:', otaPackageInfo);
});
```

**8. uploadOtaPackageFile**

```javascript
otaPackageService.uploadOtaPackageFile('your-otapackage-id', 'your-file-value', 'your-checksumalgorithm-value', 'your-checksum-value').subscribe(uploadOtaPackageFile => {
  console.log('Upload Ota Package File:', uploadOtaPackageFile);
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage('your-type-value', 'your-entity-id').subscribe(countUpdateDeviceAfterChangePackage => {
  console.log('Count Update Device After Change Package:', countUpdateDeviceAfterChangePackage);
});
```

**10. confirmDialogUpdatePackage**

```javascript
otaPackageService.confirmDialogUpdatePackage('your-entity-value', 'your-originentity-value').subscribe(confirmDialogUpdatePackage => {
  console.log('Confirm Dialog Update Package:', confirmDialogUpdatePackage);
});
```

---

### **QUEUE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const queueService = $injector.get(self.ctx.servicesMap.get('queueService'));
```

**1. getQueueById**

```javascript
queueService.getQueueById('your-queue-id').subscribe(queueById => {
  console.log('Get Queue By Id:', queueById);
});
```

**2. getQueueByName**

```javascript
queueService.getQueueByName('your-queuename-value').subscribe(queueByName => {
  console.log('Get Queue By Name:', queueByName);
});
```

**3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getTenantQueuesByServiceType(pageLink, 'your-servicetype-value').subscribe(tenantQueuesByServiceType => {
  console.log('Get Tenant Queues By Service Type:', tenantQueuesByServiceType);
});
```

**4. saveQueue**

```javascript
queueService.saveQueue('your-queue-value', 'your-servicetype-value').subscribe(queue => {
  console.log('Save Queue:', queue);
});
```

**5. getQueueStatistics**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getQueueStatistics(pageLink).subscribe(queueStatistics => {
  console.log('Get Queue Statistics:', queueStatistics);
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById('your-queuestat-id').subscribe(queueStatisticsById => {
  console.log('Get Queue Statistics By Id:', queueStatisticsById);
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds('your-queuestatids-value').subscribe(queueStatisticsByIds => {
  console.log('Get Queue Statistics By Ids:', queueStatisticsByIds);
});
```

---

### **RESOURCE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const resourceService = $injector.get(self.ctx.servicesMap.get('resourceService'));

// Alternative: Direct context access
const resourceService = self.ctx.resourceService;
```

**1. getResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.resourceService.getResources(pageLink, 'your-resourcetype-value', 'your-resourcesubtype-value').subscribe(resources => {
  console.log('Get Resources:', resources);
});
```

**2. getTenantResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.resourceService.getTenantResources(pageLink).subscribe(tenantResources => {
  console.log('Get Tenant Resources:', tenantResources);
});
```

**3. getResource**

```javascript
self.ctx.resourceService.getResource('your-resource-id').subscribe(resource => {
  console.log('Get Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
self.ctx.resourceService.getResourceInfoById('your-resource-id').subscribe(resourceInfoById => {
  console.log('Get Resource Info By Id:', resourceInfoById);
});
```

**5. getResourceInfo**

```javascript
self.ctx.resourceService.getResourceInfo('your-type-value', 'your-scope-value', 'your-key-value').subscribe(resourceInfo => {
  console.log('Get Resource Info:', resourceInfo);
});
```

**6. downloadResource**

```javascript
self.ctx.resourceService.downloadResource('your-resource-id').subscribe(downloadResource => {
  console.log('Download Resource:', downloadResource);
});
```

**7. saveResources**

```javascript
self.ctx.resourceService.saveResources('your-resources-value').subscribe(resources => {
  console.log('Save Resources:', resources);
});
```

**8. saveResource**

```javascript
self.ctx.resourceService.saveResource('your-resource-value').subscribe(resource => {
  console.log('Save Resource:', resource);
});
```

**9. uploadResources**

```javascript
self.ctx.resourceService.uploadResources('your-resources-value').subscribe(uploadResources => {
  console.log('Upload Resources:', uploadResources);
});
```

**10. uploadResource**

```javascript
self.ctx.resourceService.uploadResource('your-resource-value').subscribe(uploadResource => {
  console.log('Upload Resource:', uploadResource);
});
```

**11. updatedResourceInfo**

```javascript
self.ctx.resourceService.updatedResourceInfo('your-resource-id', 'your-updatedresources-value').subscribe(dResourceInfo => {
  console.log('Updated Resource Info:', dResourceInfo);
});
```

**12. updatedResourceData**

```javascript
self.ctx.resourceService.updatedResourceData('your-resource-id', 'your-data-value').subscribe(dResourceData => {
  console.log('Updated Resource Data:', dResourceData);
});
```

**13. getResourcesByIds**

```javascript
self.ctx.resourceService.getResourcesByIds('your-ids-value').subscribe(resourcesByIds => {
  console.log('Get Resources By Ids:', resourcesByIds);
});
```

---

### **RULE CHAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getRuleChains(pageLink, 'your-type-value').subscribe(ruleChains => {
  console.log('Get Rule Chains:', ruleChains);
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds('your-rulechainids-value').subscribe(ruleChainsByIds => {
  console.log('Get Rule Chains By Ids:', ruleChainsByIds);
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain('your-rulechain-id').subscribe(ruleChain => {
  console.log('Get Rule Chain:', ruleChain);
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels('your-rulechain-id').subscribe(ruleChainOutputLabels => {
  console.log('Get Rule Chain Output Labels:', ruleChainOutputLabels);
});
```

**5. createDefaultRuleChain**

```javascript
ruleChainService.createDefaultRuleChain('your-rulechainname-value').subscribe(defaultRuleChain => {
  console.log('Create Default Rule Chain:', defaultRuleChain);
});
```

**6. saveRuleChain**

```javascript
ruleChainService.saveRuleChain('your-rulechain-value').subscribe(ruleChain => {
  console.log('Save Rule Chain:', ruleChain);
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain('your-rulechain-id').subscribe(rootRuleChain => {
  console.log('Set Root Rule Chain:', rootRuleChain);
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata('your-rulechain-id').subscribe(ruleChainMetadata => {
  console.log('Get Rule Chain Metadata:', ruleChainMetadata);
});
```

**9. saveRuleChainMetadata**

```javascript
ruleChainService.saveRuleChainMetadata('your-rulechainmetadata-value').subscribe(ruleChainMetadata => {
  console.log('Save Rule Chain Metadata:', ruleChainMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
ruleChainService.getRuleNodeComponents('your-modulesmap-value', 'your-rulechaintype-value').subscribe(ruleNodeComponents => {
  console.log('Get Rule Node Components:', ruleNodeComponents);
});
```

**11. getRuleNodeConfigComponent**

```javascript
ruleChainService.getRuleNodeConfigComponent('your-directive-value').subscribe(ruleNodeConfigComponent => {
  console.log('Get Rule Node Config Component:', ruleNodeConfigComponent);
});
```

**12. getRuleNodeComponentByClazz**

```javascript
ruleChainService.getRuleNodeComponentByClazz('your-rulechaintype-value', 'your-clazz-value').subscribe(ruleNodeComponentByClazz => {
  console.log('Get Rule Node Component By Clazz:', ruleNodeComponentByClazz);
});
```

**13. getRuleNodeSupportedLinks**

```javascript
ruleChainService.getRuleNodeSupportedLinks('your-component-value').subscribe(ruleNodeSupportedLinks => {
  console.log('Get Rule Node Supported Links:', ruleNodeSupportedLinks);
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
ruleChainService.ruleNodeAllowCustomLinks('your-component-value').subscribe(ruleNodeAllowCustomLinks => {
  console.log('Rule Node Allow Custom Links:', ruleNodeAllowCustomLinks);
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
ruleChainService.ruleNodeSourceRuleChainId('your-component-value').subscribe(ruleNodeSourceRuleChainId => {
  console.log('Rule Node Source Rule Chain Id:', ruleNodeSourceRuleChainId);
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput('your-rulenode-id').subscribe(latestRuleNodeDebugInput => {
  console.log('Get Latest Rule Node Debug Input:', latestRuleNodeDebugInput);
});
```

**17. testScript**

```javascript
ruleChainService.testScript('your-inputparams-value', 'your-scriptlang-value').subscribe(testScript => {
  console.log('Test Script:', testScript);
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents('your-rulechaintype-value').subscribe(loadRuleNodeComponents => {
  console.log('Load Rule Node Components:', loadRuleNodeComponents);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentsUiResources('your-components-value', 'your-modulesmap-value').subscribe(resolveRuleNodeComponentsUiResources => {
  console.log('Resolve Rule Node Components Ui Resources:', resolveRuleNodeComponentsUiResources);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
ruleChainService.resolveRuleNodeComponentUiResources('your-component-value', 'your-modulesmap-value').subscribe(resolveRuleNodeComponentUiResources => {
  console.log('Resolve Rule Node Component Ui Resources:', resolveRuleNodeComponentUiResources);
});
```

**21. getEdgeRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getEdgeRuleChains('your-edge-id', pageLink).subscribe(edgeRuleChains => {
  console.log('Get Edge Rule Chains:', edgeRuleChains);
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge('your-edge-id', 'your-rulechain-id').subscribe(ruleChainToEdge => {
  console.log('Assign Rule Chain To Edge:', ruleChainToEdge);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain('your-rulechain-id').subscribe(edgeTemplateRootRuleChain => {
  console.log('Set Edge Template Root Rule Chain:', edgeTemplateRootRuleChain);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(autoAssignToEdgeRuleChain => {
  console.log('Set Auto Assign To Edge Rule Chain:', autoAssignToEdgeRuleChain);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain('your-rulechain-id').subscribe(unsetAutoAssignToEdgeRuleChain => {
  console.log('Unset Auto Assign To Edge Rule Chain:', unsetAutoAssignToEdgeRuleChain);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoAssignToEdgeRuleChains => {
  console.log('Get Auto Assign To Edge Rule Chains:', autoAssignToEdgeRuleChains);
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain('your-edge-id', 'your-rulechain-id').subscribe(edgeRootRuleChain => {
  console.log('Set Edge Root Rule Chain:', edgeRootRuleChain);
});
```

---

### **TENANT PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfiles(pageLink).subscribe(tenantProfiles => {
  console.log('Get Tenant Profiles:', tenantProfiles);
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile('your-tenantprofile-id').subscribe(tenantProfile => {
  console.log('Get Tenant Profile:', tenantProfile);
});
```

**3. saveTenantProfile**

```javascript
tenantProfileService.saveTenantProfile('your-tenantprofile-value').subscribe(tenantProfile => {
  console.log('Save Tenant Profile:', tenantProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile('your-tenantprofile-id').subscribe(defaultTenantProfile => {
  console.log('Set Default Tenant Profile:', defaultTenantProfile);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(defaultTenantProfileInfo => {
  console.log('Get Default Tenant Profile Info:', defaultTenantProfileInfo);
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo('your-tenantprofile-id').subscribe(tenantProfileInfo => {
  console.log('Get Tenant Profile Info:', tenantProfileInfo);
});
```

**7. getTenantProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(tenantProfileInfos => {
  console.log('Get Tenant Profile Infos:', tenantProfileInfos);
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds('your-tenantprofileids-value').subscribe(tenantProfilesByIds => {
  console.log('Get Tenant Profiles By Ids:', tenantProfilesByIds);
});
```

---

### **TENANT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenants(pageLink).subscribe(tenants => {
  console.log('Get Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds('your-tenantids-value').subscribe(tenantsByIds => {
  console.log('Get Tenants By Ids:', tenantsByIds);
});
```

**3. getTenantInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenantInfos(pageLink).subscribe(tenantInfos => {
  console.log('Get Tenant Infos:', tenantInfos);
});
```

**4. getTenant**

```javascript
tenantService.getTenant('your-tenant-id').subscribe(tenant => {
  console.log('Get Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo('your-tenant-id').subscribe(tenantInfo => {
  console.log('Get Tenant Info:', tenantInfo);
});
```

**6. saveTenant**

```javascript
tenantService.saveTenant('your-tenant-value').subscribe(tenant => {
  console.log('Save Tenant:', tenant);
});
```

---

### **TRENDZ SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const trendzSettingsService = $injector.get(self.ctx.servicesMap.get('trendzSettingsService'));
```

**1. getTrendzSettings**

```javascript
trendzSettingsService.getTrendzSettings().subscribe(trendzSettings => {
  console.log('Get Trendz Settings:', trendzSettings);
});
```

**2. saveTrendzSettings**

```javascript
trendzSettingsService.saveTrendzSettings('your-trendzsettings-value').subscribe(trendzSettings => {
  console.log('Save Trendz Settings:', trendzSettings);
});
```

---

### **TWO FACTOR AUTHENTICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings().subscribe(twoFaSettings => {
  console.log('Get Two Fa Settings:', twoFaSettings);
});
```

**2. saveTwoFaSettings**

```javascript
twoFactorAuthenticationService.saveTwoFaSettings('your-settings-value').subscribe(twoFaSettings => {
  console.log('Save Two Fa Settings:', twoFaSettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(availableTwoFaProviders => {
  console.log('Get Available Two Fa Providers:', availableTwoFaProviders);
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig('your-providertype-value').subscribe(twoFaAccountConfig => {
  console.log('Generate Two Fa Account Config:', twoFaAccountConfig);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(accountTwoFaSettings => {
  console.log('Get Account Two Fa Settings:', accountTwoFaSettings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig('your-providertype-value', true).subscribe(twoFaAccountConfig => {
  console.log('Update Two Fa Account Config:', twoFaAccountConfig);
});
```

**7. submitTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.submitTwoFaAccountConfig('your-authconfig-value').subscribe(submitTwoFaAccountConfig => {
  console.log('Submit Two Fa Account Config:', submitTwoFaAccountConfig);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig('your-authconfig-value', 0).subscribe(verifyAndSaveTwoFaAccountConfig => {
  console.log('Verify And Save Two Fa Account Config:', verifyAndSaveTwoFaAccountConfig);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig('your-providertype-value').subscribe(twoFaAccountConfig => {
  console.log('Delete Two Fa Account Config:', twoFaAccountConfig);
});
```

---

### **UI SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const uiSettingsService = $injector.get(self.ctx.servicesMap.get('uiSettingsService'));
```

**1. getHelpBaseUrl**

```javascript
uiSettingsService.getHelpBaseUrl().subscribe(helpBaseUrl => {
  console.log('Get Help Base Url:', helpBaseUrl);
});
```

---

### **USAGE INFO SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('usageInfoService'));
```

**1. getUsageInfo**

```javascript
usageInfoService.getUsageInfo().subscribe(usageInfo => {
  console.log('Get Usage Info:', usageInfo);
});
```

---

### **USER SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

**1. getUsers** (!!CE VERSION!!)

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getUsers(pageLink).subscribe(users => {
  console.log('Get Users:', users);
});
```

**2. getTenantAdmins**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getTenantAdmins('your-tenant-id', pageLink).subscribe(admins => {
  console.log('Get Tenant Admins:', admins);
});
```

**3. getCustomerUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getCustomerUsers('your-customer-id', pageLink).subscribe(users => {
  console.log('Get Customer Users:', users);
});
```

**4. getUsersForAssign**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getUsersForAssign('your-alarm-id', pageLink).subscribe(usersForAssign => {
  console.log('Get Users For Assign:', usersForAssign);
});
```

**5. getUser**

```javascript
self.ctx.userService.getUser('your-user-id').subscribe(user => {
  console.log('Get User:', user);
});
```

**6. getUsersByIds**

```javascript
self.ctx.userService.getUsersByIds('your-userids-value').subscribe(usersByIds => {
  console.log('Get Users By Ids:', usersByIds);
});
```

**7. saveUser**

```javascript
self.ctx.userService.saveUser('your-user-value', 'your-email@example.com').subscribe(user => {
  console.log('Save User:', user);
});
```

**8. getActivationLink**

```javascript
self.ctx.userService.getActivationLink('your-user-id').subscribe(activationLink => {
  console.log('Get Activation Link:', activationLink);
});
```

**9. getActivationLinkInfo**

```javascript
self.ctx.userService.getActivationLinkInfo('your-user-id').subscribe(activationLinkInfo => {
  console.log('Get Activation Link Info:', activationLinkInfo);
});
```

**10. setUserCredentialsEnabled**

```javascript
self.ctx.userService.setUserCredentialsEnabled('your-user-id', true).subscribe(userCredentialsEnabled => {
  console.log('Set User Credentials Enabled:', userCredentialsEnabled);
});
```

**11. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.findUsersByQuery(pageLink).subscribe(usersByQuery => {
  console.log('Find Users By Query:', usersByQuery);
});
```

---

### **USER SETTINGS SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userSettingsService = $injector.get(self.ctx.servicesMap.get('userSettingsService'));

// Alternative: Direct context access
const userSettingsService = self.ctx.userSettingsService;
```

**1. loadUserSettings**

```javascript
self.ctx.userSettingsService.loadUserSettings().subscribe(loadUserSettings => {
  console.log('Load User Settings:', loadUserSettings);
});
```

**2. saveUserSettings**

```javascript
self.ctx.userSettingsService.saveUserSettings('your-usersettings-value').subscribe(userSettings => {
  console.log('Save User Settings:', userSettings);
});
```

**3. putUserSettings**

```javascript
self.ctx.userSettingsService.putUserSettings('your-usersettingsdata-value').subscribe(result => {
  console.log('Put User Settings:', result);
});
```

**4. getDocumentationLinks**

```javascript
self.ctx.userSettingsService.getDocumentationLinks().subscribe(documentationLinks => {
  console.log('Get Documentation Links:', documentationLinks);
});
```

**5. updateDocumentationLinks**

```javascript
self.ctx.userSettingsService.updateDocumentationLinks('your-documentationlinks-value').subscribe(result => {
  console.log('Update Documentation Links:', result);
});
```

**6. getQuickLinks**

```javascript
self.ctx.userSettingsService.getQuickLinks().subscribe(quickLinks => {
  console.log('Get Quick Links:', quickLinks);
});
```

**7. updateQuickLinks**

```javascript
self.ctx.userSettingsService.updateQuickLinks('your-quicklinks-value').subscribe(result => {
  console.log('Update Quick Links:', result);
});
```

**8. getGettingStarted**

```javascript
self.ctx.userSettingsService.getGettingStarted().subscribe(gettingStarted => {
  console.log('Get Getting Started:', gettingStarted);
});
```

**9. updateGettingStarted**

```javascript
self.ctx.userSettingsService.updateGettingStarted('your-gettingstarted-value').subscribe(result => {
  console.log('Update Getting Started:', result);
});
```

**10. getUserDashboardsInfo**

```javascript
self.ctx.userSettingsService.getUserDashboardsInfo().subscribe(userDashboardsInfo => {
  console.log('Get User Dashboards Info:', userDashboardsInfo);
});
```

**11. reportUserDashboardAction**

```javascript
self.ctx.userSettingsService.reportUserDashboardAction('your-dashboard-id', 'your-action-value').subscribe(reportUserDashboardAction => {
  console.log('Report User Dashboard Action:', reportUserDashboardAction);
});
```

---

### **WIDGET SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const widgetService = $injector.get(self.ctx.servicesMap.get('widgetService'));
```

**1. getWidgetScopeVariables**

```javascript
widgetService.getWidgetScopeVariables().subscribe(widgetScopeVariables => {
  console.log('Get Widget Scope Variables:', widgetScopeVariables);
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(allWidgetsBundles => {
  console.log('Get All Widgets Bundles:', allWidgetsBundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(systemWidgetsBundles => {
  console.log('Get System Widgets Bundles:', systemWidgetsBundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(tenantWidgetsBundles => {
  console.log('Get Tenant Widgets Bundles:', tenantWidgetsBundles);
});
```

**5. getWidgetBundles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetBundles(pageLink).subscribe(widgetBundles => {
  console.log('Get Widget Bundles:', widgetBundles);
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle('your-widgetsbundle-id').subscribe(widgetsBundle => {
  console.log('Get Widgets Bundle:', widgetsBundle);
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle('your-widgetsbundle-id').subscribe(widgetsBundle => {
  console.log('Export Widgets Bundle:', widgetsBundle);
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle('your-widgetsbundle-value').subscribe(widgetsBundle => {
  console.log('Save Widgets Bundle:', widgetsBundle);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes('your-widgetsbundle-id', 'your-widgettypeids-value').subscribe(result => {
  console.log('Update Widgets Bundle Widget Types:', result);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns('your-widgetsbundle-id', 'your-widgettypefqns-value').subscribe(result => {
  console.log('Update Widgets Bundle Widget Fqns:', result);
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes('your-widgetsbundle-id').subscribe(bundleWidgetTypes => {
  console.log('Get Bundle Widget Types:', bundleWidgetTypes);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails('your-widgetsbundle-id').subscribe(bundleWidgetTypesDetails => {
  console.log('Export Bundle Widget Types Details:', bundleWidgetTypesDetails);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns('your-widgetsbundle-id').subscribe(bundleWidgetTypeFqns => {
  console.log('Get Bundle Widget Type Fqns:', bundleWidgetTypeFqns);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList('your-widgetsbundle-id').subscribe(bundleWidgetTypeInfosList => {
  console.log('Get Bundle Widget Type Infos List:', bundleWidgetTypeInfosList);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getBundleWidgetTypeInfos(pageLink, 'your-widgetsbundle-id', 'your-widgettypes-value').subscribe(bundleWidgetTypeInfos => {
  console.log('Get Bundle Widget Type Infos:', bundleWidgetTypeInfos);
});
```

**16. getWidgetType**

```javascript
widgetService.getWidgetType('your-fullfqn-value').subscribe(widgetType => {
  console.log('Get Widget Type:', widgetType);
});
```

**17. saveWidgetTypeDetails**

```javascript
widgetService.saveWidgetTypeDetails('your-widgetinfo-value', 'your--id', 0, 0).subscribe(widgetTypeDetails => {
  console.log('Save Widget Type Details:', widgetTypeDetails);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails('your-widgettypedetails-value').subscribe(importedWidgetTypeDetails => {
  console.log('Save Imported Widget Type Details:', importedWidgetTypeDetails);
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById('your-widgettype-id').subscribe(widgetTypeById => {
  console.log('Get Widget Type By Id:', widgetTypeById);
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType('your-widgettype-id').subscribe(widgetType => {
  console.log('Export Widget Type:', widgetType);
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById('your-widgettype-id').subscribe(widgetTypeInfoById => {
  console.log('Get Widget Type Info By Id:', widgetTypeInfoById);
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType('your-widgettypedetails-value').subscribe(widgetType => {
  console.log('Save Widget Type:', widgetType);
});
```

**23. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetTypes(pageLink, 'your-widgettypes-value').subscribe(widgetTypes => {
  console.log('Get Widget Types:', widgetTypes);
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate('your-widgettypeparam-value').subscribe(widgetTemplate => {
  console.log('Get Widget Template:', widgetTemplate);
});
```

**25. getWidgetInfoFromCache**

```javascript
widgetService.getWidgetInfoFromCache('your-fullfqn-value').subscribe(widgetInfoFromCache => {
  console.log('Get Widget Info From Cache:', widgetInfoFromCache);
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
widgetService.getBasicWidgetSettingsComponentBySelector('your-selector-value').subscribe(basicWidgetSettingsComponentBySelector => {
  console.log('Get Basic Widget Settings Component By Selector:', basicWidgetSettingsComponentBySelector);
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
widgetService.getWidgetSettingsComponentTypeBySelector('your-selector-value').subscribe(widgetSettingsComponentTypeBySelector => {
  console.log('Get Widget Settings Component Type By Selector:', widgetSettingsComponentTypeBySelector);
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated('your-updatedwidgettype-value').subscribe(widgetTypeUpdated => {
  console.log('Widget Type Updated:', widgetTypeUpdated);
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds('your-widgetsbundleids-value').subscribe(widgetsBundlesByIds => {
  console.log('Get Widgets Bundles By Ids:', widgetsBundlesByIds);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(loadWidgetsBundleCache => {
  console.log('Load Widgets Bundle Cache:', loadWidgetsBundleCache);
});
```

---
