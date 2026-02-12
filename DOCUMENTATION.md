# ThingsBoard Widget API Documentation

Complete reference for all available services in ThingsBoard widget development and custom actions.

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

Many service methods require PageLink objects for pagination to avoid server overload when dealing with large datasets (1000+ results).

Create a PageLink using the context helper:

```javascript
// pageSize, page, searchText, sortProperty, sortOrder  
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'name', 'ASC');

// Example: Get first 20 devices, sorted by name
const pageLink = self.ctx.pageLink(20, 0, '', 'name', 'ASC');
```

## Table of Contents

- [Admin Service](#admin-service)
- [AI Model Service](#ai-model-service)  
- [Alarm Comment Service](#alarm-comment-service)
- [Alarm Service](#alarm-service)
- [API.Identifier Service](#api.identifier-service)
- [Asset Profile Service](#asset-profile-service)
- [Asset Service](#asset-service)
- [Attribute Service](#attribute-service)
- [Audit Log Service](#audit-log-service)
- [Calculated Fields Service](#calculated-fields-service)
- [Component Descriptor Service](#component-descriptor-service)
- [Customer Service](#customer-service)
- [Dashboard Service](#dashboard-service)
- [Device Profile Service](#device-profile-service)
- [Device Service](#device-service)
- [Domain Service](#domain-service)
- [Edge Service](#edge-service)
- [Entities Version Control Service](#entities-version-control-service)
- [Entity Relation Service](#entity-relation-service)
- [Entity View Service](#entity-view-service)
- [Entity Service](#entity-service)
- [Event Service](#event-service)
- [GitHub Service](#github-service)
- [Image Service](#image-service)
- [Mobile App Service](#mobile-app-service)
- [Mobile Application Service](#mobile-application-service)
- [Notification Service](#notification-service)
- [OAuth2 Service](#oauth2-service)
- [OTA Package Service](#ota-package-service)
- [Queue Service](#queue-service)
- [Resource Service](#resource-service)
- [Rule Chain Service](#rule-chain-service)
- [Tenant Profile Service](#tenant-profile-service)
- [Tenant Service](#tenant-service)
- [Trendz Settings Service](#trendz-settings-service)
- [Two Factor Authentication Service](#two-factor-authentication-service)
- [UI Settings Service](#ui-settings-service)
- [Usage Info Service](#usage-info-service)
- [User Settings Service](#user-settings-service)
- [User Service](#user-service)
- [Widget Service](#widget-service)

---

### **ADMIN SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const adminService = $injector.get(self.ctx.servicesMap.get('adminService'));
```

**1. getRepositorySettingsInfo**

```javascript
adminService.getRepositorySettingsInfo().subscribe(repositoryInfo => {
  console.log('Repository Settings Info:', repositoryInfo);
});
```

**2. getAutoCommitSettings**

```javascript
adminService.getAutoCommitSettings().subscribe(settings => {
  console.log('Auto Commit Settings:', settings);
});
```

**3. autoCommitSettingsExists**

```javascript
adminService.autoCommitSettingsExists().subscribe(exists => {
  console.log('Auto Commit Settings Exist:', exists);
});
```

**4. saveAutoCommitSettings**

```javascript
const autoCommitSettings = {
  // Your auto commit settings object
};
adminService.saveAutoCommitSettings(autoCommitSettings).subscribe(savedSettings => {
  console.log('Saved Auto Commit Settings:', savedSettings);
});
```

**5. checkUpdates**

```javascript
adminService.checkUpdates().subscribe(updateMessage => {
  console.log('Update Message:', updateMessage);
});
```

**6. getFeaturesInfo**

```javascript
adminService.getFeaturesInfo().subscribe(featuresInfo => {
  console.log('Features Info:', featuresInfo);
});
```

**7. getLoginProcessingUrl**

```javascript
adminService.getLoginProcessingUrl().subscribe(url => {
  console.log('Login Processing URL:', url);
});
```

**8. generateAccessToken**

```javascript
adminService.generateAccessToken().subscribe(authString => {
  console.log("Generated Access String:", authString);
});
```

**9. getMailConfigTemplate**

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
  name: 'My AI Model',
  type: 'OpenAI',
  // Additional AI model configuration
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
  // Your AI model with user message
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
  comment: {
    text: 'This alarm needs investigation'
  }
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
alarmCommentService.deleteAlarmComments(alarmId, commentId).subscribe(() => {
  console.log('Alarm comment deleted successfully');
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
  type: 'Temperature Alert',
  severity: 'CRITICAL',
  // Additional alarm properties
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
alarmService.assignAlarm(alarmId, assigneeId).subscribe(() => {
  console.log('Alarm assigned successfully');
});
```

**7. unassignAlarm**

```javascript
const alarmId = 'your-alarm-id';
alarmService.unassignAlarm(alarmId).subscribe(() => {
  console.log('Alarm unassigned successfully');
});
```

**8. deleteAlarm**

```javascript
const alarmId = 'your-alarm-id';
alarmService.deleteAlarm(alarmId).subscribe(result => {
  console.log('Alarm Deletion Result:', result);
});
```

**9. getAlarms**

```javascript
const query = {
  entityFilter: {
    // Entity filter configuration
  },
  pageLink: self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC')
};
alarmService.getAlarms(query).subscribe(alarms => {
  console.log('Alarms:', alarms);
});
```

**10. getAlarmsV2**

```javascript
const query = {
  entityFilter: {
    // Entity filter configuration
  },
  pageLink: self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC')
};
alarmService.getAlarmsV2(query).subscribe(alarms => {
  console.log('Alarms V2:', alarms);
});
```

**11. getAllAlarms**

```javascript
const query = {
  entityFilter: {
    // Entity filter configuration
  },
  pageLink: self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC')
};
alarmService.getAllAlarms(query).subscribe(alarms => {
  console.log('All Alarms:', alarms);
});
```

**12. getAllAlarmsV2**

```javascript
const query = {
  entityFilter: {
    // Entity filter configuration
  },
  pageLink: self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC')
};
alarmService.getAllAlarmsV2(query).subscribe(alarms => {
  console.log('All Alarms V2:', alarms);
});
```

**13. getHighestAlarmSeverity**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const alarmSearchStatus = 'ANY';
const alarmStatus = 'ACTIVE';
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
  name: 'My API.Identifier',
  description: 'API key for external integration'
};
apiKeyService.saveApiKey(apiKey).subscribe(savedKey => {
  console.log('Saved API.Identifier:', savedKey);
});
```

**2. deleteApiKey**

```javascript
const apiKeyId = 'your-api.identifier-id';
apiKeyService.deleteApiKey(apiKeyId).subscribe(() => {
  console.log('API key deleted successfully');
});
```

**3. updateApiKeyDescription**

```javascript
const apiKeyId = 'your-api.identifier-id';
const description = 'Updated description';
apiKeyService.updateApiKeyDescription(apiKeyId, description).subscribe(updatedKey => {
  console.log('Updated API.Identifier:', updatedKey);
});
```

**4. enableApiKey**

```javascript
const apiKeyId = 'your-api.identifier-id';
const enabledValue = true;
apiKeyService.enableApiKey(apiKeyId, enabledValue).subscribe(updatedKey => {
  console.log('API.Identifier Status Updated:', updatedKey);
});
```

**5. getUserApiKeys**

```javascript
const userId = 'your-user-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
apiKeyService.getUserApiKeys(userId, pageLink).subscribe(apiKeys => {
  console.log('User API.Identifiers:', apiKeys);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
assetProfileService.getAssetProfiles(pageLink).subscribe(profiles => {
  console.log('Asset Profiles:', profiles);
});
```

**2. getAssetProfilesByIds**

```javascript
const assetProfileIds = ['profile-id-1', 'profile-id-2'];
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
assetProfileService.exportAssetProfile(assetProfileId).subscribe(exportedProfile => {
  console.log('Exported Asset Profile:', exportedProfile);
});
```

**5. saveAssetProfile**

```javascript
const assetProfile = {
  name: 'Building Profile',
  description: 'Profile for building assets',
  // Additional profile configuration
};
assetProfileService.saveAssetProfile(assetProfile).subscribe(savedProfile => {
  console.log('Saved Asset Profile:', savedProfile);
});
```

**6. setDefaultAssetProfile**

```javascript
const assetProfileId = 'your-asset-profile-id';
assetProfileService.setDefaultAssetProfile(assetProfileId).subscribe(defaultProfile => {
  console.log('Default Asset Profile Set:', defaultProfile);
});
```

**7. getDefaultAssetProfileInfo**

```javascript
assetProfileService.getDefaultAssetProfileInfo().subscribe(profileInfo => {
  console.log('Default Asset Profile Info:', profileInfo);
});
```

**8. getAssetProfileInfo**

```javascript
const assetProfileId = 'your-asset-profile-id';
assetProfileService.getAssetProfileInfo(assetProfileId).subscribe(profileInfo => {
  console.log('Asset Profile Info:', profileInfo);
});
```

**9. getAssetProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
assetProfileService.getAssetProfileInfos(pageLink).subscribe(profileInfos => {
  console.log('Asset Profile Infos:', profileInfos);
});
```

**10. getAssetProfileNames**

```javascript
const activeOnly = true;
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'Building'; // Optional asset type filter
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
const type = 'Building';
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
const assetIds = ['asset-id-1', 'asset-id-2'];
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
  name: 'Main Building',
  type: 'Building',
  // Additional asset properties
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
  entityFilter: {
    // Asset search query configuration
  }
};
assetService.findByQuery(query).subscribe(assets => {
  console.log('Assets by Query:', assets);
});
```

**13. findByName**

```javascript
const assetName = 'Main Building';
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
const type = 'Building';
assetService.getEdgeAssets(edgeId, pageLink, type).subscribe(assets => {
  console.log('Edge Assets:', assets);
});
```

**16. bulkImportAssets**

```javascript
const entitiesData = {
  // Bulk import request configuration
};
assetService.bulkImportAssets(entitiesData).subscribe(result => {
  console.log('Bulk Import Result:', result);
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
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const attributeScope = 'SERVER_SCOPE'; // Optional
const keys = ['temperature', 'humidity']; // Optional
attributeService.getEntityAttributes(entityId, attributeScope, keys).subscribe(attributes => {
  console.log('Entity Attributes:', attributes);
});
```

**2. deleteEntityAttributes**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const attributeScope = 'SERVER_SCOPE';
const attributes = [
  { key: 'oldAttribute', value: 'value' }
];
attributeService.deleteEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Attributes deleted successfully');
});
```

**3. deleteEntityTimeseries**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const timeseries = [
  { key: 'temperature', value: 25.5 }
];
const startTs = Date.now() - 86400000; // 24 hours ago
const endTs = Date.now();
attributeService.deleteEntityTimeseries(entityId, timeseries, startTs, endTs).subscribe(result => {
  console.log('Timeseries deleted successfully');
});
```

**4. saveEntityAttributes**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const attributeScope = 'SERVER_SCOPE';
const attributes = [
  { key: 'location', value: 'Building A' },
  { key: 'model', value: 'TH-100' }
];
attributeService.saveEntityAttributes(entityId, attributeScope, attributes).subscribe(result => {
  console.log('Attributes saved successfully');
});
```

**5. saveEntityTimeseries**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const timeseriesScope = 'TELEMETRY';
const timeseries = [
  { ts: Date.now(), values: { temperature: 25.5, humidity: 60 } }
];
attributeService.saveEntityTimeseries(entityId, timeseriesScope, timeseries).subscribe(result => {
  console.log('Timeseries saved successfully');
});
```

**6. getEntityTimeseries**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const keys = ['temperature', 'humidity'];
const startTs = Date.now() - 86400000; // 24 hours ago
const endTs = Date.now();
const limit = 1000;
const agg = 'AVG';
const interval = 3600000; // 1 hour
const orderBy = 'ASC';
const useStrictDataTypes = true;
attributeService.getEntityTimeseries(entityId, keys, startTs, endTs, limit, agg, interval, orderBy, useStrictDataTypes).subscribe(timeseriesData => {
  console.log('Timeseries Data:', timeseriesData);
});
```

**7. getEntityTimeseriesLatest**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const keys = ['temperature', 'humidity']; // Optional
attributeService.getEntityTimeseriesLatest(entityId, keys).subscribe(latestData => {
  console.log('Latest Timeseries Data:', latestData);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
auditLogService.getAuditLogs(pageLink).subscribe(logs => {
  console.log('Audit Logs:', logs);
});
```

**2. getAuditLogsByCustomerId**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
auditLogService.getAuditLogsByCustomerId(customerId, pageLink).subscribe(logs => {
  console.log('Customer Audit Logs:', logs);
});
```

**3. getAuditLogsByUserId**

```javascript
const userId = 'your-user-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
auditLogService.getAuditLogsByUserId(userId, pageLink).subscribe(logs => {
  console.log('User Audit Logs:', logs);
});
```

**4. getAuditLogsByEntityId**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
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
  name: 'Temperature Average',
  script: 'return (msg.temperature1 + msg.temperature2) / 2;',
  // Additional field configuration
};
calculatedFieldsService.saveCalculatedField(calculatedField).subscribe(savedField => {
  console.log('Saved Calculated Field:', savedField);
});
```

**3. deleteCalculatedField**

```javascript
const calculatedFieldId = 'your-calculated-field-id';
calculatedFieldsService.deleteCalculatedField(calculatedFieldId).subscribe(result => {
  console.log('Calculated field deleted successfully');
});
```

**4. getCalculatedFields**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const query = {
  // Query configuration
};
calculatedFieldsService.getCalculatedFields(pageLink, query).subscribe(fields => {
  console.log('Calculated Fields:', fields);
});
```

**5. getCalculatedFieldsByEntityId**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'TELEMETRY'; // Optional
calculatedFieldsService.getCalculatedFieldsByEntityId(pageLink, type).subscribe(fields => {
  console.log('Calculated Fields by Entity:', fields);
});
```

**6. testScript**

```javascript
const inputParams = {
  script: 'return msg.temperature * 2;',
  msg: { temperature: 25.5 },
  // Additional test parameters
};
calculatedFieldsService.testScript(inputParams).subscribe(result => {
  console.log('Script Test Result:', result);
});
```

**7. getLatestCalculatedFieldDebugEvent**

```javascript
const fieldId = 'your-calculated-field-id';
calculatedFieldsService.getLatestCalculatedFieldDebugEvent(fieldId).subscribe(debugEvent => {
  console.log('Latest Debug Event:', debugEvent);
});
```

**8. getCalculatedFieldNames**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'TELEMETRY';
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
  console.log('Component Descriptors:', descriptors);
});
```

**2. getComponentDescriptorsByTypes**

```javascript
const componentTypes = ['FILTER', 'ENRICHMENT'];
const ruleChainType = 'CORE';
componentDescriptorService.getComponentDescriptorsByTypes(componentTypes, ruleChainType).subscribe(descriptors => {
  console.log('Component Descriptors by Types:', descriptors);
});
```

**3. getComponentDescriptorByClazz**

```javascript
const componentDescriptorClazz = 'org.thingsboard.rule.engine.filter.TbJsFilterNode';
componentDescriptorService.getComponentDescriptorByClazz(componentDescriptorClazz).subscribe(descriptor => {
  console.log('Component Descriptor:', descriptor);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
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
const customerIds = ['customer-id-1', 'customer-id-2'];
customerService.getCustomersByIds(customerIds).subscribe(customers => {
  console.log('Customers by IDs:', customers);
});
```

**4. saveCustomer**

```javascript
const customer = {
  title: 'ACME Corporation',
  country: 'USA',
  state: 'NY',
  city: 'New York',
  // Additional customer properties
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
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
dashboardService.getTenantDashboards(pageLink).subscribe(dashboards => {
  console.log('Tenant Dashboards:', dashboards);
});
```

**2. getTenantDashboardsByTenantId**

```javascript
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
dashboardService.getTenantDashboardsByTenantId(tenantId, pageLink).subscribe(dashboards => {
  console.log('Tenant Dashboards by Tenant ID:', dashboards);
});
```

**3. getCustomerDashboards**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
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
dashboardService.exportDashboard(dashboardId).subscribe(exportedDashboard => {
  console.log('Exported Dashboard:', exportedDashboard);
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
const dashboardIds = ['dashboard-id-1', 'dashboard-id-2'];
dashboardService.getDashboards(dashboardIds).subscribe(dashboards => {
  console.log('Dashboards:', dashboards);
});
```

**8. saveDashboard**

```javascript
const dashboard = {
  title: 'My Dashboard',
  configuration: {
    // Dashboard configuration
  },
  // Additional dashboard properties
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
  console.log('Dashboard Assigned to Customer:', assignedDashboard);
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
const customerIds = ['customer-id-1', 'customer-id-2'];
dashboardService.updateDashboardCustomers(dashboardId, customerIds).subscribe(updatedDashboard => {
  console.log('Dashboard Customers Updated:', updatedDashboard);
});
```

**13. addDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['customer-id-3', 'customer-id-4'];
dashboardService.addDashboardCustomers(dashboardId, customerIds).subscribe(updatedDashboard => {
  console.log('Dashboard Customers Added:', updatedDashboard);
});
```

**14. removeDashboardCustomers**

```javascript
const dashboardId = 'your-dashboard-id';
const customerIds = ['customer-id-1'];
dashboardService.removeDashboardCustomers(dashboardId, customerIds).subscribe(updatedDashboard => {
  console.log('Dashboard Customers Removed:', updatedDashboard);
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
dashboardService.getTenantHomeDashboardInfo().subscribe(homeDashboardInfo => {
  console.log('Tenant Home Dashboard Info:', homeDashboardInfo);
});
```

**17. setTenantHomeDashboardInfo**

```javascript
const homeDashboardInfo = {
  dashboardId: 'your-dashboard-id',
  // Additional home dashboard configuration
};
dashboardService.setTenantHomeDashboardInfo(homeDashboardInfo).subscribe(result => {
  console.log('Home dashboard info set successfully');
});
```

**18. getPublicDashboardLink**

```javascript
const dashboard = {
  id: { id: 'your-dashboard-id' },
  publicCustomerId: 'public-customer-id'
};
const publicLink = dashboardService.getPublicDashboardLink(dashboard);
console.log('Public Dashboard Link:', publicLink);
```

**19. assignDashboardToEdge**

```javascript
const edgeId = 'your-edge-id';
const dashboardId = 'your-dashboard-id';
dashboardService.assignDashboardToEdge(edgeId, dashboardId).subscribe(assignedDashboard => {
  console.log('Dashboard Assigned to Edge:', assignedDashboard);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
deviceProfileService.getDeviceProfiles(pageLink).subscribe(profiles => {
  console.log('Device Profiles:', profiles);
});
```

**2. getDeviceProfilesByIds**

```javascript
const deviceProfileIds = ['profile-id-1', 'profile-id-2'];
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
deviceProfileService.exportDeviceProfile(deviceProfileId).subscribe(exportedProfile => {
  console.log('Exported Device Profile:', exportedProfile);
});
```

**5. getLwm2mObjects**

```javascript
const sortOrder = { property: 'name', direction: 'ASC' };
const objectIds = ['3', '3303']; // Optional LwM2M object IDs
const searchText = 'temperature'; // Optional
deviceProfileService.getLwm2mObjects(sortOrder, objectIds, searchText).subscribe(objects => {
  console.log('LwM2M Objects:', objects);
});
```

**6. getLwm2mBootstrapSecurityInfo**

```javascript
const isBootstrapServer = true;
deviceProfileService.getLwm2mBootstrapSecurityInfo(isBootstrapServer).subscribe(securityInfo => {
  console.log('LwM2M Bootstrap Security Info:', securityInfo);
});
```

**7. getLwm2mBootstrapSecurityInfoBySecurityType**

```javascript
const isBootstrapServer = false;
deviceProfileService.getLwm2mBootstrapSecurityInfoBySecurityType(isBootstrapServer).subscribe(securityConfig => {
  console.log('LwM2M Security Config:', securityConfig);
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
  // Original device profile
};
const deviceProfile = {
  name: 'Updated Device Profile',
  // Updated device profile properties
};
deviceProfileService.saveDeviceProfileAndConfirmOtaChange(originDeviceProfile, deviceProfile).subscribe(savedProfile => {
  console.log('Saved Device Profile with OTA:', savedProfile);
});
```

**10. setDefaultDeviceProfile**

```javascript
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.setDefaultDeviceProfile(deviceProfileId).subscribe(defaultProfile => {
  console.log('Default Device Profile Set:', defaultProfile);
});
```

**11. getDefaultDeviceProfileInfo**

```javascript
deviceProfileService.getDefaultDeviceProfileInfo().subscribe(profileInfo => {
  console.log('Default Device Profile Info:', profileInfo);
});
```

**12. getDeviceProfileInfo**

```javascript
const deviceProfileId = 'your-device-profile-id';
deviceProfileService.getDeviceProfileInfo(deviceProfileId).subscribe(profileInfo => {
  console.log('Device Profile Info:', profileInfo);
});
```

**13. getDeviceProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const transportType = 'DEFAULT'; // Optional
deviceProfileService.getDeviceProfileInfos(pageLink, transportType).subscribe(profileInfos => {
  console.log('Device Profile Infos:', profileInfos);
});
```

**14. getDeviceProfileDevicesAttributesKeys**

```javascript
const deviceProfileId = 'your-device-profile-id'; // Optional
deviceProfileService.getDeviceProfileDevicesAttributesKeys(deviceProfileId).subscribe(keys => {
  console.log('Device Attributes Keys:', keys);
});
```

**15. getDeviceProfileDevicesTimeseriesKeys**

```javascript
const deviceProfileId = 'your-device-profile-id'; // Optional
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
  deviceTypes: ['sensor', 'gateway'],
  pageLink: self.ctx.pageLink(10, 0, '', 'name', 'ASC')
};
deviceService.getDeviceInfosByQuery(deviceInfoQuery).subscribe(devices => {
  console.log('Devices by Query:', devices);
});
```

**2. getTenantDeviceInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'sensor'; // Optional device type filter
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
const type = 'sensor';
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
const deviceIds = ['device-id-1', 'device-id-2'];
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
  name: 'Temperature Sensor 01',
  type: 'sensor',
  // Additional device properties
};
deviceService.saveDevice(device).subscribe(savedDevice => {
  console.log('Saved Device:', savedDevice);
});
```

**10. saveDeviceWithCredentials**

```javascript
const device = {
  name: 'Temperature Sensor 01',
  type: 'sensor'
};
const credentials = {
  credentialsType: 'ACCESS_TOKEN',
  credentialsId: 'sensor_01_key'
};
deviceService.saveDeviceWithCredentials(device, credentials).subscribe(result => {
  console.log('Saved Device with Credentials:', result);
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
  deviceId: { id: 'your-device-id' },
  credentialsType: 'ACCESS_TOKEN',
  credentialsId: 'new_access_key'
};
deviceService.saveDeviceCredentials(deviceCredentials).subscribe(savedCredentials => {
  console.log('Saved Device Credentials:', savedCredentials);
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
  method: 'setRelayStatus',
  params: { status: true }
};
deviceService.sendOneWayRpcCommand(deviceId, requestBody).subscribe(result => {
  console.log('One-way RPC sent successfully');
});
```

**17. sendTwoWayRpcCommand**

```javascript
const deviceId = 'your-device-id';
const requestBody = {
  method: 'getTemperature',
  params: {}
};
deviceService.sendTwoWayRpcCommand(deviceId, requestBody).subscribe(response => {
  console.log('Two-way RPC Response:', response);
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
const rpcStatus = 'QUEUED'; // Optional
deviceService.getPersistedRpcRequests(deviceId, pageLink, rpcStatus).subscribe(rpcRequests => {
  console.log('Persisted RPC Requests:', rpcRequests);
});
```

**20. findByQuery**

```javascript
const query = {
  entityFilter: {
    // Device search query configuration
  }
};
deviceService.findByQuery(query).subscribe(devices => {
  console.log('Devices by Query:', devices);
});
```

**21. findByName**

```javascript
const deviceName = 'Temperature Sensor 01';
deviceService.findByName(deviceName).subscribe(device => {
  console.log('Device by Name:', device);
});
```

**22. claimDevice**

```javascript
const deviceName = 'Temperature Sensor 01';
const claimRequest = {
  privateKey: 'device_key'
};
deviceService.claimDevice(deviceName, claimRequest).subscribe(claimResult => {
  console.log('Device Claim Result:', claimResult);
});
```

**23. assignDeviceToEdge**

```javascript
const edgeId = 'your-edge-id';
const deviceId = 'your-device-id';
deviceService.assignDeviceToEdge(edgeId, deviceId).subscribe(assignedDevice => {
  console.log('Device Assigned to Edge:', assignedDevice);
});
```

**24. getEdgeDevices**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'sensor';
deviceService.getEdgeDevices(edgeId, pageLink, type).subscribe(devices => {
  console.log('Edge Devices:', devices);
});
```

**25. bulkImportDevices**

```javascript
const entitiesData = {
  // Bulk import request configuration
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
const deviceId = 'your-gateway-device-id';
deviceService.downloadGatewayDockerComposeFile(deviceId).subscribe(file => {
  console.log('Gateway Docker Compose File downloaded');
});
```

**28. rebootDevice**

```javascript
const deviceId = 'your-device-id';
const isBootstrapServer = false;
deviceService.rebootDevice(deviceId, isBootstrapServer).subscribe(result => {
  console.log('Device reboot initiated');
});
```

**29. rebootTrigger**

```javascript
const deviceId = 'your-device-id';
const resourcePath = '/3/0/4';
deviceService.rebootTrigger(deviceId, resourcePath).subscribe(result => {
  console.log('Device reboot trigger sent');
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
  name: 'example.com',
  // Domain configuration
};
const oauth2ClientIds = ['client-id-1', 'client-id-2']; // Optional
domainService.saveDomain(domain, oauth2ClientIds).subscribe(savedDomain => {
  console.log('Saved Domain:', savedDomain);
});
```

**2. updateOauth2Clients**

```javascript
const domainId = 'your-domain-id';
const oauth2ClientIds = ['client-id-1', 'client-id-2'];
domainService.updateOauth2Clients(domainId, oauth2ClientIds).subscribe(() => {
  console.log('OAuth2 clients updated successfully');
});
```

**3. getTenantDomainInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
domainService.getTenantDomainInfos(pageLink).subscribe(domains => {
  console.log('Tenant Domains:', domains);
});
```

**4. getDomainInfoById**

```javascript
const domainId = 'your-domain-id';
domainService.getDomainInfoById(domainId).subscribe(domainInfo => {
  console.log('Domain Info:', domainInfo);
});
```

**5. deleteDomain**

```javascript
const domainId = 'your-domain-id';
domainService.deleteDomain(domainId).subscribe(() => {
  console.log('Domain deleted successfully');
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
const edgeIds = ['edge-id-1', 'edge-id-2'];
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
  name: 'Factory Edge',
  type: 'gateway',
  // Additional edge properties
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
const type = 'gateway';
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
const type = 'gateway';
edgeService.getTenantEdgeInfos(pageLink, type).subscribe(edges => {
  console.log('Tenant Edges:', edges);
});
```

**10. findByQuery**

```javascript
const query = {
  entityFilter: {
    // Edge search query configuration
  }
};
edgeService.findByQuery(query).subscribe(edges => {
  console.log('Edges by Query:', edges);
});
```

**11. getEdgeEvents**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
edgeService.getEdgeEvents(entityId, pageLink).subscribe(events => {
  console.log('Edge Events:', events);
});
```

**12. findMissingToRelatedRuleChains**

```javascript
const edgeId = 'your-edge-id';
edgeService.findMissingToRelatedRuleChains(edgeId).subscribe(missingChains => {
  console.log('Missing Related Rule Chains:', missingChains);
});
```

**13. findByName**

```javascript
const edgeName = 'Factory Edge';
edgeService.findByName(edgeName).subscribe(edge => {
  console.log('Edge by Name:', edge);
});
```

**14. bulkImportEdges**

```javascript
const entitiesData = {
  // Bulk import request configuration
};
edgeService.bulkImportEdges(entitiesData).subscribe(result => {
  console.log('Bulk Import Result:', result);
});
```

**15. getEdgeInstallInstructions**

```javascript
const edgeId = 'your-edge-id';
const method = 'docker';
edgeService.getEdgeInstallInstructions(edgeId, method).subscribe(instructions => {
  console.log('Edge Install Instructions:', instructions);
});
```

**16. getEdgeUpgradeInstructions**

```javascript
const edgeVersion = '3.5.0';
const method = 'docker';
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
const externalEntityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const versionId = 'your-version-id';
entitiesVersionControlService.getEntityDataInfo(externalEntityId, versionId).subscribe(dataInfo => {
  console.log('Entity Data Info:', dataInfo);
});
```

**4. saveEntitiesVersion**

```javascript
const request = {
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
const pageLink = self.ctx.pageLink(10, 0, '', 'timestamp', 'DESC');
const branch = 'main';
const externalEntityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
entitiesVersionControlService.listEntityVersions(pageLink, branch, externalEntityId).subscribe(versions => {
  console.log('Entity Versions:', versions);
});
```

**7. listEntityTypeVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'timestamp', 'DESC');
const branch = 'main';
const entityType = 'DEVICE';
entitiesVersionControlService.listEntityTypeVersions(pageLink, branch, entityType).subscribe(versions => {
  console.log('Entity Type Versions:', versions);
});
```

**8. listVersions**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'timestamp', 'DESC');
const branch = 'main';
entitiesVersionControlService.listVersions(pageLink, branch).subscribe(versions => {
  console.log('All Versions:', versions);
});
```

**9. loadEntitiesVersion**

```javascript
const request = {
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
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const versionId = 'your-version-id';
entitiesVersionControlService.compareEntityDataToVersion(entityId, versionId).subscribe(diff => {
  console.log('Entity Data Diff:', diff);
});
```

**12. entityLoadErrorToMessage**

```javascript
const entityLoadError = {
  // Entity load error object
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
  console.log('Entity Relation:', relation);
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
  console.log('Relations by Type from Entity:', relations);
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
  console.log('Relations by Type to Entity:', relations);
});
```

**9. findByQuery**

```javascript
const query = {
  filters: [
    {
      relationType: 'Contains',
      entityTypes: ['DEVICE', 'ASSET']
    }
  ],
  parameters: {
    rootId: 'root-entity-id',
    rootType: 'ASSET'
  }
};
entityRelationService.findByQuery(query).subscribe(relations => {
  console.log('Relations by Query:', relations);
});
```

**10. findInfoByQuery**

```javascript
const query = {
  filters: [
    {
      relationType: 'Contains',
      entityTypes: ['DEVICE', 'ASSET']
    }
  ],
  parameters: {
    rootId: 'root-entity-id',
    rootType: 'ASSET'
  }
};
entityRelationService.findInfoByQuery(query).subscribe(relationInfos => {
  console.log('Relation Infos by Query:', relationInfos);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'sensor'; // Optional entity view type filter
entityViewService.getTenantEntityViewInfos(pageLink, type).subscribe(entityViews => {
  console.log('Tenant Entity Views:', entityViews);
});
```

**2. getCustomerEntityViewInfos**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'sensor';
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
const entityViewIds = ['view-id-1', 'view-id-2'];
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
  name: 'Temperature View',
  type: 'sensor',
  entityId: { entityType: 'DEVICE', id: 'device-id' },
  keys: {
    timeseries: ['temperature', 'humidity']
  }
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
entityViewService.makeEntityViewPublic(entityViewId).subscribe(publicEntityView => {
  console.log('Public Entity View:', publicEntityView);
});
```

**9. assignEntityViewToCustomer**

```javascript
const customerId = 'your-customer-id';
const entityViewId = 'your-entity-view-id';
entityViewService.assignEntityViewToCustomer(customerId, entityViewId).subscribe(assignedEntityView => {
  console.log('Assigned Entity View:', assignedEntityView);
});
```

**10. findByQuery**

```javascript
const query = {
  entityFilter: {
    // Entity view search query configuration
  }
};
entityViewService.findByQuery(query).subscribe(entityViews => {
  console.log('Entity Views by Query:', entityViews);
});
```

**11. assignEntityViewToEdge**

```javascript
const edgeId = 'your-edge-id';
const entityViewId = 'your-entity-view-id';
entityViewService.assignEntityViewToEdge(edgeId, entityViewId).subscribe(assignedEntityView => {
  console.log('Entity View Assigned to Edge:', assignedEntityView);
});
```

**12. getEdgeEntityViews**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'sensor';
entityViewService.getEdgeEntityViews(edgeId, pageLink, type).subscribe(entityViews => {
  console.log('Edge Entity Views:', entityViews);
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
const entityIds = ['device-id-1', 'device-id-2'];
entityService.getEntitiesObservable(entityType, entityIds).subscribe(entities => {
  console.log('Entities Observable:', entities);
});
```

**4. getEntities**

```javascript
const entityType = 'DEVICE';
const entityIds = ['device-id-1', 'device-id-2'];
entityService.getEntities(entityType, entityIds).subscribe(entities => {
  console.log('Entities:', entities);
});
```

**5. getSingleTenantByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
entityService.getSingleTenantByPageLinkObservable(pageLink).subscribe(tenants => {
  console.log('Single Tenant by PageLink:', tenants);
});
```

**6. getSingleCustomerByPageLinkObservable**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
entityService.getSingleCustomerByPageLinkObservable(pageLink).subscribe(customers => {
  console.log('Single Customer by PageLink:', customers);
});
```

**7. getEntitiesByPageLinkObservable**

```javascript
const entityType = 'DEVICE';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const subType = 'sensor';
entityService.getEntitiesByPageLinkObservable(entityType, pageLink, subType).subscribe(entities => {
  console.log('Entities by PageLink Observable:', entities);
});
```

**8. getEntitiesByPageLink**

```javascript
const entityType = 'DEVICE';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const subType = 'sensor';
entityService.getEntitiesByPageLink(entityType, pageLink, subType).subscribe(entities => {
  console.log('Entities by PageLink:', entities);
});
```

**9. getEntitiesByNameFilter**

```javascript
const entityType = 'DEVICE';
const entityNameFilter = 'temp';
const pageSize = 10;
const subType = 'sensor';
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
  pageLink: self.ctx.pageLink(10, 0, '', 'name', 'ASC'),
  entityFields: [
    { type: 'ENTITY_FIELD', key: 'name' }
  ]
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
  },
  pageLink: self.ctx.pageLink(10, 0, '', 'name', 'ASC')
};
const scope = 'SERVER_SCOPE'; // Optional
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
  console.log('Entity Infos by Filter and Name:', entityInfos);
});
```

**14. findSingleEntityInfoByEntityFilter**

```javascript
const filter = {
  type: 'entityType',
  entityType: 'DEVICE'
};
entityService.findSingleEntityInfoByEntityFilter(filter).subscribe(entityInfo => {
  console.log('Single Entity Info by Filter:', entityInfo);
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
  // Entity alias configuration
};
const entityTypes = ['DEVICE', 'ASSET'];
const result = entityService.filterAliasByEntityTypes(entityAlias, entityTypes);
console.log('Filter Alias Result:', result);
```

**17. filterAliasFilterTypeByEntityTypes**

```javascript
const aliasFilterType = 'entityType';
const entityTypes = ['DEVICE', 'ASSET'];
const result = entityService.filterAliasFilterTypeByEntityTypes(aliasFilterType, entityTypes);
console.log('Filter Alias Filter Type Result:', result);
```

**18. filterAliasFilterTypeByEntityType**

```javascript
const aliasFilterType = 'entityType';
const entityType = 'DEVICE';
const result = entityService.filterAliasFilterTypeByEntityType(aliasFilterType, entityType);
console.log('Filter by Entity Type Result:', result);
```

**19. prepareAllowedEntityTypesList**

```javascript
const allowedEntityTypes = ['DEVICE', 'ASSET'];
const useAliasEntityTypes = true; // Optional
const preparedTypes = entityService.prepareAllowedEntityTypesList(allowedEntityTypes, useAliasEntityTypes);
console.log('Prepared Entity Types:', preparedTypes);
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
const searchText = 'type';
const keys = entityService.getAlarmKeys(searchText);
console.log('Alarm Keys:', keys);
```

**22. getEntityKeys**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const query = 'temp';
const type = 'TIMESERIES';
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
const types = ['TIMESERIES', 'ATTRIBUTE'];
const entityTypes = ['DEVICE']; // Optional
entityService.getEntityKeysByEntityFilter(filter, types, entityTypes).subscribe(keys => {
  console.log('Entity Keys by Filter:', keys);
});
```

**24. getEntityKeysByEntityFilterAndScope**

```javascript
const filter = {
  type: 'entityType',
  entityType: 'DEVICE'
};
const types = ['ATTRIBUTE'];
const entityTypes = ['DEVICE']; // Optional
const scope = 'SERVER_SCOPE'; // Optional
entityService.getEntityKeysByEntityFilterAndScope(filter, types, entityTypes, scope).subscribe(keys => {
  console.log('Entity Keys by Filter and Scope:', keys);
});
```

**25. createDatasourcesFromSubscriptionsInfo**

```javascript
const subscriptionsInfo = [
  {
    entityId: { entityType: 'DEVICE', id: 'device-id' },
    keys: ['temperature', 'humidity']
  }
];
const datasources = entityService.createDatasourcesFromSubscriptionsInfo(subscriptionsInfo);
console.log('Created Datasources:', datasources);
```

**26. createAlarmSourceFromSubscriptionInfo**

```javascript
const subscriptionInfo = {
  entityId: { entityType: 'DEVICE', id: 'device-id' },
  keys: ['temperature', 'humidity']
};
const alarmSource = entityService.createAlarmSourceFromSubscriptionInfo(subscriptionInfo);
console.log('Created Alarm Source:', alarmSource);
```

**27. getAssignedToEdgeEntitiesByType**

```javascript
const edgeId = 'your-edge-id';
const entityType = 'DEVICE';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
entityService.getAssignedToEdgeEntitiesByType(edgeId, entityType, pageLink).subscribe(entities => {
  console.log('Edge Assigned Entities:', entities);
});
```

**28. getEntitySubtypesObservable**

```javascript
const entityType = 'DEVICE';
entityService.getEntitySubtypesObservable(entityType).subscribe(subtypes => {
  console.log('Entity Subtypes:', subtypes);
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
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const eventType = 'STATS';
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
eventService.getEvents(entityId, eventType, tenantId, pageLink).subscribe(events => {
  console.log('Events:', events);
});
```

**2. getFilterEvents**

```javascript
const entityId = {
  entityType: 'DEVICE',
  id: 'your-device-id'
};
const eventType = 'ERROR';
const tenantId = 'your-tenant-id';
const filters = {
  // Filter event body configuration
};
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
eventService.getFilterEvents(entityId, eventType, tenantId, filters, pageLink).subscribe(events => {
  console.log('Filtered Events:', events);
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
gitHubService.getGitHubStar().subscribe(starCount => {
  console.log('GitHub Star Count:', starCount);
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
const file = document.querySelector('input[type="file"]').files[0];
const title = 'My Image';
const imageSubType = 'GENERAL';
imageService.uploadImage(file, title, imageSubType).subscribe(imageInfo => {
  console.log('Uploaded Image Info:', imageInfo);
});
```

**2. updateImage**

```javascript
const type = 'SYSTEM';
const key = 'image-key';
const file = document.querySelector('input[type="file"]').files[0];
imageService.updateImage(type, key, file).subscribe(updatedImageInfo => {
  console.log('Updated Image Info:', updatedImageInfo);
});
```

**3. updateImageInfo**

```javascript
const imageInfo = {
  id: 'image-id',
  title: 'Updated Image Title',
  // Additional image info properties
};
imageService.updateImageInfo(imageInfo).subscribe(updatedImageInfo => {
  console.log('Updated Image Info:', updatedImageInfo);
});
```

**4. updateImagePublicStatus**

```javascript
const imageInfo = {
  id: 'image-id'
};
const isPublic = true;
imageService.updateImagePublicStatus(imageInfo, isPublic).subscribe(updatedImageInfo => {
  console.log('Updated Image Public Status:', updatedImageInfo);
});
```

**5. getImages**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
const imageSubType = 'GENERAL';
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
const type = 'SYSTEM';
const key = 'image-key';
imageService.downloadImage(type, key).subscribe(downloadResult => {
  console.log('Image downloaded successfully');
});
```

**12. exportImage**

```javascript
const type = 'SYSTEM';
const key = 'image-key';
imageService.exportImage(type, key).subscribe(exportData => {
  console.log('Exported Image Data:', exportData);
});
```

**13. importImage**

```javascript
const imageData = {
  // Image export data
};
imageService.importImage(imageData).subscribe(importedImageInfo => {
  console.log('Imported Image Info:', importedImageInfo);
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
  name: 'My Mobile App',
  platformType: 'ANDROID',
  // Additional mobile app configuration
};
mobileAppService.saveMobileApp(mobileApp).subscribe(savedApp => {
  console.log('Saved Mobile App:', savedApp);
});
```

**2. getTenantMobileAppInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const platformType = 'ANDROID'; // Optional
mobileAppService.getTenantMobileAppInfos(pageLink, platformType).subscribe(apps => {
  console.log('Tenant Mobile Apps:', apps);
});
```

**3. getMobileAppInfoById**

```javascript
const mobileAppId = 'your-mobile-app-id';
mobileAppService.getMobileAppInfoById(mobileAppId).subscribe(appInfo => {
  console.log('Mobile App Info:', appInfo);
});
```

**4. deleteMobileApp**

```javascript
const mobileAppId = 'your-mobile-app-id';
mobileAppService.deleteMobileApp(mobileAppId).subscribe(() => {
  console.log('Mobile app deleted successfully');
});
```

**5. getTenantMobileAppBundleInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
mobileAppService.getTenantMobileAppBundleInfos(pageLink).subscribe(bundles => {
  console.log('Mobile App Bundles:', bundles);
});
```

**6. getMobileAppBundleInfoById**

```javascript
const bundleId = 'your-bundle-id';
mobileAppService.getMobileAppBundleInfoById(bundleId).subscribe(bundleInfo => {
  console.log('Mobile App Bundle Info:', bundleInfo);
});
```

**7. deleteMobileAppBundle**

```javascript
const bundleId = 'your-bundle-id';
mobileAppService.deleteMobileAppBundle(bundleId).subscribe(() => {
  console.log('Mobile app bundle deleted successfully');
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
  // QR code settings configuration
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
const pageLink = self.ctx.pageLink(10, 0, '', 'createdTime', 'DESC');
notificationService.getNotifications(pageLink).subscribe(notifications => {
  console.log('Notifications:', notifications);
});
```

**2. deleteNotification**

```javascript
const notificationId = 'your-notification-id';
notificationService.deleteNotification(notificationId).subscribe(() => {
  console.log('Notification deleted successfully');
});
```

**3. markNotificationAsRead**

```javascript
const notificationId = 'your-notification-id';
notificationService.markNotificationAsRead(notificationId).subscribe(() => {
  console.log('Notification marked as read');
});
```

**4. markAllNotificationsAsRead**

```javascript
notificationService.markAllNotificationsAsRead().subscribe(() => {
  console.log('All notifications marked as read');
});
```

**5. createNotificationRequest**

```javascript
const notification = {
  subject: 'Test Notification',
  text: 'This is a test notification',
  // Additional notification configuration
};
notificationService.createNotificationRequest(notification).subscribe(createdRequest => {
  console.log('Created Notification Request:', createdRequest);
});
```

**6. sendEntitiesLimitIncreaseRequest**

```javascript
const entityType = 'DEVICE';
notificationService.sendEntitiesLimitIncreaseRequest(entityType).subscribe(() => {
  console.log('Entities limit increase request sent');
});
```

**7. getNotificationRequestById**

```javascript
const requestId = 'your-notification-request-id';
notificationService.getNotificationRequestById(requestId).subscribe(request => {
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
const requestId = 'your-notification-request-id';
notificationService.deleteNotificationRequest(requestId).subscribe(() => {
  console.log('Notification request deleted successfully');
});
```

**10. getNotificationRequestPreview**

```javascript
const notification = {
  subject: 'Test Preview',
  text: 'Preview text'
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
  // Notification settings configuration
};
notificationService.saveNotificationSettings(notificationSettings).subscribe(savedSettings => {
  console.log('Saved Notification Settings:', savedSettings);
});
```

**14. listSlackConversations**

```javascript
const type = 'public_channel';
const authIdentifier = 'slack-bot-identifier'; // Optional
notificationService.listSlackConversations(type, authIdentifier).subscribe(conversations => {
  console.log('Slack Conversations:', conversations);
});
```

**15. saveNotificationRule**

```javascript
const notificationRule = {
  name: 'Temperature Alert Rule',
  // Rule configuration
};
notificationService.saveNotificationRule(notificationRule).subscribe(savedRule => {
  console.log('Saved Notification Rule:', savedRule);
});
```

**16. getNotificationRuleById**

```javascript
const ruleId = 'your-notification-rule-id';
notificationService.getNotificationRuleById(ruleId).subscribe(rule => {
  console.log('Notification Rule:', rule);
});
```

**17. deleteNotificationRule**

```javascript
const ruleId = 'your-notification-rule-id';
notificationService.deleteNotificationRule(ruleId).subscribe(() => {
  console.log('Notification rule deleted successfully');
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
  name: 'Email Target',
  // Target configuration
};
notificationService.saveNotificationTarget(notificationTarget).subscribe(savedTarget => {
  console.log('Saved Notification Target:', savedTarget);
});
```

**20. getNotificationTargetById**

```javascript
const targetId = 'your-notification-target-id';
notificationService.getNotificationTargetById(targetId).subscribe(target => {
  console.log('Notification Target:', target);
});
```

**21. deleteNotificationTarget**

```javascript
const targetId = 'your-notification-target-id';
notificationService.deleteNotificationTarget(targetId).subscribe(() => {
  console.log('Notification target deleted successfully');
});
```

**22. getNotificationTargetsByIds**

```javascript
const targetIds = ['target-id-1', 'target-id-2'];
notificationService.getNotificationTargetsByIds(targetIds).subscribe(targets => {
  console.log('Notification Targets by IDs:', targets);
});
```

**23. getNotificationTargets**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const type = 'EMAIL'; // Optional
notificationService.getNotificationTargets(pageLink, type).subscribe(targets => {
  console.log('Notification Targets:', targets);
});
```

**24. getRecipientsForNotificationTargetConfig**

```javascript
const notificationTarget = {
  // Notification target configuration
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
  // Template configuration
};
notificationService.saveNotificationTemplate(notificationTemplate).subscribe(savedTemplate => {
  console.log('Saved Notification Template:', savedTemplate);
});
```

**26. getNotificationTemplateById**

```javascript
const templateId = 'your-notification-template-id';
notificationService.getNotificationTemplateById(templateId).subscribe(template => {
  console.log('Notification Template:', template);
});
```

**27. deleteNotificationTemplate**

```javascript
const templateId = 'your-notification-template-id';
notificationService.deleteNotificationTemplate(templateId).subscribe(() => {
  console.log('Notification template deleted successfully');
});
```

**28. getNotificationTemplates**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const notificationTypes = 'ALARM'; // Optional
notificationService.getNotificationTemplates(pageLink, notificationTypes).subscribe(templates => {
  console.log('Notification Templates:', templates);
});
```

**29. getNotificationUserSettings**

```javascript
notificationService.getNotificationUserSettings().subscribe(userSettings => {
  console.log('Notification User Settings:', userSettings);
});
```

**30. saveNotificationUserSettings**

```javascript
const settings = {
  // User notification settings
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
  title: 'My OAuth2 Client',
  // OAuth2 client configuration
};
oAuth2Service.saveOAuth2Client(oAuth2Client).subscribe(savedClient => {
  console.log('Saved OAuth2 Client:', savedClient);
});
```

**3. findTenantOAuth2ClientInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
oAuth2Service.findTenantOAuth2ClientInfos(pageLink).subscribe(clientInfos => {
  console.log('Tenant OAuth2 Client Infos:', clientInfos);
});
```

**4. findTenantOAuth2ClientInfosByIds**

```javascript
const clientIds = ['client-id-1', 'client-id-2'];
oAuth2Service.findTenantOAuth2ClientInfosByIds(clientIds).subscribe(clientInfos => {
  console.log('OAuth2 Client Infos by IDs:', clientInfos);
});
```

**5. getOAuth2ClientById**

```javascript
const clientId = 'your-oauth2-client-id';
oAuth2Service.getOAuth2ClientById(clientId).subscribe(client => {
  console.log('OAuth2 Client:', client);
});
```

**6. deleteOauth2Client**

```javascript
const clientId = 'your-oauth2-client-id';
oAuth2Service.deleteOauth2Client(clientId).subscribe(() => {
  console.log('OAuth2 client deleted successfully');
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
  console.log('OTA Packages by Device Profile:', packages);
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
  console.log('OTA package download initiated');
});
```

**6. saveOtaPackage**

```javascript
const otaPackage = {
  title: 'Firmware v1.2.0',
  type: 'FIRMWARE',
  // Additional package configuration
};
otaPackageService.saveOtaPackage(otaPackage).subscribe(savedPackage => {
  console.log('Saved OTA Package:', savedPackage);
});
```

**7. saveOtaPackageInfo**

```javascript
const otaPackageInfo = {
  title: 'Firmware v1.2.0',
  type: 'FIRMWARE'
};
otaPackageService.saveOtaPackageInfo(otaPackageInfo).subscribe(savedPackage => {
  console.log('Saved OTA Package Info:', savedPackage);
});
```

**8. uploadOtaPackageFile**

```javascript
const otaPackageId = 'your-ota-package-id';
const file = document.querySelector('input[type="file"]').files[0];
const checksumAlgorithm = 'SHA256';
const checksum = 'abc123...'; // Optional
otaPackageService.uploadOtaPackageFile(otaPackageId, file, checksumAlgorithm, checksum).subscribe(result => {
  console.log('OTA package file uploaded successfully');
});
```

**9. countUpdateDeviceAfterChangePackage**

```javascript
const type = 'FIRMWARE';
const entityId = {
  entityType: 'DEVICE_PROFILE',
  id: 'your-device-profile-id'
};
otaPackageService.countUpdateDeviceAfterChangePackage(type, entityId).subscribe(count => {
  console.log('Device Update Count:', count);
});
```

**10. confirmDialogUpdatePackage**

```javascript
const entity = {
  // Entity with OTA pages IDs
};
const originEntity = {
  // Original entity with OTA pages IDs
};
otaPackageService.confirmDialogUpdatePackage(entity, originEntity).subscribe(confirmed => {
  console.log('Update Package Confirmed:', confirmed);
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
  console.log('Queue Info:', queue);
});
```

**2. getQueueByName**

```javascript
const queueName = 'Main.Processing';
queueService.getQueueByName(queueName).subscribe(queue => {
  console.log('Queue by Name:', queue);
});
```

**3. getTenantQueuesByServiceType**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const serviceType = 'TB_RULE_ENGINE';
queueService.getTenantQueuesByServiceType(pageLink, serviceType).subscribe(queues => {
  console.log('Tenant Queues by Service Type:', queues);
});
```

**4. saveQueue**

```javascript
const queue = {
  name: 'Custom.Queue',
  topic: 'custom-topic',
  // Additional queue configuration
};
const serviceType = 'TB_RULE_ENGINE';
queueService.saveQueue(queue, serviceType).subscribe(savedQueue => {
  console.log('Saved Queue:', savedQueue);
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
queueService.getQueueStatisticsById(queueStatId).subscribe(statistic => {
  console.log('Queue Statistic:', statistic);
});
```

**7. getQueueStatisticsByIds**

```javascript
const queueStatIds = ['stat-id-1', 'stat-id-2'];
queueService.getQueueStatisticsByIds(queueStatIds).subscribe(statistics => {
  console.log('Queue Statistics by IDs:', statistics);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
const resourceType = 'JS_MODULE'; // Optional
const resourceSubType = 'EXTENSION'; // Optional
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
  console.log('Resource Info by ID:', resourceInfo);
});
```

**5. getResourceInfo**

```javascript
const type = 'JS_MODULE';
const scope = 'TENANT';
const key = 'my-module';
resourceService.getResourceInfo(type, scope, key).subscribe(resourceInfo => {
  console.log('Resource Info:', resourceInfo);
});
```

**6. downloadResource**

```javascript
const resourceId = 'your-resource-id';
resourceService.downloadResource(resourceId).subscribe(download => {
  console.log('Resource download initiated');
});
```

**7. saveResources**

```javascript
const resources = [
  {
    title: 'My JS Module',
    resourceType: 'JS_MODULE',
    data: 'function myFunction() { return "Hello"; }'
  }
];
resourceService.saveResources(resources).subscribe(savedResources => {
  console.log('Saved Resources:', savedResources);
});
```

**8. saveResource**

```javascript
const resource = {
  title: 'My JS Module',
  resourceType: 'JS_MODULE',
  data: 'function myFunction() { return "Hello"; }'
};
resourceService.saveResource(resource).subscribe(savedResource => {
  console.log('Saved Resource:', savedResource);
});
```

**9. uploadResources**

```javascript
const resources = [
  {
    title: 'My JS Module',
    resourceType: 'JS_MODULE',
    data: 'function myFunction() { return "Hello"; }'
  }
];
resourceService.uploadResources(resources).subscribe(uploadedResources => {
  console.log('Uploaded Resources:', uploadedResources);
});
```

**10. uploadResource**

```javascript
const resource = {
  title: 'My JS Module',
  resourceType: 'JS_MODULE',
  data: 'function myFunction() { return "Hello"; }'
};
resourceService.uploadResource(resource).subscribe(uploadedResource => {
  console.log('Uploaded Resource:', uploadedResource);
});
```

**11. updatedResourceInfo**

```javascript
const resourceId = 'your-resource-id';
const updatedResources = {
  title: 'Updated Resource Title'
};
resourceService.updatedResourceInfo(resourceId, updatedResources).subscribe(updatedResource => {
  console.log('Updated Resource Info:', updatedResource);
});
```

**12. updatedResourceData**

```javascript
const resourceId = 'your-resource-id';
const data = document.querySelector('input[type="file"]').files[0];
resourceService.updatedResourceData(resourceId, data).subscribe(updatedResource => {
  console.log('Updated Resource Data:', updatedResource);
});
```

**13. getResourcesByIds**

```javascript
const resourceIds = ['resource-id-1', 'resource-id-2'];
resourceService.getResourcesByIds(resourceIds).subscribe(resources => {
  console.log('Resources by IDs:', resources);
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
const ruleChainName = 'My New Rule Chain';
ruleChainService.createDefaultRuleChain(ruleChainName).subscribe(ruleChain => {
  console.log('Created Default Rule Chain:', ruleChain);
});
```

**6. saveRuleChain**

```javascript
const ruleChain = {
  name: 'My Custom Rule Chain',
  root: false,
  // Additional rule chain configuration
};
ruleChainService.saveRuleChain(ruleChain).subscribe(savedRuleChain => {
  console.log('Saved Rule Chain:', savedRuleChain);
});
```

**7. setRootRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setRootRuleChain(ruleChainId).subscribe(rootRuleChain => {
  console.log('Root Rule Chain Set:', rootRuleChain);
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
  ruleChainId: { id: 'your-rule-chain-id' },
  nodes: [
    // Rule nodes configuration
  ],
  connections: [
    // Rule node connections
  ]
};
ruleChainService.saveRuleChainMetadata(ruleChainMetaData).subscribe(savedMetadata => {
  console.log('Saved Rule Chain Metadata:', savedMetadata);
});
```

**10. getRuleNodeComponents**

```javascript
const modulesMap = new Map(); // Modules map
const ruleChainType = 'CORE';
ruleChainService.getRuleNodeComponents(modulesMap, ruleChainType).subscribe(components => {
  console.log('Rule Node Components:', components);
});
```

**11. getRuleNodeConfigComponent**

```javascript
const directive = 'tbFilterNode';
const componentType = ruleChainService.getRuleNodeConfigComponent(directive);
console.log('Rule Node Config Component:', componentType);
```

**12. getRuleNodeComponentByClazz**

```javascript
const ruleChainType = 'CORE';
const clazz = 'org.thingsboard.rule.engine.filter.TbJsFilterNode';
const component = ruleChainService.getRuleNodeComponentByClazz(ruleChainType, clazz);
console.log('Rule Node Component by Class:', component);
```

**13. getRuleNodeSupportedLinks**

```javascript
const component = {
  clazz: 'org.thingsboard.rule.engine.filter.TbJsFilterNode'
};
const supportedLinks = ruleChainService.getRuleNodeSupportedLinks(component);
console.log('Supported Links:', supportedLinks);
```

**14. ruleNodeAllowCustomLinks**

```javascript
const component = {
  clazz: 'org.thingsboard.rule.engine.filter.TbJsFilterNode'
};
const allowCustomLinks = ruleChainService.ruleNodeAllowCustomLinks(component);
console.log('Allow Custom Links:', allowCustomLinks);
```

**15. ruleNodeSourceRuleChainId**

```javascript
const component = {
  clazz: 'org.thingsboard.rule.engine.flow.TbRuleChainInputNode'
};
const config = {
  ruleChainId: 'source-rule-chain-id'
};
const sourceChainId = ruleChainService.ruleNodeSourceRuleChainId(component, config);
console.log('Source Rule Chain ID:', sourceChainId);
```

**16. getLatestRuleNodeDebugInput**

```javascript
const ruleNodeId = 'your-rule-node-id';
ruleChainService.getLatestRuleNodeDebugInput(ruleNodeId).subscribe(debugInput => {
  console.log('Latest Rule Node Debug Input:', debugInput);
});
```

**17. testScript**

```javascript
const inputParams = {
  script: 'return {temperature: msg.temp * 2};',
  msg: { temp: 25.5 },
  metadata: {},
  msgType: 'POST_TELEMETRY_REQUEST'
};
const scriptLang = 'JS'; // Optional
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
  // Array of rule node component descriptors
];
const modulesMap = new Map();
ruleChainService.resolveRuleNodeComponentsUiResources(components, modulesMap).subscribe(resolvedComponents => {
  console.log('Resolved Rule Node Components:', resolvedComponents);
});
```

**20. resolveRuleNodeComponentUiResources**

```javascript
const component = {
  clazz: 'org.thingsboard.rule.engine.filter.TbJsFilterNode'
};
const modulesMap = new Map();
ruleChainService.resolveRuleNodeComponentUiResources(component, modulesMap).subscribe(resolvedComponent => {
  console.log('Resolved Rule Node Component:', resolvedComponent);
});
```

**21. getEdgeRuleChains**

```javascript
const edgeId = 'your-edge-id';
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
ruleChainService.getEdgeRuleChains(edgeId, pageLink).subscribe(ruleChains => {
  console.log('Edge Rule Chains:', ruleChains);
});
```

**22. assignRuleChainToEdge**

```javascript
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.assignRuleChainToEdge(edgeId, ruleChainId).subscribe(assignedRuleChain => {
  console.log('Rule Chain Assigned to Edge:', assignedRuleChain);
});
```

**23. setEdgeTemplateRootRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeTemplateRootRuleChain(ruleChainId).subscribe(templateRuleChain => {
  console.log('Edge Template Root Rule Chain Set:', templateRuleChain);
});
```

**24. setAutoAssignToEdgeRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setAutoAssignToEdgeRuleChain(ruleChainId).subscribe(autoAssignRuleChain => {
  console.log('Auto Assign to Edge Rule Chain Set:', autoAssignRuleChain);
});
```

**25. unsetAutoAssignToEdgeRuleChain**

```javascript
const ruleChainId = 'your-rule-chain-id';
ruleChainService.unsetAutoAssignToEdgeRuleChain(ruleChainId).subscribe(unsetRuleChain => {
  console.log('Auto Assign to Edge Rule Chain Unset:', unsetRuleChain);
});
```

**26. getAutoAssignToEdgeRuleChains**

```javascript
ruleChainService.getAutoAssignToEdgeRuleChains().subscribe(autoAssignRuleChains => {
  console.log('Auto Assign to Edge Rule Chains:', autoAssignRuleChains);
});
```

**27. setEdgeRootRuleChain**

```javascript
const edgeId = 'your-edge-id';
const ruleChainId = 'your-rule-chain-id';
ruleChainService.setEdgeRootRuleChain(edgeId, ruleChainId).subscribe(edge => {
  console.log('Edge Root Rule Chain Set:', edge);
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
  name: 'Custom Tenant Profile',
  // Tenant profile configuration
};
tenantProfileService.saveTenantProfile(tenantProfile).subscribe(savedProfile => {
  console.log('Saved Tenant Profile:', savedProfile);
});
```

**4. setDefaultTenantProfile**

```javascript
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.setDefaultTenantProfile(tenantProfileId).subscribe(defaultProfile => {
  console.log('Default Tenant Profile Set:', defaultProfile);
});
```

**5. getDefaultTenantProfileInfo**

```javascript
tenantProfileService.getDefaultTenantProfileInfo().subscribe(profileInfo => {
  console.log('Default Tenant Profile Info:', profileInfo);
});
```

**6. getTenantProfileInfo**

```javascript
const tenantProfileId = 'your-tenant-profile-id';
tenantProfileService.getTenantProfileInfo(tenantProfileId).subscribe(profileInfo => {
  console.log('Tenant Profile Info:', profileInfo);
});
```

**7. getTenantProfileInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
tenantProfileService.getTenantProfileInfos(pageLink).subscribe(profileInfos => {
  console.log('Tenant Profile Infos:', profileInfos);
});
```

**8. getTenantProfilesByIds**

```javascript
const tenantProfileIds = ['profile-id-1', 'profile-id-2'];
tenantProfileService.getTenantProfilesByIds(tenantProfileIds).subscribe(profiles => {
  console.log('Tenant Profiles by IDs:', profiles);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'title', 'ASC');
tenantService.getTenants(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

**2. getTenantsByIds**

```javascript
const tenantIds = ['tenant-id-1', 'tenant-id-2'];
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
  title: 'ACME Corporation',
  country: 'USA',
  state: 'NY',
  city: 'New York',
  // Additional tenant properties
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
  // Trendz settings configuration
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
  console.log('Two FA Settings:', settings);
});
```

**2. saveTwoFaSettings**

```javascript
const settings = {
  // Two factor authentication settings
};
twoFactorAuthenticationService.saveTwoFaSettings(settings).subscribe(savedSettings => {
  console.log('Saved Two FA Settings:', savedSettings);
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
  console.log('Two FA Account Config:', config);
});
```

**5. getAccountTwoFaSettings**

```javascript
twoFactorAuthenticationService.getAccountTwoFaSettings().subscribe(accountSettings => {
  console.log('Account Two FA Settings:', accountSettings);
});
```

**6. updateTwoFaAccountConfig**

```javascript
const providerType = 'TOTP';
const useByDefault = true;
twoFactorAuthenticationService.updateTwoFaAccountConfig(providerType, useByDefault).subscribe(updatedSettings => {
  console.log('Updated Two FA Account Config:', updatedSettings);
});
```

**7. submitTwoFaAccountConfig**

```javascript
const authConfig = {
  providerType: 'TOTP',
  // Two FA configuration
};
twoFactorAuthenticationService.submitTwoFaAccountConfig(authConfig).subscribe(result => {
  console.log('Two FA config submitted successfully');
});
```

**8. verifyAndSaveTwoFaAccountConfig**

```javascript
const authConfig = {
  providerType: 'TOTP',
  // Two FA configuration
};
const verificationCode = 123456; // Optional
twoFactorAuthenticationService.verifyAndSaveTwoFaAccountConfig(authConfig, verificationCode).subscribe(settings => {
  console.log('Verified and Saved Two FA Config:', settings);
});
```

**9. deleteTwoFaAccountConfig**

```javascript
const providerType = 'TOTP';
twoFactorAuthenticationService.deleteTwoFaAccountConfig(providerType).subscribe(updatedSettings => {
  console.log('Deleted Two FA Account Config:', updatedSettings);
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
uiSettingsService.getHelpBaseUrl().subscribe(helpUrl => {
  console.log('Help Base URL:', helpUrl);
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
  console.log('Usage Info:', usageInfo);
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
  // User settings configuration
};
userSettingsService.saveUserSettings(userSettings).subscribe(savedSettings => {
  console.log('Saved User Settings:', savedSettings);
});
```

**3. putUserSettings**

```javascript
const userSettingsData = {
  // Partial user settings data
};
userSettingsService.putUserSettings(userSettingsData).subscribe(() => {
  console.log('User settings updated successfully');
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
  // Documentation links configuration
};
userSettingsService.updateDocumentationLinks(documentationLinks).subscribe(() => {
  console.log('Documentation links updated successfully');
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
  // Quick links configuration
};
userSettingsService.updateQuickLinks(quickLinks).subscribe(() => {
  console.log('Quick links updated successfully');
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
  // Getting started configuration
};
userSettingsService.updateGettingStarted(gettingStarted).subscribe(() => {
  console.log('Getting started updated successfully');
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
userSettingsService.reportUserDashboardAction(dashboardId, action).subscribe(updatedInfo => {
  console.log('User Dashboard Action Reported:', updatedInfo);
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
const pageLink = self.ctx.pageLink(10, 0, '', 'email', 'ASC');
userService.getUsers(pageLink).subscribe(users => {
  console.log('Users:', users);
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
const userIds = ['user-id-1', 'user-id-2'];
userService.getUsersByIds(userIds).subscribe(users => {
  console.log('Users by IDs:', users);
});
```

**7. saveUser**

```javascript
const user = {
  email: 'user@example.com',
  firstName: 'John',
  lastName: 'Doe',
  // Additional user properties
};
const sendActivationMail = true;
userService.saveUser(user, sendActivationMail).subscribe(savedUser => {
  console.log('Saved User:', savedUser);
});
```

**8. getActivationLink**

```javascript
const userId = 'your-user-id';
userService.getActivationLink(userId).subscribe(activationLink => {
  console.log('Activation Link:', activationLink);
});
```

**9. getActivationLinkInfo**

```javascript
const userId = 'your-user-id';
userService.getActivationLinkInfo(userId).subscribe(activationLinkInfo => {
  console.log('Activation Link Info:', activationLinkInfo);
});
```

**10. setUserCredentialsEnabled**

```javascript
const userId = 'your-user-id';
const userCredentialsEnabled = true; // Optional
userService.setUserCredentialsEnabled(userId, userCredentialsEnabled).subscribe(result => {
  console.log('User credentials enabled status updated');
});
```

**11. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'john', 'email', 'ASC');
userService.findUsersByQuery(pageLink).subscribe(users => {
  console.log('Users by Query:', users);
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
const scopeVariables = widgetService.getWidgetScopeVariables();
console.log('Widget Scope Variables:', scopeVariables);
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
widgetService.exportWidgetsBundle(widgetsBundleId).subscribe(exportedBundle => {
  console.log('Exported Widgets Bundle:', exportedBundle);
});
```

**8. saveWidgetsBundle**

```javascript
const widgetsBundle = {
  title: 'My Custom Bundle',
  // Widgets bundle configuration
};
widgetService.saveWidgetsBundle(widgetsBundle).subscribe(savedBundle => {
  console.log('Saved Widgets Bundle:', savedBundle);
});
```

**9. updateWidgetsBundleWidgetTypes**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeIds = ['widget-type-id-1', 'widget-type-id-2'];
widgetService.updateWidgetsBundleWidgetTypes(widgetsBundleId, widgetTypeIds).subscribe(() => {
  console.log('Widget bundle widget types updated successfully');
});
```

**10. updateWidgetsBundleWidgetFqns**

```javascript
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypeFqns = ['bundle.widget1', 'bundle.widget2'];
widgetService.updateWidgetsBundleWidgetFqns(widgetsBundleId, widgetTypeFqns).subscribe(() => {
  console.log('Widget bundle widget FQNs updated successfully');
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
widgetService.exportBundleWidgetTypesDetails(widgetsBundleId).subscribe(widgetTypesDetails => {
  console.log('Exported Bundle Widget Types Details:', widgetTypesDetails);
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
widgetService.getBundleWidgetTypeInfosList(widgetsBundleId).subscribe(widgetTypeInfos => {
  console.log('Bundle Widget Type Infos List:', widgetTypeInfos);
});
```

**15. getBundleWidgetTypeInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const widgetsBundleId = 'your-widgets-bundle-id';
const widgetTypes = ['timeseries', 'latest'];
widgetService.getBundleWidgetTypeInfos(pageLink, widgetsBundleId, widgetTypes).subscribe(widgetTypeInfos => {
  console.log('Bundle Widget Type Infos:', widgetTypeInfos);
});
```

**16. getWidgetType**

```javascript
const fullFqn = 'cards.simple_card';
widgetService.getWidgetType(fullFqn).subscribe(widgetType => {
  console.log('Widget Type:', widgetType);
});
```

**17. saveWidgetTypeDetails**

```javascript
const widgetInfo = {
  // Widget information
};
const id = { id: 'widget-type-id' };
const createdTime = Date.now();
const version = 1;
widgetService.saveWidgetTypeDetails(widgetInfo, id, createdTime, version).subscribe(savedWidgetType => {
  console.log('Saved Widget Type Details:', savedWidgetType);
});
```

**18. saveImportedWidgetTypeDetails**

```javascript
const widgetTypeDetails = {
  // Widget type details from import
};
widgetService.saveImportedWidgetTypeDetails(widgetTypeDetails).subscribe(importedWidgetType => {
  console.log('Saved Imported Widget Type Details:', importedWidgetType);
});
```

**19. getWidgetTypeById**

```javascript
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeById(widgetTypeId).subscribe(widgetTypeDetails => {
  console.log('Widget Type by ID:', widgetTypeDetails);
});
```

**20. exportWidgetType**

```javascript
const widgetTypeId = 'your-widget-type-id';
widgetService.exportWidgetType(widgetTypeId).subscribe(exportedWidgetType => {
  console.log('Exported Widget Type:', exportedWidgetType);
});
```

**21. getWidgetTypeInfoById**

```javascript
const widgetTypeId = 'your-widget-type-id';
widgetService.getWidgetTypeInfoById(widgetTypeId).subscribe(widgetTypeInfo => {
  console.log('Widget Type Info by ID:', widgetTypeInfo);
});
```

**22. saveWidgetType**

```javascript
const widgetTypeDetails = {
  // Widget type configuration
};
widgetService.saveWidgetType(widgetTypeDetails).subscribe(savedWidgetType => {
  console.log('Saved Widget Type:', savedWidgetType);
});
```

**23. getWidgetTypes**

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'name', 'ASC');
const widgetTypes = ['timeseries', 'latest'];
widgetService.getWidgetTypes(pageLink, widgetTypes).subscribe(widgetTypeInfos => {
  console.log('Widget Types:', widgetTypeInfos);
});
```

**24. getWidgetTemplate**

```javascript
const widgetTypeParam = 'cards.simple_card';
widgetService.getWidgetTemplate(widgetTypeParam).subscribe(widgetTemplate => {
  console.log('Widget Template:', widgetTemplate);
});
```

**25. getWidgetInfoFromCache**

```javascript
const fullFqn = 'cards.simple_card';
const widgetInfo = widgetService.getWidgetInfoFromCache(fullFqn);
console.log('Widget Info from Cache:', widgetInfo);
```

**26. getBasicWidgetSettingsComponentBySelector**

```javascript
const selector = 'tb-basic-chart-config';
const componentType = widgetService.getBasicWidgetSettingsComponentBySelector(selector);
console.log('Basic Widget Settings Component:', componentType);
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
  // Updated widget type
};
widgetService.widgetTypeUpdated(updatedWidgetType);
console.log('Widget type updated notification sent');
```

**29. getWidgetsBundlesByIds**

```javascript
const widgetsBundleIds = ['bundle-id-1', 'bundle-id-2'];
widgetService.getWidgetsBundlesByIds(widgetsBundleIds).subscribe(bundles => {
  console.log('Widgets Bundles by IDs:', bundles);
});
```

**30. loadWidgetsBundleCache**

```javascript
widgetService.loadWidgetsBundleCache().subscribe(result => {
  console.log('Widgets bundle cache loaded successfully');
});
```

---

## Complete Reference

This documentation covers all available ThingsBoard widget services. For additional examples and advanced usage patterns, refer to the ThingsBoard documentation and community forums.

Remember to always handle errors appropriately in your widget code:

```javascript
deviceService.getDevice(deviceId).subscribe(
  device => {
    console.log('Device:', device);
  },
  error => {
    console.error('Error loading device:', error);
  }
);
```