# ThingsBoard CE Widget Service Documentation

Auto-generated from TB CE commit `79bb2b0a659d`.
42 services, 453 methods.

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
- [O AUTH SERVICE](#o-auth-service)
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

## USING SERVICES IN WIDGETS / CUSTOM ACTIONS

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

## USING PAGE LINKS

Many service methods return paginated results. PageLinks control pagination to avoid overloading the server when you have thousands of records.

```javascript
const pageLink = self.ctx.pageLink(
  10,                // pageSize - number of results per page
  0,                 // page - starting page (0-indexed)
  'searchText',      // textSearch - filter results by text
  'sortProperty',    // sortProperty - field to sort by
  'sortOrder'        // sortOrder - 'ASC' or 'DESC'
);
```

---

### **ADMIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. sendTestMail**

```javascript
const adminSettings = adminSettings;
adminService.sendTestMail(adminSettings).subscribe(result => {
  console.log('Send Test Mail: result');
});
```

**2. sendTestSms**

```javascript
const testSmsRequest = testSmsRequest;
adminService.sendTestSms(testSmsRequest).subscribe(result => {
  console.log('Send Test Sms: result');
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings().subscribe(securitysettings => {
  console.log('Get Security Settings: securitysettings');
});
```

**4. saveSecuritySettings**

```javascript
const securitySettings = securitySettings;
adminService.saveSecuritySettings(securitySettings).subscribe(savedSecuritySettings => {
  console.log('Save Security Settings: savedSecuritySettings');
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings().subscribe(jwtsettings => {
  console.log('Get Jwt Settings: jwtsettings');
});
```

**6. saveJwtSettings**

```javascript
const jwtSettings = jwtSettings;
adminService.saveJwtSettings(jwtSettings).subscribe(savedJwtSettings => {
  console.log('Save Jwt Settings: savedJwtSettings');
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(repositorysettings => {
  console.log('Get Repository Settings: repositorysettings');
});
```

**8. saveRepositorySettings**

```javascript
const repositorySettings = repositorySettings;
adminService.saveRepositorySettings(repositorySettings).subscribe(savedRepositorySettings => {
  console.log('Save Repository Settings: savedRepositorySettings');
});
```

**9. checkRepositoryAccess**

```javascript
const repositorySettings = repositorySettings;
adminService.checkRepositoryAccess(repositorySettings).subscribe(result => {
  console.log('Check Repository Access: result');
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(repositorySettingsInfo => {
  console.log('Get Repository Settings Info: repositorySettingsInfo');
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(autocommitsettings => {
  console.log('Get Auto Commit Settings: autocommitsettings');
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(result => {
  console.log('Auto Commit Settings Exists: result');
});
```

**13. saveAutoCommitSettings**

```javascript
const autoCommitSettings = autoCommitSettings;
adminService.saveAutoCommitSettings(autoCommitSettings).subscribe(savedAutoCommitSettings => {
  console.log('Save Auto Commit Settings: savedAutoCommitSettings');
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(result => {
  console.log('Check Updates: result');
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(featuresInfo => {
  console.log('Get Features Info: featuresInfo');
});
```

**16. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url: loginProcessingUrl');
});
```

**17. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(result => {
  console.log('Generate Access Token: result');
});
```

