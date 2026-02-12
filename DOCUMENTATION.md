# ThingsBoard Widget Services Documentation

Complete reference for all 41 widget services with 459+ methods in ThingsBoard Community Edition.

## USING SERVICES IN WIDGETS/CUSTOM ACTIONS

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

Many service methods use PageLink for pagination to avoid overloading the server when you have 1000+ results.

PageLinks control how many results to return, which page, sorting, and search text:

```javascript
// Create a PageLink: pageSize, page, textSearch, sortProperty, sortOrder
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'name', 'ASC');

// Use with any paginated service method
deviceService.getTenantDeviceInfos(pageLink, '').subscribe(devices => {
  console.log('Devices:', devices);
});
```

Parameters:
- **pageSize**: Number of items per page (e.g., 10)
- **page**: Page number starting from 0
- **textSearch**: Search string to filter results (or empty string '')
- **sortProperty**: Property to sort by (e.g., 'name', 'createdTime')
- **sortOrder**: 'ASC' or 'DESC'

## TABLE OF CONTENTS

- [AdminService](#adminservice)
- [AiModelService](#aimodelservice)  
- [AlarmCommentService](#alarmcommentservice)
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

## Services

### **ADMIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. getRepositorySettings**

```javascript
adminService.getRepositorySettings().subscribe(settings => {
  console.log('Repository Settings:', settings);
});
```

**2. saveRepositorySettings**

```javascript
const repositorySettings = {
  // your repository settings object
};
adminService.saveRepositorySettings(repositorySettings).subscribe(savedSettings => {
  console.log('Saved Repository Settings:', savedSettings);
});
```

**3. repositorySettingsExists**

```javascript
adminService.repositorySettingsExists().subscribe(exists => {
  console.log('Repository Settings Exist:', exists);
});
```

**4. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(info => {
  console.log('Repository Settings Info:', info);
});
```

**5. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(settings => {
  console.log('Auto Commit Settings:', settings);
});
```

**6. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(exists => {
  console.log('Auto Commit Settings Exist:', exists);
});
```

**7. saveAutoCommitSettings**

```javascript
const autoCommitSettings = {
  // your auto commit settings object
};
adminService.saveAutoCommitSettings(autoCommitSettings).subscribe(savedSettings => {
  console.log('Saved Auto Commit Settings:', savedSettings);
});
```

**8. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(updateMessage => {
  console.log('Update Message:', updateMessage);
});
```

**9. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(features => {
  console.log('Features Info:', features);
});
```

**10. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(url => {
  console.log('Login Processing URL:', url);
});
```

**11. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(token => {
  console.log('Access Token:', token);
});
```

**12. getMailConfigTemplate**

```javascript
adminService.getMailConfigTemplate().subscribe(templates => {
  console.log('Mail Config Templates:', templates);
});
```

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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
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
  console.log('Connectivity Result:', result);
});
```

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
  comment: 'This is a comment'
};
alarmCommentService.saveAlarmComment(alarmId, alarmComment).subscribe(savedComment => {
  console.log('Saved Alarm Comment:', savedComment);
});
```

**2. getAlarmComments**

```javascript
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
alarmCommentService.getAlarmComments(alarmId, pageLink).subscribe(comments => {
  console.log('Alarm Comments:', comments);
});
```

**3. deleteAlarmComments**

```javascript
const alarmId = 'your-alarm-id';
const commentId = 'your-comment-id';
alarmCommentService.deleteAlarmComments(alarmId, commentId).subscribe(result => {
  console.log('Comment Deleted:', result);
});
```

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
  console.log('Acknowledged Alarm:', alarmInfo);
});
```

**5. clearAlarm**

```javascript
const alarmId = 'your-alarm-id';
alarmService.clearAlarm(alarmId).subscribe(alarmInfo => {
  console.log('Cleared Alarm:', alarmInfo);
});
```

**6. assignAlarm**

```javascript
const alarmId = 'your-alarm-id';
const assigneeId = 'your-assignee-id';
alarmService.assignAlarm(alarmId, assigneeId).subscribe(result => {
  console.log('Alarm Assigned:', result);
});
```

**7. unassignAlarm**

```javascript
const alarmId = 'your-alarm-id';
alarmService.unassignAlarm(alarmId).subscribe(result => {
  console.log('Alarm Unassigned:', result);
});
```

**8. deleteAlarm**

```javascript
const alarmId = 'your-alarm-id';
alarmService.deleteAlarm(alarmId).subscribe(deleted => {
  console.log('Alarm Deleted:', deleted);
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
  // your alarm query v2 object
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
alarmService.getAllAlarms(query).subscribe(allAlarms => {
  console.log('All Alarms:', allAlarms);
});
```

**12. getAllAlarmsV2**

```javascript
const query = {
  // your alarm query v2 object
};
alarmService.getAllAlarmsV2(query).subscribe(allAlarms => {
  console.log('All Alarms V2:', allAlarms);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'type', 'ASC');
alarmService.getAlarmTypes(pageLink).subscribe(types => {
  console.log('Alarm Types:', types);
});
```

### **API KEY SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const apiKeyService = $injector.get(self.ctx.servicesMap.get('apiKeyService'));
```

**1. saveApiKey**

```javascript
const apiKey = {
  name: 'My API Key',
  description: 'API key for testing'
};
apiKeyService.saveApiKey(apiKey).subscribe(savedKey => {
  console.log('Saved API Key:', savedKey);
});
```

**2. deleteApiKey**

```javascript
const id = 'your-api-key-id';
apiKeyService.deleteApiKey(id).subscribe(result => {
  console.log('API Key Deleted:', result);
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
  console.log('API Key Enabled:', updatedKey);
});
```

**5. getUserApiKeys**

```javascript
const userId = 'your-user-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
apiKeyService.getUserApiKeys(userId, pageLink).subscribe(apiKeys => {
  console.log('User API Keys:', apiKeys);
});
```

### **ASSET PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const assetProfileService = $injector.get(self.ctx.servicesMap.get('assetProfileService'));
```

**1. getAssetProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
assetProfileService.getAssetProfiles(pageLink).subscribe(profiles => {
  console.log('Asset Profiles:', profiles);
});
```

**2. getAssetProfilesByIds**

```javascript
const assetProfileIds = ['id1', 'id2', 'id3'];
assetProfileService.getAssetProfilesByIds(assetProfileIds).subscribe(profiles => {
  console.log('Asset Profiles by IDs:', profiles);
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
assetProfileService.exportAssetProfile(assetProfileId).subscribe(exported => {
  console.log('Exported Asset Profile:', exported);
});
```

**5. saveAssetProfile**

```javascript
const assetProfile = {
  name: 'My Asset Profile',
  description: 'Profile for testing'
};
assetProfileService.saveAssetProfile(assetProfile).subscribe(savedProfile => {
  console.log('Saved Asset Profile:', savedProfile);
});
```

**6. setDefaultAssetProfile**

```javascript
const assetProfileId = 'your-asset-profile-id';
assetProfileService.setDefaultAssetProfile(assetProfileId).subscribe(defaultProfile => {
  console.log('Default Asset Profile:', defaultProfile);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(infos => {
  console.log('Asset Profile Infos:', infos);
});
```

**10. getAssetProfileNames**

```javascript
const activeOnly = true;
assetProfileService.getAssetProfileNames(activeOnly).subscribe(names => {
  console.log('Asset Profile Names:', names);
});
```

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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = ''; // empty string for all types
assetService.getTenantAssetInfos(pageLink, type).subscribe(assets => {
  console.log('Tenant Assets:', assets);
});
```

**2. getTenantAssetInfosByAssetProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const assetProfileId = 'your-asset-profile-id';
assetService.getTenantAssetInfosByAssetProfileId(pageLink, assetProfileId).subscribe(assets => {
  console.log('Assets by Profile:', assets);
});
```

**3. getCustomerAssetInfos**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = '';
assetService.getCustomerAssetInfos(customerId, pageLink, type).subscribe(assets => {
  console.log('Customer Assets:', assets);
});
```

**4. getCustomerAssetInfosByAssetProfileId**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const assetProfileId = 'your-asset-profile-id';
assetService.getCustomerAssetInfosByAssetProfileId(customerId, pageLink, assetProfileId).subscribe(assets => {
  console.log('Customer Assets by Profile:', assets);
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
  console.log('Assets by IDs:', assets);
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
  name: 'My Asset',
  type: 'building'
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
assetService.makeAssetPublic(assetId).subscribe(publicAsset => {
  console.log('Public Asset:', publicAsset);
});
```

**11. assignAssetToCustomer**

```javascript
const customerId = 'your-customer-id';
const assetId = 'your-asset-id';
assetService.assignAssetToCustomer(customerId, assetId).subscribe(assignedAsset => {
  console.log('Assigned Asset:', assignedAsset);
});
```

**12. findByQuery**

```javascript
const query = {
  // your asset search query
};
assetService.findByQuery(query).subscribe(assets => {
  console.log('Assets by Query:', assets);
});
```

**13. findByName**

```javascript
const assetName = 'Asset Name';
assetService.findByName(assetName).subscribe(asset => {
  console.log('Asset by Name:', asset);
});
```

**14. assignAssetToEdge**

```javascript
const edgeId = 'your-edge-id';
const assetId = 'your-asset-id';
assetService.assignAssetToEdge(edgeId, assetId).subscribe(assignedAsset => {
  console.log('Asset Assigned to Edge:', assignedAsset);
});
```

**15. getEdgeAssets**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = '';
assetService.getEdgeAssets(edgeId, pageLink, type).subscribe(edgeAssets => {
  console.log('Edge Assets:', edgeAssets);
});
```

**16. bulkImportAssets**

```javascript
const entitiesData = {
  // your bulk import request
};
assetService.bulkImportAssets(entitiesData).subscribe(result => {
  console.log('Bulk Import Result:', result);
});
```

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
const attributeScope = 'SERVER_SCOPE'; // or CLIENT_SCOPE, SHARED_SCOPE
const keys = ['temperature', 'humidity']; // optional - get all if not specified
attributeService.getEntityAttributes(entityId, attributeScope, keys).subscribe(attributes => {
  console.log('Entity Attributes:', attributes);
});
```

**2. deleteEntityAttributes**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'SERVER_SCOPE';
const attributes = [
  { key: 'temperature', value: 25 },
  { key: 'humidity', value: 60 }
];
attributeService.deleteEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Deleted Attributes:', result);
});
```

**3. deleteEntityTimeseries**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const timeseries = [
  { key: 'temperature' },
  { key: 'humidity' }
];
const startTs = Date.now() - 86400000; // 24 hours ago
const endTs = Date.now();
attributeService.deleteEntityTimeseries(entityId, timeseries, startTs, endTs).subscribe(result => {
  console.log('Deleted Timeseries:', result);
});
```

**4. saveEntityAttributes**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const attributeScope = 'SERVER_SCOPE';
const attributes = [
  { key: 'temperature', value: 25.5 },
  { key: 'humidity', value: 65 }
];
attributeService.saveEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Saved Attributes:', result);
});
```

**5. saveEntityTimeseries**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const timeseriesScope = 'ANY';
const timeseries = [
  { key: 'temperature', value: 25.5, ts: Date.now() },
  { key: 'humidity', value: 65, ts: Date.now() }
];
attributeService.saveEntityTimeseries(entityId, timeseriesScope, timeseries).subscribe(result => {
  console.log('Saved Timeseries:', result);
});
```

**6. getEntityTimeseries**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const keys = ['temperature', 'humidity'];
const startTs = Date.now() - 86400000; // 24 hours ago
const endTs = Date.now();
const limit = 100;
const agg = 'NONE'; // or AVG, MIN, MAX, SUM, COUNT
const interval = 3600000; // 1 hour in milliseconds
const orderBy = 'ASC'; // or DESC
const useStrictDataTypes = false;
attributeService.getEntityTimeseries(entityId, keys, startTs, endTs, limit, agg, interval, orderBy, useStrictDataTypes).subscribe(timeseries => {
  console.log('Entity Timeseries:', timeseries);
});
```

**7. getEntityTimeseriesLatest**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const keys = ['temperature', 'humidity']; // optional
attributeService.getEntityTimeseriesLatest(entityId, keys).subscribe(latestData => {
  console.log('Latest Timeseries:', latestData);
});
```

### **AUDIT LOG SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const auditLogService = $injector.get(self.ctx.servicesMap.get('auditLogService'));
```

**1. getAuditLogs**

```javascript
const pageLink = {
  page: 0,
  pageSize: 10,
  textSearch: '',
  sortProperty: 'createdTime',
  sortOrder: 'DESC',
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
  page: 0,
  pageSize: 10,
  textSearch: '',
  sortProperty: 'createdTime',
  sortOrder: 'DESC',
  startTime: Date.now() - 86400000,
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
  page: 0,
  pageSize: 10,
  textSearch: '',
  sortProperty: 'createdTime',
  sortOrder: 'DESC',
  startTime: Date.now() - 86400000,
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
  page: 0,
  pageSize: 10,
  textSearch: '',
  sortProperty: 'createdTime',
  sortOrder: 'DESC',
  startTime: Date.now() - 86400000,
  endTime: Date.now()
};
auditLogService.getAuditLogsByEntityId(entityId, pageLink).subscribe(logs => {
  console.log('Entity Audit Logs:', logs);
});
```

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
  name: 'My Calculated Field',
  type: 'ATTRIBUTE',
  script: 'return msg.temperature * 1.8 + 32;'
};
calculatedFieldsService.saveCalculatedField(calculatedField).subscribe(savedField => {
  console.log('Saved Calculated Field:', savedField);
});
```

**3. deleteCalculatedField**

```javascript
const calculatedFieldId = 'your-calculated-field-id';
calculatedFieldsService.deleteCalculatedField(calculatedFieldId).subscribe(deleted => {
  console.log('Field Deleted:', deleted);
});
```

**4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const query = {
  // your calculated fields query
};
calculatedFieldsService.getCalculatedFields(pageLink, query).subscribe(fields => {
  console.log('Calculated Fields:', fields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'ATTRIBUTE'; // or TIMESERIES
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, type).subscribe(fields => {
  console.log('Entity Calculated Fields:', fields);
});
```

**6. testScript**

```javascript
const inputParams = {
  script: 'return msg.temperature * 1.8 + 32;',
  msg: { temperature: 25 }
};
calculatedFieldsService.testScript(inputParams).subscribe(result => {
  console.log('Script Test Result:', result);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
const id = 'your-calculated-field-id';
calculatedFieldsService.getLatestCalculatedFieldDebugEvent(id).subscribe(debugEvent => {
  console.log('Latest Debug Event:', debugEvent);
});
```

**8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'ATTRIBUTE';
calculatedFieldsService.getCalculatedFieldNames(pageLink, type).subscribe(names => {
  console.log('Calculated Field Names:', names);
});
```

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
  console.log('Component Descriptors:', descriptors);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
const componentTypes = ['FILTER', 'ENRICHMENT', 'TRANSFORMATION'];
const ruleChainType = 'CORE';
componentDescriptorService.getComponentDescriptorsByTypes(componentTypes, ruleChainType).subscribe(descriptors => {
  console.log('Component Descriptors by Types:', descriptors);
});
```

**3. getComponentDescriptorByClazz**

```javascript
const componentDescriptorClazz = 'org.thingsboard.rule.engine.filter.TbMsgTypeFilter';
componentDescriptorService.getComponentDescriptorByClazz(componentDescriptorClazz).subscribe(descriptor => {
  console.log('Component Descriptor:', descriptor);
});
```

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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
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
  console.log('Customers by IDs:', customers);
});
```

**4. saveCustomer**

```javascript
const customer = {
  title: 'My Customer',
  email: 'customer@example.com'
};
customerService.saveCustomer(customer).subscribe(savedCustomer => {
  console.log('Saved Customer:', savedCustomer);
});
```

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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
dashboardService.getTenantDashboards(pageLink).subscribe(dashboards => {
  console.log('Tenant Dashboards:', dashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
dashboardService.getTenantDashboardsByTenantId(tenantId, pageLink).subscribe(dashboards => {
  console.log('Tenant Dashboards by ID:', dashboards);
});
```

**3. getCustomerDashboards**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
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
dashboardService.exportDashboard(dashboardId).subscribe(exported => {
  console.log('Exported Dashboard:', exported);
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
  console.log('Dashboards by IDs:', dashboards);
});
```

**8. saveDashboard**

```javascript
const dashboard = {
  title: 'My Dashboard',
  configuration: {}
};
dashboardService.saveDashboard(dashboard).subscribe(savedDashboard => {
  console.log('Saved Dashboard:', savedDashboard);
});
```

**9. assignDashboardToCustomer**

```javascript
const customerId = 'your-customer-id';
const dashboardId = 'your-dashboard-id';
dashboardService.assignDashboardToCustomer(customerId, dashboardId).subscribe(assignedDashboard => {
  console.log('Assigned Dashboard:', assignedDashboard);
});
```

**10. makeDashboardPublic**

```javascript
const dashboardId = 'your-dashboard-id';
dashboardService.makeDashboardPublic(dashboardId).subscribe(publicDashboard => {
  console.log('Public Dashboard:', publicDashboard);
});
```

**11. makeDashboardPrivate**

```javascript
const dashboardId = 'your-dashboard-id';
dashboardService.makeDashboardPrivate(dashboardId).subscribe(privateDashboard => {
  console.log('Private Dashboard:', privateDashboard);
});
```

**12. updateDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['customer1', 'customer2'];
dashboardService.updateDashboardCustomers(dashboardId, customerIds).subscribe(updated => {
  console.log('Updated Dashboard Customers:', updated);
});
```

**13. addDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['customer1', 'customer2'];
dashboardService.addDashboardCustomers(dashboardId, customerIds).subscribe(updated => {
  console.log('Added Dashboard Customers:', updated);
});
```

**14. removeDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['customer1', 'customer2'];
dashboardService.removeDashboardCustomers(dashboardId, customerIds).subscribe(updated => {
  console.log('Removed Dashboard Customers:', updated);
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
dashboardService.getTenantHomeDashboardInfo().subscribe(homeInfo => {
  console.log('Tenant Home Dashboard Info:', homeInfo);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
const homeDashboardInfo = {
  dashboardId: 'your-dashboard-id'
};
dashboardService.setTenantHomeDashboardInfo(homeDashboardInfo).subscribe(result => {
  console.log('Set Home Dashboard:', result);
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

**19. assignDashboardToEdge**

```javascript
const edgeId = 'your-edge-id';
const dashboardId = 'your-dashboard-id';
dashboardService.assignDashboardToEdge(edgeId, dashboardId).subscribe(assigned => {
  console.log('Dashboard Assigned to Edge:', assigned);
});
```

### **DEVICE PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const deviceProfileService = $injector.get(self.ctx.servicesMap.get('deviceProfileService'));
```

**1. getDeviceProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
deviceProfileService.getDeviceProfiles(pageLink).subscribe(profiles => {
  console.log('Device Profiles:', profiles);
});
```

**2. getDeviceProfilesByIds**

```javascript
const deviceProfileIds = ['id1', 'id2', 'id3'];
deviceProfileService.getDeviceProfilesByIds(deviceProfileIds).subscribe(profiles => {
  console.log('Device Profiles by IDs:', profiles);
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
deviceProfileService.exportDeviceProfile(deviceProfileId).subscribe(exported => {
  console.log('Exported Device Profile:', exported);
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
deviceProfileService.getLwm2mBootstrapSecurityInfo(isBootstrapServer).subscribe(securityInfo => {
  console.log('Bootstrap Security Info:', securityInfo);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
const isBootstrapServer = true;
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(isBootstrapServer).subscribe(config => {
  console.log('Bootstrap Security Config:', config);
});
```

**8. getLwm2mObjectsPage**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
deviceProfileService.getLwm2mObjectsPage(pageLink).subscribe(objects => {
  console.log('LwM2M Objects Page:', objects);
});
```

**9. saveDeviceProfileAndConfirmOtaChange**

```javascript
const originDeviceProfile = {
  // original device profile
};
const deviceProfile = {
  // updated device profile
};
deviceProfileService.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(saved => {
  console.log('Saved with OTA Confirmation:', saved);
});
```

**10. setDefaultDeviceProfile**

```javascript
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.setDefaultDeviceProfile(deviceProfileId).subscribe(defaultProfile => {
  console.log('Default Device Profile:', defaultProfile);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const transportType = 'DEFAULT'; // optional
deviceProfileService.getDeviceProfileInfos(pageLink, transportType).subscribe(infos => {
  console.log('Device Profile Infos:', infos);
});
```

**14. getDeviceProfileDevicesAttributesKeys**

```javascript
const deviceProfileId = 'your-device-profile-id'; // optional
deviceProfileService.getDeviceProfileDevicesAttributesKeys(deviceProfileId).subscribe(keys => {
  console.log('Device Attributes Keys:', keys);
});
```

**15. getDeviceProfileDevicesTimeseriesKeys**

```javascript
const deviceProfileId = 'your-device-profile-id'; // optional
deviceProfileService.getDeviceProfileDevicesTimeseriesKeys(deviceProfileId).subscribe(keys => {
  console.log('Device Timeseries Keys:', keys);
});
```

**16. getDeviceProfileNames**

```javascript
const activeOnly = true;
deviceProfileService.getDeviceProfileNames(activeOnly).subscribe(names => {
  console.log('Device Profile Names:', names);
});
```

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
  console.log('Devices by Query:', devices);
});
```

**2. getTenantDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = ''; // empty string for all types
deviceService.getTenantDeviceInfos(pageLink, type).subscribe(devices => {
  console.log('Tenant Devices:', devices);
});
```

**3. getTenantDeviceInfosByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const deviceProfileId = 'your-device-profile-id';
deviceService.getTenantDeviceInfosByDeviceProfileId(pageLink, deviceProfileId).subscribe(devices => {
  console.log('Devices by Profile:', devices);
});
```

**4. getCustomerDeviceInfos**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = '';
deviceService.getCustomerDeviceInfos(customerId, pageLink, type).subscribe(devices => {
  console.log('Customer Devices:', devices);
});
```

**5. getCustomerDeviceInfosByDeviceProfileId**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const deviceProfileId = 'your-device-profile-id';
deviceService.getCustomerDeviceInfosByDeviceProfileId(customerId, pageLink, deviceProfileId).subscribe(devices => {
  console.log('Customer Devices by Profile:', devices);
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
  console.log('Devices by IDs:', devices);
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
  name: 'My Device',
  type: 'thermostat'
};
deviceService.saveDevice(device).subscribe(savedDevice => {
  console.log('Saved Device:', savedDevice);
});
```

**10. saveDeviceWithCredentials**

```javascript
const device = {
  name: 'My Device',
  type: 'thermostat'
};
const credentials = {
  credentialsType: 'ACCESS_TOKEN',
  credentialsId: 'my-access-token'
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
  deviceId: { entityType: 'DEVICE', id: 'your-device-id' },
  credentialsType: 'ACCESS_TOKEN',
  credentialsId: 'new-access-token'
};
deviceService.saveDeviceCredentials(deviceCredentials).subscribe(saved => {
  console.log('Saved Credentials:', saved);
});
```

**14. makeDevicePublic**

```javascript
const deviceId = 'your-device-id';
deviceService.makeDevicePublic(deviceId).subscribe(publicDevice => {
  console.log('Public Device:', publicDevice);
});
```

**15. assignDeviceToCustomer**

```javascript
const customerId = 'your-customer-id';
const deviceId = 'your-device-id';
deviceService.assignDeviceToCustomer(customerId, deviceId).subscribe(assignedDevice => {
  console.log('Assigned Device:', assignedDevice);
});
```

**16. sendOneWayRpcCommand**

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  method: 'setTemperature',
  params: { temperature: 25 }
};
deviceService.sendOneWayRpcCommand(deviceId, requestBody).subscribe(result => {
  console.log('RPC Command Sent:', result);
});
```

**17. sendTwoWayRpcCommand**

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  method: 'getTemperature',
  timeout: 5000
};
deviceService.sendTwoWayRpcCommand(deviceId, requestBody).subscribe(response => {
  console.log('RPC Response:', response);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
const rpcStatus = 'SUCCESSFUL'; // optional
deviceService.getPersistedRpcRequests(deviceId, pageLink, rpcStatus).subscribe(requests => {
  console.log('RPC Requests:', requests);
});
```

**20. findByQuery**

```javascript
const query = {
  // your device search query
};
deviceService.findByQuery(query).subscribe(devices => {
  console.log('Devices by Query:', devices);
});
```

**21. findByName**

```javascript
const deviceName = 'Device Name';
deviceService.findByName(deviceName).subscribe(device => {
  console.log('Device by Name:', device);
});
```

**22. claimDevice**

```javascript
const deviceName = 'Device Name';
const claimRequest = {
  secretKey: 'secret'
};
deviceService.claimDevice(deviceName, claimRequest).subscribe(result => {
  console.log('Claim Result:', result);
});
```

**23. assignDeviceToEdge**

```javascript
const edgeId = 'your-edge-id';
const deviceId = 'your-device-id';
deviceService.assignDeviceToEdge(edgeId, deviceId).subscribe(assigned => {
  console.log('Device Assigned to Edge:', assigned);
});
```

**24. getEdgeDevices**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = '';
deviceService.getEdgeDevices(edgeId, pageLink, type).subscribe(edgeDevices => {
  console.log('Edge Devices:', edgeDevices);
});
```

**25. bulkImportDevices**

```javascript
const entitiesData = {
  // your bulk import request
};
deviceService.bulkImportDevices(entitiesData).subscribe(result => {
  console.log('Bulk Import Result:', result);
});
```

**26. getDevicePublishTelemetryCommands**

```javascript
const deviceId = 'your-device-id';
deviceService.getDevicePublishTelemetryCommands(deviceId).subscribe(commands => {
  console.log('Publish Telemetry Commands:', commands);
});
```

**27. downloadGatewayDockerComposeFile**

```javascript
const deviceId = 'your-device-id';
deviceService.downloadGatewayDockerComposeFile(deviceId).subscribe(file => {
  console.log('Docker Compose File:', file);
});
```

**28. rebootDevice**

```javascript
const deviceId = 'your-device-id';
const isBootstrapServer = false;
deviceService.rebootDevice(deviceId, isBootstrapServer).subscribe(result => {
  console.log('Device Reboot Result:', result);
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

### **DOMAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const domainService = $injector.get(self.ctx.servicesMap.get('domainService'));
```

**1. saveDomain**

```javascript
const domain = {
  name: 'my-domain.com'
};
const oauth2ClientIds = ['client1', 'client2']; // optional
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
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
  console.log('Domain Deleted:', result);
});
```

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
  console.log('Edges by IDs:', edges);
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
  name: 'My Edge',
  type: 'gateway'
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = '';
edgeService.getCustomerEdgeInfos(customerId, pageLink, type).subscribe(edges => {
  console.log('Customer Edges:', edges);
});
```

**7. assignEdgeToCustomer**

```javascript
const customerId = 'your-customer-id';
const edgeId = 'your-edge-id';
edgeService.assignEdgeToCustomer(customerId, edgeId).subscribe(assignedEdge => {
  console.log('Assigned Edge:', assignedEdge);
});
```

**8. makeEdgePublic**

```javascript
const edgeId = 'your-edge-id';
edgeService.makeEdgePublic(edgeId).subscribe(publicEdge => {
  console.log('Public Edge:', publicEdge);
});
```

**9. getTenantEdgeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = '';
edgeService.getTenantEdgeInfos(pageLink, type).subscribe(edges => {
  console.log('Tenant Edges:', edges);
});
```

**10. findByQuery**

```javascript
const query = {
  // your edge search query
};
edgeService.findByQuery(query).subscribe(edges => {
  console.log('Edges by Query:', edges);
});
```

**11. getEdgeEvents**

```javascript
const entityId = { entityType: 'EDGE', id: 'your-edge-id' };
const pageLink = {
  page: 0,
  pageSize: 10,
  textSearch: '',
  sortProperty: 'createdTime',
  sortOrder: 'DESC',
  startTime: Date.now() - 86400000,
  endTime: Date.now()
};
edgeService.getEdgeEvents(entityId, pageLink).subscribe(events => {
  console.log('Edge Events:', events);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
const edgeId = 'your-edge-id';
edgeService.findMissingToRelatedRuleChains(edgeId).subscribe(missing => {
  console.log('Missing Rule Chains:', missing);
});
```

**13. findByName**

```javascript
const edgeName = 'Edge Name';
edgeService.findByName(edgeName).subscribe(edge => {
  console.log('Edge by Name:', edge);
});
```

**14. bulkImportEdges**

```javascript
const entitiesData = {
  // your bulk import request
};
edgeService.bulkImportEdges(entitiesData).subscribe(result => {
  console.log('Bulk Import Result:', result);
});
```

**15. getEdgeInstallInstructions**

```javascript
const edgeId = 'your-edge-id';
const method = 'docker'; // or other install methods
edgeService.getEdgeInstallInstructions(edgeId, method).subscribe(instructions => {
  console.log('Install Instructions:', instructions);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
const edgeVersion = '3.5.0';
const method = 'docker';
edgeService.getEdgeUpgradeInstructions(edgeVersion, method).subscribe(instructions => {
  console.log('Upgrade Instructions:', instructions);
});
```

**17. isEdgeUpgradeAvailable**

```javascript
const edgeId = 'your-edge-id';
edgeService.isEdgeUpgradeAvailable(edgeId).subscribe(available => {
  console.log('Upgrade Available:', available);
});
```

### **ENTITIES VERSION CONTROL SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const entitiesVersionControlService = $injector.get(self.ctx.servicesMap.get('entitiesVersionControlService'));
```

**1. clearBranchList**

```javascript
entitiesVersionControlService.clearBranchList();
console.log('Branch list cleared');
```

**2. listBranches**

```javascript
entitiesVersionControlService.listBranches().subscribe(branches => {
  console.log('Branches:', branches);
});
```

**3. getEntityDataInfo**

```javascript
const externalEntityId = { entityType: 'DEVICE', id: 'your-device-id' };
const versionId = 'your-version-id';
entitiesVersionControlService.getEntityDataInfo(externalEntityId, versionId).subscribe(dataInfo => {
  console.log('Entity Data Info:', dataInfo);
});
```

**4. saveEntitiesVersion**

```javascript
const request = {
  branch: 'main',
  versionName: 'v1.0',
  entityIds: [
    { entityType: 'DEVICE', id: 'device-id-1' }
  ]
};
entitiesVersionControlService.saveEntitiesVersion(request).subscribe(result => {
  console.log('Version Creation Result:', result);
});
```

**5. getVersionCreateRequestStatus**

```javascript
const requestId = 'your-request-id';
entitiesVersionControlService.getVersionCreateRequestStatus(requestId).subscribe(status => {
  console.log('Version Create Status:', status);
});
```

**6. listEntityVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
const branch = 'main';
const externalEntityId = { entityType: 'DEVICE', id: 'your-device-id' };
entitiesVersionControlService.listEntityVersions(pageLink, branch, externalEntityId).subscribe(versions => {
  console.log('Entity Versions:', versions);
});
```

**7. listEntityTypeVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
const branch = 'main';
const entityType = 'DEVICE';
entitiesVersionControlService.listEntityTypeVersions(pageLink, branch, entityType).subscribe(versions => {
  console.log('Entity Type Versions:', versions);
});
```

**8. listVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
const branch = 'main';
entitiesVersionControlService.listVersions(pageLink, branch).subscribe(versions => {
  console.log('All Versions:', versions);
});
```

**9. loadEntitiesVersion**

```javascript
const request = {
  branch: 'main',
  versionId: 'your-version-id',
  entityTypes: ['DEVICE', 'ASSET']
};
entitiesVersionControlService.loadEntitiesVersion(request).subscribe(result => {
  console.log('Version Load Result:', result);
});
```

**10. getVersionLoadRequestStatus**

```javascript
const requestId = 'your-request-id';
entitiesVersionControlService.getVersionLoadRequestStatus(requestId).subscribe(status => {
  console.log('Version Load Status:', status);
});
```

**11. compareEntityDataToVersion**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const versionId = 'your-version-id';
entitiesVersionControlService.compareEntityDataToVersion(entityId, versionId).subscribe(diff => {
  console.log('Entity Data Diff:', diff);
});
```

**12. entityLoadErrorToMessage**

```javascript
const entityLoadError = {
  // your entity load error object
};
const message = entitiesVersionControlService.entityLoadErrorToMessage(entityLoadError);
console.log('Error Message:', message);
```

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
  from: { entityType: 'DEVICE', id: 'device-id' },
  to: { entityType: 'ASSET', id: 'asset-id' },
  type: 'Contains'
};
entityRelationService.saveRelation(relation).subscribe(savedRelation => {
  console.log('Saved Relation:', savedRelation);
});
```

**2. getRelation**

```javascript
const fromId = { entityType: 'DEVICE', id: 'device-id' };
const relationType = 'Contains';
const toId = { entityType: 'ASSET', id: 'asset-id' };
entityRelationService.getRelation(fromId, relationType, toId).subscribe(relation => {
  console.log('Relation:', relation);
});
```

**3. findByFrom**

```javascript
const fromId = { entityType: 'DEVICE', id: 'device-id' };
entityRelationService.findByFrom(fromId).subscribe(relations => {
  console.log('Relations from Entity:', relations);
});
```

**4. findInfoByFrom**

```javascript
const fromId = { entityType: 'DEVICE', id: 'device-id' };
entityRelationService.findInfoByFrom(fromId).subscribe(relationInfos => {
  console.log('Relation Infos from Entity:', relationInfos);
});
```

**5. findByFromAndType**

```javascript
const fromId = { entityType: 'DEVICE', id: 'device-id' };
const relationType = 'Contains';
entityRelationService.findByFromAndType(fromId, relationType).subscribe(relations => {
  console.log('Relations by Type:', relations);
});
```

**6. findByTo**

```javascript
const toId = { entityType: 'ASSET', id: 'asset-id' };
entityRelationService.findByTo(toId).subscribe(relations => {
  console.log('Relations to Entity:', relations);
});
```

**7. findInfoByTo**

```javascript
const toId = { entityType: 'ASSET', id: 'asset-id' };
entityRelationService.findInfoByTo(toId).subscribe(relationInfos => {
  console.log('Relation Infos to Entity:', relationInfos);
});
```

**8. findByToAndType**

```javascript
const toId = { entityType: 'ASSET', id: 'asset-id' };
const relationType = 'Contains';
entityRelationService.findByToAndType(toId, relationType).subscribe(relations => {
  console.log('Relations to Entity by Type:', relations);
});
```

**9. findByQuery**

```javascript
const query = {
  parameters: {
    rootId: { entityType: 'DEVICE', id: 'device-id' },
    direction: 'FROM'
  },
  filters: [
    {
      relationType: 'Contains'
    }
  ]
};
entityRelationService.findByQuery(query).subscribe(relations => {
  console.log('Relations by Query:', relations);
});
```

**10. findInfoByQuery**

```javascript
const query = {
  parameters: {
    rootId: { entityType: 'DEVICE', id: 'device-id' },
    direction: 'FROM'
  },
  filters: [
    {
      relationType: 'Contains'
    }
  ]
};
entityRelationService.findInfoByQuery(query).subscribe(relationInfos => {
  console.log('Relation Infos by Query:', relationInfos);
});
```

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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(tenants => {
  console.log('Single Tenant Observable:', tenants);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
entityService.getSingleCustomerByPageLinkObservable(pageLink).subscribe(customers => {
  console.log('Single Customer Observable:', customers);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
const entityType = 'DEVICE';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const subType = 'thermostat';
entityService.getEntitiesByPageLinkObservable(entityType, pageLink, subType).subscribe(entities => {
  console.log('Entities by Page Observable:', entities);
});
```

**8. getEntitiesByPageLink**

```javascript
const entityType = 'DEVICE';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const subType = 'thermostat';
entityService.getEntitiesByPageLink(entityType, pageLink, subType).subscribe(entities => {
  console.log('Entities by Page:', entities);
});
```

**9. getEntitiesByNameFilter**

```javascript
const entityType = 'DEVICE';
const entityNameFilter = 'sensor';
const pageSize = 10;
const subType = 'temperature';
entityService.getEntitiesByNameFilter(entityType, entityNameFilter, pageSize, subType).subscribe(entities => {
  console.log('Entities by Name Filter:', entities);
});
```

**10. findEntityDataByQuery**

```javascript
const query = {
  entityFilter: {
    type: 'entityType',
    entityType: 'DEVICE'
  },
  pageLink: self.ctx.pageLink(10, 0, '', 'name', 'ASC')
};
entityService.findEntityDataByQuery(query).subscribe(entityData => {
  console.log('Entity Data by Query:', entityData);
});
```

**11. findEntityKeysByQuery**

```javascript
const query = {
  entityFilter: {
    type: 'entityType',
    entityType: 'DEVICE'
  }
};
const scope = 'SERVER_SCOPE'; // optional
entityService.findEntityKeysByQuery(query, scope).subscribe(keys => {
  console.log('Entity Keys by Query:', keys);
});
```

**12. findAlarmDataByQuery**

```javascript
const query = {
  entityFilter: {
    type: 'entityType',
    entityType: 'DEVICE'
  },
  pageLink: self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC')
};
entityService.findAlarmDataByQuery(query).subscribe(alarmData => {
  console.log('Alarm Data by Query:', alarmData);
});
```

**13. findEntityInfosByFilterAndName**

```javascript
const filter = {
  type: 'entityType',
  entityType: 'DEVICE'
};
const searchText = 'sensor';
entityService.findEntityInfosByFilterAndName(filter, searchText).subscribe(entityInfos => {
  console.log('Entity Infos by Filter:', entityInfos);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
const filter = {
  type: 'entityType',
  entityType: 'DEVICE'
};
entityService.findSingleEntityInfoByEntityFilter(filter).subscribe(entityInfo => {
  console.log('Single Entity Info:', entityInfo);
});
```

**15. getAliasFilterTypesByEntityTypes**

```javascript
const entityTypes = ['DEVICE', 'ASSET'];
const filterTypes = entityService.getAliasFilterTypesByEntityTypes(entityTypes);
console.log('Alias Filter Types:', filterTypes);
```

**16. filterAliasByEntityTypes**

```javascript
const entityAlias = {
  // your entity alias object
};
const entityTypes = ['DEVICE', 'ASSET'];
const filtered = entityService.filterAliasByEntityTypes(entityAlias, entityTypes);
console.log('Filtered Alias:', filtered);
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
const aliasFilterType = 'entityType';
const entityTypes = ['DEVICE', 'ASSET'];
const filtered = entityService.filterAliasFilterTypeByEntityTypes(aliasFilterType, entityTypes);
console.log('Filtered Filter Type:', filtered);
```

**18. filterAliasFilterTypeByEntityType**

```javascript
const aliasFilterType = 'entityType';
const entityType = 'DEVICE';
const filtered = entityService.filterAliasFilterTypeByEntityType(aliasFilterType, entityType);
console.log('Filtered by Entity Type:', filtered);
```

**19. prepareAllowedEntityTypesList**

```javascript
const allowedEntityTypes = ['DEVICE', 'ASSET'];
const useAliasEntityTypes = true; // optional
const prepared = entityService.prepareAllowedEntityTypesList(allowedEntityTypes, useAliasEntityTypes);
console.log('Prepared Entity Types:', prepared);
```

**20. getEntityFieldKeys**

```javascript
const entityType = 'DEVICE';
const searchText = 'name';
const keys = entityService.getEntityFieldKeys(entityType, searchText);
console.log('Entity Field Keys:', keys);
```

**21. getAlarmKeys**

```javascript
const searchText = 'temperature';
const keys = entityService.getAlarmKeys(searchText);
console.log('Alarm Keys:', keys);
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
  type: 'entityType',
  entityType: 'DEVICE'
};
const types = ['timeseries', 'attributes'];
const entityTypes = ['DEVICE']; // optional
entityService.getEntityKeysByEntityFilter(filter, types, entityTypes).subscribe(keys => {
  console.log('Keys by Entity Filter:', keys);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
const filter = {
  type: 'entityType',
  entityType: 'DEVICE'
};
const types = ['timeseries', 'attributes'];
const entityTypes = ['DEVICE']; // optional
const scope = 'SERVER_SCOPE'; // optional
entityService.getEntityKeysByEntityFilterAndScope(filter, types, entityTypes, scope).subscribe(keys => {
  console.log('Keys by Filter and Scope:', keys);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
const subscriptionsInfo = [
  // your subscription info array
];
const datasources = entityService.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo);
console.log('Datasources from Subscriptions:', datasources);
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
const subscriptionInfo = {
  // your subscription info object
};
const alarmSource = entityService.createAlarmSourceFromSubscriptionInfo(subscriptionInfo);
console.log('Alarm Source:', alarmSource);
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
const edgeId = 'your-edge-id';
const entityType = 'DEVICE';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
entityService.getAssignedToEdgeEntitiesByType(edgeId, entityType, pageLink).subscribe(entities => {
  console.log('Edge Entities by Type:', entities);
});
```

**28. getEntitySubtypesObservable**

```javascript
const entityType = 'DEVICE';
entityService.getEntitySubtypesObservable(entityType).subscribe(subtypes => {
  console.log('Entity Subtypes:', subtypes);
});
```

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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = ''; // empty string for all types
entityViewService.getTenantEntityViewInfos(pageLink, type).subscribe(entityViews => {
  console.log('Tenant Entity Views:', entityViews);
});
```

**2. getCustomerEntityViewInfos**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = '';
entityViewService.getCustomerEntityViewInfos(customerId, pageLink, type).subscribe(entityViews => {
  console.log('Customer Entity Views:', entityViews);
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
  console.log('Entity Views by IDs:', entityViews);
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
  name: 'My Entity View',
  type: 'temperature_view'
};
entityViewService.saveEntityView(entityView).subscribe(savedView => {
  console.log('Saved Entity View:', savedView);
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
entityViewService.makeEntityViewPublic(entityViewId).subscribe(publicView => {
  console.log('Public Entity View:', publicView);
});
```

**9. assignEntityViewToCustomer**

```javascript
const customerId = 'your-customer-id';
const entityViewId = 'your-entity-view-id';
entityViewService.assignEntityViewToCustomer(customerId, entityViewId).subscribe(assignedView => {
  console.log('Assigned Entity View:', assignedView);
});
```

**10. findByQuery**

```javascript
const query = {
  // your entity view search query
};
entityViewService.findByQuery(query).subscribe(entityViews => {
  console.log('Entity Views by Query:', entityViews);
});
```

**11. assignEntityViewToEdge**

```javascript
const edgeId = 'your-edge-id';
const entityViewId = 'your-entity-view-id';
entityViewService.assignEntityViewToEdge(edgeId, entityViewId).subscribe(assigned => {
  console.log('Entity View Assigned to Edge:', assigned);
});
```

**12. getEdgeEntityViews**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = '';
entityViewService.getEdgeEntityViews(edgeId, pageLink, type).subscribe(edgeViews => {
  console.log('Edge Entity Views:', edgeViews);
});
```

### **EVENT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const eventService = $injector.get(self.ctx.servicesMap.get('eventService'));
```

**1. getEvents**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const eventType = 'STATS';
const tenantId = 'your-tenant-id';
const pageLink = {
  page: 0,
  pageSize: 10,
  textSearch: '',
  sortProperty: 'createdTime',
  sortOrder: 'DESC',
  startTime: Date.now() - 86400000,
  endTime: Date.now()
};
eventService.getEvents(entityId, eventType, tenantId, pageLink).subscribe(events => {
  console.log('Events:', events);
});
```

**2. getFilterEvents**

```javascript
const entityId = { entityType: 'DEVICE', id: 'your-device-id' };
const eventType = 'STATS';
const tenantId = 'your-tenant-id';
const filters = {
  msgType: 'POST_TELEMETRY_REQUEST'
};
const pageLink = {
  page: 0,
  pageSize: 10,
  textSearch: '',
  sortProperty: 'createdTime',
  sortOrder: 'DESC',
  startTime: Date.now() - 86400000,
  endTime: Date.now()
};
eventService.getFilterEvents(entityId, eventType, tenantId, filters, pageLink).subscribe(events => {
  console.log('Filtered Events:', events);
});
```

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

### **IMAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
```

**1. uploadImage**

```javascript
const file = event.target.files[0]; // from file input
const title = 'My Image';
const imageSubType = 'dashboard';
imageService.uploadImage(file, title, imageSubType).subscribe(imageInfo => {
  console.log('Uploaded Image:', imageInfo);
});
```

**2. updateImage**

```javascript
const type = 'SYSTEM';
const key = 'image-key';
const file = event.target.files[0]; // from file input
imageService.updateImage(type, key, file).subscribe(updatedImage => {
  console.log('Updated Image:', updatedImage);
});
```

**3. updateImageInfo**

```javascript
const imageInfo = {
  // your image info object
};
imageService.updateImageInfo(imageInfo).subscribe(updated => {
  console.log('Updated Image Info:', updated);
});
```

**4. updateImagePublicStatus**

```javascript
const imageInfo = {
  // your image info object
};
const isPublic = true;
imageService.updateImagePublicStatus(imageInfo, isPublic).subscribe(updated => {
  console.log('Updated Public Status:', updated);
});
```

**5. getImages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
const imageSubType = 'dashboard';
imageService.getImages(pageLink, imageSubType).subscribe(images => {
  console.log('Images:', images);
});
```

**6. getImageInfo**

```javascript
const type = 'SYSTEM';
const key = 'image-key';
imageService.getImageInfo(type, key).subscribe(imageInfo => {
  console.log('Image Info:', imageInfo);
});
```

**7. getImageDataUrl**

```javascript
const imageUrl = '/api/images/system/image-key';
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
const imageUrl = '/api/images/system/image-key';
imageService.getImageString(imageUrl).subscribe(imageString => {
  console.log('Image String:', imageString);
});
```

**10. resolveImageUrl**

```javascript
const imageUrl = '/api/images/system/image-key';
imageService.resolveImageUrl(imageUrl).subscribe(resolvedUrl => {
  console.log('Resolved Image URL:', resolvedUrl);
});
```

**11. downloadImage**

```javascript
const type = 'SYSTEM';
const key = 'image-key';
imageService.downloadImage(type, key).subscribe(downloadResult => {
  console.log('Image Downloaded:', downloadResult);
});
```

**12. exportImage**

```javascript
const type = 'SYSTEM';
const key = 'image-key';
imageService.exportImage(type, key).subscribe(exportData => {
  console.log('Exported Image:', exportData);
});
```

**13. importImage**

```javascript
const imageData = {
  // your image export data
};
imageService.importImage(imageData).subscribe(importedImage => {
  console.log('Imported Image:', importedImage);
});
```

### **MOBILE APP SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const mobileAppService = $injector.get(self.ctx.servicesMap.get('mobileAppService'));
```

**1. saveMobileApp**

```javascript
const mobileApp = {
  appName: 'My Mobile App',
  pkgName: 'com.example.myapp'
};
mobileAppService.saveMobileApp(mobileApp).subscribe(savedApp => {
  console.log('Saved Mobile App:', savedApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'appName', 'ASC');
const platformType = 'ANDROID'; // optional: ANDROID, IOS
mobileAppService.getTenantMobileAppInfos(pageLink, platformType).subscribe(apps => {
  console.log('Tenant Mobile Apps:', apps);
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
  console.log('Mobile App Deleted:', result);
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(bundles => {
  console.log('Mobile App Bundles:', bundles);
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
  console.log('Mobile App Bundle Deleted:', result);
});
```

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
mobileApplicationService.saveMobileAppSettings(mobileAppSettings).subscribe(saved => {
  console.log('Saved Mobile App Settings:', saved);
});
```

**3. getMobileAppDeepLink**

```javascript
mobileApplicationService.getMobileAppDeepLink().subscribe(deepLink => {
  console.log('Mobile App Deep Link:', deepLink);
});
```

### **NOTIFICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const notificationService = $injector.get(self.ctx.servicesMap.get('notificationService'));
```

**1. getNotifications**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
notificationService.getNotifications(pageLink).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
const id = 'your-notification-id';
notificationService.deleteNotification(id).subscribe(result => {
  console.log('Notification Deleted:', result);
});
```

**3. markNotificationAsRead**

```javascript
const id = 'your-notification-id';
notificationService.markNotificationAsRead(id).subscribe(result => {
  console.log('Notification Marked as Read:', result);
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(result => {
  console.log('All Notifications Marked as Read:', result);
});
```

**5. createNotificationRequest**

```javascript
const notification = {
  targets: ['user-id-1', 'user-id-2'],
  templateId: 'your-template-id',
  info: {
    subject: 'Test Notification',
    message: 'This is a test'
  }
};
notificationService.createNotificationRequest(notification).subscribe(created => {
  console.log('Created Notification Request:', created);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
const entityType = 'DEVICE';
notificationService.sendEntitiesLimitIncreaseRequest(entityType).subscribe(result => {
  console.log('Limit Increase Request Sent:', result);
});
```

**7. getNotificationRequestById**

```javascript
const id = 'your-notification-request-id';
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
const id = 'your-notification-request-id';
notificationService.deleteNotificationRequest(id).subscribe(result => {
  console.log('Notification Request Deleted:', result);
});
```

**10. getNotificationRequestPreview**

```javascript
const notification = {
  targets: ['user-id-1'],
  templateId: 'your-template-id',
  info: {
    subject: 'Preview Test',
    message: 'This is a preview'
  }
};
notificationService.getNotificationRequestPreview(notification).subscribe(preview => {
  console.log('Notification Preview:', preview);
});
```

**11. getNotificationRequests**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
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
notificationService.saveNotificationSettings(notificationSettings).subscribe(saved => {
  console.log('Saved Notification Settings:', saved);
});
```

**14. listSlackConversations**

```javascript
const type = 'PUBLIC_CHANNEL';
const token = 'your-slack-token'; // optional
notificationService.listSlackConversations(type, token).subscribe(conversations => {
  console.log('Slack Conversations:', conversations);
});
```

**15. saveNotificationRule**

```javascript
const notificationRule = {
  name: 'Temperature Alert',
  enabled: true
};
notificationService.saveNotificationRule(notificationRule).subscribe(saved => {
  console.log('Saved Notification Rule:', saved);
});
```

**16. getNotificationRuleById**

```javascript
const id = 'your-notification-rule-id';
notificationService.getNotificationRuleById(id).subscribe(rule => {
  console.log('Notification Rule:', rule);
});
```

**17. deleteNotificationRule**

```javascript
const id = 'your-notification-rule-id';
notificationService.deleteNotificationRule(id).subscribe(result => {
  console.log('Notification Rule Deleted:', result);
});
```

**18. getNotificationRules**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
notificationService.getNotificationRules(pageLink).subscribe(rules => {
  console.log('Notification Rules:', rules);
});
```

**19. saveNotificationTarget**

```javascript
const notificationTarget = {
  name: 'Email Recipients',
  type: 'EMAIL'
};
notificationService.saveNotificationTarget(notificationTarget).subscribe(saved => {
  console.log('Saved Notification Target:', saved);
});
```

**20. getNotificationTargetById**

```javascript
const id = 'your-notification-target-id';
notificationService.getNotificationTargetById(id).subscribe(target => {
  console.log('Notification Target:', target);
});
```

**21. deleteNotificationTarget**

```javascript
const id = 'your-notification-target-id';
notificationService.deleteNotificationTarget(id).subscribe(result => {
  console.log('Notification Target Deleted:', result);
});
```

**22. getNotificationTargetsByIds**

```javascript
const ids = ['target-id-1', 'target-id-2'];
notificationService.getNotificationTargetsByIds(ids).subscribe(targets => {
  console.log('Notification Targets:', targets);
});
```

**23. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'EMAIL'; // optional
notificationService.getNotificationTargets(pageLink, type).subscribe(targets => {
  console.log('Notification Targets:', targets);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
const notificationTarget = {
  // your notification target object
};
const pageLink = self.ctx.pageLink(10, 0, '', 'email', 'ASC');
notificationService.getRecipientsForNotificationTargetConfig(notificationTarget, pageLink).subscribe(recipients => {
  console.log('Notification Recipients:', recipients);
});
```

**25. saveNotificationTemplate**

```javascript
const notificationTemplate = {
  name: 'Alert Template',
  notificationType: 'GENERAL'
};
notificationService.saveNotificationTemplate(notificationTemplate).subscribe(saved => {
  console.log('Saved Notification Template:', saved);
});
```

**26. getNotificationTemplateById**

```javascript
const id = 'your-notification-template-id';
notificationService.getNotificationTemplateById(id).subscribe(template => {
  console.log('Notification Template:', template);
});
```

**27. deleteNotificationTemplate**

```javascript
const id = 'your-notification-template-id';
notificationService.deleteNotificationTemplate(id).subscribe(result => {
  console.log('Notification Template Deleted:', result);
});
```

**28. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const notificationTypes = 'GENERAL'; // optional
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
notificationService.saveNotificationUserSettings(settings).subscribe(saved => {
  console.log('Saved User Settings:', saved);
});
```

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
  title: 'My OAuth2 Client'
};
oAuth2Service.saveOAuth2Client(oAuth2Client).subscribe(saved => {
  console.log('Saved OAuth2 Client:', saved);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(clients => {
  console.log('Tenant OAuth2 Clients:', clients);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
const clientIds = ['client-id-1', 'client-id-2'];
oAuth2Service.findTenantOAuth2ClientInfosByIds(clientIds).subscribe(clients => {
  console.log('OAuth2 Clients by IDs:', clients);
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
  console.log('OAuth2 Client Deleted:', result);
});
```

**7. getLoginProcessingUrl**

```javascript
oAuth2Service.getLoginProcessingUrl().subscribe(url => {
  console.log('Login Processing URL:', url);
});
```

### **OTA PACKAGE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const otaPackageService = $injector.get(self.ctx.servicesMap.get('otaPackageService'));
```

**1. getOtaPackages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
otaPackageService.getOtaPackages(pageLink).subscribe(packages => {
  console.log('OTA Packages:', packages);
});
```

**2. getOtaPackagesInfoByDeviceProfileId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
const deviceProfileId = 'your-device-profile-id';
const type = 'FIRMWARE';
otaPackageService.getOtaPackagesInfoByDeviceProfileId(pageLink, deviceProfileId, type).subscribe(packages => {
  console.log('OTA Packages by Profile:', packages);
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
otaPackageService.downloadOtaPackage(otaPackageId).subscribe(download => {
  console.log('OTA Package Downloaded:', download);
});
```

**6. saveOtaPackage**

```javascript
const otaPackage = {
  title: 'Firmware v1.0',
  version: '1.0'
};
otaPackageService.saveOtaPackage(otaPackage).subscribe(saved => {
  console.log('Saved OTA Package:', saved);
});
```

**7. saveOtaPackageInfo**

```javascript
const otaPackageInfo = {
  title: 'Firmware v1.0',
  version: '1.0'
};
otaPackageService.saveOtaPackageInfo(otaPackageInfo).subscribe(saved => {
  console.log('Saved OTA Package Info:', saved);
});
```

**8. uploadOtaPackageFile**

```javascript
const otaPackageId = 'your-ota-package-id';
const file = event.target.files[0]; // from file input
const checksumAlgorithm = 'MD5';
const checksum = 'abc123'; // optional
otaPackageService.uploadOtaPackageFile(otaPackageId, file, checksumAlgorithm, checksum).subscribe(result => {
  console.log('OTA Package File Uploaded:', result);
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
const type = 'FIRMWARE';
const entityId = { entityType: 'DEVICE_PROFILE', id: 'your-profile-id' };
otaPackageService.countUpdateDeviceAfterChangePackage(type, entityId).subscribe(count => {
  console.log('Update Device Count:', count);
});
```

**10. confirmDialogUpdatePackage**

```javascript
const entity = {
  // your entity with OTA pages IDs
};
const originEntity = {
  // original entity with OTA pages IDs
};
otaPackageService.confirmDialogUpdatePackage(entity, originEntity).subscribe(confirmed => {
  console.log('Dialog Confirmed:', confirmed);
});
```

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
  console.log('Queue by ID:', queue);
});
```

**2. getQueueByName**

```javascript
const queueName = 'Main';
queueService.getQueueByName(queueName).subscribe(queue => {
  console.log('Queue by Name:', queue);
});
```

**3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const serviceType = 'TB_RULE_ENGINE';
queueService.getTenantQueuesByServiceType(pageLink, serviceType).subscribe(queues => {
  console.log('Tenant Queues:', queues);
});
```

**4. saveQueue**

```javascript
const queue = {
  name: 'Custom Queue',
  topic: 'custom.queue'
};
const serviceType = 'TB_RULE_ENGINE';
queueService.saveQueue(queue, serviceType).subscribe(saved => {
  console.log('Saved Queue:', saved);
});
```

**5. getQueueStatistics**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'queueName', 'ASC');
queueService.getQueueStatistics(pageLink).subscribe(statistics => {
  console.log('Queue Statistics:', statistics);
});
```

**6. getQueueStatisticsById**

```javascript
const queueStatId = 'your-queue-stat-id';
queueService.getQueueStatisticsById(queueStatId).subscribe(statistics => {
  console.log('Queue Statistics by ID:', statistics);
});
```

**7. getQueueStatisticsByIds**

```javascript
const queueStatIds = ['stat-id-1', 'stat-id-2'];
queueService.getQueueStatisticsByIds(queueStatIds).subscribe(statistics => {
  console.log('Queue Statistics by IDs:', statistics);
});
```

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
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
const resourceType = 'JS_MODULE'; // optional
const resourceSubType = 'EXTENSION'; // optional
resourceService.getResources(pageLink, resourceType, resourceSubType).subscribe(resources => {
  console.log('Resources:', resources);
});
```

**2. getTenantResources**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
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
const type = 'JS_MODULE';
const scope = 'TENANT';
const key = 'my-resource-key';
resourceService.getResourceInfo(type, scope, key).subscribe(resourceInfo => {
  console.log('Resource Info by Key:', resourceInfo);
});
```

**6. downloadResource**

```javascript
const resourceId = 'your-resource-id';
resourceService.downloadResource(resourceId).subscribe(download => {
  console.log('Resource Downloaded:', download);
});
```

**7. saveResources**

```javascript
const resources = [
  {
    title: 'My Resource',
    resourceType: 'JS_MODULE',
    data: 'function myFunction() { return true; }'
  }
];
resourceService.saveResources(resources).subscribe(saved => {
  console.log('Saved Resources:', saved);
});
```

**8. saveResource**

```javascript
const resource = {
  title: 'My Resource',
  resourceType: 'JS_MODULE',
  data: 'function myFunction() { return true; }'
};
resourceService.saveResource(resource).subscribe(saved => {
  console.log('Saved Resource:', saved);
});
```

**9. uploadResources**

```javascript
const resources = [
  {
    title: 'Uploaded Resource',
    resourceType: 'JS_MODULE',
    data: 'function uploadedFunction() { return true; }'
  }
];
resourceService.uploadResources(resources).subscribe(uploaded => {
  console.log('Uploaded Resources:', uploaded);
});
```

**10. uploadResource**

```javascript
const resource = {
  title: 'Uploaded Resource',
  resourceType: 'JS_MODULE',
  data: 'function uploadedFunction() { return true; }'
};
resourceService.uploadResource(resource).subscribe(uploaded => {
  console.log('Uploaded Resource:', uploaded);
});
```

**11. updatedResourceInfo**

```javascript
const resourceId = 'your-resource-id';
const updatedResources = {
  title: 'Updated Title',
  description: 'Updated description'
};
resourceService.updatedResourceInfo(resourceId, updatedResources).subscribe(updated => {
  console.log('Updated Resource Info:', updated);
});
```

**12. updatedResourceData**

```javascript
const resourceId = 'your-resource-id';
const data = new File(['new data content'], 'resource.js');
resourceService.updatedResourceData(resourceId, data).subscribe(updated => {
  console.log('Updated Resource Data:', updated);
});
```

**13. getResourcesByIds**

```javascript
const ids = ['resource-id-1', 'resource-id-2'];
resourceService.getResourcesByIds(ids).subscribe(resources => {
  console.log('Resources by IDs:', resources);
});
```

### **RULE CHAIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const ruleChainService = $injector.get(self.ctx.servicesMap.get('ruleChainService'));
```

**1. getRuleChains**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'CORE';
ruleChainService.getRuleChains(pageLink, type).subscribe(ruleChains => {
  console.log('Rule Chains:', ruleChains);
});
```

**2. getRuleChainsByIds**

```javascript
const ruleChainIds = ['chain-id-1', 'chain-id-2'];
ruleChainService.getRuleChainsByIds(ruleChainIds).subscribe(ruleChains => {
  console.log('Rule Chains by IDs:', ruleChains);
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
  name: 'My Rule Chain',
  type: 'CORE'
};
ruleChainService.saveRuleChain(ruleChain).subscribe(saved => {
  console.log('Saved Rule Chain:', saved);
});
```

**7. setRootRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setRootRuleChain(ruleChainId).subscribe(rootChain => {
  console.log('Set Root Rule Chain:', rootChain);
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
ruleChainService.saveRuleChainMetadata(ruleChainMetaData).subscribe(saved => {
  console.log('Saved Rule Chain Metadata:', saved);
});
```

**10. getRuleNodeComponents**

```javascript
const modulesMap = {
  // your modules map
};
const ruleChainType = 'CORE';
ruleChainService.getRuleNodeComponents(modulesMap, ruleChainType).subscribe(components => {
  console.log('Rule Node Components:', components);
});
```

**11. getRuleNodeConfigComponent**

```javascript
const directive = 'tbFilterNodeConfig';
const component = ruleChainService.getRuleNodeConfigComponent(directive);
console.log('Rule Node Config Component:', component);
```

**12. getRuleNodeComponentByClazz**

```javascript
const ruleChainType = 'CORE';
const clazz = 'org.thingsboard.rule.engine.filter.TbMsgTypeFilter';
const component = ruleChainService.getRuleNodeComponentByClazz(ruleChainType, clazz);
console.log('Rule Node Component:', component);
```

**13. getRuleNodeSupportedLinks**

```javascript
const component = {
  // your rule node component descriptor
};
const links = ruleChainService.getRuleNodeSupportedLinks(component);
console.log('Supported Links:', links);
```

**14. ruleNodeAllowCustomLinks**

```javascript
const component = {
  // your rule node component descriptor
};
const allowsCustom = ruleChainService.ruleNodeAllowCustomLinks(component);
console.log('Allows Custom Links:', allowsCustom);
```

**15. ruleNodeSourceRuleChainId**

```javascript
const component = {
  // your rule node component descriptor
};
const config = {
  // your rule node configuration
};
const sourceId = ruleChainService.ruleNodeSourceRuleChainId(component, config);
console.log('Source Rule Chain ID:', sourceId);
```

**16. getLatestRuleNodeDebugInput**

```javascript
const ruleNodeId = 'your-rule-node-id';
ruleChainService.getLatestRuleNodeDebugInput(ruleNodeId).subscribe(debugInput => {
  console.log('Latest Debug Input:', debugInput);
});
```

**17. testScript**

```javascript
const inputParams = {
  script: 'return msg.temperature > 25;',
  msg: { temperature: 30 },
  metadata: {},
  msgType: 'POST_TELEMETRY_REQUEST'
};
const scriptLang = 'JS'; // optional
ruleChainService.testScript(inputParams, scriptLang).subscribe(result => {
  console.log('Script Test Result:', result);
});
```

**18. loadRuleNodeComponents**

```javascript
const ruleChainType = 'CORE';
ruleChainService.loadRuleNodeComponents(ruleChainType).subscribe(components => {
  console.log('Loaded Rule Node Components:', components);
});
```

**19. resolveRuleNodeComponentsUiResources**

```javascript
const components = [
  // your rule node component descriptors
];
const modulesMap = {
  // your modules map
};
ruleChainService.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(resolved => {
  console.log('Resolved UI Resources:', resolved);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
const component = {
  // your rule node component descriptor
};
const modulesMap = {
  // your modules map
};
ruleChainService.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(resolved => {
  console.log('Resolved Component UI Resources:', resolved);
});
```

**21. getEdgeRuleChains**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
ruleChainService.getEdgeRuleChains(edgeId, pageLink).subscribe(edgeChains => {
  console.log('Edge Rule Chains:', edgeChains);
});
```

**22. assignRuleChainToEdge**

```javascript
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.assignRuleChainToEdge(edgeId, ruleChainId).subscribe(assigned => {
  console.log('Assigned to Edge:', assigned);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeTemplateRootRuleChain(ruleChainId).subscribe(templateRoot => {
  console.log('Set Edge Template Root:', templateRoot);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setAutoAssignToEdgeRuleChain(ruleChainId).subscribe(autoAssign => {
  console.log('Set Auto Assign to Edge:', autoAssign);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.unsetAutoAssignToEdgeRuleChain(ruleChainId).subscribe(unset => {
  console.log('Unset Auto Assign to Edge:', unset);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoAssignChains => {
  console.log('Auto Assign Rule Chains:', autoAssignChains);
});
```

**27. setEdgeRootRuleChain**

```javascript
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeRootRuleChain(edgeId, ruleChainId).subscribe(edge => {
  console.log('Set Edge Root Rule Chain:', edge);
});
```

### **TENANT PROFILE SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantProfileService = $injector.get(self.ctx.servicesMap.get('tenantProfileService'));
```

**1. getTenantProfiles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
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
  name: 'My Tenant Profile'
};
tenantProfileService.saveTenantProfile(tenantProfile).subscribe(saved => {
  console.log('Saved Tenant Profile:', saved);
});
```

**4. setDefaultTenantProfile**

```javascript
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.setDefaultTenantProfile(tenantProfileId).subscribe(defaultProfile => {
  console.log('Default Tenant Profile:', defaultProfile);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(infos => {
  console.log('Tenant Profile Infos:', infos);
});
```

**8. getTenantProfilesByIds**

```javascript
const tenantProfileIds = ['id1', 'id2', 'id3'];
tenantProfileService.getTenantProfilesByIds(tenantProfileIds).subscribe(profiles => {
  console.log('Tenant Profiles by IDs:', profiles);
});
```

### **TENANT SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const tenantService = $injector.get(self.ctx.servicesMap.get('tenantService'));
```

**1. getTenants**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
tenantService.getTenants(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
const tenantIds = ['id1', 'id2', 'id3'];
tenantService.getTenantsByIds(tenantIds).subscribe(tenants => {
  console.log('Tenants by IDs:', tenants);
});
```

**3. getTenantInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
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
  title: 'My Tenant',
  email: 'tenant@example.com'
};
tenantService.saveTenant(tenant).subscribe(saved => {
  console.log('Saved Tenant:', saved);
});
```

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
  // your Trendz settings object
};
trendzSettingsService.saveTrendzSettings(trendzSettings).subscribe(saved => {
  console.log('Saved Trendz Settings:', saved);
});
```

### **TWO FACTOR AUTHENTICATION SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const twoFactorAuthenticationService = $injector.get(self.ctx.servicesMap.get('twoFactorAuthenticationService'));
```

**1. getTwoFaSettings**

```javascript
twoFactorAuthenticationService.getTwoFaSettings().subscribe(settings => {
  console.log('Two FA Settings:', settings);
});
```

**2. saveTwoFaSettings**

```javascript
const settings = {
  // your two factor auth settings
};
twoFactorAuthenticationService.saveTwoFaSettings(settings).subscribe(saved => {
  console.log('Saved Two FA Settings:', saved);
});
```

**3. getAvailableTwoFaProviders**

```javascript
twoFactorAuthenticationService.getAvailableTwoFaProviders().subscribe(providers => {
  console.log('Available Two FA Providers:', providers);
});
```

**4. generateTwoFaAccountConfig**

```javascript
const providerType = 'TOTP';
twoFactorAuthenticationService.generateTwoFaAccountConfig(providerType).subscribe(config => {
  console.log('Generated Account Config:', config);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(settings => {
  console.log('Account Two FA Settings:', settings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
const providerType = 'TOTP';
const useByDefault = true;
twoFactorAuthenticationService.updateTwoFaAccountConfig(providerType, useByDefault).subscribe(updated => {
  console.log('Updated Account Config:', updated);
});
```

**7. submitTwoFaAccountConfig**

```javascript
const authConfig = {
  // your two factor auth config
};
twoFactorAuthenticationService.submitTwoFaAccountConfig(authConfig).subscribe(result => {
  console.log('Submitted Config:', result);
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
const authConfig = {
  // your two factor auth config
};
const verificationCode = 123456; // optional
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(authConfig, verificationCode).subscribe(verified => {
  console.log('Verified and Saved Config:', verified);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
const providerType = 'TOTP';
twoFactorAuthenticationService.deleteTwoFaAccountConfig(providerType).subscribe(deleted => {
  console.log('Deleted Account Config:', deleted);
});
```

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

### **USAGE INFO SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const usageInfoService = $injector.get(self.ctx.servicesMap.get('usageInfoService'));
```

**1. getUsageInfo**

```javascript
usageInfoService.getUsageInfo().subscribe(usageInfo => {
  console.log('Usage Info:', usageInfo);
});
```

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
const pageLink = self.ctx.pageLink(10, 0, '', 'email', 'ASC');
userService.getUsers(pageLink).subscribe(users => {
  console.log('List of Users:', users);
});
```

**2. getTenantAdmins**

```javascript
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'email', 'ASC');
userService.getTenantAdmins(tenantId, pageLink).subscribe(admins => {
  console.log('Tenant Admins:', admins);
});
```

**3. getCustomerUsers**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'email', 'ASC');
userService.getCustomerUsers(customerId, pageLink).subscribe(users => {
  console.log('Customer Users:', users);
});
```

**4. getUsersForAssign**

```javascript
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'email', 'ASC');
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
  console.log('Users by IDs:', users);
});
```

**7. saveUser**

```javascript
const user = {
  email: 'newuser@example.com',
  firstName: 'John',
  lastName: 'Doe'
};
const sendActivationMail = true;
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
const userCredentialsEnabled = true; // optional
userService.setUserCredentialsEnabled(userId, userCredentialsEnabled).subscribe(result => {
  console.log('User Credentials Enabled:', result);
});
```

**11. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'john', 'email', 'ASC');
userService.findUsersByQuery(pageLink).subscribe(users => {
  console.log('Users by Query:', users);
});
```

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
userSettingsService.saveUserSettings(userSettings).subscribe(saved => {
  console.log('Saved User Settings:', saved);
});
```

**3. putUserSettings**

```javascript
const userSettingsData = {
  // partial user settings data to update
};
userSettingsService.putUserSettings(userSettingsData).subscribe(result => {
  console.log('Updated User Settings:', result);
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
userSettingsService.getQuickLinks().subscribe(quickLinks => {
  console.log('Quick Links:', quickLinks);
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
const action = 'VISIT';
userSettingsService.reportUserDashboardAction(dashboardId, action).subscribe(updated => {
  console.log('Dashboard Action Reported:', updated);
});
```

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
  console.log('All Widget Bundles:', bundles);
});
```

**3. getSystemWidgetsBundles**

```javascript
widgetService.getSystemWidgetsBundles().subscribe(bundles => {
  console.log('System Widget Bundles:', bundles);
});
```

**4. getTenantWidgetsBundles**

```javascript
widgetService.getTenantWidgetsBundles().subscribe(bundles => {
  console.log('Tenant Widget Bundles:', bundles);
});
```

**5. getWidgetBundles**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
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
widgetService.exportWidgetsBundle(widgetsBundleId).subscribe(exported => {
  console.log('Exported Widgets Bundle:', exported);
});
```

**8. saveWidgetsBundle**

```javascript
const widgetsBundle = {
  title: 'My Widget Bundle',
  description: 'Custom widgets'
};
widgetService.saveWidgetsBundle(widgetsBundle).subscribe(saved => {
  console.log('Saved Widgets Bundle:', saved);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeIds = ['type-id-1', 'type-id-2'];
widgetService.updateWidgetsBundleWidgetTypes(widgetsBundleId, widgetTypeIds).subscribe(result => {
  console.log('Updated Bundle Widget Types:', result);
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeFqns = ['bundle.widget1', 'bundle.widget2'];
widgetService.updateWidgetsBundleWidgetFqns(widgetsBundleId, widgetTypeFqns).subscribe(result => {
  console.log('Updated Bundle Widget FQNs:', result);
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
  console.log('Exported Widget Type Details:', details);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypes = 'latest';
widgetService.getBundleWidgetTypeInfos(pageLink, widgetsBundleId, widgetTypes).subscribe(infos => {
  console.log('Bundle Widget Type Infos:', infos);
});
```

**16. getWidgetType**

```javascript
const fullFqn = 'bundle.widgetType';
widgetService.getWidgetType(fullFqn).subscribe(widgetType => {
  console.log('Widget Type:', widgetType);
});
```

**17. saveWidgetTypeDetails**

```javascript
const widgetInfo = {
  // your widget info object
};
const id = { id: 'widget-type-id', entityType: 'WIDGET_TYPE' };
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
widgetService.saveImportedWidgetTypeDetails(widgetTypeDetails).subscribe(saved => {
  console.log('Saved Imported Widget Type:', saved);
});
```

**19. getWidgetTypeById**

```javascript
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeById(widgetTypeId).subscribe(widgetType => {
  console.log('Widget Type by ID:', widgetType);
});
```

**20. exportWidgetType**

```javascript
const widgetTypeId = 'your-widget-type-id';
widgetService.exportWidgetType(widgetTypeId).subscribe(exported => {
  console.log('Exported Widget Type:', exported);
});
```

**21. getWidgetTypeInfoById**

```javascript
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeInfoById(widgetTypeId).subscribe(info => {
  console.log('Widget Type Info:', info);
});
```

**22. saveWidgetType**

```javascript
const widgetTypeDetails = {
  // your widget type details object
};
widgetService.saveWidgetType(widgetTypeDetails).subscribe(saved => {
  console.log('Saved Widget Type:', saved);
});
```

**23. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const widgetTypes = 'latest';
widgetService.getWidgetTypes(pageLink, widgetTypes).subscribe(types => {
  console.log('Widget Types:', types);
});
```

**24. getWidgetTemplate**

```javascript
const widgetTypeParam = 'charts';
widgetService.getWidgetTemplate(widgetTypeParam).subscribe(template => {
  console.log('Widget Template:', template);
});
```

**25. getWidgetInfoFromCache**

```javascript
const fullFqn = 'bundle.widgetType';
const widgetInfo = widgetService.getWidgetInfoFromCache(fullFqn);
console.log('Widget Info from Cache:', widgetInfo);
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
const selector = 'tb-basic-chart-config';
const component = widgetService.getBasicWidgetSettingsComponentBySelector(selector);
console.log('Basic Widget Settings Component:', component);
```

**27. getWidgetSettingsComponentTypeBySelector**

```javascript
const selector = 'tb-chart-config';
const componentType = widgetService.getWidgetSettingsComponentTypeBySelector(selector);
console.log('Widget Settings Component Type:', componentType);
```

**28. widgetTypeUpdated**

```javascript
const updatedWidgetType = {
  // your updated widget type
};
widgetService.widgetTypeUpdated(updatedWidgetType);
console.log('Widget Type Updated');
```

**29. getWidgetsBundlesByIds**

```javascript
const widgetsBundleIds = ['bundle-id-1', 'bundle-id-2'];
widgetService.getWidgetsBundlesByIds(widgetsBundleIds).subscribe(bundles => {
  console.log('Widget Bundles by IDs:', bundles);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(result => {
  console.log('Loaded Widget Bundle Cache:', result);
});
```

---

## Full Documentation Generated

This complete documentation covers all 41 widget services with 459+ methods available in ThingsBoard Community Edition. Each method includes working code examples that you can copy directly into your widget development or custom actions.

The services are organized alphabetically for easy reference, and each includes proper injection patterns with both standard and direct context access where available.

For the most current information, always refer to the ThingsBoard source code or official API documentation, as service methods may change between versions.