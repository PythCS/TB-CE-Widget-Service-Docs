# ThingsBoard CE Widget Services Documentation

*Auto-generated from ThingsBoard CE commit c3f22cd9db on 2026-02-12*

**41 services • 459 methods**

This is comprehensive documentation for all ThingsBoard CE widget services. Each method includes a complete, copy-paste ready example that works directly in your widget code.

---

## Table of Contents

- [USING SERVICES IN WIDGETS/CUSTOM ACTIONS](#using-services-in-widgetscustom-actions)
- [USING PAGE LINKS](#using-page-links)
- [**ADMIN SERVICE**](#admin-service)
- [**AI MODEL SERVICE**](#ai-model-service)
- [**ALARM COMMENT SERVICE**](#alarm-comment-service)
- [**ALARM SERVICE**](#alarm-service)
- [**API KEY SERVICE**](#api-key-service)
- [**ASSET PROFILE SERVICE**](#asset-profile-service)
- [**ASSET SERVICE**](#asset-service)
- [**ATTRIBUTE SERVICE**](#attribute-service)
- [**AUDIT LOG SERVICE**](#audit-log-service)
- [**CALCULATED FIELDS SERVICE**](#calculated-fields-service)
- [**COMPONENT DESCRIPTOR SERVICE**](#component-descriptor-service)
- [**CUSTOMER SERVICE**](#customer-service)
- [**DASHBOARD SERVICE**](#dashboard-service)
- [**DEVICE PROFILE SERVICE**](#device-profile-service)
- [**DEVICE SERVICE**](#device-service)
- [**DOMAIN SERVICE**](#domain-service)
- [**EDGE SERVICE**](#edge-service)
- [**ENTITIES VERSION CONTROL SERVICE**](#entities-version-control-service)
- [**ENTITY RELATION SERVICE**](#entity-relation-service)
- [**ENTITY SERVICE**](#entity-service)
- [**ENTITY VIEW SERVICE**](#entity-view-service)
- [**EVENT SERVICE**](#event-service)
- [**GITHUB SERVICE**](#github-service)
- [**IMAGE SERVICE**](#image-service)
- [**MOBILE APP SERVICE**](#mobile-app-service)
- [**MOBILE APPLICATION SERVICE**](#mobile-application-service)
- [**NOTIFICATION SERVICE**](#notification-service)
- [**OAUTH2 SERVICE**](#oauth2-service)
- [**OTA PACKAGE SERVICE**](#ota-package-service)
- [**QUEUE SERVICE**](#queue-service)
- [**RESOURCE SERVICE**](#resource-service)
- [**RULE CHAIN SERVICE**](#rule-chain-service)
- [**TENANT PROFILE SERVICE**](#tenant-profile-service)
- [**TENANT SERVICE**](#tenant-service)
- [**TRENDZ SETTINGS SERVICE**](#trendz-settings-service)
- [**TWO FACTOR AUTHENTICATION SERVICE**](#two-factor-authentication-service)
- [**UI SETTINGS SERVICE**](#ui-settings-service)
- [**USAGE INFO SERVICE**](#usage-info-service)
- [**USER SETTINGS SERVICE**](#user-settings-service)
- [**USER SERVICE**](#user-service)
- [**WIDGET SERVICE**](#widget-service)

---

## USING SERVICES IN WIDGETS/CUSTOM ACTIONS

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

## USING PAGE LINKS

Page links are ThingsBoard's pagination system. They prevent server overload when you have hundreds or thousands of results. Instead of returning all 1000+ users at once, you get them in manageable chunks (pages).

**Why use page links?** Without pagination, loading large datasets can crash browsers and overwhelm servers. Page links let you specify exactly how many results you want and where to start.

**Complete example:**

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Create a page link: 20 results, starting from page 0, search for 'admin', sort by 'email', ascending order
const pageLink = self.ctx.pageLink(20, 0, 'admin', 'email', 'ASC');

userService.getUsers(pageLink).subscribe(users => {
  console.log('Page of Users:', users.data);
  console.log('Total Pages:', users.totalPages);
  console.log('Total Elements:', users.totalElements);
  console.log('Has Next Page:', users.hasNext);
});
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
const adminSettings = {
  // your admin settings object
};
adminService.sendTestMail(adminSettings).subscribe(result => {
  console.log('Test Mail Sent:', result);
});
```

**2. sendTestSms**

```javascript
const testSmsRequest = {
  // your test SMS request object
};
adminService.sendTestSms(testSmsRequest).subscribe(result => {
  console.log('Test SMS Sent:', result);
});
```

**3. getSecuritySettings**

```javascript
adminService.getSecuritySettings().subscribe(settings => {
  console.log('Security Settings:', settings);
});
```

**4. saveSecuritySettings**

```javascript
const securitySettings = {
  // your security settings object
};
adminService.saveSecuritySettings(securitySettings).subscribe(savedSettings => {
  console.log('Saved Security Settings:', savedSettings);
});
```

**5. getJwtSettings**

```javascript
adminService.getJwtSettings().subscribe(settings => {
  console.log('JWT Settings:', settings);
});
```

**6. saveJwtSettings**

```javascript
const jwtSettings = {
  // your JWT settings object
};
adminService.saveJwtSettings(jwtSettings).subscribe(response => {
  console.log('Saved JWT Settings:', response);
});
```

**7. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(settings => {
  console.log('Repository Settings:', settings);
});
```

**8. saveRepositorySettings**

```javascript
const repositorySettings = {
  // your repository settings object
};
adminService.saveRepositorySettings(repositorySettings).subscribe(savedSettings => {
  console.log('Saved Repository Settings:', savedSettings);
});
```

**9. checkRepositoryAccess**

```javascript
const repositorySettings = {
  // your repository settings object
};
adminService.checkRepositoryAccess(repositorySettings).subscribe(result => {
  console.log('Repository Access Check:', result);
});
```

**10. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(info => {
  console.log('Repository Settings Info:', info);
});
```

**11. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(settings => {
  console.log('Auto Commit Settings:', settings);
});
```

**12. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(exists => {
  console.log('Auto Commit Settings Exists:', exists);
});
```

**13. saveAutoCommitSettings**

```javascript
const autoCommitSettings = {
  // your auto commit settings object
};
adminService.saveAutoCommitSettings(autoCommitSettings).subscribe(savedSettings => {
  console.log('Saved Auto Commit Settings:', savedSettings);
});
```

**14. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(updateMessage => {
  console.log('Update Message:', updateMessage);
});
```

**15. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(features => {
  console.log('Features Info:', features);
});
```

**16. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(url => {
  console.log('Login Processing URL:', url);
});
```

**17. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(token => {
  console.log('Generated Access Token:', token);
});
```

**18. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(templates => {
  console.log('Mail Config Templates:', templates);
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
const aiModel = {
  // your AI model object
};
aiModelService.saveAiModel(aiModel).subscribe(savedModel => {
  console.log('Saved AI Model:', savedModel);
});
```

**2. getAiModels**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
aiModelService.getAiModels(pageLink).subscribe(models => {
  console.log('AI Models:', models);
});
```

**3. getAiModelById**

```javascript
const aiModelId = 'your-ai-model-id';
aiModelService.getAiModelById(aiModelId).subscribe(model => {
  console.log('AI Model:', model);
});
```

**4. checkConnectivity**

```javascript
const aiModelWithUserMsg = {
  // your AI model with user message object
};
aiModelService.checkConnectivity(aiModelWithUserMsg).subscribe(result => {
  console.log('Connectivity Check Result:', result);
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
const alarmId = 'your-alarm-id';
const alarmComment = {
  // your alarm comment object
};
alarmCommentService.saveAlarmComment(alarmId, alarmComment).subscribe(savedComment => {
  console.log('Saved Alarm Comment:', savedComment);
});
```

**2. getAlarmComments**

```javascript
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmCommentService.getAlarmComments(alarmId, pageLink).subscribe(comments => {
  console.log('Alarm Comments:', comments);
});
```

**3. deleteAlarmComments**

```javascript
const alarmId = 'your-alarm-id';
const commentId = 'your-comment-id';
alarmCommentService.deleteAlarmComments(alarmId, commentId).subscribe(result => {
  console.log('Deleted Alarm Comment:', result);
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
const alarmId = 'your-alarm-id';
alarmService.getAlarm(alarmId).subscribe(alarm => {
  console.log('Alarm:', alarm);
});
```

**2. getAlarmInfo**

```javascript
const alarmId = 'your-alarm-id';
alarmService.getAlarmInfo(alarmId).subscribe(alarmInfo => {
  console.log('Alarm Info:', alarmInfo);
});
```

**3. saveAlarm**

```javascript
const alarm = {
  // your alarm object
};
alarmService.saveAlarm(alarm).subscribe(savedAlarm => {
  console.log('Saved Alarm:', savedAlarm);
});
```

**4. ackAlarm**

```javascript
const alarmId = 'your-alarm-id';
alarmService.ackAlarm(alarmId).subscribe(alarmInfo => {
  console.log('Acknowledged Alarm Info:', alarmInfo);
});
```

**5. clearAlarm**

```javascript
const alarmId = 'your-alarm-id';
alarmService.clearAlarm(alarmId).subscribe(alarmInfo => {
  console.log('Cleared Alarm Info:', alarmInfo);
});
```

**6. assignAlarm**

```javascript
const alarmId = 'your-alarm-id';
const assigneeId = 'your-assignee-id';
alarmService.assignAlarm(alarmId, assigneeId).subscribe(result => {
  console.log('Assigned Alarm:', result);
});
```

**7. unassignAlarm**

```javascript
const alarmId = 'your-alarm-id';
alarmService.unassignAlarm(alarmId).subscribe(result => {
  console.log('Unassigned Alarm:', result);
});
```

**8. deleteAlarm**

```javascript
const alarmId = 'your-alarm-id';
alarmService.deleteAlarm(alarmId).subscribe(result => {
  console.log('Deleted Alarm:', result);
});
```

**9. getAlarms**

```javascript
const query = {
  // your alarm query object
};
alarmService.getAlarms(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

**10. getAlarmsV2**

```javascript
const query = {
  // your alarm query V2 object
};
alarmService.getAlarmsV2(query).subscribe(alarms => {
  console.log('Alarms V2:', alarms);
});
```

**11. getAllAlarms**

```javascript
const query = {
  // your alarm query object
};
alarmService.getAllAlarms(query).subscribe(alarms => {
  console.log('All Alarms:', alarms);
});
```

**12. getAllAlarmsV2**

```javascript
const query = {
  // your alarm query V2 object
};
alarmService.getAllAlarmsV2(query).subscribe(alarms => {
  console.log('All Alarms V2:', alarms);
});
```

**13. getHighestAlarmSeverity**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const alarmSearchStatus = 'ACTIVE';
const alarmStatus = 'ACTIVE_UNACK';
alarmService.getHighestAlarmSeverity(entityId, alarmSearchStatus, alarmStatus).subscribe(severity => {
  console.log('Highest Alarm Severity:', severity);
});
```

**14. getAlarmTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
alarmService.getAlarmTypes(pageLink).subscribe(types => {
  console.log('Alarm Types:', types);
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
const apiKey = {
  // your API key info object
};
apiKeyService.saveApiKey(apiKey).subscribe(savedKey => {
  console.log('Saved API Key:', savedKey);
});
```

**2. deleteApiKey**

```javascript
const id = 'your-api-key-id';
apiKeyService.deleteApiKey(id).subscribe(result => {
  console.log('Deleted API Key:', result);
});
```

**3. updateApiKeyDescription**

```javascript
const id = 'your-api-key-id';
const description = 'Updated description';
apiKeyService.updateApiKeyDescription(id, description).subscribe(updatedKey => {
  console.log('Updated API Key:', updatedKey);
});
```

**4. enableApiKey**

```javascript
const id = 'your-api-key-id';
const enabledValue = true;
apiKeyService.enableApiKey(id, enabledValue).subscribe(updatedKey => {
  console.log('Enabled API Key:', updatedKey);
});
```

**5. getUserApiKeys**

```javascript
const userId = 'your-user-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
apiKeyService.getUserApiKeys(userId, pageLink).subscribe(keys => {
  console.log('User API Keys:', keys);
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
assetProfileService.getAssetProfiles(pageLink).subscribe(profiles => {
  console.log('Asset Profiles:', profiles);
});
```

**2. getAssetProfilesByIds**

```javascript
const assetProfileIds = ['id1', 'id2', 'id3'];
assetProfileService.getAssetProfilesByIds(assetProfileIds).subscribe(profiles => {
  console.log('Asset Profiles By IDs:', profiles);
});
```

**3. getAssetProfile**

```javascript
const assetProfileId = 'your-asset-profile-id';
assetProfileService.getAssetProfile(assetProfileId).subscribe(profile => {
  console.log('Asset Profile:', profile);
});
```

**4. exportAssetProfile**

```javascript
const assetProfileId = 'your-asset-profile-id';
assetProfileService.exportAssetProfile(assetProfileId).subscribe(profile => {
  console.log('Exported Asset Profile:', profile);
});
```

**5. saveAssetProfile**

```javascript
const assetProfile = {
  // your asset profile object
};
assetProfileService.saveAssetProfile(assetProfile).subscribe(savedProfile => {
  console.log('Saved Asset Profile:', savedProfile);
});
```

**6. setDefaultAssetProfile**

```javascript
const assetProfileId = 'your-asset-profile-id';
assetProfileService.setDefaultAssetProfile(assetProfileId).subscribe(profile => {
  console.log('Set Default Asset Profile:', profile);
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(info => {
  console.log('Default Asset Profile Info:', info);
});
```

**8. getAssetProfileInfo**

```javascript
const assetProfileId = 'your-asset-profile-id';
assetProfileService.getAssetProfileInfo(assetProfileId).subscribe(info => {
  console.log('Asset Profile Info:', info);
});
```

**9. getAssetProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(infos => {
  console.log('Asset Profile Infos:', infos);
});
```

**10. getAssetProfileNames**

```javascript
const activeOnly = false;
assetProfileService.getAssetProfileNames(activeOnly).subscribe(names => {
  console.log('Asset Profile Names:', names);
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
const type = '';
assetService.getTenantAssetInfos(pageLink, type).subscribe(assets => {
  console.log('Tenant Asset Infos:', assets);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const assetProfileId = '';
assetService.getTenantAssetInfosByAssetProfileId(pageLink, assetProfileId).subscribe(assets => {
  console.log('Tenant Asset Infos By Profile ID:', assets);
});
```

**3. getCustomerAssetInfos**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
assetService.getCustomerAssetInfos(customerId, pageLink, type).subscribe(assets => {
  console.log('Customer Asset Infos:', assets);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const assetProfileId = '';
assetService.getCustomerAssetInfosByAssetProfileId(customerId, pageLink, assetProfileId).subscribe(assets => {
  console.log('Customer Asset Infos By Profile ID:', assets);
});
```

**5. getAsset**

```javascript
const assetId = 'your-asset-id';
assetService.getAsset(assetId).subscribe(asset => {
  console.log('Asset:', asset);
});
```

**6. getAssets**

```javascript
const assetIds = ['id1', 'id2', 'id3'];
assetService.getAssets(assetIds).subscribe(assets => {
  console.log('Assets:', assets);
});
```

**7. getAssetInfo**

```javascript
const assetId = 'your-asset-id';
assetService.getAssetInfo(assetId).subscribe(assetInfo => {
  console.log('Asset Info:', assetInfo);
});
```

**8. saveAsset**

```javascript
const asset = {
  // your asset object
};
assetService.saveAsset(asset).subscribe(savedAsset => {
  console.log('Saved Asset:', savedAsset);
});
```

**9. getAssetTypes**

```javascript
assetService.getAssetTypes().subscribe(types => {
  console.log('Asset Types:', types);
});
```

**10. makeAssetPublic**

```javascript
const assetId = 'your-asset-id';
assetService.makeAssetPublic(assetId).subscribe(asset => {
  console.log('Made Asset Public:', asset);
});
```

**11. assignAssetToCustomer**

```javascript
const customerId = 'your-customer-id';
const assetId = 'your-asset-id';
assetService.assignAssetToCustomer(customerId, assetId).subscribe(asset => {
  console.log('Assigned Asset to Customer:', asset);
});
```

**12. findByQuery**

```javascript
const query = {
  // your asset search query object
};
assetService.findByQuery(query).subscribe(assets => {
  console.log('Assets By Query:', assets);
});
```

**13. findByName**

```javascript
const assetName = 'your-asset-name';
assetService.findByName(assetName).subscribe(asset => {
  console.log('Asset By Name:', asset);
});
```

**14. assignAssetToEdge**

```javascript
const edgeId = 'your-edge-id';
const assetId = 'your-asset-id';
assetService.assignAssetToEdge(edgeId, assetId).subscribe(asset => {
  console.log('Assigned Asset to Edge:', asset);
});
```

**15. getEdgeAssets**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
assetService.getEdgeAssets(edgeId, pageLink, type).subscribe(assets => {
  console.log('Edge Assets:', assets);
});
```

**16. bulkImportAssets**

```javascript
const entitiesData = {
  // your bulk import request object
};
assetService.bulkImportAssets(entitiesData).subscribe(result => {
  console.log('Bulk Import Assets Result:', result);
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
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'CLIENT_SCOPE';
const keys = ['key1', 'key2'];
attributeService.getEntityAttributes(entityId, attributeScope, keys).subscribe(attributes => {
  console.log('Entity Attributes:', attributes);
});
```

**2. deleteEntityAttributes**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'CLIENT_SCOPE';
const attributes = [
  // your attribute data array
];
attributeService.deleteEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Deleted Entity Attributes:', result);
});
```

**3. deleteEntityTimeseries**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const timeseries = [
  // your timeseries data array
];
const startTs = Date.now() - 86400000; // 24 hours ago
const endTs = Date.now();
attributeService.deleteEntityTimeseries(entityId, timeseries, startTs, endTs).subscribe(result => {
  console.log('Deleted Entity Timeseries:', result);
});
```

**4. saveEntityAttributes**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'CLIENT_SCOPE';
const attributes = [
  // your attribute data array
];
attributeService.saveEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Saved Entity Attributes:', result);
});
```

**5. saveEntityTimeseries**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const timeseriesScope = 'TIMESERIES';
const timeseries = [
  // your timeseries data array
];
attributeService.saveEntityTimeseries(entityId, timeseriesScope, timeseries).subscribe(result => {
  console.log('Saved Entity Timeseries:', result);
});
```

**6. getEntityTimeseries**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const keys = ['temperature', 'humidity'];
const startTs = Date.now() - 86400000; // 24 hours ago
const endTs = Date.now();
const limit = 100;
const agg = 'NONE';
const interval = 3600000; // 1 hour
const orderBy = 'DESC';
const useStrictDataTypes = false;
attributeService.getEntityTimeseries(entityId, keys, startTs, endTs, limit, agg, interval, orderBy, useStrictDataTypes).subscribe(timeseries => {
  console.log('Entity Timeseries:', timeseries);
});
```

**7. getEntityTimeseriesLatest**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const keys = ['temperature', 'humidity'];
attributeService.getEntityTimeseriesLatest(entityId, keys).subscribe(timeseries => {
  console.log('Latest Entity Timeseries:', timeseries);
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
const pageLink = {
  pageSize: 10,
  page: 0,
  sortOrder: {
    key: 'createdTime',
    direction: 'DESC'
  },
  startTime: Date.now() - 86400000, // 24 hours ago
  endTime: Date.now()
};
auditLogService.getAuditLogs(pageLink).subscribe(logs => {
  console.log('Audit Logs:', logs);
});
```

**2. getAuditLogsByCustomerId**

```javascript
const customerId = 'your-customer-id';
const pageLink = {
  pageSize: 10,
  page: 0,
  sortOrder: {
    key: 'createdTime',
    direction: 'DESC'
  },
  startTime: Date.now() - 86400000, // 24 hours ago
  endTime: Date.now()
};
auditLogService.getAuditLogsByCustomerId(customerId, pageLink).subscribe(logs => {
  console.log('Customer Audit Logs:', logs);
});
```

**3. getAuditLogsByUserId**

```javascript
const userId = 'your-user-id';
const pageLink = {
  pageSize: 10,
  page: 0,
  sortOrder: {
    key: 'createdTime',
    direction: 'DESC'
  },
  startTime: Date.now() - 86400000, // 24 hours ago
  endTime: Date.now()
};
auditLogService.getAuditLogsByUserId(userId, pageLink).subscribe(logs => {
  console.log('User Audit Logs:', logs);
});
```

**4. getAuditLogsByEntityId**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const pageLink = {
  pageSize: 10,
  page: 0,
  sortOrder: {
    key: 'createdTime',
    direction: 'DESC'
  },
  startTime: Date.now() - 86400000, // 24 hours ago
  endTime: Date.now()
};
auditLogService.getAuditLogsByEntityId(entityId, pageLink).subscribe(logs => {
  console.log('Entity Audit Logs:', logs);
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
const calculatedFieldId = 'your-calculated-field-id';
calculatedFieldsService.getCalculatedFieldById(calculatedFieldId).subscribe(field => {
  console.log('Calculated Field:', field);
});
```

**2. saveCalculatedField**

```javascript
const calculatedField = {
  // your calculated field object
};
calculatedFieldsService.saveCalculatedField(calculatedField).subscribe(savedField => {
  console.log('Saved Calculated Field:', savedField);
});
```

**3. deleteCalculatedField**

```javascript
const calculatedFieldId = 'your-calculated-field-id';
calculatedFieldsService.deleteCalculatedField(calculatedFieldId).subscribe(result => {
  console.log('Deleted Calculated Field:', result);
});
```

**4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const query = {
  // your calculated fields query object
};
calculatedFieldsService.getCalculatedFields(pageLink, query).subscribe(fields => {
  console.log('Calculated Fields:', fields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'ATTRIBUTE';
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, type).subscribe(fields => {
  console.log('Calculated Fields By Entity ID:', fields);
});
```

**6. testScript**

```javascript
const inputParams = {
  // your test script input parameters object
};
calculatedFieldsService.testScript(inputParams).subscribe(result => {
  console.log('Test Script Result:', result);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
const id = 'your-calculated-field-id';
calculatedFieldsService.getLatestCalculatedFieldDebugEvent(id).subscribe(event => {
  console.log('Latest Debug Event:', event);
});
```

**8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'ATTRIBUTE';
calculatedFieldsService.getCalculatedFieldNames(pageLink, type).subscribe(names => {
  console.log('Calculated Field Names:', names);
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
const componentType = 'FILTER';
const ruleChainType = 'CORE';
componentDescriptorService.getComponentDescriptorsByType(componentType, ruleChainType).subscribe(descriptors => {
  console.log('Component Descriptors By Type:', descriptors);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
const componentTypes = ['FILTER', 'ENRICHMENT'];
const ruleChainType = 'CORE';
componentDescriptorService.getComponentDescriptorsByTypes(componentTypes, ruleChainType).subscribe(descriptors => {
  console.log('Component Descriptors By Types:', descriptors);
});
```

**3. getComponentDescriptorByClazz**

```javascript
const componentDescriptorClazz = 'org.thingsboard.rule.engine.filter.TbJsFilterNode';
componentDescriptorService.getComponentDescriptorByClazz(componentDescriptorClazz).subscribe(descriptor => {
  console.log('Component Descriptor By Class:', descriptor);
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
  console.log('Customers:', customers);
});
```

**2. getCustomer**

```javascript
const customerId = 'your-customer-id';
customerService.getCustomer(customerId).subscribe(customer => {
  console.log('Customer:', customer);
});
```

**3. getCustomersByIds**

```javascript
const customerIds = ['id1', 'id2', 'id3'];
customerService.getCustomersByIds(customerIds).subscribe(customers => {
  console.log('Customers By IDs:', customers);
});
```

**4. saveCustomer**

```javascript
const customer = {
  // your customer object
};
customerService.saveCustomer(customer).subscribe(savedCustomer => {
  console.log('Saved Customer:', savedCustomer);
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
dashboardService.getTenantDashboards(pageLink).subscribe(dashboards => {
  console.log('Tenant Dashboards:', dashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getTenantDashboardsByTenantId(tenantId, pageLink).subscribe(dashboards => {
  console.log('Tenant Dashboards By Tenant ID:', dashboards);
});
```

**3. getCustomerDashboards**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
dashboardService.getCustomerDashboards(customerId, pageLink).subscribe(dashboards => {
  console.log('Customer Dashboards:', dashboards);
});
```

**4. getDashboard**

```javascript
const dashboardId = 'your-dashboard-id';
dashboardService.getDashboard(dashboardId).subscribe(dashboard => {
  console.log('Dashboard:', dashboard);
});
```

**5. exportDashboard**

```javascript
const dashboardId = 'your-dashboard-id';
dashboardService.exportDashboard(dashboardId).subscribe(dashboard => {
  console.log('Exported Dashboard:', dashboard);
});
```

**6. getDashboardInfo**

```javascript
const dashboardId = 'your-dashboard-id';
dashboardService.getDashboardInfo(dashboardId).subscribe(dashboardInfo => {
  console.log('Dashboard Info:', dashboardInfo);
});
```

**7. getDashboards**

```javascript
const dashboardIds = ['id1', 'id2', 'id3'];
dashboardService.getDashboards(dashboardIds).subscribe(dashboards => {
  console.log('Dashboards:', dashboards);
});
```

**8. saveDashboard**

```javascript
const dashboard = {
  // your dashboard object
};
dashboardService.saveDashboard(dashboard).subscribe(savedDashboard => {
  console.log('Saved Dashboard:', savedDashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
const customerId = 'your-customer-id';
const dashboardId = 'your-dashboard-id';
dashboardService.assignDashboardToCustomer(customerId, dashboardId).subscribe(dashboard => {
  console.log('Assigned Dashboard to Customer:', dashboard);
});
```

**10. makeDashboardPublic**

```javascript
const dashboardId = 'your-dashboard-id';
dashboardService.makeDashboardPublic(dashboardId).subscribe(dashboard => {
  console.log('Made Dashboard Public:', dashboard);
});
```

**11. makeDashboardPrivate**

```javascript
const dashboardId = 'your-dashboard-id';
dashboardService.makeDashboardPrivate(dashboardId).subscribe(dashboard => {
  console.log('Made Dashboard Private:', dashboard);
});
```

**12. updateDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['id1', 'id2', 'id3'];
dashboardService.updateDashboardCustomers(dashboardId, customerIds).subscribe(dashboard => {
  console.log('Updated Dashboard Customers:', dashboard);
});
```

**13. addDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['id1', 'id2', 'id3'];
dashboardService.addDashboardCustomers(dashboardId, customerIds).subscribe(dashboard => {
  console.log('Added Dashboard Customers:', dashboard);
});
```

**14. removeDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['id1', 'id2', 'id3'];
dashboardService.removeDashboardCustomers(dashboardId, customerIds).subscribe(dashboard => {
  console.log('Removed Dashboard Customers:', dashboard);
});
```

**15. getHomeDashboard**

```javascript
dashboardService.getHomeDashboard().subscribe(homeDashboard => {
  console.log('Home Dashboard:', homeDashboard);
});
```

**16. getTenantHomeDashboardInfo**

```javascript
dashboardService.getTenantHomeDashboardInfo().subscribe(info => {
  console.log('Tenant Home Dashboard Info:', info);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
const homeDashboardInfo = {
  // your home dashboard info object
};
dashboardService.setTenantHomeDashboardInfo(homeDashboardInfo).subscribe(result => {
  console.log('Set Tenant Home Dashboard Info:', result);
});
```

**18. getPublicDashboardLink**

```javascript
const dashboard = {
  // your dashboard info object
};
const link = dashboardService.getPublicDashboardLink(dashboard);
console.log('Public Dashboard Link:', link);
```

**19. getServerTimeDiff**

```javascript
dashboardService.getServerTimeDiff().subscribe(timeDiff => {
  console.log('Server Time Diff:', timeDiff);
});
```

**20. getEdgeDashboards**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
dashboardService.getEdgeDashboards(edgeId, pageLink, type).subscribe(dashboards => {
  console.log('Edge Dashboards:', dashboards);
});
```

**21. assignDashboardToEdge**

```javascript
const edgeId = 'your-edge-id';
const dashboardId = 'your-dashboard-id';
dashboardService.assignDashboardToEdge(edgeId, dashboardId).subscribe(dashboard => {
  console.log('Assigned Dashboard to Edge:', dashboard);
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
deviceProfileService.getDeviceProfiles(pageLink).subscribe(profiles => {
  console.log('Device Profiles:', profiles);
});
```

**2. getDeviceProfilesByIds**

```javascript
const deviceProfileIds = ['id1', 'id2', 'id3'];
deviceProfileService.getDeviceProfilesByIds(deviceProfileIds).subscribe(profiles => {
  console.log('Device Profiles By IDs:', profiles);
});
```

**3. getDeviceProfile**

```javascript
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfile(deviceProfileId).subscribe(profile => {
  console.log('Device Profile:', profile);
});
```

**4. exportDeviceProfile**

```javascript
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.exportDeviceProfile(deviceProfileId).subscribe(profile => {
  console.log('Exported Device Profile:', profile);
});
```

**5. getLwm2mObjects**

```javascript
const sortOrder = 'ASC';
const objectIds = ['1', '2', '3'];
const searchText = 'temperature';
deviceProfileService.getLwm2mObjects(sortOrder, objectIds, searchText).subscribe(objects => {
  console.log('LwM2M Objects:', objects);
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
const isBootstrapServer = true;
deviceProfileService.getLwm2mBootstrapSecurityInfo(isBootstrapServer).subscribe(info => {
  console.log('LwM2M Bootstrap Security Info:', info);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
const isBootstrapServer = true;
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(isBootstrapServer).subscribe(config => {
  console.log('LwM2M Bootstrap Security Config:', config);
});
```

**8. getLwm2mObjectsPage**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(objects => {
  console.log('LwM2M Objects Page:', objects);
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
const originDeviceProfile = {
  // your original device profile object
};
const deviceProfile = {
  // your modified device profile object
};
deviceProfileService.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(savedProfile => {
  console.log('Saved Device Profile with OTA Confirmation:', savedProfile);
});
```

**10. setDefaultDeviceProfile**

```javascript
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.setDefaultDeviceProfile(deviceProfileId).subscribe(profile => {
  console.log('Set Default Device Profile:', profile);
});
```

**11. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(info => {
  console.log('Default Device Profile Info:', info);
});
```

**12. getDeviceProfileInfo**

```javascript
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileInfo(deviceProfileId).subscribe(info => {
  console.log('Device Profile Info:', info);
});
```

**13. getDeviceProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const transportType = 'DEFAULT';
deviceProfileService.getDeviceProfileInfos(pageLink, transportType).subscribe(infos => {
  console.log('Device Profile Infos:', infos);
});
```

**14. getDeviceProfileDevicesAttributesKeys**

```javascript
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileDevicesAttributesKeys(deviceProfileId).subscribe(keys => {
  console.log('Device Profile Attributes Keys:', keys);
});
```

**15. getDeviceProfileDevicesTimeseriesKeys**

```javascript
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys(deviceProfileId).subscribe(keys => {
  console.log('Device Profile Timeseries Keys:', keys);
});
```

**16. getDeviceProfileNames**

```javascript
const activeOnly = false;
deviceProfileService.getDeviceProfileNames(activeOnly).subscribe(names => {
  console.log('Device Profile Names:', names);
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
const deviceInfoQuery = {
  // your device info query object
};
deviceService.getDeviceInfosByQuery(deviceInfoQuery).subscribe(devices => {
  console.log('Device Infos By Query:', devices);
});
```

**2. getTenantDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
deviceService.getTenantDeviceInfos(pageLink, type).subscribe(devices => {
  console.log('Tenant Device Infos:', devices);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = '';
deviceService.getTenantDeviceInfosByDeviceProfileId(pageLink, deviceProfileId).subscribe(devices => {
  console.log('Tenant Device Infos By Profile ID:', devices);
});
```

**4. getCustomerDeviceInfos**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
deviceService.getCustomerDeviceInfos(customerId, pageLink, type).subscribe(devices => {
  console.log('Customer Device Infos:', devices);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = '';
deviceService.getCustomerDeviceInfosByDeviceProfileId(customerId, pageLink, deviceProfileId).subscribe(devices => {
  console.log('Customer Device Infos By Profile ID:', devices);
});
```

**6. getDevice**

```javascript
const deviceId = 'your-device-id';
deviceService.getDevice(deviceId).subscribe(device => {
  console.log('Device:', device);
});
```

**7. getDevices**

```javascript
const deviceIds = ['id1', 'id2', 'id3'];
deviceService.getDevices(deviceIds).subscribe(devices => {
  console.log('Devices:', devices);
});
```

**8. getDeviceInfo**

```javascript
const deviceId = 'your-device-id';
deviceService.getDeviceInfo(deviceId).subscribe(deviceInfo => {
  console.log('Device Info:', deviceInfo);
});
```

**9. saveDevice**

```javascript
const device = {
  // your device object
};
deviceService.saveDevice(device).subscribe(savedDevice => {
  console.log('Saved Device:', savedDevice);
});
```

**10. saveDeviceWithCredentials**

```javascript
const device = {
  // your device object
};
const credentials = {
  // your device credentials object
};
deviceService.saveDeviceWithCredentials(device, credentials).subscribe(savedDevice => {
  console.log('Saved Device with Credentials:', savedDevice);
});
```

**11. getDeviceTypes**

```javascript
deviceService.getDeviceTypes().subscribe(types => {
  console.log('Device Types:', types);
});
```

**12. getDeviceCredentials**

```javascript
const deviceId = 'your-device-id';
const sync = false;
deviceService.getDeviceCredentials(deviceId, sync).subscribe(credentials => {
  console.log('Device Credentials:', credentials);
});
```

**13. saveDeviceCredentials**

```javascript
const deviceCredentials = {
  // your device credentials object
};
deviceService.saveDeviceCredentials(deviceCredentials).subscribe(savedCredentials => {
  console.log('Saved Device Credentials:', savedCredentials);
});
```

**14. makeDevicePublic**

```javascript
const deviceId = 'your-device-id';
deviceService.makeDevicePublic(deviceId).subscribe(device => {
  console.log('Made Device Public:', device);
});
```

**15. assignDeviceToCustomer**

```javascript
const customerId = 'your-customer-id';
const deviceId = 'your-device-id';
deviceService.assignDeviceToCustomer(customerId, deviceId).subscribe(device => {
  console.log('Assigned Device to Customer:', device);
});
```

**16. sendOneWayRpcCommand**

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  method: 'setValue',
  params: { value: 25 }
};
deviceService.sendOneWayRpcCommand(deviceId, requestBody).subscribe(result => {
  console.log('One Way RPC Result:', result);
});
```

**17. sendTwoWayRpcCommand**

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  method: 'getValue',
  params: {}
};
deviceService.sendTwoWayRpcCommand(deviceId, requestBody).subscribe(result => {
  console.log('Two Way RPC Result:', result);
});
```

**18. getPersistedRpc**

```javascript
const rpcId = 'your-rpc-id';
deviceService.getPersistedRpc(rpcId).subscribe(rpc => {
  console.log('Persisted RPC:', rpc);
});
```

**19. getPersistedRpcRequests**

```javascript
const deviceId = 'your-device-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const rpcStatus = 'QUEUED';
deviceService.getPersistedRpcRequests(deviceId, pageLink, rpcStatus).subscribe(requests => {
  console.log('Persisted RPC Requests:', requests);
});
```

**20. findByQuery**

```javascript
const query = {
  // your device search query object
};
deviceService.findByQuery(query).subscribe(devices => {
  console.log('Devices By Query:', devices);
});
```

**21. findByName**

```javascript
const deviceName = 'your-device-name';
deviceService.findByName(deviceName).subscribe(device => {
  console.log('Device By Name:', device);
});
```

**22. claimDevice**

```javascript
const deviceName = 'your-device-name';
const claimRequest = {
  // your claim request object
};
deviceService.claimDevice(deviceName, claimRequest).subscribe(result => {
  console.log('Claim Device Result:', result);
});
```

**23. assignDeviceToEdge**

```javascript
const edgeId = 'your-edge-id';
const deviceId = 'your-device-id';
deviceService.assignDeviceToEdge(edgeId, deviceId).subscribe(device => {
  console.log('Assigned Device to Edge:', device);
});
```

**24. getEdgeDevices**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
deviceService.getEdgeDevices(edgeId, pageLink, type).subscribe(devices => {
  console.log('Edge Devices:', devices);
});
```

**25. bulkImportDevices**

```javascript
const entitiesData = {
  // your bulk import request object
};
deviceService.bulkImportDevices(entitiesData).subscribe(result => {
  console.log('Bulk Import Devices Result:', result);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
const deviceId = 'your-device-id';
deviceService.getDevicePublishTelemetryCommands(deviceId).subscribe(commands => {
  console.log('Device Publish Telemetry Commands:', commands);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
const deviceId = 'your-device-id';
deviceService.downloadGatewayDockerComposeFile(deviceId).subscribe(file => {
  console.log('Gateway Docker Compose File:', file);
});
```

**28. rebootDevice**

```javascript
const deviceId = 'your-device-id';
const isBootstrapServer = false;
deviceService.rebootDevice(deviceId, isBootstrapServer).subscribe(result => {
  console.log('Reboot Device Result:', result);
});
```

**29. rebootTrigger**

```javascript
const deviceId = 'your-device-id';
const resourcePath = '/3/0/4';
deviceService.rebootTrigger(deviceId, resourcePath).subscribe(result => {
  console.log('Reboot Trigger Result:', result);
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
const domain = {
  // your domain object
};
const oauth2ClientIds = ['client1', 'client2'];
domainService.saveDomain(domain, oauth2ClientIds).subscribe(savedDomain => {
  console.log('Saved Domain:', savedDomain);
});
```

**2. updateOauth2Clients**

```javascript
const id = 'your-domain-id';
const oauth2ClientIds = ['client1', 'client2'];
domainService.updateOauth2Clients(id, oauth2ClientIds).subscribe(result => {
  console.log('Updated OAuth2 Clients:', result);
});
```

**3. getTenantDomainInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
domainService.getTenantDomainInfos(pageLink).subscribe(domains => {
  console.log('Tenant Domain Infos:', domains);
});
```

**4. getDomainInfoById**

```javascript
const id = 'your-domain-id';
domainService.getDomainInfoById(id).subscribe(domainInfo => {
  console.log('Domain Info:', domainInfo);
});
```

**5. deleteDomain**

```javascript
const id = 'your-domain-id';
domainService.deleteDomain(id).subscribe(result => {
  console.log('Deleted Domain:', result);
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
const edgeIds = ['id1', 'id2', 'id3'];
edgeService.getEdges(edgeIds).subscribe(edges => {
  console.log('Edges:', edges);
});
```

**2. getEdge**

```javascript
const edgeId = 'your-edge-id';
edgeService.getEdge(edgeId).subscribe(edge => {
  console.log('Edge:', edge);
});
```

**3. getEdgeInfo**

```javascript
const edgeId = 'your-edge-id';
edgeService.getEdgeInfo(edgeId).subscribe(edgeInfo => {
  console.log('Edge Info:', edgeInfo);
});
```

**4. saveEdge**

```javascript
const edge = {
  // your edge object
};
edgeService.saveEdge(edge).subscribe(savedEdge => {
  console.log('Saved Edge:', savedEdge);
});
```

**5. getEdgeTypes**

```javascript
edgeService.getEdgeTypes().subscribe(types => {
  console.log('Edge Types:', types);
});
```

**6. getCustomerEdgeInfos**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
edgeService.getCustomerEdgeInfos(customerId, pageLink, type).subscribe(edges => {
  console.log('Customer Edge Infos:', edges);
});
```

**7. assignEdgeToCustomer**

```javascript
const customerId = 'your-customer-id';
const edgeId = 'your-edge-id';
edgeService.assignEdgeToCustomer(customerId, edgeId).subscribe(edge => {
  console.log('Assigned Edge to Customer:', edge);
});
```

**8. makeEdgePublic**

```javascript
const edgeId = 'your-edge-id';
edgeService.makeEdgePublic(edgeId).subscribe(edge => {
  console.log('Made Edge Public:', edge);
});
```

**9. getTenantEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
edgeService.getTenantEdgeInfos(pageLink, type).subscribe(edges => {
  console.log('Tenant Edge Infos:', edges);
});
```

**10. findByQuery**

```javascript
const query = {
  // your edge search query object
};
edgeService.findByQuery(query).subscribe(edges => {
  console.log('Edges By Query:', edges);
});
```

**11. getEdgeEvents**

```javascript
const entityId = { entityType: 'EDGE', id: 'your-edge-id' };
const pageLink = {
  pageSize: 10,
  page: 0,
  sortOrder: {
    key: 'createdTime',
    direction: 'DESC'
  },
  startTime: Date.now() - 86400000, // 24 hours ago
  endTime: Date.now()
};
edgeService.getEdgeEvents(entityId, pageLink).subscribe(events => {
  console.log('Edge Events:', events);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
const edgeId = 'your-edge-id';
edgeService.findMissingToRelatedRuleChains(edgeId).subscribe(result => {
  console.log('Missing Related Rule Chains:', result);
});
```

**13. findByName**

```javascript
const edgeName = 'your-edge-name';
edgeService.findByName(edgeName).subscribe(edge => {
  console.log('Edge By Name:', edge);
});
```

**14. bulkImportEdges**

```javascript
const entitiesData = {
  // your bulk import request object
};
edgeService.bulkImportEdges(entitiesData).subscribe(result => {
  console.log('Bulk Import Edges Result:', result);
});
```

**15. getEdgeInstallInstructions**

```javascript
const edgeId = 'your-edge-id';
const method = 'ubuntu';
edgeService.getEdgeInstallInstructions(edgeId, method).subscribe(instructions => {
  console.log('Edge Install Instructions:', instructions);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
const edgeVersion = '3.4.0';
const method = 'ubuntu';
edgeService.getEdgeUpgradeInstructions(edgeVersion, method).subscribe(instructions => {
  console.log('Edge Upgrade Instructions:', instructions);
});
```

**17. isEdgeUpgradeAvailable**

```javascript
const edgeId = 'your-edge-id';
edgeService.isEdgeUpgradeAvailable(edgeId).subscribe(available => {
  console.log('Edge Upgrade Available:', available);
});
```

---

### **ENTITIES VERSION CONTROL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
```

**1. listBranches**

```javascript
const branches = entitiesVersionControlService.listBranches();
console.log('Branches:', branches);
```

**2. getEntityDataInfo**

```javascript
const externalEntityId = { entityType: 'DEVICE', id: 'your-device-id' };
const versionId = 'your-version-id';
entitiesVersionControlService.getEntityDataInfo(externalEntityId, versionId).subscribe(dataInfo => {
  console.log('Entity Data Info:', dataInfo);
});
```

**3. saveEntitiesVersion**

```javascript
const request = {
  // your version create request object
};
entitiesVersionControlService.saveEntitiesVersion(request).subscribe(result => {
  console.log('Save Entities Version Result:', result);
});
```

**4. getVersionCreateRequestStatus**

```javascript
const requestId = 'your-request-id';
entitiesVersionControlService.getVersionCreateRequestStatus(requestId).subscribe(result => {
  console.log('Version Create Request Status:', result);
});
```

**5. listEntityVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = 'main';
const externalEntityId = { entityType: 'DEVICE', id: 'your-device-id' };
entitiesVersionControlService.listEntityVersions(pageLink, branch, externalEntityId).subscribe(versions => {
  console.log('Entity Versions:', versions);
});
```

**6. listEntityTypeVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = 'main';
const entityType = 'DEVICE';
entitiesVersionControlService.listEntityTypeVersions(pageLink, branch, entityType).subscribe(versions => {
  console.log('Entity Type Versions:', versions);
});
```

**7. listVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const branch = 'main';
entitiesVersionControlService.listVersions(pageLink, branch).subscribe(versions => {
  console.log('Versions:', versions);
});
```

**8. loadEntitiesVersion**

```javascript
const request = {
  // your version load request object
};
entitiesVersionControlService.loadEntitiesVersion(request).subscribe(result => {
  console.log('Load Entities Version Result:', result);
});
```

**9. getVersionLoadRequestStatus**

```javascript
const requestId = 'your-request-id';
entitiesVersionControlService.getVersionLoadRequestStatus(requestId).subscribe(result => {
  console.log('Version Load Request Status:', result);
});
```

**10. compareEntityDataToVersion**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const versionId = 'your-version-id';
entitiesVersionControlService.compareEntityDataToVersion(entityId, versionId).subscribe(diff => {
  console.log('Entity Data Diff:', diff);
});
```

**11. entityLoadErrorToMessage**

```javascript
const entityLoadError = {
  // your entity load error object
};
const message = entitiesVersionControlService.entityLoadErrorToMessage(entityLoadError);
console.log('Error Message:', message);
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
const relation = {
  // your entity relation object
};
entityRelationService.saveRelation(relation).subscribe(savedRelation => {
  console.log('Saved Relation:', savedRelation);
});
```

**2. getRelation**

```javascript
const fromId = { entityType: 'DEVICE', id: 'your-device-id' };
const relationType = 'Contains';
const toId = { entityType: 'ASSET', id: 'your-asset-id' };
entityRelationService.getRelation(fromId, relationType, toId).subscribe(relation => {
  console.log('Relation:', relation);
});
```

**3. findByFrom**

```javascript
const fromId = { entityType: 'DEVICE', id: 'your-device-id' };
entityRelationService.findByFrom(fromId).subscribe(relations => {
  console.log('Relations From Entity:', relations);
});
```

**4. findInfoByFrom**

```javascript
const fromId = { entityType: 'DEVICE', id: 'your-device-id' };
entityRelationService.findInfoByFrom(fromId).subscribe(relations => {
  console.log('Relation Infos From Entity:', relations);
});
```

**5. findByFromAndType**

```javascript
const fromId = { entityType: 'DEVICE', id: 'your-device-id' };
const relationType = 'Contains';
entityRelationService.findByFromAndType(fromId, relationType).subscribe(relations => {
  console.log('Relations By From and Type:', relations);
});
```

**6. findByTo**

```javascript
const toId = { entityType: 'ASSET', id: 'your-asset-id' };
entityRelationService.findByTo(toId).subscribe(relations => {
  console.log('Relations To Entity:', relations);
});
```

**7. findInfoByTo**

```javascript
const toId = { entityType: 'ASSET', id: 'your-asset-id' };
entityRelationService.findInfoByTo(toId).subscribe(relations => {
  console.log('Relation Infos To Entity:', relations);
});
```

**8. findByToAndType**

```javascript
const toId = { entityType: 'ASSET', id: 'your-asset-id' };
const relationType = 'Contains';
entityRelationService.findByToAndType(toId, relationType).subscribe(relations => {
  console.log('Relations By To and Type:', relations);
});
```

**9. findByQuery**

```javascript
const query = {
  // your entity relations query object
};
entityRelationService.findByQuery(query).subscribe(relations => {
  console.log('Relations By Query:', relations);
});
```

**10. findInfoByQuery**

```javascript
const query = {
  // your entity relations query object
};
entityRelationService.findInfoByQuery(query).subscribe(relations => {
  console.log('Relation Infos By Query:', relations);
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
const entityType = 'DEVICE';
const entityId = 'your-device-id';
entityService.getEntityObservable(entityType, entityId).subscribe(entity => {
  console.log('Entity Observable:', entity);
});
```

**2. getEntity**

```javascript
const entityType = 'DEVICE';
const entityId = 'your-device-id';
entityService.getEntity(entityType, entityId).subscribe(entity => {
  console.log('Entity:', entity);
});
```

**3. getEntitiesObservable**

```javascript
const entityType = 'DEVICE';
const entityIds = ['id1', 'id2', 'id3'];
entityService.getEntitiesObservable(entityType, entityIds).subscribe(entities => {
  console.log('Entities Observable:', entities);
});
```

**4. getEntities**

```javascript
const entityType = 'DEVICE';
const entityIds = ['id1', 'id2', 'id3'];
entityService.getEntities(entityType, entityIds).subscribe(entities => {
  console.log('Entities:', entities);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(tenants => {
  console.log('Single Tenant Observable:', tenants);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getSingleCustomerByPageLinkObservable(pageLink).subscribe(customers => {
  console.log('Single Customer Observable:', customers);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
const entityType = 'DEVICE';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const subType = '';
entityService.getEntitiesByPageLinkObservable(entityType, pageLink, subType).subscribe(entities => {
  console.log('Entities By Page Link Observable:', entities);
});
```

**8. getEntitiesByPageLink**

```javascript
const entityType = 'DEVICE';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const subType = '';
entityService.getEntitiesByPageLink(entityType, pageLink, subType).subscribe(entities => {
  console.log('Entities By Page Link:', entities);
});
```

**9. getEntitiesByNameFilter**

```javascript
const entityType = 'DEVICE';
const entityNameFilter = 'temp';
const pageSize = 10;
const subType = '';
entityService.getEntitiesByNameFilter(entityType, entityNameFilter, pageSize, subType).subscribe(entities => {
  console.log('Entities By Name Filter:', entities);
});
```

**10. findEntityDataByQuery**

```javascript
const query = {
  // your entity data query object
};
entityService.findEntityDataByQuery(query).subscribe(data => {
  console.log('Entity Data By Query:', data);
});
```

**11. findEntityKeysByQuery**

```javascript
const query = {
  // your entity data query object
};
const scope = 'CLIENT_SCOPE';
entityService.findEntityKeysByQuery(query, scope).subscribe(keys => {
  console.log('Entity Keys By Query:', keys);
});
```

**12. findAlarmDataByQuery**

```javascript
const query = {
  // your alarm data query object
};
entityService.findAlarmDataByQuery(query).subscribe(alarmData => {
  console.log('Alarm Data By Query:', alarmData);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
const filter = {
  // your entity filter object
};
const searchText = 'temperature';
entityService.findEntityInfosByFilterAndName(filter, searchText).subscribe(infos => {
  console.log('Entity Infos By Filter and Name:', infos);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
const filter = {
  // your entity filter object
};
entityService.findSingleEntityInfoByEntityFilter(filter).subscribe(info => {
  console.log('Single Entity Info By Filter:', info);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
const entityTypes = ['DEVICE', 'ASSET'];
const filterTypes = entityService.getAliasFilterTypesByEntityTypes(entityTypes);
console.log('Alias Filter Types By Entity Types:', filterTypes);
```

**16. filterAliasByEntityTypes**

```javascript
const entityAlias = {
  // your entity alias object
};
const entityTypes = ['DEVICE', 'ASSET'];
const result = entityService.filterAliasByEntityTypes(entityAlias, entityTypes);
console.log('Filter Alias By Entity Types:', result);
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
const aliasFilterType = 'singleEntity';
const entityTypes = ['DEVICE', 'ASSET'];
const result = entityService.filterAliasFilterTypeByEntityTypes(aliasFilterType, entityTypes);
console.log('Filter Alias Filter Type By Entity Types:', result);
```

**18. filterAliasFilterTypeByEntityType**

```javascript
const aliasFilterType = 'singleEntity';
const entityType = 'DEVICE';
const result = entityService.filterAliasFilterTypeByEntityType(aliasFilterType, entityType);
console.log('Filter Alias Filter Type By Entity Type:', result);
```

**19. prepareAllowedEntityTypesList**

```javascript
const allowedEntityTypes = ['DEVICE', 'ASSET'];
const useAliasEntityTypes = true;
const preparedTypes = entityService.prepareAllowedEntityTypesList(allowedEntityTypes, useAliasEntityTypes);
console.log('Prepared Allowed Entity Types:', preparedTypes);
```

**20. getEntityFieldKeys**

```javascript
const entityType = 'DEVICE';
const searchText = '';
const fieldKeys = entityService.getEntityFieldKeys(entityType, searchText);
console.log('Entity Field Keys:', fieldKeys);
```

**21. getAlarmKeys**

```javascript
const searchText = '';
const alarmKeys = entityService.getAlarmKeys(searchText);
console.log('Alarm Keys:', alarmKeys);
```

**22. getEntityKeys**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const query = 'temp';
const type = 'timeseries';
entityService.getEntityKeys(entityId, query, type).subscribe(keys => {
  console.log('Entity Keys:', keys);
});
```

**23. getEntityKeysByEntityFilter**

```javascript
const filter = {
  // your entity filter object
};
const types = ['timeseries', 'attribute'];
const entityTypes = ['DEVICE'];
entityService.getEntityKeysByEntityFilter(filter, types, entityTypes).subscribe(keys => {
  console.log('Entity Keys By Filter:', keys);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
const filter = {
  // your entity filter object
};
const types = ['attribute'];
const entityTypes = ['DEVICE'];
const scope = 'CLIENT_SCOPE';
entityService.getEntityKeysByEntityFilterAndScope(filter, types, entityTypes, scope).subscribe(keys => {
  console.log('Entity Keys By Filter and Scope:', keys);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
const subscriptionsInfo = [
  // your subscription info array
];
const datasources = entityService.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo);
console.log('Datasources From Subscriptions Info:', datasources);
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
const subscriptionInfo = {
  // your subscription info object
};
const alarmSource = entityService.createAlarmSourceFromSubscriptionInfo(subscriptionInfo);
console.log('Alarm Source From Subscription Info:', alarmSource);
```

**27. resolveAlias**

```javascript
const entityAlias = {
  // your entity alias object
};
const stateParams = {
  // your state parameters object
};
entityService.resolveAlias(entityAlias, stateParams).subscribe(aliasInfo => {
  console.log('Resolved Alias:', aliasInfo);
});
```

**28. resolveAliasFilter**

```javascript
const filter = {
  // your entity alias filter object
};
const stateParams = {
  // your state parameters object
};
entityService.resolveAliasFilter(filter, stateParams).subscribe(filterResult => {
  console.log('Resolved Alias Filter:', filterResult);
});
```

**29. checkEntityAlias**

```javascript
const entityAlias = {
  // your entity alias object
};
entityService.checkEntityAlias(entityAlias).subscribe(valid => {
  console.log('Entity Alias Valid:', valid);
});
```

**30. resolveAlarmFilter**

```javascript
const alarmFilterConfig = {
  // your alarm filter config object
};
const alarmFilter = entityService.resolveAlarmFilter(alarmFilterConfig);
console.log('Resolved Alarm Filter:', alarmFilter);
```

**31. saveEntityParameters**

```javascript
const entityType = 'DEVICE';
const entityData = {
  // your import entity data object
};
const update = false;
entityService.saveEntityParameters(entityType, entityData, update).subscribe(result => {
  console.log('Saved Entity Parameters:', result);
});
```

**32. getSaveEntityObservable**

```javascript
const entityType = 'DEVICE';
const entityData = {
  // your import entity data object
};
entityService.getSaveEntityObservable(entityType, entityData).subscribe(entity => {
  console.log('Saved Entity Observable:', entity);
});
```

**33. getUpdateEntityTasks**

```javascript
const entityType = 'DEVICE';
const entityData = {
  // your import entity data object
};
const entity = {
  // your entity object
};
const tasks = entityService.getUpdateEntityTasks(entityType, entityData, entity);
console.log('Update Entity Tasks:', tasks);
```

**34. saveEntityData**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const entityData = {
  // your import entity data object
};
entityService.saveEntityData(entityId, entityData).subscribe(result => {
  console.log('Saved Entity Data:', result);
});
```

**35. getAssignedToEdgeEntitiesByType**

```javascript
const edgeId = 'your-edge-id';
const entityType = 'DEVICE';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
entityService.getAssignedToEdgeEntitiesByType(edgeId, entityType, pageLink).subscribe(entities => {
  console.log('Assigned to Edge Entities By Type:', entities);
});
```

**36. getEntitySubtypesObservable**

```javascript
const entityType = 'DEVICE';
entityService.getEntitySubtypesObservable(entityType).subscribe(subtypes => {
  console.log('Entity Subtypes Observable:', subtypes);
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
const type = '';
entityViewService.getTenantEntityViewInfos(pageLink, type).subscribe(entityViews => {
  console.log('Tenant Entity View Infos:', entityViews);
});
```

**2. getCustomerEntityViewInfos**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
entityViewService.getCustomerEntityViewInfos(customerId, pageLink, type).subscribe(entityViews => {
  console.log('Customer Entity View Infos:', entityViews);
});
```

**3. getEntityView**

```javascript
const entityViewId = 'your-entity-view-id';
entityViewService.getEntityView(entityViewId).subscribe(entityView => {
  console.log('Entity View:', entityView);
});
```

**4. getEntityViews**

```javascript
const entityViewIds = ['id1', 'id2', 'id3'];
entityViewService.getEntityViews(entityViewIds).subscribe(entityViews => {
  console.log('Entity Views:', entityViews);
});
```

**5. getEntityViewInfo**

```javascript
const entityViewId = 'your-entity-view-id';
entityViewService.getEntityViewInfo(entityViewId).subscribe(entityViewInfo => {
  console.log('Entity View Info:', entityViewInfo);
});
```

**6. saveEntityView**

```javascript
const entityView = {
  // your entity view object
};
entityViewService.saveEntityView(entityView).subscribe(savedEntityView => {
  console.log('Saved Entity View:', savedEntityView);
});
```

**7. getEntityViewTypes**

```javascript
entityViewService.getEntityViewTypes().subscribe(types => {
  console.log('Entity View Types:', types);
});
```

**8. makeEntityViewPublic**

```javascript
const entityViewId = 'your-entity-view-id';
entityViewService.makeEntityViewPublic(entityViewId).subscribe(entityView => {
  console.log('Made Entity View Public:', entityView);
});
```

**9. assignEntityViewToCustomer**

```javascript
const customerId = 'your-customer-id';
const entityViewId = 'your-entity-view-id';
entityViewService.assignEntityViewToCustomer(customerId, entityViewId).subscribe(entityView => {
  console.log('Assigned Entity View to Customer:', entityView);
});
```

**10. findByQuery**

```javascript
const query = {
  // your entity view search query object
};
entityViewService.findByQuery(query).subscribe(entityViews => {
  console.log('Entity Views By Query:', entityViews);
});
```

**11. assignEntityViewToEdge**

```javascript
const edgeId = 'your-edge-id';
const entityViewId = 'your-entity-view-id';
entityViewService.assignEntityViewToEdge(edgeId, entityViewId).subscribe(entityView => {
  console.log('Assigned Entity View to Edge:', entityView);
});
```

**12. getEdgeEntityViews**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = '';
entityViewService.getEdgeEntityViews(edgeId, pageLink, type).subscribe(entityViews => {
  console.log('Edge Entity Views:', entityViews);
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
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const eventType = 'LC_EVENT';
const tenantId = 'your-tenant-id';
const pageLink = {
  pageSize: 10,
  page: 0,
  sortOrder: {
    key: 'createdTime',
    direction: 'DESC'
  },
  startTime: Date.now() - 86400000, // 24 hours ago
  endTime: Date.now()
};
eventService.getEvents(entityId, eventType, tenantId, pageLink).subscribe(events => {
  console.log('Events:', events);
});
```

**2. getFilterEvents**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const eventType = 'LC_EVENT';
const tenantId = 'your-tenant-id';
const filters = {
  // your filter event body object
};
const pageLink = {
  pageSize: 10,
  page: 0,
  sortOrder: {
    key: 'createdTime',
    direction: 'DESC'
  },
  startTime: Date.now() - 86400000, // 24 hours ago
  endTime: Date.now()
};
eventService.getFilterEvents(entityId, eventType, tenantId, filters, pageLink).subscribe(events => {
  console.log('Filter Events:', events);
});
```

---

### **GITHUB SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const gitHubService = $injector.get(self.ctx.servicesMap.get('gitHubService'));
```

**1. getGitHubStar**

```javascript
gitHubService.getGitHubStar().subscribe(stars => {
  console.log('GitHub Stars:', stars);
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
const file = new File(['content'], 'image.jpg', { type: 'image/jpeg' });
const title = 'My Image';
const imageSubType = 'IMAGE';
imageService.uploadImage(file, title, imageSubType).subscribe(imageInfo => {
  console.log('Uploaded Image:', imageInfo);
});
```

**2. updateImage**

```javascript
const type = 'TENANT';
const key = 'your-image-key';
const file = new File(['content'], 'updated-image.jpg', { type: 'image/jpeg' });
imageService.updateImage(type, key, file).subscribe(imageInfo => {
  console.log('Updated Image:', imageInfo);
});
```

**3. updateImageInfo**

```javascript
const imageInfo = {
  // your image resource info object
};
imageService.updateImageInfo(imageInfo).subscribe(updatedImageInfo => {
  console.log('Updated Image Info:', updatedImageInfo);
});
```

**4. updateImagePublicStatus**

```javascript
const imageInfo = {
  // your image resource info object
};
const isPublic = true;
imageService.updateImagePublicStatus(imageInfo, isPublic).subscribe(updatedImageInfo => {
  console.log('Updated Image Public Status:', updatedImageInfo);
});
```

**5. getImages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const imageSubType = 'IMAGE';
imageService.getImages(pageLink, imageSubType).subscribe(images => {
  console.log('Images:', images);
});
```

**6. getImageInfo**

```javascript
const type = 'TENANT';
const key = 'your-image-key';
imageService.getImageInfo(type, key).subscribe(imageInfo => {
  console.log('Image Info:', imageInfo);
});
```

**7. getImageDataUrl**

```javascript
const imageUrl = 'https://example.com/image.jpg';
imageService.getImageDataUrl(imageUrl).subscribe(dataUrl => {
  console.log('Image Data URL:', dataUrl);
});
```

**8. loadImageDataUrl**

```javascript
const imageLink = 'https://example.com/image.jpg';
imageService.loadImageDataUrl(imageLink).subscribe(dataUrl => {
  console.log('Loaded Image Data URL:', dataUrl);
});
```

**9. getImageString**

```javascript
const imageUrl = 'https://example.com/image.jpg';
imageService.getImageString(imageUrl).subscribe(imageString => {
  console.log('Image String:', imageString);
});
```

**10. resolveImageUrl**

```javascript
const imageUrl = 'https://example.com/image.jpg';
imageService.resolveImageUrl(imageUrl).subscribe(resolvedUrl => {
  console.log('Resolved Image URL:', resolvedUrl);
});
```

**11. downloadImage**

```javascript
const type = 'TENANT';
const key = 'your-image-key';
imageService.downloadImage(type, key).subscribe(image => {
  console.log('Downloaded Image:', image);
});
```

**12. exportImage**

```javascript
const type = 'TENANT';
const key = 'your-image-key';
imageService.exportImage(type, key).subscribe(imageData => {
  console.log('Exported Image:', imageData);
});
```

**13. importImage**

```javascript
const imageData = {
  // your image export data object
};
imageService.importImage(imageData).subscribe(imageInfo => {
  console.log('Imported Image:', imageInfo);
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
const mobileApp = {
  // your mobile app object
};
mobileAppService.saveMobileApp(mobileApp).subscribe(savedApp => {
  console.log('Saved Mobile App:', savedApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const platformType = 'ANDROID';
mobileAppService.getTenantMobileAppInfos(pageLink, platformType).subscribe(apps => {
  console.log('Tenant Mobile App Infos:', apps);
});
```

**3. getMobileAppInfoById**

```javascript
const id = 'your-mobile-app-id';
mobileAppService.getMobileAppInfoById(id).subscribe(appInfo => {
  console.log('Mobile App Info:', appInfo);
});
```

**4. deleteMobileApp**

```javascript
const id = 'your-mobile-app-id';
mobileAppService.deleteMobileApp(id).subscribe(result => {
  console.log('Deleted Mobile App:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(bundles => {
  console.log('Tenant Mobile App Bundle Infos:', bundles);
});
```

**6. getMobileAppBundleInfoById**

```javascript
const id = 'your-bundle-id';
mobileAppService.getMobileAppBundleInfoById(id).subscribe(bundleInfo => {
  console.log('Mobile App Bundle Info:', bundleInfo);
});
```

**7. deleteMobileAppBundle**

```javascript
const id = 'your-bundle-id';
mobileAppService.deleteMobileAppBundle(id).subscribe(result => {
  console.log('Deleted Mobile App Bundle:', result);
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
  console.log('Mobile App Settings:', settings);
});
```

**2. saveMobileAppSettings**

```javascript
const mobileAppSettings = {
  // your QR code settings object
};
mobileApplicationService.saveMobileAppSettings(mobileAppSettings).subscribe(savedSettings => {
  console.log('Saved Mobile App Settings:', savedSettings);
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(deepLink => {
  console.log('Mobile App Deep Link:', deepLink);
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
  console.log('Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
const id = 'your-notification-id';
notificationService.deleteNotification(id).subscribe(result => {
  console.log('Deleted Notification:', result);
});
```

**3. markNotificationAsRead**

```javascript
const id = 'your-notification-id';
notificationService.markNotificationAsRead(id).subscribe(result => {
  console.log('Marked Notification as Read:', result);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('Marked All Notifications as Read:', result);
});
```

**5. createNotificationRequest**

```javascript
const notification = {
  // your notification request object
};
notificationService.createNotificationRequest(notification).subscribe(createdRequest => {
  console.log('Created Notification Request:', createdRequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
const entityType = 'DEVICE';
notificationService.sendEntitiesLimitIncreaseRequest(entityType).subscribe(result => {
  console.log('Sent Entities Limit Increase Request:', result);
});
```

**7. getNotificationRequestById**

```javascript
const id = 'your-request-id';
notificationService.getNotificationRequestById(id).subscribe(request => {
  console.log('Notification Request:', request);
});
```

**8. getAvailableDeliveryMethods**

```javascript
notificationService.getAvailableDeliveryMethods().subscribe(methods => {
  console.log('Available Delivery Methods:', methods);
});
```

**9. deleteNotificationRequest**

```javascript
const id = 'your-request-id';
notificationService.deleteNotificationRequest(id).subscribe(result => {
  console.log('Deleted Notification Request:', result);
});
```

**10. getNotificationRequestPreview**

```javascript
const notification = {
  // your notification request object
};
notificationService.getNotificationRequestPreview(notification).subscribe(preview => {
  console.log('Notification Request Preview:', preview);
});
```

**11. getNotificationRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRequests(pageLink).subscribe(requests => {
  console.log('Notification Requests:', requests);
});
```

**12. getNotificationSettings**

```javascript
notificationService.getNotificationSettings().subscribe(settings => {
  console.log('Notification Settings:', settings);
});
```

**13. saveNotificationSettings**

```javascript
const notificationSettings = {
  // your notification settings object
};
notificationService.saveNotificationSettings(notificationSettings).subscribe(savedSettings => {
  console.log('Saved Notification Settings:', savedSettings);
});
```

**14. listSlackConversations**

```javascript
const type = 'PUBLIC_CHANNEL';
const token = 'your-slack-token';
notificationService.listSlackConversations(type, token).subscribe(conversations => {
  console.log('Slack Conversations:', conversations);
});
```

**15. saveNotificationRule**

```javascript
const notificationRule = {
  // your notification rule object
};
notificationService.saveNotificationRule(notificationRule).subscribe(savedRule => {
  console.log('Saved Notification Rule:', savedRule);
});
```

**16. getNotificationRuleById**

```javascript
const id = 'your-rule-id';
notificationService.getNotificationRuleById(id).subscribe(rule => {
  console.log('Notification Rule:', rule);
});
```

**17. deleteNotificationRule**

```javascript
const id = 'your-rule-id';
notificationService.deleteNotificationRule(id).subscribe(result => {
  console.log('Deleted Notification Rule:', result);
});
```

**18. getNotificationRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getNotificationRules(pageLink).subscribe(rules => {
  console.log('Notification Rules:', rules);
});
```

**19. saveNotificationTarget**

```javascript
const notificationTarget = {
  // your notification target object
};
notificationService.saveNotificationTarget(notificationTarget).subscribe(savedTarget => {
  console.log('Saved Notification Target:', savedTarget);
});
```

**20. getNotificationTargetById**

```javascript
const id = 'your-target-id';
notificationService.getNotificationTargetById(id).subscribe(target => {
  console.log('Notification Target:', target);
});
```

**21. deleteNotificationTarget**

```javascript
const id = 'your-target-id';
notificationService.deleteNotificationTarget(id).subscribe(result => {
  console.log('Deleted Notification Target:', result);
});
```

**22. getNotificationTargetsByIds**

```javascript
const ids = ['id1', 'id2', 'id3'];
notificationService.getNotificationTargetsByIds(ids).subscribe(targets => {
  console.log('Notification Targets By IDs:', targets);
});
```

**23. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'PLATFORM_USERS';
notificationService.getNotificationTargets(pageLink, type).subscribe(targets => {
  console.log('Notification Targets:', targets);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
const notificationTarget = {
  // your notification target object
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
notificationService.getRecipientsForNotificationTargetConfig(notificationTarget, pageLink).subscribe(recipients => {
  console.log('Recipients for Notification Target:', recipients);
});
```

**25. saveNotificationTemplate**

```javascript
const notificationTarget = {
  // your notification template object
};
notificationService.saveNotificationTemplate(notificationTarget).subscribe(savedTemplate => {
  console.log('Saved Notification Template:', savedTemplate);
});
```

**26. getNotificationTemplateById**

```javascript
const id = 'your-template-id';
notificationService.getNotificationTemplateById(id).subscribe(template => {
  console.log('Notification Template:', template);
});
```

**27. deleteNotificationTemplate**

```javascript
const id = 'your-template-id';
notificationService.deleteNotificationTemplate(id).subscribe(result => {
  console.log('Deleted Notification Template:', result);
});
```

**28. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const notificationTypes = 'GENERAL';
notificationService.getNotificationTemplates(pageLink, notificationTypes).subscribe(templates => {
  console.log('Notification Templates:', templates);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(settings => {
  console.log('Notification User Settings:', settings);
});
```

**30. saveNotificationUserSettings**

```javascript
const settings = {
  // your notification user settings object
};
notificationService.saveNotificationUserSettings(settings).subscribe(savedSettings => {
  console.log('Saved Notification User Settings:', savedSettings);
});
```

---

### **OAUTH2 SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const oAuth2Service = $injector.get(self.ctx.servicesMap.get('oAuth2Service'));
```

**1. getOAuth2Template**

```javascript
oAuth2Service.getOAuth2Template().subscribe(templates => {
  console.log('OAuth2 Templates:', templates);
});
```

**2. saveOAuth2Client**

```javascript
const oAuth2Client = {
  // your OAuth2 client object
};
oAuth2Service.saveOAuth2Client(oAuth2Client).subscribe(savedClient => {
  console.log('Saved OAuth2 Client:', savedClient);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(clientInfos => {
  console.log('Tenant OAuth2 Client Infos:', clientInfos);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
const clientIds = ['id1', 'id2', 'id3'];
oAuth2Service.findTenantOAuth2ClientInfosByIds(clientIds).subscribe(clientInfos => {
  console.log('Tenant OAuth2 Client Infos By IDs:', clientInfos);
});
```

**5. getOAuth2ClientById**

```javascript
const id = 'your-oauth2-client-id';
oAuth2Service.getOAuth2ClientById(id).subscribe(client => {
  console.log('OAuth2 Client:', client);
});
```

**6. deleteOauth2Client**

```javascript
const id = 'your-oauth2-client-id';
oAuth2Service.deleteOauth2Client(id).subscribe(result => {
  console.log('Deleted OAuth2 Client:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(url => {
  console.log('Login Processing URL:', url);
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
otaPackageService.getOtaPackages(pageLink).subscribe(packages => {
  console.log('OTA Packages:', packages);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const deviceProfileId = 'your-device-profile-id';
const type = 'FIRMWARE';
otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, deviceProfileId, type).subscribe(packages => {
  console.log('OTA Packages By Device Profile ID:', packages);
});
```

**3. getOtaPackage**

```javascript
const otaPackageId = 'your-ota-package-id';
otaPackageService.getOtaPackage(otaPackageId).subscribe(package => {
  console.log('OTA Package:', package);
});
```

**4. getOtaPackageInfo**

```javascript
const otaPackageId = 'your-ota-package-id';
otaPackageService.getOtaPackageInfo(otaPackageId).subscribe(packageInfo => {
  console.log('OTA Package Info:', packageInfo);
});
```

**5. downloadOtaPackage**

```javascript
const otaPackageId = 'your-ota-package-id';
otaPackageService.downloadOtaPackage(otaPackageId).subscribe(package => {
  console.log('Downloaded OTA Package:', package);
});
```

**6. saveOtaPackage**

```javascript
const otaPackage = {
  // your OTA package object
};
otaPackageService.saveOtaPackage(otaPackage).subscribe(savedPackage => {
  console.log('Saved OTA Package:', savedPackage);
});
```

**7. saveOtaPackageInfo**

```javascript
const otaPackageInfo = {
  // your OTA package info object
};
otaPackageService.saveOtaPackageInfo(otaPackageInfo).subscribe(savedPackage => {
  console.log('Saved OTA Package Info:', savedPackage);
});
```

**8. uploadOtaPackageFile**

```javascript
const otaPackageId = 'your-ota-package-id';
const file = new File(['content'], 'firmware.bin', { type: 'application/octet-stream' });
const checksumAlgorithm = 'SHA256';
const checksum = 'your-checksum-value';
otaPackageService.uploadOtaPackageFile(otaPackageId, file, checksumAlgorithm, checksum).subscribe(result => {
  console.log('Uploaded OTA Package File:', result);
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
const type = 'FIRMWARE';
const entityId = { entityType: 'DEVICE_PROFILE', id: 'your-device-profile-id' };
otaPackageService.countUpdateDeviceAfterChangePackage(type, entityId).subscribe(count => {
  console.log('Update Device Count:', count);
});
```

**10. confirmDialogUpdatePackage**

```javascript
const entity = {
  // your entity with OTA page IDs object
};
const originEntity = {
  // your original entity object
};
otaPackageService.confirmDialogUpdatePackage(entity, originEntity).subscribe(confirmed => {
  console.log('Confirm Dialog Update Package:', confirmed);
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
const queueId = 'your-queue-id';
queueService.getQueueById(queueId).subscribe(queue => {
  console.log('Queue:', queue);
});
```

**2. getQueueByName**

```javascript
const queueName = 'Main';
queueService.getQueueByName(queueName).subscribe(queue => {
  console.log('Queue By Name:', queue);
});
```

**3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const serviceType = 'TB_RULE_ENGINE';
queueService.getTenantQueuesByServiceType(pageLink, serviceType).subscribe(queues => {
  console.log('Tenant Queues By Service Type:', queues);
});
```

**4. saveQueue**

```javascript
const queue = {
  // your queue info object
};
const serviceType = 'TB_RULE_ENGINE';
queueService.saveQueue(queue, serviceType).subscribe(savedQueue => {
  console.log('Saved Queue:', savedQueue);
});
```

**5. getQueueStatistics**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
queueService.getQueueStatistics(pageLink).subscribe(statistics => {
  console.log('Queue Statistics:', statistics);
});
```

**6. getQueueStatisticsById**

```javascript
const queueStatId = 'your-queue-stat-id';
queueService.getQueueStatisticsById(queueStatId).subscribe(statistics => {
  console.log('Queue Statistics By ID:', statistics);
});
```

**7. getQueueStatisticsByIds**

```javascript
const queueStatIds = ['id1', 'id2', 'id3'];
queueService.getQueueStatisticsByIds(queueStatIds).subscribe(statistics => {
  console.log('Queue Statistics By IDs:', statistics);
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
const resourceType = 'LWM2M_MODEL';
const resourceSubType = 'LWM2M_MODEL';
resourceService.getResources(pageLink, resourceType, resourceSubType).subscribe(resources => {
  console.log('Resources:', resources);
});
```

**2. getTenantResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
resourceService.getTenantResources(pageLink).subscribe(resources => {
  console.log('Tenant Resources:', resources);
});
```

**3. getResource**

```javascript
const resourceId = 'your-resource-id';
resourceService.getResource(resourceId).subscribe(resource => {
  console.log('Resource:', resource);
});
```

**4. getResourceInfoById**

```javascript
const resourceId = 'your-resource-id';
resourceService.getResourceInfoById(resourceId).subscribe(resourceInfo => {
  console.log('Resource Info:', resourceInfo);
});
```

**5. getResourceInfo**

```javascript
const type = 'LWM2M_MODEL';
const scope = 'TENANT';
const key = 'your-resource-key';
resourceService.getResourceInfo(type, scope, key).subscribe(resourceInfo => {
  console.log('Resource Info By Key:', resourceInfo);
});
```

**6. downloadResource**

```javascript
const resourceId = 'your-resource-id';
resourceService.downloadResource(resourceId).subscribe(resource => {
  console.log('Downloaded Resource:', resource);
});
```

**7. saveResources**

```javascript
const resources = [
  // your resource objects array
];
resourceService.saveResources(resources).subscribe(savedResources => {
  console.log('Saved Resources:', savedResources);
});
```

**8. saveResource**

```javascript
const resource = {
  // your resource object
};
resourceService.saveResource(resource).subscribe(savedResource => {
  console.log('Saved Resource:', savedResource);
});
```

**9. uploadResources**

```javascript
const resources = [
  // your resource objects array
];
resourceService.uploadResources(resources).subscribe(uploadedResources => {
  console.log('Uploaded Resources:', uploadedResources);
});
```

**10. uploadResource**

```javascript
const resource = {
  // your resource object
};
resourceService.uploadResource(resource).subscribe(uploadedResource => {
  console.log('Uploaded Resource:', uploadedResource);
});
```

**11. updatedResourceInfo**

```javascript
const resourceId = 'your-resource-id';
const updatedResources = {
  // your partial resource update object
};
resourceService.updatedResourceInfo(resourceId, updatedResources).subscribe(updatedResource => {
  console.log('Updated Resource Info:', updatedResource);
});
```

**12. updatedResourceData**

```javascript
const resourceId = 'your-resource-id';
const data = new File(['content'], 'resource.txt', { type: 'text/plain' });
resourceService.updatedResourceData(resourceId, data).subscribe(updatedResource => {
  console.log('Updated Resource Data:', updatedResource);
});
```

**13. getResourcesByIds**

```javascript
const ids = ['id1', 'id2', 'id3'];
resourceService.getResourcesByIds(ids).subscribe(resources => {
  console.log('Resources By IDs:', resources);
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
const type = 'CORE';
ruleChainService.getRuleChains(pageLink, type).subscribe(ruleChains => {
  console.log('Rule Chains:', ruleChains);
});
```

**2. getRuleChainsByIds**

```javascript
const ruleChainIds = ['id1', 'id2', 'id3'];
ruleChainService.getRuleChainsByIds(ruleChainIds).subscribe(ruleChains => {
  console.log('Rule Chains By IDs:', ruleChains);
});
```

**3. getRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.getRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Rule Chain:', ruleChain);
});
```

**4. getRuleChainOutputLabels**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.getRuleChainOutputLabels(ruleChainId).subscribe(labels => {
  console.log('Rule Chain Output Labels:', labels);
});
```

**5. createDefaultRuleChain**

```javascript
const ruleChainName = 'My Default Rule Chain';
ruleChainService.createDefaultRuleChain(ruleChainName).subscribe(ruleChain => {
  console.log('Created Default Rule Chain:', ruleChain);
});
```

**6. saveRuleChain**

```javascript
const ruleChain = {
  // your rule chain object
};
ruleChainService.saveRuleChain(ruleChain).subscribe(savedRuleChain => {
  console.log('Saved Rule Chain:', savedRuleChain);
});
```

**7. setRootRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setRootRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Set Root Rule Chain:', ruleChain);
});
```

**8. getRuleChainMetadata**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.getRuleChainMetadata(ruleChainId).subscribe(metadata => {
  console.log('Rule Chain Metadata:', metadata);
});
```

**9. saveRuleChainMetadata**

```javascript
const ruleChainMetaData = {
  // your rule chain metadata object
};
ruleChainService.saveRuleChainMetadata(ruleChainMetaData).subscribe(savedMetadata => {
  console.log('Saved Rule Chain Metadata:', savedMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
const modulesMap = {
  // your modules map object
};
const ruleChainType = 'CORE';
ruleChainService.getRuleNodeComponents(modulesMap, ruleChainType).subscribe(components => {
  console.log('Rule Node Components:', components);
});
```

**11. getRuleNodeConfigComponent**

```javascript
const directive = 'tbFilterNodeConfigDirective';
const component = ruleChainService.getRuleNodeConfigComponent(directive);
console.log('Rule Node Config Component:', component);
```

**12. getRuleNodeComponentByClazz**

```javascript
const ruleChainType = 'CORE';
const clazz = 'org.thingsboard.rule.engine.filter.TbJsFilterNode';
const component = ruleChainService.getRuleNodeComponentByClazz(ruleChainType, clazz);
console.log('Rule Node Component By Class:', component);
```

**13. getLatestRuleNodeDebugInput**

```javascript
const ruleNodeId = 'your-rule-node-id';
ruleChainService.getLatestRuleNodeDebugInput(ruleNodeId).subscribe(debugInput => {
  console.log('Latest Rule Node Debug Input:', debugInput);
});
```

**14. testScript**

```javascript
const inputParams = {
  // your test script input parameters object
};
const scriptLang = 'JS';
ruleChainService.testScript(inputParams, scriptLang).subscribe(result => {
  console.log('Test Script Result:', result);
});
```

**15. loadRuleNodeComponents**

```javascript
const ruleChainType = 'CORE';
ruleChainService.loadRuleNodeComponents(ruleChainType).subscribe(components => {
  console.log('Loaded Rule Node Components:', components);
});
```

**16. resolveRuleNodeComponentsUiResources**

```javascript
const components = [
  // your rule node component descriptors array
];
const modulesMap = {
  // your modules map object
};
ruleChainService.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(resolvedComponents => {
  console.log('Resolved Rule Node Components UI Resources:', resolvedComponents);
});
```

**17. resolveRuleNodeComponentUiResources**

```javascript
const component = {
  // your rule node component descriptor object
};
const modulesMap = {
  // your modules map object
};
ruleChainService.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(resolvedComponent => {
  console.log('Resolved Rule Node Component UI Resources:', resolvedComponent);
});
```

**18. getEdgeRuleChains**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
ruleChainService.getEdgeRuleChains(edgeId, pageLink).subscribe(ruleChains => {
  console.log('Edge Rule Chains:', ruleChains);
});
```

**19. assignRuleChainToEdge**

```javascript
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.assignRuleChainToEdge(edgeId, ruleChainId).subscribe(ruleChain => {
  console.log('Assigned Rule Chain to Edge:', ruleChain);
});
```

**20. setEdgeTemplateRootRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeTemplateRootRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Set Edge Template Root Rule Chain:', ruleChain);
});
```

**21. setAutoAssignToEdgeRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setAutoAssignToEdgeRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Set Auto Assign to Edge Rule Chain:', ruleChain);
});
```

**22. unsetAutoAssignToEdgeRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.unsetAutoAssignToEdgeRuleChain(ruleChainId).subscribe(ruleChain => {
  console.log('Unset Auto Assign to Edge Rule Chain:', ruleChain);
});
```

**23. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(ruleChains => {
  console.log('Auto Assign to Edge Rule Chains:', ruleChains);
});
```

**24. setEdgeRootRuleChain**

```javascript
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeRootRuleChain(edgeId, ruleChainId).subscribe(edge => {
  console.log('Set Edge Root Rule Chain:', edge);
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
tenantProfileService.getTenantProfiles(pageLink).subscribe(profiles => {
  console.log('Tenant Profiles:', profiles);
});
```

**2. getTenantProfile**

```javascript
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.getTenantProfile(tenantProfileId).subscribe(profile => {
  console.log('Tenant Profile:', profile);
});
```

**3. saveTenantProfile**

```javascript
const tenantProfile = {
  // your tenant profile object
};
tenantProfileService.saveTenantProfile(tenantProfile).subscribe(savedProfile => {
  console.log('Saved Tenant Profile:', savedProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.setDefaultTenantProfile(tenantProfileId).subscribe(profile => {
  console.log('Set Default Tenant Profile:', profile);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(info => {
  console.log('Default Tenant Profile Info:', info);
});
```

**6. getTenantProfileInfo**

```javascript
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.getTenantProfileInfo(tenantProfileId).subscribe(info => {
  console.log('Tenant Profile Info:', info);
});
```

**7. getTenantProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(infos => {
  console.log('Tenant Profile Infos:', infos);
});
```

**8. getTenantProfilesByIds**

```javascript
const tenantProfileIds = ['id1', 'id2', 'id3'];
tenantProfileService.getTenantProfilesByIds(tenantProfileIds).subscribe(profiles => {
  console.log('Tenant Profiles By IDs:', profiles);
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
  console.log('Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
const tenantIds = ['id1', 'id2', 'id3'];
tenantService.getTenantsByIds(tenantIds).subscribe(tenants => {
  console.log('Tenants By IDs:', tenants);
});
```

**3. getTenantInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
tenantService.getTenantInfos(pageLink).subscribe(tenantInfos => {
  console.log('Tenant Infos:', tenantInfos);
});
```

**4. getTenant**

```javascript
const tenantId = 'your-tenant-id';
tenantService.getTenant(tenantId).subscribe(tenant => {
  console.log('Tenant:', tenant);
});
```

**5. getTenantInfo**

```javascript
const tenantId = 'your-tenant-id';
tenantService.getTenantInfo(tenantId).subscribe(tenantInfo => {
  console.log('Tenant Info:', tenantInfo);
});
```

**6. saveTenant**

```javascript
const tenant = {
  // your tenant object
};
tenantService.saveTenant(tenant).subscribe(savedTenant => {
  console.log('Saved Tenant:', savedTenant);
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
trendzSettingsService.getTrendzSettings().subscribe(settings => {
  console.log('Trendz Settings:', settings);
});
```

**2. saveTrendzSettings**

```javascript
const trendzSettings = {
  // your trendz settings object
};
trendzSettingsService.saveTrendzSettings(trendzSettings).subscribe(savedSettings => {
  console.log('Saved Trendz Settings:', savedSettings);
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
twoFactorAuthenticationService.getTwoFaSettings().subscribe(settings => {
  console.log('Two Factor Auth Settings:', settings);
});
```

**2. saveTwoFaSettings**

```javascript
const settings = {
  // your two factor auth settings object
};
twoFactorAuthenticationService.saveTwoFaSettings(settings).subscribe(savedSettings => {
  console.log('Saved Two Factor Auth Settings:', savedSettings);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(providers => {
  console.log('Available Two Factor Auth Providers:', providers);
});
```

**4. generateTwoFaAccountConfig**

```javascript
const providerType = 'TOTP';
twoFactorAuthenticationService.generateTwoFaAccountConfig(providerType).subscribe(config => {
  console.log('Generated Two Factor Auth Account Config:', config);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(settings => {
  console.log('Account Two Factor Auth Settings:', settings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
const providerType = 'TOTP';
const useByDefault = true;
twoFactorAuthenticationService.updateTwoFaAccountConfig(providerType, useByDefault).subscribe(settings => {
  console.log('Updated Two Factor Auth Account Config:', settings);
});
```

**7. submitTwoFaAccountConfig**

```javascript
const authConfig = {
  // your two factor auth account config object
};
twoFactorAuthenticationService.submitTwoFaAccountConfig(authConfig).subscribe(result => {
  console.log('Submitted Two Factor Auth Account Config:', result);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
const authConfig = {
  // your two factor auth account config object
};
const verificationCode = 123456;
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(authConfig, verificationCode).subscribe(settings => {
  console.log('Verified and Saved Two Factor Auth Account Config:', settings);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
const providerType = 'TOTP';
twoFactorAuthenticationService.deleteTwoFaAccountConfig(providerType).subscribe(settings => {
  console.log('Deleted Two Factor Auth Account Config:', settings);
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
uiSettingsService.getHelpBaseUrl().subscribe(url => {
  console.log('Help Base URL:', url);
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
usageInfoService.getUsageInfo().subscribe(info => {
  console.log('Usage Info:', info);
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
userSettingsService.loadUserSettings().subscribe(settings => {
  console.log('User Settings:', settings);
});
```

**2. saveUserSettings**

```javascript
const userSettings = {
  // your user settings object
};
userSettingsService.saveUserSettings(userSettings).subscribe(savedSettings => {
  console.log('Saved User Settings:', savedSettings);
});
```

**3. putUserSettings**

```javascript
const userSettingsData = {
  // your partial user settings object
};
userSettingsService.putUserSettings(userSettingsData).subscribe(result => {
  console.log('Put User Settings:', result);
});
```

**4. getDocumentationLinks**

```javascript
userSettingsService.getDocumentationLinks().subscribe(links => {
  console.log('Documentation Links:', links);
});
```

**5. updateDocumentationLinks**

```javascript
const documentationLinks = {
  // your documentation links object
};
userSettingsService.updateDocumentationLinks(documentationLinks).subscribe(result => {
  console.log('Updated Documentation Links:', result);
});
```

**6. getQuickLinks**

```javascript
userSettingsService.getQuickLinks().subscribe(links => {
  console.log('Quick Links:', links);
});
```

**7. updateQuickLinks**

```javascript
const quickLinks = {
  // your quick links object
};
userSettingsService.updateQuickLinks(quickLinks).subscribe(result => {
  console.log('Updated Quick Links:', result);
});
```

**8. getGettingStarted**

```javascript
userSettingsService.getGettingStarted().subscribe(gettingStarted => {
  console.log('Getting Started:', gettingStarted);
});
```

**9. updateGettingStarted**

```javascript
const gettingStarted = {
  // your getting started object
};
userSettingsService.updateGettingStarted(gettingStarted).subscribe(result => {
  console.log('Updated Getting Started:', result);
});
```

**10. getUserDashboardsInfo**

```javascript
userSettingsService.getUserDashboardsInfo().subscribe(dashboardsInfo => {
  console.log('User Dashboards Info:', dashboardsInfo);
});
```

**11. reportUserDashboardAction**

```javascript
const dashboardId = 'your-dashboard-id';
const action = 'ASSIGNED';
userSettingsService.reportUserDashboardAction(dashboardId, action).subscribe(dashboardsInfo => {
  console.log('Reported User Dashboard Action:', dashboardsInfo);
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
  console.log('Users:', users);
});
```

**2. getTenantAdmins**

```javascript
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getTenantAdmins(tenantId, pageLink).subscribe(admins => {
  console.log('Tenant Admins:', admins);
});
```

**3. getCustomerUsers**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getCustomerUsers(customerId, pageLink).subscribe(users => {
  console.log('Customer Users:', users);
});
```

**4. getUsersForAssign**

```javascript
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getUsersForAssign(alarmId, pageLink).subscribe(users => {
  console.log('Users for Assign:', users);
});
```

**5. getUser**

```javascript
const userId = 'your-user-id';
userService.getUser(userId).subscribe(user => {
  console.log('User:', user);
});
```

**6. getUsersByIds**

```javascript
const userIds = ['id1', 'id2', 'id3'];
userService.getUsersByIds(userIds).subscribe(users => {
  console.log('Users By IDs:', users);
});
```

**7. saveUser**

```javascript
const user = {
  // your user object
};
const sendActivationMail = false;
userService.saveUser(user, sendActivationMail).subscribe(savedUser => {
  console.log('Saved User:', savedUser);
});
```

**8. getActivationLink**

```javascript
const userId = 'your-user-id';
userService.getActivationLink(userId).subscribe(link => {
  console.log('Activation Link:', link);
});
```

**9. getActivationLinkInfo**

```javascript
const userId = 'your-user-id';
userService.getActivationLinkInfo(userId).subscribe(linkInfo => {
  console.log('Activation Link Info:', linkInfo);
});
```

**10. setUserCredentialsEnabled**

```javascript
const userId = 'your-user-id';
const userCredentialsEnabled = true;
userService.setUserCredentialsEnabled(userId, userCredentialsEnabled).subscribe(result => {
  console.log('Set User Credentials Enabled:', result);
});
```

**11. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.findUsersByQuery(pageLink).subscribe(users => {
  console.log('Users By Query:', users);
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
const variables = widgetService.getWidgetScopeVariables();
console.log('Widget Scope Variables:', variables);
```

**2. getAllWidgetsBundles**

```javascript
widgetService.getAllWidgetsBundles().subscribe(bundles => {
  console.log('All Widgets Bundles:', bundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(bundles => {
  console.log('System Widgets Bundles:', bundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(bundles => {
  console.log('Tenant Widgets Bundles:', bundles);
});
```

**5. getWidgetBundles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
widgetService.getWidgetBundles(pageLink).subscribe(bundles => {
  console.log('Widget Bundles:', bundles);
});
```

**6. getWidgetsBundle**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getWidgetsBundle(widgetsBundleId).subscribe(bundle => {
  console.log('Widgets Bundle:', bundle);
});
```

**7. exportWidgetsBundle**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.exportWidgetsBundle(widgetsBundleId).subscribe(bundle => {
  console.log('Exported Widgets Bundle:', bundle);
});
```

**8. saveWidgetsBundle**

```javascript
const widgetsBundle = {
  // your widgets bundle object
};
widgetService.saveWidgetsBundle(widgetsBundle).subscribe(savedBundle => {
  console.log('Saved Widgets Bundle:', savedBundle);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeIds = ['id1', 'id2', 'id3'];
widgetService.updateWidgetsBundleWidgetTypes(widgetsBundleId, widgetTypeIds).subscribe(result => {
  console.log('Updated Widgets Bundle Widget Types:', result);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeFqns = ['fqn1', 'fqn2', 'fqn3'];
widgetService.updateWidgetsBundleWidgetFqns(widgetsBundleId, widgetTypeFqns).subscribe(result => {
  console.log('Updated Widgets Bundle Widget FQNs:', result);
});
```

**11. getBundleWidgetTypes**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getBundleWidgetTypes(widgetsBundleId).subscribe(widgetTypes => {
  console.log('Bundle Widget Types:', widgetTypes);
});
```

**12. exportBundleWidgetTypesDetails**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.exportBundleWidgetTypesDetails(widgetsBundleId).subscribe(details => {
  console.log('Export Bundle Widget Types Details:', details);
});
```

**13. getBundleWidgetTypeFqns**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getBundleWidgetTypeFqns(widgetsBundleId).subscribe(fqns => {
  console.log('Bundle Widget Type FQNs:', fqns);
});
```

**14. getBundleWidgetTypeInfosList**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
widgetService.getBundleWidgetTypeInfosList(widgetsBundleId).subscribe(infos => {
  console.log('Bundle Widget Type Infos List:', infos);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypes = null;
widgetService.getBundleWidgetTypeInfos(pageLink, widgetsBundleId, widgetTypes).subscribe(infos => {
  console.log('Bundle Widget Type Infos:', infos);
});
```

**16. getWidgetType**

```javascript
const fullFqn = 'your.widget.fqn';
widgetService.getWidgetType(fullFqn).subscribe(widgetType => {
  console.log('Widget Type:', widgetType);
});
```

**17. saveWidgetTypeDetails**

```javascript
const widgetInfo = {
  // your widget info object
};
const id = { id: 'your-widget-type-id', entityType: 'WIDGET_TYPE' };
const createdTime = Date.now();
const version = 1;
widgetService.saveWidgetTypeDetails(widgetInfo, id, createdTime, version).subscribe(details => {
  console.log('Saved Widget Type Details:', details);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
const widgetTypeDetails = {
  // your widget type details object
};
widgetService.saveImportedWidgetTypeDetails(widgetTypeDetails).subscribe(details => {
  console.log('Saved Imported Widget Type Details:', details);
});
```

**19. getWidgetTypeById**

```javascript
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeById(widgetTypeId).subscribe(widgetType => {
  console.log('Widget Type By ID:', widgetType);
});
```

**20. exportWidgetType**

```javascript
const widgetTypeId = 'your-widget-type-id';
widgetService.exportWidgetType(widgetTypeId).subscribe(widgetType => {
  console.log('Exported Widget Type:', widgetType);
});
```

**21. getWidgetTypeInfoById**

```javascript
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeInfoById(widgetTypeId).subscribe(widgetTypeInfo => {
  console.log('Widget Type Info By ID:', widgetTypeInfo);
});
```

**22. saveWidgetType**

```javascript
const widgetTypeDetails = {
  // your widget type details object
};
widgetService.saveWidgetType(widgetTypeDetails).subscribe(savedWidgetType => {
  console.log('Saved Widget Type:', savedWidgetType);
});
```

**23. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const widgetTypes = null;
widgetService.getWidgetTypes(pageLink, widgetTypes).subscribe(types => {
  console.log('Widget Types:', types);
});
```

**24. getWidgetTemplate**

```javascript
const widgetTypeParam = 'cards';
widgetService.getWidgetTemplate(widgetTypeParam).subscribe(template => {
  console.log('Widget Template:', template);
});
```

**25. getWidgetInfoFromCache**

```javascript
const fullFqn = 'your.widget.fqn';
const widgetInfo = widgetService.getWidgetInfoFromCache(fullFqn);
console.log('Widget Info From Cache:', widgetInfo);
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
const selector = 'tb-basic-widget-config';
const component = widgetService.getBasicWidgetSettingsComponentBySelector(selector);
console.log('Basic Widget Settings Component:', component);
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
const selector = 'tb-widget-config';
const componentType = widgetService.getWidgetSettingsComponentTypeBySelector(selector);
console.log('Widget Settings Component Type:', componentType);
```

**28. widgetTypeUpdated**

```javascript
const updatedWidgetType = {
  // your base widget type object
};
widgetService.widgetTypeUpdated(updatedWidgetType);
console.log('Widget Type Updated');
```

**29. getWidgetsBundlesByIds**

```javascript
const widgetsBundleIds = ['id1', 'id2', 'id3'];
widgetService.getWidgetsBundlesByIds(widgetsBundleIds).subscribe(bundles => {
  console.log('Widgets Bundles By IDs:', bundles);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(result => {
  console.log('Loaded Widgets Bundle Cache:', result);
});
```

---

*This documentation was auto-generated from ThingsBoard CE commit c3f22cd9db on 2026-02-12. For the latest updates, please refer to the official ThingsBoard documentation.*