**18. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(mailConfigTemplate => {
  console.log('Get Mail Config Template: mailConfigTemplate');
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
const aiModel = aiModel;
aiModelService.saveAiModel(aiModel).subscribe(savedAiModel => {
  console.log('Save Ai Model: savedAiModel');
});
```

**2. getAiModels**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aiModelService.getAiModels(pageLink).subscribe(aimodels => {
  console.log('Get Ai Models: aimodels');
});
```

**3. getAiModelById**

```javascript
aiModelService.getAiModelById('your-id').subscribe(aiModelById => {
  console.log('Get Ai Model By Id: aiModelById');
});
```

**4. checkConnectivity**

```javascript
const aiModelWithUserMsg = aiModelWithUserMsg;
aiModelService.checkConnectivity(aiModelWithUserMsg).subscribe(result => {
  console.log('Check Connectivity: result');
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
const alarmComment = alarmComment;
alarmCommentService.saveAlarmComment('your-alarm-id', alarmComment).subscribe(savedAlarmComment => {
  console.log('Save Alarm Comment: savedAlarmComment');
});
```

**2. getAlarmComments**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmCommentService.getAlarmComments('your-alarm-id', pageLink).subscribe(alarmcomments => {
  console.log('Get Alarm Comments: alarmcomments');
});
```

**3. deleteAlarmComments**

```javascript
alarmCommentService.deleteAlarmComments('your-alarm-id', 'your-comment-id').subscribe(result => {
  console.log('Delete Alarm Comments: result');
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
alarmRulesService.getAlarmRuleById('your-alarm-rule-id').subscribe(alarmRuleById => {
  console.log('Get Alarm Rule By Id: alarmRuleById');
});
```

**2. saveAlarmRule**

```javascript
const alarmRule = alarmRule;
alarmRulesService.saveAlarmRule(alarmRule).subscribe(savedAlarmRule => {
  console.log('Save Alarm Rule: savedAlarmRule');
});
```

**3. deleteAlarmRule**

```javascript
alarmRulesService.deleteAlarmRule('your-alarm-rule-id').subscribe(result => {
  console.log('Delete Alarm Rule: result');
});
```

**4. getAlarmRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = query;
alarmRulesService.getAlarmRules(pageLink, query).subscribe(alarmrules => {
  console.log('Get Alarm Rules: alarmrules');
});
```

**5. getAlarmRulesByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRulesByEntityId(pageLink).subscribe(alarmRulesByEntityId => {
  console.log('Get Alarm Rules By Entity Id: alarmRulesByEntityId');
});
```

**6. testScript**

```javascript
const inputParams = inputParams;
alarmRulesService.testScript(inputParams).subscribe(result => {
  console.log('Test Script: result');
});
```

**7. getLatestAlarmRuleDebugEvent**

```javascript
alarmRulesService.getLatestAlarmRuleDebugEvent('your-id').subscribe(latestAlarmRuleDebugEvent => {
  console.log('Get Latest Alarm Rule Debug Event:latestAlarmRuleDebugEvent');
});
```

**8. getAlarmRuleNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmRulesService.getAlarmRuleNames(pageLink).subscribe(alarmrulenames => {
  console.log('Get Alarm Rule Names: alarmrulenames');
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
  console.log('Get Alarm: alarm');
});
```

**2. getAlarmInfo**

```javascript
alarmService.getAlarmInfo('your-alarm-id').subscribe(alarmInfo => {
  console.log('Get Alarm Info: alarmInfo');
});
```

**3. saveAlarm**

```javascript
const alarm = alarm;
alarmService.saveAlarm(alarm).subscribe(savedAlarm => {
  console.log('Save Alarm: savedAlarm');
});
```

**4. ackAlarm**

```javascript
alarmService.ackAlarm('your-alarm-id').subscribe(result => {
  console.log('Ack Alarm: result');
});
```

**5. clearAlarm**

```javascript
alarmService.clearAlarm('your-alarm-id').subscribe(result => {
  console.log('Clear Alarm: result');
});
```

**6. assignAlarm**

```javascript
alarmService.assignAlarm('your-alarm-id', 'your-assignee-id').subscribe(result => {
  console.log('Assign Alarm: result');
});
```

**7. unassignAlarm**

```javascript
alarmService.unassignAlarm('your-alarm-id').subscribe(result => {
  console.log('Unassign Alarm: result');
});
```

**8. deleteAlarm**

```javascript
alarmService.deleteAlarm('your-alarm-id').subscribe(result => {
  console.log('Delete Alarm: result');
});
```

**9. getAlarms**

```javascript
const query = query;
alarmService.getAlarms(query).subscribe(alarms => {
  console.log('Get Alarms: alarms');
});
```

**10. getAlarmsV2**

```javascript
const query = query;
alarmService.getAlarmsV2(query).subscribe(alarmsV2 => {
  console.log('Get Alarms V: alarmsV2');
});
```

**11. getAllAlarms**

```javascript
const query = query;
alarmService.getAllAlarms(query).subscribe(allalarms => {
  console.log('Get All Alarms: allalarms');
});
```

**12. getAllAlarmsV2**

```javascript
const query = query;
alarmService.getAllAlarmsV2(query).subscribe(allAlarmsV2 => {
  console.log('Get All Alarms V: allAlarmsV2');
});
```

**13. getHighestAlarmSeverity**

```javascript
const alarmSearchStatus = alarmSearchStatus;
const alarmStatus = alarmStatus;
alarmService.getHighestAlarmSeverity('your-entity-id', alarmSearchStatus, alarmStatus).subscribe(highestAlarmSeverity => {
  console.log('Get Highest Alarm Severity: highestAlarmSeverity');
});
```

**14. getAlarmTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmService.getAlarmTypes(pageLink).subscribe(alarmtypes => {
  console.log('Get Alarm Types: alarmtypes');
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
const apiKey = apiKey;
apiKeyService.saveApiKey(apiKey).subscribe(savedApiKey => {
  console.log('Save Api Key: savedApiKey');
});
```

**2. deleteApiKey**

```javascript
apiKeyService.deleteApiKey('your-id').subscribe(result => {
  console.log('Delete Api Key: result');
});
```

**3. updateApiKeyDescription**

```javascript
const description = description;
apiKeyService.updateApiKeyDescription('your-id', description).subscribe(result => {
  console.log('Update Api Key Description: result');
});
```

**4. enableApiKey**

```javascript
apiKeyService.enableApiKey('your-id', true).subscribe(result => {
  console.log('Enable Api Key: result');
});
```

**5. getUserApiKeys**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apiKeyService.getUserApiKeys('your-user-id', pageLink).subscribe(userapikeys => {
  console.log('Get User Api Keys: userapikeys');
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
assetProfileService.getAssetProfiles(pageLink).subscribe(assetprofiles => {
  console.log('Get Asset Profiles: assetprofiles');
});
```

**2. getAssetProfilesByIds**

```javascript
assetProfileService.getAssetProfilesByIds('your-id').subscribe(assetprofilesbyids => {
  console.log('Get Asset Profiles By Ids: assetprofilesbyids');
});
```

**3. getAssetProfile**

```javascript
assetProfileService.getAssetProfile('your-asset-profile-id').subscribe(assetProfile => {
  console.log('Get Asset Profile: assetProfile');
});
```

**4. exportAssetProfile**

```javascript
assetProfileService.exportAssetProfile('your-asset-profile-id').subscribe(exported => {
  console.log('Export Asset Profile: exported');
});
```

**5. saveAssetProfile**

```javascript
const assetProfile = assetProfile;
assetProfileService.saveAssetProfile(assetProfile).subscribe(savedAssetProfile => {
  console.log('Save Asset Profile: savedAssetProfile');
});
```

**6. setDefaultAssetProfile**

```javascript
assetProfileService.setDefaultAssetProfile('your-asset-profile-id').subscribe(result => {
  console.log('Set Default Asset Profile: result');
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(defaultAssetProfileInfo => {
  console.log('Get Default Asset Profile Info:defaultAssetProfileInfo');
});
```

**8. getAssetProfileInfo**

```javascript
assetProfileService.getAssetProfileInfo('your-asset-profile-id').subscribe(assetProfileInfo => {
  console.log('Get Asset Profile Info: assetProfileInfo');
});
```

**9. getAssetProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(assetprofileinfos => {
  console.log('Get Asset Profile Infos: assetprofileinfos');
});
```

**10. getAssetProfileNames**

```javascript
assetProfileService.getAssetProfileNames(true).subscribe(assetprofilenames => {
  console.log('Get Asset Profile Names: assetprofilenames');
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
assetService.getTenantAssetInfos(pageLink, 'type').subscribe(tenantassetinfos => {
  console.log('Get Tenant Asset Infos: tenantassetinfos');
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetService.getTenantAssetInfosByAssetProfileId(pageLink, 'your-asset-profile-id').subscribe(tenantAssetInfosByAssetProfileId => {
  console.log('Get Tenant Asset Infos By Asset Profile Id:tenantAssetInfosByAssetProfileId');
});
```

**3. getCustomerAssetInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetService.getCustomerAssetInfos('your-customer-id', pageLink, 'type').subscribe(customerassetinfos => {
  console.log('Get Customer Asset Infos: customerassetinfos');
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetService.getCustomerAssetInfosByAssetProfileId('your-customer-id', pageLink, 'your-asset-profile-id').subscribe(customerAssetInfosByAssetProfileId => {
  console.log('Get Customer Asset Infos By Asset Profile Id:customerAssetInfosByAssetProfileId');
});
```

**5. getAsset**

```javascript
assetService.getAsset('your-asset-id').subscribe(asset => {
  console.log('Get Asset: asset');
});
```

**6. getAssets**

```javascript
assetService.getAssets('your-id').subscribe(assets => {
  console.log('Get Assets: assets');
});
```

**7. getAssetInfo**

```javascript
assetService.getAssetInfo('your-asset-id').subscribe(assetInfo => {
  console.log('Get Asset Info: assetInfo');
});
```

**8. saveAsset**

```javascript
const asset = asset;
assetService.saveAsset(asset).subscribe(savedAsset => {
  console.log('Save Asset: savedAsset');
});
```

**9. getAssetTypes**

```javascript
assetService.getAssetTypes().subscribe(assettypes => {
  console.log('Get Asset Types: assettypes');
});
```

**10. makeAssetPublic**

```javascript
assetService.makeAssetPublic('your-asset-id').subscribe(result => {
  console.log('Make Asset Public: result');
});
```

**11. assignAssetToCustomer**

```javascript
assetService.assignAssetToCustomer('your-customer-id', 'your-asset-id').subscribe(result => {
  console.log('Assign Asset To Customer: result');
});
```

**12. findByQuery**

```javascript
const query = query;
assetService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**13. findByName**

```javascript
const assetName = assetName;
assetService.findByName(assetName).subscribe(entity => {
  console.log('Find By Name: entity');
});
```

**14. assignAssetToEdge**

```javascript
assetService.assignAssetToEdge('your-edge-id', 'your-asset-id').subscribe(result => {
  console.log('Assign Asset To Edge: result');
});
```

**15. getEdgeAssets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetService.getEdgeAssets('your-edge-id', pageLink, 'type').subscribe(edgeassets => {
  console.log('Get Edge Assets: edgeassets');
});
```

**16. bulkImportAssets**

```javascript
const entitiesData = entitiesData;
assetService.bulkImportAssets(entitiesData).subscribe(result => {
  console.log('Bulk Import Assets: result');
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
attributeService.getEntityAttributes('your-entity-id', 'SERVER_SCOPE', ['key1', 'key2']).subscribe(entityattributes => {
  console.log('Get Entity Attributes: entityattributes');
});
```

**2. deleteEntityAttributes**

```javascript
attributeService.deleteEntityAttributes('your-entity-id', 'SERVER_SCOPE', [{key: 'key1', value: 'value1'}]).subscribe(result => {
  console.log('Delete Entity Attributes: result');
});
```

**3. deleteEntityTimeseries**

```javascript
const startTs = Date.now() - 86400000;
const endTs = Date.now();
attributeService.deleteEntityTimeseries('your-entity-id', [{key: 'tsKey', ts: Date.now(), value: 42}], startTs, endTs).subscribe(result => {
  console.log('Delete Entity Timeseries: result');
});
```

**4. saveEntityAttributes**

```javascript
attributeService.saveEntityAttributes('your-entity-id', 'SERVER_SCOPE', [{key: 'key1', value: 'value1'}]).subscribe(savedEntityAttributes => {
  console.log('Save Entity Attributes: savedEntityAttributes');
});
```

**5. saveEntityTimeseries**

```javascript
attributeService.saveEntityTimeseries('your-entity-id', 'SERVER_SCOPE', [{key: 'tsKey', ts: Date.now(), value: 42}]).subscribe(savedEntityTimeseries => {
  console.log('Save Entity Timeseries: savedEntityTimeseries');
});
```

**6. getEntityTimeseries**

```javascript
const startTs = Date.now() - 86400000;
const endTs = Date.now();
attributeService.getEntityTimeseries('your-entity-id', ['key1', 'key2'], startTs, endTs, 100, 'NONE', 3600000, 'ASC', 'type').subscribe(entitytimeseries => {
  console.log('Get Entity Timeseries: entitytimeseries');
});
```

**7. getEntityTimeseriesLatest**

```javascript
attributeService.getEntityTimeseriesLatest('your-entity-id', ['key1', 'key2']).subscribe(entityTimeseriesLatest => {
  console.log('Get Entity Timeseries Latest: entityTimeseriesLatest');
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
auditLogService.getAuditLogs(pageLink).subscribe(auditlogs => {
  console.log('Get Audit Logs: auditlogs');
});
```

**2. getAuditLogsByCustomerId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByCustomerId('your-customer-id', pageLink).subscribe(auditLogsByCustomerId => {
  console.log('Get Audit Logs By Customer Id: auditLogsByCustomerId');
});
```

**3. getAuditLogsByUserId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByUserId('your-user-id', pageLink).subscribe(auditLogsByUserId => {
  console.log('Get Audit Logs By User Id: auditLogsByUserId');
});
```

**4. getAuditLogsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
auditLogService.getAuditLogsByEntityId('your-entity-id', pageLink).subscribe(auditLogsByEntityId => {
  console.log('Get Audit Logs By Entity Id: auditLogsByEntityId');
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
calculatedFieldsService.getCalculatedFieldById('your-calculated-field-id').subscribe(calculatedFieldById => {
  console.log('Get Calculated Field By Id: calculatedFieldById');
});
```

**2. saveCalculatedField**

```javascript
const calculatedField = calculatedField;
calculatedFieldsService.saveCalculatedField(calculatedField).subscribe(savedCalculatedField => {
  console.log('Save Calculated Field: savedCalculatedField');
});
```

**3. deleteCalculatedField**

```javascript
calculatedFieldsService.deleteCalculatedField('your-calculated-field-id').subscribe(result => {
  console.log('Delete Calculated Field: result');
});
```

**4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = query;
calculatedFieldsService.getCalculatedFields(pageLink, query).subscribe(calculatedfields => {
  console.log('Get Calculated Fields: calculatedfields');
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, 'type').subscribe(calculatedFieldsByEntityId => {
  console.log('Get Calculated Fields By Entity Id:calculatedFieldsByEntityId');
});
```

**6. testScript**

```javascript
const inputParams = inputParams;
calculatedFieldsService.testScript(inputParams).subscribe(result => {
  console.log('Test Script: result');
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
calculatedFieldsService.getLatestCalculatedFieldDebugEvent('your-id').subscribe(latestCalculatedFieldDebugEvent => {
  console.log('Get Latest Calculated Field Debug Event:latestCalculatedFieldDebugEvent');
});
```

**8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
calculatedFieldsService.getCalculatedFieldNames(pageLink, 'type').subscribe(calculatedfieldnames => {
  console.log('Get Calculated Field Names: calculatedfieldnames');
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
componentDescriptorService.getComponentDescriptorsByType('type', 'type').subscribe(componentDescriptorsByType => {
  console.log('Get Component Descriptors By Type:componentDescriptorsByType');
});
```

**2. getComponentDescriptorsByTypes**

```javascript
componentDescriptorService.getComponentDescriptorsByTypes('type', 'type').subscribe(componentdescriptorsbytypes => {
  console.log('Get Component Descriptors By Types:componentdescriptorsbytypes');
});
```

**3. getComponentDescriptorByClazz**

```javascript
const componentDescriptorClazz = componentDescriptorClazz;
componentDescriptorService.getComponentDescriptorByClazz(componentDescriptorClazz).subscribe(componentDescriptorByClazz => {
  console.log('Get Component Descriptor By Clazz:componentDescriptorByClazz');
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
customerService.getCustomers(pageLink).subscribe(customers => {
  console.log('Get Customers: customers');
});
```

**2. getCustomer**

```javascript
customerService.getCustomer('your-customer-id').subscribe(customer => {
  console.log('Get Customer: customer');
});
```

**3. getCustomersByIds**

```javascript
customerService.getCustomersByIds('your-id').subscribe(customersbyids => {
  console.log('Get Customers By Ids: customersbyids');
});
```

**4. saveCustomer**

```javascript
const customer = customer;
customerService.saveCustomer(customer).subscribe(savedCustomer => {
  console.log('Save Customer: savedCustomer');
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
dashboardService.getTenantDashboards(pageLink).subscribe(tenantdashboards => {
  console.log('Get Tenant Dashboards: tenantdashboards');
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getTenantDashboardsByTenantId('your-tenant-id', pageLink).subscribe(tenantDashboardsByTenantId => {
  console.log('Get Tenant Dashboards By Tenant Id:tenantDashboardsByTenantId');
});
```

**3. getCustomerDashboards**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getCustomerDashboards('your-customer-id', pageLink).subscribe(customerdashboards => {
  console.log('Get Customer Dashboards: customerdashboards');
});
```

**4. getDashboard**

```javascript
dashboardService.getDashboard('your-dashboard-id').subscribe(dashboard => {
  console.log('Get Dashboard: dashboard');
});
```

**5. exportDashboard**

```javascript
dashboardService.exportDashboard('your-dashboard-id').subscribe(exported => {
  console.log('Export Dashboard: exported');
});
```

**6. getDashboardInfo**

```javascript
dashboardService.getDashboardInfo('your-dashboard-id').subscribe(dashboardInfo => {
  console.log('Get Dashboard Info: dashboardInfo');
});
```

**7. getDashboards**

```javascript
dashboardService.getDashboards('your-id').subscribe(dashboards => {
  console.log('Get Dashboards: dashboards');
});
```

**8. saveDashboard**

```javascript
const dashboard = dashboard;
dashboardService.saveDashboard(dashboard).subscribe(savedDashboard => {
  console.log('Save Dashboard: savedDashboard');
});
```

**9. assignDashboardToCustomer**

```javascript
dashboardService.assignDashboardToCustomer('your-customer-id', 'your-dashboard-id').subscribe(result => {
  console.log('Assign Dashboard To Customer: result');
});
```

**10. makeDashboardPublic**

```javascript
dashboardService.makeDashboardPublic('your-dashboard-id').subscribe(result => {
  console.log('Make Dashboard Public: result');
});
```

**11. makeDashboardPrivate**

```javascript
dashboardService.makeDashboardPrivate('your-dashboard-id').subscribe(result => {
  console.log('Make Dashboard Private: result');
});
```

**12. updateDashboardCustomers**

```javascript
dashboardService.updateDashboardCustomers('your-dashboard-id', 'your-id').subscribe(result => {
  console.log('Update Dashboard Customers: result');
});
```

**13. addDashboardCustomers**

```javascript
dashboardService.addDashboardCustomers('your-dashboard-id', 'your-id').subscribe(result => {
  console.log('Add Dashboard Customers: result');
});
```

**14. removeDashboardCustomers**

```javascript
dashboardService.removeDashboardCustomers('your-dashboard-id', 'your-id').subscribe(result => {
  console.log('Remove Dashboard Customers: result');
});
```

**15. getHomeDashboard**

```javascript
dashboardService.getHomeDashboard().subscribe(homeDashboard => {
  console.log('Get Home Dashboard: homeDashboard');
});
```

**16. getTenantHomeDashboardInfo**

```javascript
dashboardService.getTenantHomeDashboardInfo().subscribe(tenantHomeDashboardInfo => {
  console.log('Get Tenant Home Dashboard Info:tenantHomeDashboardInfo');
});
```

**17. setTenantHomeDashboardInfo**

```javascript
const homeDashboardInfo = homeDashboardInfo;
dashboardService.setTenantHomeDashboardInfo(homeDashboardInfo).subscribe(result => {
  console.log('Set Tenant Home Dashboard Info:result');
});
```

**18. getPublicDashboardLink**

```javascript
const dashboard = dashboard;
dashboardService.getPublicDashboardLink(dashboard).subscribe(publicDashboardLink => {
  console.log('Get Public Dashboard Link: publicDashboardLink');
});
```

**19. assignDashboardToEdge**

```javascript
dashboardService.assignDashboardToEdge('your-edge-id', 'your-dashboard-id').subscribe(result => {
  console.log('Assign Dashboard To Edge: result');
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
deviceProfileService.getDeviceProfiles(pageLink).subscribe(deviceprofiles => {
  console.log('Get Device Profiles: deviceprofiles');
});
```

**2. getDeviceProfilesByIds**

```javascript
deviceProfileService.getDeviceProfilesByIds('your-id').subscribe(deviceprofilesbyids => {
  console.log('Get Device Profiles By Ids: deviceprofilesbyids');
});
```

**3. getDeviceProfile**

```javascript
deviceProfileService.getDeviceProfile('your-device-profile-id').subscribe(deviceProfile => {
  console.log('Get Device Profile: deviceProfile');
});
```

**4. exportDeviceProfile**

```javascript
deviceProfileService.exportDeviceProfile('your-device-profile-id').subscribe(exported => {
  console.log('Export Device Profile: exported');
});
```

**5. getLwm2mObjects**

```javascript
deviceProfileService.getLwm2mObjects('ASC', 'your-id', 'searchText').subscribe(lwm2mobjects => {
  console.log('Get Lwm m Objects: lwm2mobjects');
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfo(true).subscribe(lwm2mBootstrapSecurityInfo => {
  console.log('Get Lwm m Bootstrap Security Info:lwm2mBootstrapSecurityInfo');
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(true).subscribe(lwm2mBootstrapSecurityInfoBySecurityType => {
  console.log('Get Lwm m Bootstrap Security Info By Security Type:lwm2mBootstrapSecurityInfoBySecurityType');
});
```

**8. getLwm2mObjectsPage**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(lwm2mObjectsPage => {
  console.log('Get Lwm m Objects Page: lwm2mObjectsPage');
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
const originDeviceProfile = originEntity;
const deviceProfile = deviceProfile;
deviceProfileService.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(savedDeviceProfileAndConfirmOtaChange => {
  console.log('Save Device Profile And Confirm Ota Change:savedDeviceProfileAndConfirmOtaChange');
});
```

**10. saveDeviceProfile**

```javascript
deviceProfileService.saveDeviceProfile().subscribe(savedDeviceProfile => {
  console.log('Save Device Profile: savedDeviceProfile');
});
```

**11. setDefaultDeviceProfile**

```javascript
deviceProfileService.setDefaultDeviceProfile('your-device-profile-id').subscribe(result => {
  console.log('Set Default Device Profile: result');
});
```

**12. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(defaultDeviceProfileInfo => {
  console.log('Get Default Device Profile Info:defaultDeviceProfileInfo');
});
```

**13. getDeviceProfileInfo**

```javascript
deviceProfileService.getDeviceProfileInfo('your-device-profile-id').subscribe(deviceProfileInfo => {
  console.log('Get Device Profile Info: deviceProfileInfo');
});
```

**14. getDeviceProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getDeviceProfileInfos(pageLink, 'type').subscribe(deviceprofileinfos => {
  console.log('Get Device Profile Infos: deviceprofileinfos');
});
```

**15. getDeviceProfileDevicesAttributesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesAttributesKeys('your-device-profile-id').subscribe(deviceprofiledevicesattributeskeys => {
  console.log('Get Device Profile Devices Attributes Keys:deviceprofiledevicesattributeskeys');
});
```

**16. getDeviceProfileDevicesTimeseriesKeys**

```javascript
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys('your-device-profile-id').subscribe(deviceprofiledevicestimeserieskeys => {
  console.log('Get Device Profile Devices Timeseries Keys:deviceprofiledevicestimeserieskeys');
});
```

**17. getDeviceProfileNames**

```javascript
deviceProfileService.getDeviceProfileNames(true).subscribe(deviceprofilenames => {
  console.log('Get Device Profile Names: deviceprofilenames');
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
const deviceInfoQuery = query;
deviceService.getDeviceInfosByQuery(deviceInfoQuery).subscribe(deviceInfosByQuery => {
  console.log('Get Device Infos By Query: deviceInfosByQuery');
});
```

**2. getTenantDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getTenantDeviceInfos(pageLink, 'type').subscribe(tenantdeviceinfos => {
  console.log('Get Tenant Device Infos: tenantdeviceinfos');
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getTenantDeviceInfosByDeviceProfileId(pageLink, 'your-device-profile-id').subscribe(tenantDeviceInfosByDeviceProfileId => {
  console.log('Get Tenant Device Infos By Device Profile Id:tenantDeviceInfosByDeviceProfileId');
});
```

**4. getCustomerDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getCustomerDeviceInfos('your-customer-id', pageLink, 'type').subscribe(customerdeviceinfos => {
  console.log('Get Customer Device Infos: customerdeviceinfos');
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getCustomerDeviceInfosByDeviceProfileId('your-customer-id', pageLink, 'your-device-profile-id').subscribe(customerDeviceInfosByDeviceProfileId => {
  console.log('Get Customer Device Infos By Device Profile Id:customerDeviceInfosByDeviceProfileId');
});
```

**6. getDevice**

```javascript
deviceService.getDevice('your-device-id').subscribe(device => {
  console.log('Get Device: device');
});
```

**7. getDevices**

```javascript
deviceService.getDevices('your-id').subscribe(devices => {
  console.log('Get Devices: devices');
});
```

**8. getDeviceInfo**

```javascript
deviceService.getDeviceInfo('your-device-id').subscribe(deviceInfo => {
  console.log('Get Device Info: deviceInfo');
});
```

**9. saveDevice**

```javascript
const device = device;
deviceService.saveDevice(device).subscribe(savedDevice => {
  console.log('Save Device: savedDevice');
});
```

**10. saveDeviceWithCredentials**

```javascript
const device = device;
const credentials = credentials;
deviceService.saveDeviceWithCredentials(device, credentials).subscribe(savedDeviceWithCredentials => {
  console.log('Save Device With Credentials: savedDeviceWithCredentials');
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes().subscribe(devicetypes => {
  console.log('Get Device Types: devicetypes');
});
```

**12. getDeviceCredentials**

```javascript
deviceService.getDeviceCredentials('your-device-id', false).subscribe(devicecredentials => {
  console.log('Get Device Credentials: devicecredentials');
});
```

**13. saveDeviceCredentials**

```javascript
const deviceCredentials = deviceCredentials;
deviceService.saveDeviceCredentials(deviceCredentials).subscribe(savedDeviceCredentials => {
  console.log('Save Device Credentials: savedDeviceCredentials');
});
```

**14. makeDevicePublic**

```javascript
deviceService.makeDevicePublic('your-device-id').subscribe(result => {
  console.log('Make Device Public: result');
});
```

**15. assignDeviceToCustomer**

```javascript
deviceService.assignDeviceToCustomer('your-customer-id', 'your-device-id').subscribe(result => {
  console.log('Assign Device To Customer: result');
});
```

**16. sendOneWayRpcCommand**

```javascript
deviceService.sendOneWayRpcCommand('your-device-id', { method: 'getMethod', params: {} }).subscribe(result => {
  console.log('Send One Way Rpc Command: result');
});
```

**17. sendTwoWayRpcCommand**

```javascript
deviceService.sendTwoWayRpcCommand('your-device-id', { method: 'getMethod', params: {} }).subscribe(result => {
  console.log('Send Two Way Rpc Command: result');
});
```

**18. getPersistedRpc**

```javascript
deviceService.getPersistedRpc('your-rpc-id').subscribe(persistedRpc => {
  console.log('Get Persisted Rpc: persistedRpc');
});
```

**19. getPersistedRpcRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const rpcStatus = rpcStatus;
deviceService.getPersistedRpcRequests('your-device-id', pageLink, rpcStatus).subscribe(persistedrpcrequests => {
  console.log('Get Persisted Rpc Requests: persistedrpcrequests');
});
```

**20. findByQuery**

```javascript
const query = query;
deviceService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**21. findByName**

```javascript
const deviceName = deviceName;
deviceService.findByName(deviceName).subscribe(entity => {
  console.log('Find By Name: entity');
});
```

**22. claimDevice**

```javascript
const deviceName = deviceName;
const claimRequest = claimRequest;
deviceService.claimDevice(deviceName, claimRequest).subscribe(result => {
  console.log('Claim Device: result');
});
```

**23. assignDeviceToEdge**

```javascript
deviceService.assignDeviceToEdge('your-edge-id', 'your-device-id').subscribe(result => {
  console.log('Assign Device To Edge: result');
});
```

**24. getEdgeDevices**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceService.getEdgeDevices('your-edge-id', pageLink, 'type').subscribe(edgedevices => {
  console.log('Get Edge Devices: edgedevices');
});
```

**25. bulkImportDevices**

```javascript
const entitiesData = entitiesData;
deviceService.bulkImportDevices(entitiesData).subscribe(result => {
  console.log('Bulk Import Devices: result');
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
deviceService.getDevicePublishTelemetryCommands('your-device-id').subscribe(devicepublishtelemetrycommands => {
  console.log('Get Device Publish Telemetry Commands:devicepublishtelemetrycommands');
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
deviceService.downloadGatewayDockerComposeFile('your-device-id').subscribe(result => {
  console.log('Download Gateway Docker Compose File:result');
});
```

**28. rebootDevice**

```javascript
deviceService.rebootDevice('your-device-id', true).subscribe(result => {
  console.log('Reboot Device: result');
});
```

**29. rebootTrigger**

```javascript
const resourcePath = resourcePath;
deviceService.rebootTrigger('your-device-id', resourcePath).subscribe(result => {
  console.log('Reboot Trigger: result');
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
const domain = domain;
domainService.saveDomain(domain, 'your-id').subscribe(savedDomain => {
  console.log('Save Domain: savedDomain');
});
```

**2. updateOauth2Clients**

```javascript
domainService.updateOauth2Clients('your-id', 'your-id').subscribe(result => {
  console.log('Update Oauth Clients: result');
});
```

**3. getTenantDomainInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domainService.getTenantDomainInfos(pageLink).subscribe(tenantdomaininfos => {
  console.log('Get Tenant Domain Infos: tenantdomaininfos');
});
```

**4. getDomainInfoById**

```javascript
domainService.getDomainInfoById('your-id').subscribe(domainInfoById => {
  console.log('Get Domain Info By Id: domainInfoById');
});
```

**5. deleteDomain**

```javascript
domainService.deleteDomain('your-id').subscribe(result => {
  console.log('Delete Domain: result');
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
edgeService.getEdges('your-id').subscribe(edges => {
  console.log('Get Edges: edges');
});
```

**2. getEdge**

```javascript
edgeService.getEdge('your-edge-id').subscribe(edge => {
  console.log('Get Edge: edge');
});
```

**3. getEdgeInfo**

```javascript
edgeService.getEdgeInfo('your-edge-id').subscribe(edgeInfo => {
  console.log('Get Edge Info: edgeInfo');
});
```

**4. saveEdge**

```javascript
const edge = edge;
edgeService.saveEdge(edge).subscribe(savedEdge => {
  console.log('Save Edge: savedEdge');
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes().subscribe(edgetypes => {
  console.log('Get Edge Types: edgetypes');
});
```

**6. getCustomerEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getCustomerEdgeInfos('your-customer-id', pageLink, 'type').subscribe(customeredgeinfos => {
  console.log('Get Customer Edge Infos: customeredgeinfos');
});
```

**7. assignEdgeToCustomer**

```javascript
edgeService.assignEdgeToCustomer('your-customer-id', 'your-edge-id').subscribe(result => {
  console.log('Assign Edge To Customer: result');
});
```

**8. makeEdgePublic**

```javascript
edgeService.makeEdgePublic('your-edge-id').subscribe(result => {
  console.log('Make Edge Public: result');
});
```

**9. getTenantEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getTenantEdgeInfos(pageLink, 'type').subscribe(tenantedgeinfos => {
  console.log('Get Tenant Edge Infos: tenantedgeinfos');
});
```

**10. findByQuery**

```javascript
const query = query;
edgeService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**11. getEdgeEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
edgeService.getEdgeEvents('your-entity-id', pageLink).subscribe(edgeevents => {
  console.log('Get Edge Events: edgeevents');
});
```

**12. findMissingToRelatedRuleChains**

```javascript
edgeService.findMissingToRelatedRuleChains('your-edge-id').subscribe(ruleChains => {
  console.log('Find Missing To Related Rule Chains:ruleChains');
});
```

**13. findByName**

```javascript
const edgeName = edgeName;
edgeService.findByName(edgeName).subscribe(entity => {
  console.log('Find By Name: entity');
});
```

**14. bulkImportEdges**

```javascript
const entitiesData = entitiesData;
edgeService.bulkImportEdges(entitiesData).subscribe(result => {
  console.log('Bulk Import Edges: result');
});
```

**15. getEdgeInstallInstructions**

```javascript
const method = method;
edgeService.getEdgeInstallInstructions('your-edge-id', method).subscribe(edgeinstallinstructions => {
  console.log('Get Edge Install Instructions: edgeinstallinstructions');
});
```

**16. getEdgeUpgradeInstructions**

```javascript
const edgeVersion = edgeVersion;
const method = method;
edgeService.getEdgeUpgradeInstructions(edgeVersion, method).subscribe(edgeupgradeinstructions => {
  console.log('Get Edge Upgrade Instructions: edgeupgradeinstructions');
});
```

**17. isEdgeUpgradeAvailable**

```javascript
edgeService.isEdgeUpgradeAvailable('your-edge-id').subscribe(result => {
  console.log('Is Edge Upgrade Available: result');
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
entitiesVersionControlService.clearBranchList().subscribe(result => {
  console.log('Clear Branch List: result');
});
```

**2. listBranches**

```javascript
entitiesVersionControlService.listBranches().subscribe(results => {
  console.log('List Branches: results');
});
```

**3. getEntityDataInfo**

```javascript
entitiesVersionControlService.getEntityDataInfo('your-id', 'your-id').subscribe(entityDataInfo => {
  console.log('Get Entity Data Info: entityDataInfo');
});
```

**4. saveEntitiesVersion**

```javascript
const request = request;
entitiesVersionControlService.saveEntitiesVersion(request).subscribe(savedEntitiesVersion => {
  console.log('Save Entities Version: savedEntitiesVersion');
});
```

**5. getVersionCreateRequestStatus**

```javascript
entitiesVersionControlService.getVersionCreateRequestStatus('your-id').subscribe(versioncreaterequeststatus => {
  console.log('Get Version Create Request Status:versioncreaterequeststatus');
});
```

**6. listEntityVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = branch;
entitiesVersionControlService.listEntityVersions(pageLink, branch, 'your-id').subscribe(results => {
  console.log('List Entity Versions: results');
});
```

**7. listEntityTypeVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = branch;
entitiesVersionControlService.listEntityTypeVersions(pageLink, branch, 'type').subscribe(results => {
  console.log('List Entity Type Versions: results');
});
```

**8. listVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = branch;
entitiesVersionControlService.listVersions(pageLink, branch).subscribe(results => {
  console.log('List Versions: results');
});
```

**9. loadEntitiesVersion**

```javascript
const request = request;
entitiesVersionControlService.loadEntitiesVersion(request).subscribe(result => {
  console.log('Load Entities Version: result');
});
```

**10. getVersionLoadRequestStatus**

```javascript
entitiesVersionControlService.getVersionLoadRequestStatus('your-id').subscribe(versionloadrequeststatus => {
  console.log('Get Version Load Request Status:versionloadrequeststatus');
});
```

**11. compareEntityDataToVersion**

```javascript
entitiesVersionControlService.compareEntityDataToVersion('your-entity-id', 'your-id').subscribe(result => {
  console.log('Compare Entity Data To Version:result');
});
```

**12. entityLoadErrorToMessage**

```javascript
const entityLoadError = entityLoadError;
entitiesVersionControlService.entityLoadErrorToMessage(entityLoadError).subscribe(result => {
  console.log('Entity Load Error To Message: result');
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
const relation = relation;
entityRelationService.saveRelation(relation).subscribe(savedRelation => {
  console.log('Save Relation: savedRelation');
});
```

**2. getRelation**

```javascript
entityRelationService.getRelation('your-id', 'type', 'your-id').subscribe(relation => {
  console.log('Get Relation: relation');
});
```

**3. findByFrom**

```javascript
entityRelationService.findByFrom('your-id').subscribe(relations => {
  console.log('Find By From: relations');
});
```

**4. findInfoByFrom**

```javascript
entityRelationService.findInfoByFrom('your-id').subscribe(relations => {
  console.log('Find Info By From: relations');
});
```

**5. findByFromAndType**

```javascript
entityRelationService.findByFromAndType('your-id', 'type').subscribe(relations => {
  console.log('Find By From And Type: relations');
});
```

**6. findByTo**

```javascript
entityRelationService.findByTo('your-id').subscribe(relations => {
  console.log('Find By To: relations');
});
```

**7. findInfoByTo**

```javascript
entityRelationService.findInfoByTo('your-id').subscribe(relations => {
  console.log('Find Info By To: relations');
});
```

**8. findByToAndType**

```javascript
entityRelationService.findByToAndType('your-id', 'type').subscribe(relations => {
  console.log('Find By To And Type: relations');
});
```

**9. findByQuery**

```javascript
const query = query;
entityRelationService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**10. findInfoByQuery**

```javascript
const query = query;
entityRelationService.findInfoByQuery(query).subscribe(relations => {
  console.log('Find Info By Query: relations');
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
entityService.getEntityObservable('type', 'your-entity-id').subscribe(entityObservable => {
  console.log('Get Entity Observable: entityObservable');
});
```

**2. getEntity**

```javascript
entityService.getEntity('type', 'your-entity-id').subscribe(entity => {
  console.log('Get Entity: entity');
});
```

**3. getEntitiesObservable**

```javascript
entityService.getEntitiesObservable('type', 'your-id').subscribe(entitiesObservable => {
  console.log('Get Entities Observable: entitiesObservable');
});
```

**4. getEntities**

```javascript
entityService.getEntities('type', 'your-id').subscribe(entities => {
  console.log('Get Entities: entities');
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(singleTenantByPageLinkObservable => {
  console.log('Get Single Tenant By Page Link Observable:singleTenantByPageLinkObservable');
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getSingleCustomerByPageLinkObservable(pageLink).subscribe(singleCustomerByPageLinkObservable => {
  console.log('Get Single Customer By Page Link Observable:singleCustomerByPageLinkObservable');
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getEntitiesByPageLinkObservable('type', pageLink, 'type').subscribe(entitiesByPageLinkObservable => {
  console.log('Get Entities By Page Link Observable:entitiesByPageLinkObservable');
});
```

**8. getEntitiesByPageLink**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getEntitiesByPageLink('type', pageLink, 'type').subscribe(entitiesByPageLink => {
  console.log('Get Entities By Page Link: entitiesByPageLink');
});
```

**9. getEntitiesByNameFilter**

```javascript
const entityNameFilter = entityNameFilter;
const pageSize = pageSize;
entityService.getEntitiesByNameFilter('type', entityNameFilter, pageSize, 'type').subscribe(entitiesByNameFilter => {
  console.log('Get Entities By Name Filter: entitiesByNameFilter');
});
```

**10. findEntityDataByQuery**

```javascript
const query = query;
entityService.findEntityDataByQuery(query).subscribe(results => {
  console.log('Find Entity Data By Query: results');
});
```

**11. findEntityKeysByQuery**

```javascript
const query = query;
entityService.findEntityKeysByQuery(query, 'SERVER_SCOPE').subscribe(results => {
  console.log('Find Entity Keys By Query: results');
});
```

**12. findAlarmDataByQuery**

```javascript
const query = query;
entityService.findAlarmDataByQuery(query).subscribe(results => {
  console.log('Find Alarm Data By Query: results');
});
```

**13. findEntityInfosByFilterAndName**

```javascript
const filter = filter;
entityService.findEntityInfosByFilterAndName(filter, 'searchText').subscribe(results => {
  console.log('Find Entity Infos By Filter And Name:results');
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
const filter = filter;
entityService.findSingleEntityInfoByEntityFilter(filter).subscribe(results => {
  console.log('Find Single Entity Info By Entity Filter:results');
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
entityService.getAliasFilterTypesByEntityTypes('type').subscribe(aliasfiltertypesbyentitytypes => {
  console.log('Get Alias Filter Types By Entity Types:aliasfiltertypesbyentitytypes');
});
```

**16. filterAliasByEntityTypes**

```javascript
const entityAlias = entityAlias;
entityService.filterAliasByEntityTypes(entityAlias, 'type').subscribe(result => {
  console.log('Filter Alias By Entity Types: result');
});
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
entityService.filterAliasFilterTypeByEntityTypes('type', 'type').subscribe(result => {
  console.log('Filter Alias Filter Type By Entity Types:result');
});
```

**18. filterAliasFilterTypeByEntityType**

```javascript
entityService.filterAliasFilterTypeByEntityType('type', 'type').subscribe(result => {
  console.log('Filter Alias Filter Type By Entity Type:result');
});
```

**19. prepareAllowedEntityTypesList**

```javascript
entityService.prepareAllowedEntityTypesList('type', 'type').subscribe(result => {
  console.log('Prepare Allowed Entity Types List:result');
});
```

**20. getEntityFieldKeys**

```javascript
entityService.getEntityFieldKeys('type', 'searchText').subscribe(entityfieldkeys => {
  console.log('Get Entity Field Keys: entityfieldkeys');
});
```

**21. getAlarmKeys**

```javascript
entityService.getAlarmKeys('searchText').subscribe(alarmkeys => {
  console.log('Get Alarm Keys: alarmkeys');
});
```

**22. getEntityKeys**

```javascript
const query = query;
entityService.getEntityKeys('your-entity-id', query, 'type').subscribe(entitykeys => {
  console.log('Get Entity Keys: entitykeys');
});
```

**23. getEntityKeysByEntityFilter**

```javascript
const filter = filter;
entityService.getEntityKeysByEntityFilter(filter, 'type', 'type').subscribe(entityKeysByEntityFilter => {
  console.log('Get Entity Keys By Entity Filter:entityKeysByEntityFilter');
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
const filter = filter;
entityService.getEntityKeysByEntityFilterAndScope(filter, 'type', 'type', 'SERVER_SCOPE').subscribe(entityKeysByEntityFilterAndScope => {
  console.log('Get Entity Keys By Entity Filter And Scope:entityKeysByEntityFilterAndScope');
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
const subscriptionsInfo = subscriptionsInfo;
entityService.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo).subscribe(result => {
  console.log('Create Datasources From Subscriptions Info:result');
});
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
const subscriptionInfo = subscriptionInfo;
entityService.createAlarmSourceFromSubscriptionInfo(subscriptionInfo).subscribe(result => {
  console.log('Create Alarm Source From Subscription Info:result');
});
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getAssignedToEdgeEntitiesByType('your-edge-id', 'type', pageLink).subscribe(assignedToEdgeEntitiesByType => {
  console.log('Get Assigned To Edge Entities By Type:assignedToEdgeEntitiesByType');
});
```

**28. case**

```javascript
entityService.case().subscribe(result => {
  console.log('Case: result');
});
```

**29. getEntitySubtypesObservable**

```javascript
entityService.getEntitySubtypesObservable('type').subscribe(entitySubtypesObservable => {
  console.log('Get Entity Subtypes Observable:entitySubtypesObservable');
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
entityViewService.getTenantEntityViewInfos(pageLink, 'type').subscribe(tenantentityviewinfos => {
  console.log('Get Tenant Entity View Infos: tenantentityviewinfos');
});
```

**2. getCustomerEntityViewInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityViewService.getCustomerEntityViewInfos('your-customer-id', pageLink, 'type').subscribe(customerentityviewinfos => {
  console.log('Get Customer Entity View Infos:customerentityviewinfos');
});
```

**3. getEntityView**

```javascript
entityViewService.getEntityView('your-entity-view-id').subscribe(entityView => {
  console.log('Get Entity View: entityView');
});
```

**4. getEntityViews**

```javascript
entityViewService.getEntityViews('your-id').subscribe(entityviews => {
  console.log('Get Entity Views: entityviews');
});
```

**5. getEntityViewInfo**

```javascript
entityViewService.getEntityViewInfo('your-entity-view-id').subscribe(entityViewInfo => {
  console.log('Get Entity View Info: entityViewInfo');
});
```

**6. saveEntityView**

```javascript
const entityView = entityView;
entityViewService.saveEntityView(entityView).subscribe(savedEntityView => {
  console.log('Save Entity View: savedEntityView');
});
```

**7. getEntityViewTypes**

```javascript
entityViewService.getEntityViewTypes().subscribe(entityviewtypes => {
  console.log('Get Entity View Types: entityviewtypes');
});
```

**8. makeEntityViewPublic**

```javascript
entityViewService.makeEntityViewPublic('your-entity-view-id').subscribe(result => {
  console.log('Make Entity View Public: result');
});
```

**9. assignEntityViewToCustomer**

```javascript
entityViewService.assignEntityViewToCustomer('your-customer-id', 'your-entity-view-id').subscribe(result => {
  console.log('Assign Entity View To Customer:result');
});
```

**10. findByQuery**

```javascript
const query = query;
entityViewService.findByQuery(query).subscribe(results => {
  console.log('Find By Query: results');
});
```

**11. assignEntityViewToEdge**

```javascript
entityViewService.assignEntityViewToEdge('your-edge-id', 'your-entity-view-id').subscribe(result => {
  console.log('Assign Entity View To Edge: result');
});
```

**12. getEdgeEntityViews**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityViewService.getEdgeEntityViews('your-edge-id', pageLink, 'type').subscribe(edgeentityviews => {
  console.log('Get Edge Entity Views: edgeentityviews');
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
eventService.getEvents('your-entity-id', 'type', 'your-tenant-id', pageLink).subscribe(events => {
  console.log('Get Events: events');
});
```

**2. getFilterEvents**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const filters = filters;
eventService.getFilterEvents('your-entity-id', 'type', 'your-tenant-id', filters, pageLink).subscribe(filterevents => {
  console.log('Get Filter Events: filterevents');
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
  console.log('Get Git Hub Star: gitHubStar');
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
const file = file;
const title = title;
imageService.uploadImage(file, title, 'type').subscribe(result => {
  console.log('Upload Image: result');
});
```

**2. updateImage**

```javascript
const key = key;
const file = file;
imageService.updateImage('type', key, file).subscribe(result => {
  console.log('Update Image: result');
});
```

**3. updateImageInfo**

```javascript
const imageInfo = imageInfo;
imageService.updateImageInfo(imageInfo).subscribe(result => {
  console.log('Update Image Info: result');
});
```

**4. updateImagePublicStatus**

```javascript
const imageInfo = imageInfo;
imageService.updateImagePublicStatus(imageInfo, true).subscribe(result => {
  console.log('Update Image Public Status: result');
});
```

**5. getImages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
imageService.getImages(pageLink, 'type').subscribe(images => {
  console.log('Get Images: images');
});
```

**6. getImageInfo**

```javascript
const key = key;
imageService.getImageInfo('type', key).subscribe(imageInfo => {
  console.log('Get Image Info: imageInfo');
});
```

**7. getImageDataUrl**

```javascript
const imageUrl = imageUrl;
imageService.getImageDataUrl(imageUrl).subscribe(imageDataUrl => {
  console.log('Get Image Data Url: imageDataUrl');
});
```

**8. loadImageDataUrl**

```javascript
const imageLink = imageLink;
imageService.loadImageDataUrl(imageLink).subscribe(result => {
  console.log('Load Image Data Url: result');
});
```

**9. getImageString**

```javascript
const imageUrl = imageUrl;
imageService.getImageString(imageUrl).subscribe(imageString => {
  console.log('Get Image String: imageString');
});
```

**10. resolveImageUrl**

```javascript
const imageUrl = imageUrl;
imageService.resolveImageUrl(imageUrl).subscribe(result => {
  console.log('Resolve Image Url: result');
});
```

**11. downloadImage**

```javascript
const key = key;
imageService.downloadImage('type', key).subscribe(result => {
  console.log('Download Image: result');
});
```

**12. exportImage**

```javascript
const key = key;
imageService.exportImage('type', key).subscribe(exported => {
  console.log('Export Image: exported');
});
```

**13. importImage**

```javascript
const imageData = imageData;
imageService.importImage(imageData).subscribe(result => {
  console.log('Import Image: result');
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
const mobileApp = mobileApp;
mobileAppService.saveMobileApp(mobileApp).subscribe(savedMobileApp => {
  console.log('Save Mobile App: savedMobileApp');
});
```

**2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppInfos(pageLink, 'type').subscribe(tenantmobileappinfos => {
  console.log('Get Tenant Mobile App Infos: tenantmobileappinfos');
});
```

**3. getMobileAppInfoById**

```javascript
mobileAppService.getMobileAppInfoById('your-id').subscribe(mobileAppInfoById => {
  console.log('Get Mobile App Info By Id: mobileAppInfoById');
});
```

**4. deleteMobileApp**

```javascript
mobileAppService.deleteMobileApp('your-id').subscribe(result => {
  console.log('Delete Mobile App: result');
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(tenantmobileappbundleinfos => {
  console.log('Get Tenant Mobile App Bundle Infos:tenantmobileappbundleinfos');
});
```

**6. getMobileAppBundleInfoById**

```javascript
mobileAppService.getMobileAppBundleInfoById('your-id').subscribe(mobileAppBundleInfoById => {
  console.log('Get Mobile App Bundle Info By Id:mobileAppBundleInfoById');
});
```

**7. deleteMobileAppBundle**

```javascript
mobileAppService.deleteMobileAppBundle('your-id').subscribe(result => {
  console.log('Delete Mobile App Bundle: result');
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
mobileApplicationService.getMobileAppSettings().subscribe(mobileappsettings => {
  console.log('Get Mobile App Settings: mobileappsettings');
});
```

**2. saveMobileAppSettings**

```javascript
const mobileAppSettings = mobileAppSettings;
mobileApplicationService.saveMobileAppSettings(mobileAppSettings).subscribe(savedMobileAppSettings => {
  console.log('Save Mobile App Settings: savedMobileAppSettings');
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(mobileAppDeepLink => {
  console.log('Get Mobile App Deep Link: mobileAppDeepLink');
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
  console.log('Get Notifications: notifications');
});
```

**2. deleteNotification**

```javascript
notificationService.deleteNotification('your-id').subscribe(result => {
  console.log('Delete Notification: result');
});
```

**3. markNotificationAsRead**

```javascript
notificationService.markNotificationAsRead('your-id').subscribe(result => {
  console.log('Mark Notification As Read: result');
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('Mark All Notifications As Read:result');
});
```

**5. createNotificationRequest**

```javascript
const notification = notification;
notificationService.createNotificationRequest(notification).subscribe(result => {
  console.log('Create Notification Request: result');
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
notificationService.sendEntitiesLimitIncreaseRequest('type').subscribe(result => {
  console.log('Send Entities Limit Increase Request:result');
});
```

**7. getNotificationRequestById**

```javascript
notificationService.getNotificationRequestById('your-id').subscribe(notificationRequestById => {
  console.log('Get Notification Request By Id:notificationRequestById');
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(availabledeliverymethods => {
  console.log('Get Available Delivery Methods:availabledeliverymethods');
});
```

**9. deleteNotificationRequest**

```javascript
notificationService.deleteNotificationRequest('your-id').subscribe(result => {
  console.log('Delete Notification Request: result');
});
```

**10. getNotificationRequestPreview**

```javascript
const notification = notification;
notificationService.getNotificationRequestPreview(notification).subscribe(notificationRequestPreview => {
  console.log('Get Notification Request Preview:notificationRequestPreview');
});
```

**11. getNotificationRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRequests(pageLink).subscribe(notificationrequests => {
  console.log('Get Notification Requests: notificationrequests');
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(notificationsettings => {
  console.log('Get Notification Settings: notificationsettings');
});
```

**13. saveNotificationSettings**

```javascript
const notificationSettings = notificationSettings;
notificationService.saveNotificationSettings(notificationSettings).subscribe(savedNotificationSettings => {
  console.log('Save Notification Settings: savedNotificationSettings');
});
```

**14. listSlackConversations**

```javascript
const token = token;
notificationService.listSlackConversations('type', token).subscribe(results => {
  console.log('List Slack Conversations: results');
});
```

**15. saveNotificationRule**

```javascript
const notificationRule = notificationRule;
notificationService.saveNotificationRule(notificationRule).subscribe(savedNotificationRule => {
  console.log('Save Notification Rule: savedNotificationRule');
});
```

**16. getNotificationRuleById**

```javascript
notificationService.getNotificationRuleById('your-id').subscribe(notificationRuleById => {
  console.log('Get Notification Rule By Id: notificationRuleById');
});
```

**17. deleteNotificationRule**

```javascript
notificationService.deleteNotificationRule('your-id').subscribe(result => {
  console.log('Delete Notification Rule: result');
});
```

**18. getNotificationRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRules(pageLink).subscribe(notificationrules => {
  console.log('Get Notification Rules: notificationrules');
});
```

**19. saveNotificationTarget**

```javascript
const notificationTarget = notificationTarget;
notificationService.saveNotificationTarget(notificationTarget).subscribe(savedNotificationTarget => {
  console.log('Save Notification Target: savedNotificationTarget');
});
```

**20. getNotificationTargetById**

```javascript
notificationService.getNotificationTargetById('your-id').subscribe(notificationTargetById => {
  console.log('Get Notification Target By Id: notificationTargetById');
});
```

**21. deleteNotificationTarget**

```javascript
notificationService.deleteNotificationTarget('your-id').subscribe(result => {
  console.log('Delete Notification Target: result');
});
```

**22. getNotificationTargetsByIds**

```javascript
notificationService.getNotificationTargetsByIds('your-id').subscribe(notificationtargetsbyids => {
  console.log('Get Notification Targets By Ids:notificationtargetsbyids');
});
```

**23. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTargets(pageLink, 'type').subscribe(notificationtargets => {
  console.log('Get Notification Targets: notificationtargets');
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const notificationTarget = notificationTarget;
notificationService.getRecipientsForNotificationTargetConfig(notificationTarget, pageLink).subscribe(recipientsForNotificationTargetConfig => {
  console.log('Get Recipients For Notification Target Config:recipientsForNotificationTargetConfig');
});
```

**25. saveNotificationTemplate**

```javascript
const notificationTarget = notificationTarget;
notificationService.saveNotificationTemplate(notificationTarget).subscribe(savedNotificationTemplate => {
  console.log('Save Notification Template: savedNotificationTemplate');
});
```

**26. getNotificationTemplateById**

```javascript
notificationService.getNotificationTemplateById('your-id').subscribe(notificationTemplateById => {
  console.log('Get Notification Template By Id:notificationTemplateById');
});
```

**27. deleteNotificationTemplate**

```javascript
notificationService.deleteNotificationTemplate('your-id').subscribe(result => {
  console.log('Delete Notification Template: result');
});
```

**28. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationTemplates(pageLink, 'type').subscribe(notificationtemplates => {
  console.log('Get Notification Templates: notificationtemplates');
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(notificationusersettings => {
  console.log('Get Notification User Settings:notificationusersettings');
});
```

**30. saveNotificationUserSettings**

```javascript
const settings = settings;
notificationService.saveNotificationUserSettings(settings).subscribe(savedNotificationUserSettings => {
  console.log('Save Notification User Settings:savedNotificationUserSettings');
});
```

---

### **O AUTH SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template().subscribe(oAuth2Template => {
  console.log('Get O Auth Template: oAuth2Template');
});
```

**2. saveOAuth2Client**

```javascript
const oAuth2Client = oAuth2Client;
oAuth2Service.saveOAuth2Client(oAuth2Client).subscribe(savedOAuth2Client => {
  console.log('Save O Auth Client: savedOAuth2Client');
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(results => {
  console.log('Find Tenant O Auth Client Infos:results');
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
oAuth2Service.findTenantOAuth2ClientInfosByIds('your-id').subscribe(results => {
  console.log('Find Tenant O Auth Client Infos By Ids:results');
});
```

**5. getOAuth2ClientById**

```javascript
oAuth2Service.getOAuth2ClientById('your-id').subscribe(oAuth2ClientById => {
  console.log('Get O Auth Client By Id: oAuth2ClientById');
});
```

**6. deleteOauth2Client**

```javascript
oAuth2Service.deleteOauth2Client('your-id').subscribe(result => {
  console.log('Delete Oauth Client: result');
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(loginProcessingUrl => {
  console.log('Get Login Processing Url: loginProcessingUrl');
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
otaPackageService.getOtaPackages(pageLink).subscribe(otapackages => {
  console.log('Get Ota Packages: otapackages');
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, 'your-device-profile-id', 'type').subscribe(otaPackagesInfoByDeviceProfileId => {
  console.log('Get Ota Packages Info By Device Profile Id:otaPackagesInfoByDeviceProfileId');
});
```

**3. getOtaPackage**

```javascript
otaPackageService.getOtaPackage('your-ota-package-id').subscribe(otaPackage => {
  console.log('Get Ota Package: otaPackage');
});
```

**4. getOtaPackageInfo**

```javascript
otaPackageService.getOtaPackageInfo('your-ota-package-id').subscribe(otaPackageInfo => {
  console.log('Get Ota Package Info: otaPackageInfo');
});
```

**5. downloadOtaPackage**

```javascript
otaPackageService.downloadOtaPackage('your-ota-package-id').subscribe(result => {
  console.log('Download Ota Package: result');
});
```

**6. saveOtaPackage**

```javascript
const otaPackage = otaPackage;
otaPackageService.saveOtaPackage(otaPackage).subscribe(savedOtaPackage => {
  console.log('Save Ota Package: savedOtaPackage');
});
```

**7. saveOtaPackageInfo**

```javascript
const otaPackageInfo = otaPackageInfo;
otaPackageService.saveOtaPackageInfo(otaPackageInfo).subscribe(savedOtaPackageInfo => {
  console.log('Save Ota Package Info: savedOtaPackageInfo');
});
```

**8. uploadOtaPackageFile**

```javascript
const file = file;
otaPackageService.uploadOtaPackageFile('your-ota-package-id', file, 'SHA256', 'checksum').subscribe(result => {
  console.log('Upload Ota Package File: result');
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
otaPackageService.countUpdateDeviceAfterChangePackage('type', 'your-entity-id').subscribe(count => {
  console.log('Count Update Device After Change Package:count');
});
```

**10. confirmDialogUpdatePackage**

```javascript
const entity = entity;
const originEntity = originEntity;
otaPackageService.confirmDialogUpdatePackage(entity, originEntity).subscribe(result => {
  console.log('Confirm Dialog Update Package: result');
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
  console.log('Get Queue By Id: queueById');
});
```

**2. getQueueByName**

```javascript
const queueName = queueName;
queueService.getQueueByName(queueName).subscribe(queueByName => {
  console.log('Get Queue By Name: queueByName');
});
```

**3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getTenantQueuesByServiceType(pageLink, 'type').subscribe(tenantQueuesByServiceType => {
  console.log('Get Tenant Queues By Service Type:tenantQueuesByServiceType');
});
```

**4. saveQueue**

```javascript
const queue = queue;
queueService.saveQueue(queue, 'type').subscribe(savedQueue => {
  console.log('Save Queue: savedQueue');
});
```

**5. getQueueStatistics**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getQueueStatistics(pageLink).subscribe(queuestatistics => {
  console.log('Get Queue Statistics: queuestatistics');
});
```

**6. getQueueStatisticsById**

```javascript
queueService.getQueueStatisticsById('your-id').subscribe(queueStatisticsById => {
  console.log('Get Queue Statistics By Id: queueStatisticsById');
});
```

**7. getQueueStatisticsByIds**

```javascript
queueService.getQueueStatisticsByIds('your-id').subscribe(queuestatisticsbyids => {
  console.log('Get Queue Statistics By Ids: queuestatisticsbyids');
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
resourceService.getResources(pageLink, 'type', 'type').subscribe(resources => {
  console.log('Get Resources: resources');
});
```

**2. getTenantResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
resourceService.getTenantResources(pageLink).subscribe(tenantresources => {
  console.log('Get Tenant Resources: tenantresources');
});
```

**3. getResource**

```javascript
resourceService.getResource('your-resource-id').subscribe(resource => {
  console.log('Get Resource: resource');
});
```

**4. getResourceInfoById**

```javascript
resourceService.getResourceInfoById('your-resource-id').subscribe(resourceInfoById => {
  console.log('Get Resource Info By Id: resourceInfoById');
});
```

**5. getResourceInfo**

```javascript
const key = key;
resourceService.getResourceInfo('type', 'SERVER_SCOPE', key).subscribe(resourceInfo => {
  console.log('Get Resource Info: resourceInfo');
});
```

**6. downloadResource**

```javascript
resourceService.downloadResource('your-resource-id').subscribe(result => {
  console.log('Download Resource: result');
});
```

**7. saveResources**

```javascript
const resources = resources;
resourceService.saveResources(resources).subscribe(savedResources => {
  console.log('Save Resources: savedResources');
});
```

**8. saveResource**

```javascript
const resource = resource;
resourceService.saveResource(resource).subscribe(savedResource => {
  console.log('Save Resource: savedResource');
});
```

**9. uploadResources**

```javascript
const resources = resources;
resourceService.uploadResources(resources).subscribe(result => {
  console.log('Upload Resources: result');
});
```

**10. uploadResource**

```javascript
const resource = resource;
resourceService.uploadResource(resource).subscribe(result => {
  console.log('Upload Resource: result');
});
```

**11. updatedResourceInfo**

```javascript
const updatedResources = updatedResources;
resourceService.updatedResourceInfo('your-resource-id', updatedResources).subscribe(result => {
  console.log('Updated Resource Info: result');
});
```

**12. updatedResourceData**

```javascript
const data = data;
resourceService.updatedResourceData('your-resource-id', data).subscribe(result => {
  console.log('Updated Resource Data: result');
});
```

**13. getResourcesByIds**

```javascript
resourceService.getResourcesByIds('your-id').subscribe(resourcesbyids => {
  console.log('Get Resources By Ids: resourcesbyids');
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
ruleChainService.getRuleChains(pageLink, 'type').subscribe(rulechains => {
  console.log('Get Rule Chains: rulechains');
});
```

**2. getRuleChainsByIds**

```javascript
ruleChainService.getRuleChainsByIds('your-id').subscribe(rulechainsbyids => {
  console.log('Get Rule Chains By Ids: rulechainsbyids');
});
```

**3. getRuleChain**

```javascript
ruleChainService.getRuleChain('your-rule-chain-id').subscribe(ruleChain => {
  console.log('Get Rule Chain: ruleChain');
});
```

**4. getRuleChainOutputLabels**

```javascript
ruleChainService.getRuleChainOutputLabels('your-rule-chain-id').subscribe(rulechainoutputlabels => {
  console.log('Get Rule Chain Output Labels: rulechainoutputlabels');
});
```

**5. createDefaultRuleChain**

```javascript
const ruleChainName = ruleChainName;
ruleChainService.createDefaultRuleChain(ruleChainName).subscribe(result => {
  console.log('Create Default Rule Chain: result');
});
```

**6. saveRuleChain**

```javascript
const ruleChain = ruleChain;
ruleChainService.saveRuleChain(ruleChain).subscribe(savedRuleChain => {
  console.log('Save Rule Chain: savedRuleChain');
});
```

**7. setRootRuleChain**

```javascript
ruleChainService.setRootRuleChain('your-rule-chain-id').subscribe(result => {
  console.log('Set Root Rule Chain: result');
});
```

**8. getRuleChainMetadata**

```javascript
ruleChainService.getRuleChainMetadata('your-rule-chain-id').subscribe(ruleChainMetadata => {
  console.log('Get Rule Chain Metadata: ruleChainMetadata');
});
```

**9. saveRuleChainMetadata**

```javascript
const ruleChainMetaData = ruleChainMetaData;
ruleChainService.saveRuleChainMetadata(ruleChainMetaData).subscribe(savedRuleChainMetadata => {
  console.log('Save Rule Chain Metadata: savedRuleChainMetadata');
});
```

**10. getRuleNodeComponents**

```javascript
const modulesMap = modulesMap;
ruleChainService.getRuleNodeComponents(modulesMap, 'type').subscribe(rulenodecomponents => {
  console.log('Get Rule Node Components: rulenodecomponents');
});
```

**11. getRuleNodeConfigComponent**

```javascript
const directive = directive;
ruleChainService.getRuleNodeConfigComponent(directive).subscribe(ruleNodeConfigComponent => {
  console.log('Get Rule Node Config Component:ruleNodeConfigComponent');
});
```

**12. getRuleNodeComponentByClazz**

```javascript
const clazz = clazz;
ruleChainService.getRuleNodeComponentByClazz('type', clazz).subscribe(ruleNodeComponentByClazz => {
  console.log('Get Rule Node Component By Clazz:ruleNodeComponentByClazz');
});
```

**13. getRuleNodeSupportedLinks**

```javascript
const component = component;
ruleChainService.getRuleNodeSupportedLinks(component).subscribe(rulenodesupportedlinks => {
  console.log('Get Rule Node Supported Links: rulenodesupportedlinks');
});
```

**14. ruleNodeAllowCustomLinks**

```javascript
const component = component;
ruleChainService.ruleNodeAllowCustomLinks(component).subscribe(result => {
  console.log('Rule Node Allow Custom Links: result');
});
```

**15. ruleNodeSourceRuleChainId**

```javascript
const component = component;
ruleChainService.ruleNodeSourceRuleChainId(component).subscribe(result => {
  console.log('Rule Node Source Rule Chain Id:result');
});
```

**16. getLatestRuleNodeDebugInput**

```javascript
ruleChainService.getLatestRuleNodeDebugInput('your-id').subscribe(latestRuleNodeDebugInput => {
  console.log('Get Latest Rule Node Debug Input:latestRuleNodeDebugInput');
});
```

**17. testScript**

```javascript
const inputParams = inputParams;
const scriptLang = scriptLang;
ruleChainService.testScript(inputParams, scriptLang).subscribe(result => {
  console.log('Test Script: result');
});
```

**18. loadRuleNodeComponents**

```javascript
ruleChainService.loadRuleNodeComponents('type').subscribe(result => {
  console.log('Load Rule Node Components: result');
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
const components = components;
const modulesMap = modulesMap;
ruleChainService.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(result => {
  console.log('Resolve Rule Node Components Ui Resources:result');
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
const component = component;
const modulesMap = modulesMap;
ruleChainService.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(result => {
  console.log('Resolve Rule Node Component Ui Resources:result');
});
```

**21. getEdgeRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getEdgeRuleChains('your-edge-id', pageLink).subscribe(edgerulechains => {
  console.log('Get Edge Rule Chains: edgerulechains');
});
```

**22. assignRuleChainToEdge**

```javascript
ruleChainService.assignRuleChainToEdge('your-edge-id', 'your-rule-chain-id').subscribe(result => {
  console.log('Assign Rule Chain To Edge: result');
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
ruleChainService.setEdgeTemplateRootRuleChain('your-rule-chain-id').subscribe(result => {
  console.log('Set Edge Template Root Rule Chain:result');
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.setAutoAssignToEdgeRuleChain('your-rule-chain-id').subscribe(result => {
  console.log('Set Auto Assign To Edge Rule Chain:result');
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
ruleChainService.unsetAutoAssignToEdgeRuleChain('your-rule-chain-id').subscribe(result => {
  console.log('Unset Auto Assign To Edge Rule Chain:result');
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoassigntoedgerulechains => {
  console.log('Get Auto Assign To Edge Rule Chains:autoassigntoedgerulechains');
});
```

**27. setEdgeRootRuleChain**

```javascript
ruleChainService.setEdgeRootRuleChain('your-edge-id', 'your-rule-chain-id').subscribe(result => {
  console.log('Set Edge Root Rule Chain: result');
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
tenantProfileService.getTenantProfiles(pageLink).subscribe(tenantprofiles => {
  console.log('Get Tenant Profiles: tenantprofiles');
});
```

**2. getTenantProfile**

```javascript
tenantProfileService.getTenantProfile('your-tenant-profile-id').subscribe(tenantProfile => {
  console.log('Get Tenant Profile: tenantProfile');
});
```

**3. saveTenantProfile**

```javascript
const tenantProfile = tenantProfile;
tenantProfileService.saveTenantProfile(tenantProfile).subscribe(savedTenantProfile => {
  console.log('Save Tenant Profile: savedTenantProfile');
});
```

**4. setDefaultTenantProfile**

```javascript
tenantProfileService.setDefaultTenantProfile('your-tenant-profile-id').subscribe(result => {
  console.log('Set Default Tenant Profile: result');
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(defaultTenantProfileInfo => {
  console.log('Get Default Tenant Profile Info:defaultTenantProfileInfo');
});
```

**6. getTenantProfileInfo**

```javascript
tenantProfileService.getTenantProfileInfo('your-tenant-profile-id').subscribe(tenantProfileInfo => {
  console.log('Get Tenant Profile Info: tenantProfileInfo');
});
```

**7. getTenantProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(tenantprofileinfos => {
  console.log('Get Tenant Profile Infos: tenantprofileinfos');
});
```

**8. getTenantProfilesByIds**

```javascript
tenantProfileService.getTenantProfilesByIds('your-id').subscribe(tenantprofilesbyids => {
  console.log('Get Tenant Profiles By Ids: tenantprofilesbyids');
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
  console.log('Get Tenants: tenants');
});
```

**2. getTenantsByIds**

```javascript
tenantService.getTenantsByIds('your-id').subscribe(tenantsbyids => {
  console.log('Get Tenants By Ids: tenantsbyids');
});
```

**3. getTenantInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenantInfos(pageLink).subscribe(tenantinfos => {
  console.log('Get Tenant Infos: tenantinfos');
});
```

**4. getTenant**

```javascript
tenantService.getTenant('your-tenant-id').subscribe(tenant => {
  console.log('Get Tenant: tenant');
});
```

**5. getTenantInfo**

```javascript
tenantService.getTenantInfo('your-tenant-id').subscribe(tenantInfo => {
  console.log('Get Tenant Info: tenantInfo');
});
```

**6. saveTenant**

```javascript
const tenant = tenant;
tenantService.saveTenant(tenant).subscribe(savedTenant => {
  console.log('Save Tenant: savedTenant');
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
trendzSettingsService.getTrendzSettings().subscribe(trendzsettings => {
  console.log('Get Trendz Settings: trendzsettings');
});
```

**2. saveTrendzSettings**

```javascript
const trendzSettings = trendzSettings;
trendzSettingsService.saveTrendzSettings(trendzSettings).subscribe(savedTrendzSettings => {
  console.log('Save Trendz Settings: savedTrendzSettings');
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
twoFactorAuthenticationService.getTwoFaSettings().subscribe(twofasettings => {
  console.log('Get Two Fa Settings: twofasettings');
});
```

**2. saveTwoFaSettings**

```javascript
const settings = settings;
twoFactorAuthenticationService.saveTwoFaSettings(settings).subscribe(savedTwoFaSettings => {
  console.log('Save Two Fa Settings: savedTwoFaSettings');
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(availabletwofaproviders => {
  console.log('Get Available Two Fa Providers:availabletwofaproviders');
});
```

**4. generateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.generateTwoFaAccountConfig('your-id').subscribe(result => {
  console.log('Generate Two Fa Account Config:result');
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(accounttwofasettings => {
  console.log('Get Account Two Fa Settings: accounttwofasettings');
});
```

**6. updateTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.updateTwoFaAccountConfig('your-id', true).subscribe(result => {
  console.log('Update Two Fa Account Config: result');
});
```

**7. submitTwoFaAccountConfig**

```javascript
const authConfig = authConfig;
twoFactorAuthenticationService.submitTwoFaAccountConfig(authConfig).subscribe(result => {
  console.log('Submit Two Fa Account Config: result');
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
const authConfig = authConfig;
const verificationCode = verificationCode;
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(authConfig, verificationCode).subscribe(result => {
  console.log('Verify And Save Two Fa Account Config:result');
});
```

**9. deleteTwoFaAccountConfig**

```javascript
twoFactorAuthenticationService.deleteTwoFaAccountConfig('your-id').subscribe(result => {
  console.log('Delete Two Fa Account Config: result');
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
  console.log('Get Help Base Url: helpBaseUrl');
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
  console.log('Get Usage Info: usageInfo');
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
userService.getUsers(pageLink).subscribe(users => {
  console.log('Get Users: users');
});
```

**2. getTenantAdmins**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getTenantAdmins('your-tenant-id', pageLink).subscribe(tenantadmins => {
  console.log('Get Tenant Admins: tenantadmins');
});
```

**3. getCustomerUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getCustomerUsers('your-customer-id', pageLink).subscribe(customerusers => {
  console.log('Get Customer Users: customerusers');
});
```

**4. getUsersForAssign**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getUsersForAssign('your-alarm-id', pageLink).subscribe(usersForAssign => {
  console.log('Get Users For Assign: usersForAssign');
});
```

**5. getUser**

```javascript
userService.getUser('your-user-id').subscribe(user => {
  console.log('Get User: user');
});
```

**6. getUsersByIds**

```javascript
userService.getUsersByIds('your-id').subscribe(usersbyids => {
  console.log('Get Users By Ids: usersbyids');
});
```

**7. saveUser**

```javascript
const user = user;
userService.saveUser(user, true).subscribe(savedUser => {
  console.log('Save User: savedUser');
});
```

**8. getActivationLink**

```javascript
userService.getActivationLink('your-user-id').subscribe(activationLink => {
  console.log('Get Activation Link: activationLink');
});
```

**9. getActivationLinkInfo**

```javascript
userService.getActivationLinkInfo('your-user-id').subscribe(activationLinkInfo => {
  console.log('Get Activation Link Info: activationLinkInfo');
});
```

**10. setUserCredentialsEnabled**

```javascript
userService.setUserCredentialsEnabled('your-user-id', true).subscribe(result => {
  console.log('Set User Credentials Enabled: result');
});
```

**11. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.findUsersByQuery(pageLink).subscribe(results => {
  console.log('Find Users By Query: results');
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
userSettingsService.loadUserSettings().subscribe(result => {
  console.log('Load User Settings: result');
});
```

**2. saveUserSettings**

```javascript
const userSettings = userSettings;
userSettingsService.saveUserSettings(userSettings).subscribe(savedUserSettings => {
  console.log('Save User Settings: savedUserSettings');
});
```

**3. putUserSettings**

```javascript
const userSettingsData = userSettingsData;
userSettingsService.putUserSettings(userSettingsData).subscribe(result => {
  console.log('Put User Settings: result');
});
```

**4. getDocumentationLinks**

```javascript
userSettingsService.getDocumentationLinks().subscribe(documentationlinks => {
  console.log('Get Documentation Links: documentationlinks');
});
```

**5. updateDocumentationLinks**

```javascript
const documentationLinks = documentationLinks;
userSettingsService.updateDocumentationLinks(documentationLinks).subscribe(result => {
  console.log('Update Documentation Links: result');
});
```

**6. getQuickLinks**

```javascript
userSettingsService.getQuickLinks().subscribe(quicklinks => {
  console.log('Get Quick Links: quicklinks');
});
```

**7. updateQuickLinks**

```javascript
const quickLinks = quickLinks;
userSettingsService.updateQuickLinks(quickLinks).subscribe(result => {
  console.log('Update Quick Links: result');
});
```

**8. getGettingStarted**

```javascript
userSettingsService.getGettingStarted().subscribe(gettingStarted => {
  console.log('Get Getting Started: gettingStarted');
});
```

**9. updateGettingStarted**

```javascript
const gettingStarted = gettingStarted;
userSettingsService.updateGettingStarted(gettingStarted).subscribe(result => {
  console.log('Update Getting Started: result');
});
```

**10. getUserDashboardsInfo**

```javascript
userSettingsService.getUserDashboardsInfo().subscribe(userDashboardsInfo => {
  console.log('Get User Dashboards Info: userDashboardsInfo');
});
```

**11. reportUserDashboardAction**

```javascript
const action = action;
userSettingsService.reportUserDashboardAction('your-dashboard-id', action).subscribe(result => {
  console.log('Report User Dashboard Action: result');
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
widgetService.getWidgetScopeVariables().subscribe(widgetscopevariables => {
  console.log('Get Widget Scope Variables: widgetscopevariables');
});
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(allwidgetsbundles => {
  console.log('Get All Widgets Bundles: allwidgetsbundles');
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(systemwidgetsbundles => {
  console.log('Get System Widgets Bundles: systemwidgetsbundles');
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(tenantwidgetsbundles => {
  console.log('Get Tenant Widgets Bundles: tenantwidgetsbundles');
});
```

**5. getWidgetBundles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetBundles(pageLink).subscribe(widgetbundles => {
  console.log('Get Widget Bundles: widgetbundles');
});
```

**6. getWidgetsBundle**

```javascript
widgetService.getWidgetsBundle('your-widgets-bundle-id').subscribe(widgetsBundle => {
  console.log('Get Widgets Bundle: widgetsBundle');
});
```

**7. exportWidgetsBundle**

```javascript
widgetService.exportWidgetsBundle('your-widgets-bundle-id').subscribe(exported => {
  console.log('Export Widgets Bundle: exported');
});
```

**8. saveWidgetsBundle**

```javascript
widgetService.saveWidgetsBundle('your-id').subscribe(savedWidgetsBundle => {
  console.log('Save Widgets Bundle: savedWidgetsBundle');
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
widgetService.updateWidgetsBundleWidgetTypes('your-widgets-bundle-id', 'your-id').subscribe(result => {
  console.log('Update Widgets Bundle Widget Types:result');
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
widgetService.updateWidgetsBundleWidgetFqns('your-widgets-bundle-id', 'your-id').subscribe(result => {
  console.log('Update Widgets Bundle Widget Fqns:result');
});
```

**11. getBundleWidgetTypes**

```javascript
widgetService.getBundleWidgetTypes('your-widgets-bundle-id').subscribe(bundlewidgettypes => {
  console.log('Get Bundle Widget Types: bundlewidgettypes');
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
widgetService.exportBundleWidgetTypesDetails('your-widgets-bundle-id').subscribe(exported => {
  console.log('Export Bundle Widget Types Details:exported');
});
```

**13. getBundleWidgetTypeFqns**

```javascript
widgetService.getBundleWidgetTypeFqns('your-widgets-bundle-id').subscribe(bundlewidgettypefqns => {
  console.log('Get Bundle Widget Type Fqns: bundlewidgettypefqns');
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
widgetService.getBundleWidgetTypeInfosList('your-widgets-bundle-id').subscribe(bundleWidgetTypeInfosList => {
  console.log('Get Bundle Widget Type Infos List:bundleWidgetTypeInfosList');
});
```

**15. getBundleWidgetTypeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getBundleWidgetTypeInfos(pageLink, 'your-widgets-bundle-id', 'your-id').subscribe(bundlewidgettypeinfos => {
  console.log('Get Bundle Widget Type Infos: bundlewidgettypeinfos');
});
```

**16. getWidgetType**

```javascript
const fullFqn = fullFqn;
widgetService.getWidgetType(fullFqn).subscribe(widgetType => {
  console.log('Get Widget Type: widgetType');
});
```

**17. saveWidgetTypeDetails**

```javascript
const createdTime = createdTime;
const version = version;
widgetService.saveWidgetTypeDetails('your-id', 'your-id', createdTime, version).subscribe(savedWidgetTypeDetails => {
  console.log('Save Widget Type Details: savedWidgetTypeDetails');
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
widgetService.saveImportedWidgetTypeDetails('your-id').subscribe(savedImportedWidgetTypeDetails => {
  console.log('Save Imported Widget Type Details:savedImportedWidgetTypeDetails');
});
```

**19. getWidgetTypeById**

```javascript
widgetService.getWidgetTypeById('your-widget-type-id').subscribe(widgetTypeById => {
  console.log('Get Widget Type By Id: widgetTypeById');
});
```

**20. exportWidgetType**

```javascript
widgetService.exportWidgetType('your-widget-type-id').subscribe(exported => {
  console.log('Export Widget Type: exported');
});
```

**21. getWidgetTypeInfoById**

```javascript
widgetService.getWidgetTypeInfoById('your-widget-type-id').subscribe(widgetTypeInfoById => {
  console.log('Get Widget Type Info By Id: widgetTypeInfoById');
});
```

**22. saveWidgetType**

```javascript
widgetService.saveWidgetType('your-id').subscribe(savedWidgetType => {
  console.log('Save Widget Type: savedWidgetType');
});
```

**23. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetTypes(pageLink, 'your-id').subscribe(widgettypes => {
  console.log('Get Widget Types: widgettypes');
});
```

**24. getWidgetTemplate**

```javascript
widgetService.getWidgetTemplate('your-id').subscribe(widgetTemplate => {
  console.log('Get Widget Template: widgetTemplate');
});
```

**25. getWidgetInfoFromCache**

```javascript
const fullFqn = fullFqn;
widgetService.getWidgetInfoFromCache(fullFqn).subscribe(widgetInfoFromCache => {
  console.log('Get Widget Info From Cache: widgetInfoFromCache');
});
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
const selector = selector;
widgetService.getBasicWidgetSettingsComponentBySelector(selector).subscribe(basicWidgetSettingsComponentBySelector => {
  console.log('Get Basic Widget Settings Component By Selector:basicWidgetSettingsComponentBySelector');
});
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
const selector = selector;
widgetService.getWidgetSettingsComponentTypeBySelector(selector).subscribe(widgetSettingsComponentTypeBySelector => {
  console.log('Get Widget Settings Component Type By Selector:widgetSettingsComponentTypeBySelector');
});
```

**28. widgetTypeUpdated**

```javascript
widgetService.widgetTypeUpdated('your-id').subscribe(result => {
  console.log('Widget Type Updated: result');
});
```

**29. getWidgetsBundlesByIds**

```javascript
widgetService.getWidgetsBundlesByIds('your-id').subscribe(widgetsbundlesbyids => {
  console.log('Get Widgets Bundles By Ids: widgetsbundlesbyids');
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(result => {
  console.log('Load Widgets Bundle Cache: result');
});
```

---
