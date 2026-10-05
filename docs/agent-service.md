# AGENT SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
```

**1. getAgentById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
agentService.getAgentById(agentId).subscribe(agentBy => {
  console.log('Get Agent By Id:', agentBy);
});
```

**2. getAgentInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
agentService.getAgentInfoById(agentId).subscribe(agentInfoBy => {
  console.log('Get Agent Info By Id:', agentInfoBy);
});
```

**3. getAgentInfosByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentIds = ['your-agent-i-1', 'your-agent-i-2'];
agentService.getAgentInfosByIds(agentIds).subscribe(agentInfosBys => {
  console.log('Get Agent Infos By Ids:', agentInfosBys);
});
```

**4. getAgentInstallInstructions**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const method = 'value';
agentService.getAgentInstallInstructions(agentId, method).subscribe(agentInstallInstructions => {
  console.log('Get Agent Install Instructions:', agentInstallInstructions);
});
```

**5. getAgentProvisionInstructions**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const method = 'value';
agentService.getAgentProvisionInstructions(agentProfileId, method).subscribe(agentProvisionInstructions => {
  console.log('Get Agent Provision Instructions:', agentProvisionInstructions);
});
```

**6. upgradeAgent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const imageRef = 'your-image-ref';
agentService.upgradeAgent(agentId, imageRef).subscribe(upgradeAgent => {
  console.log('Upgrade Agent:', upgradeAgent);
});
```

**7. saveAgent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agent = {  // Agent object
  // ... set the fields you need
};
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
agentService.saveAgent(agent, entityGroupIds).subscribe(savedAgent => {
  console.log('Saved Agent:', savedAgent);
});
```

**8. join**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const result = agentService.join();
console.log('Result:', result);
```

**9. deleteAgent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
agentService.deleteAgent(agentId).subscribe(result => {
  console.log('Delete Agent result:', result);
});
```

**10. getTenantAgentInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentInfos(pageLink).subscribe(tenantAgentInfos => {
  console.log('List of Tenant Agent Infos:', tenantAgentInfos);
});
```

**11. getCustomerAgentInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getCustomerAgentInfos(customerId, pageLink).subscribe(customerAgentInfos => {
  console.log('List of Customer Agent Infos:', customerAgentInfos);
});
```

**12. getAgentProfileById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.getAgentProfileById(agentProfileId).subscribe(agentProfileBy => {
  console.log('Get Agent Profile By Id:', agentProfileBy);
});
```

**13. getAgentProfileInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.getAgentProfileInfoById(agentProfileId).subscribe(agentProfileInfoBy => {
  console.log('Get Agent Profile Info By Id:', agentProfileInfoBy);
});
```

**14. saveAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfile = {  // AgentProfile object
  // ... set the fields you need
};
const appProfileIds = ['your-app-profile-i-1', 'your-app-profile-i-2'];
agentService.saveAgentProfile(agentProfile, appProfileIds).subscribe(savedAgentProfile => {
  console.log('Saved Agent Profile:', savedAgentProfile);
});
```

**15. deleteAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.deleteAgentProfile(agentProfileId).subscribe(result => {
  console.log('Delete Agent Profile result:', result);
});
```

**16. setDefaultAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.setDefaultAgentProfile(agentProfileId).subscribe(setDefaultAgentProfile => {
  console.log('Set Default Agent Profile:', setDefaultAgentProfile);
});
```

**17. getDefaultAgentProfileInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
agentService.getDefaultAgentProfileInfo().subscribe(defaultAgentProfileInfo => {
  console.log('Get Default Agent Profile Info:', defaultAgentProfileInfo);
});
```

**18. getTenantAgentProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentProfiles(pageLink).subscribe(tenantAgentProfiles => {
  console.log('List of Tenant Agent Profiles:', tenantAgentProfiles);
});
```

**19. getTenantAgentProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentProfileInfos(pageLink).subscribe(tenantAgentProfileInfos => {
  console.log('List of Tenant Agent Profile Infos:', tenantAgentProfileInfos);
});
```

**20. getAgentProfileAppProfileInfos**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
agentService.getAgentProfileAppProfileInfos(agentProfileId).subscribe(agentProfileAppProfileInfos => {
  console.log('Get Agent Profile App Profile Infos:', agentProfileAppProfileInfos);
});
```

**21. assignAppProfileToAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
agentService.assignAppProfileToAgentProfile(agentProfileId, applicationProfileId).subscribe(assignAppProfileToAgentProfile => {
  console.log('Assign App Profile To Agent Profile:', assignAppProfileToAgentProfile);
});
```

**22. assignAppProfilesToAgentProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const appProfileIds = ['your-app-profile-i-1', 'your-app-profile-i-2'];
agentService.assignAppProfilesToAgentProfile(agentProfileId, appProfileIds).subscribe(assignAppProfilesToAgentProfile => {
  console.log('Assign App Profiles To Agent Profile:', assignAppProfilesToAgentProfile);
});
```

**23. join**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const result = agentService.join();
console.log('Result:', result);
```

**24. setAppProfileRelatesOnAutoDiscovery**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
const relate = true;
agentService.setAppProfileRelatesOnAutoDiscovery(agentProfileId, applicationProfileId, relate).subscribe(setAppProfileRelatesOnAutoDiscovery => {
  console.log('Set App Profile Relates On Auto Discovery:', setAppProfileRelatesOnAutoDiscovery);
});
```

**25. previewBulkOperation**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
const request = {  // BulkOperationRequest object
  // ... set the fields you need
};
agentService.previewBulkOperation(agentProfileId, applicationProfileId, request).subscribe(previewBulkOperation => {
  console.log('Preview Bulk Operation:', previewBulkOperation);
});
```

**26. bulkOperation**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
const request = {  // BulkOperationRequest object
  // ... set the fields you need
};
agentService.bulkOperation(agentProfileId, applicationProfileId, request).subscribe(bulkOperation => {
  console.log('Bulk Operation:', bulkOperation);
});
```

**27. getAgentApplicationInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
agentService.getAgentApplicationInfoById(applicationId).subscribe(agentApplicationInfoBy => {
  console.log('Get Agent Application Info By Id:', agentApplicationInfoBy);
});
```

**28. getAgentApplicationsByAgentId**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentApplicationsByAgentId(agentId, pageLink).subscribe(agentApplicationsByAgents => {
  console.log('List of Agent Applications By Agent Ids:', agentApplicationsByAgents);
});
```

**29. getAgentApplicationByRelatedEntity**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const entityType = 'your-entity-type';
const entityId = 'your-entity-id';
agentService.getAgentApplicationByRelatedEntity(entityType, entityId).subscribe(agentApplicationByRelatedEntity => {
  console.log('Get Agent Application By Related Entity:', agentApplicationByRelatedEntity);
});
```

**30. updateAgentApplication**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const application = {  // AgentApplication object
  // ... set the fields you need
};
agentService.updateAgentApplication(application).subscribe(savedAgentApplication => {
  console.log('Saved Agent Application:', savedAgentApplication);
});
```

**31. installAgentApp**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const request = {  // AgentAppEventRequest object
  // ... set the fields you need
};
agentService.installAgentApp(request).subscribe(installAgentApp => {
  console.log('Install Agent App:', installAgentApp);
});
```

**32. createAgentAppEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const request = {  // AgentAppEventRequest object
  // ... set the fields you need
};
agentService.createAgentAppEvent(applicationId, request).subscribe(createAgentAppEvent => {
  console.log('Create Agent App Event:', createAgentAppEvent);
});
```

**33. cancelAgentAppEvent**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const eventId = 'your-event-id';
agentService.cancelAgentAppEvent(applicationId, eventId).subscribe(cancelAgentAppEvent => {
  console.log('Cancel Agent App Event:', cancelAgentAppEvent);
});
```

**34. getAgentAppEventById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const eventId = 'your-event-id';
agentService.getAgentAppEventById(eventId).subscribe(agentAppEventBy => {
  console.log('Get Agent App Event By Id:', agentAppEventBy);
});
```

**35. getAgentAppEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const actionType = 'your-action-type';
const processingStatus = 'your-processing-status';
agentService.getAgentAppEvents(applicationId, pageLink, actionType, processingStatus).subscribe(agentAppEvents => {
  console.log('List of Agent App Events:', agentAppEvents);
});
```

**36. getAgentAppEventsByAgentId**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentAppEventsByAgentId(agentId, pageLink).subscribe(agentAppEventsByAgents => {
  console.log('List of Agent App Events By Agent Ids:', agentAppEventsByAgents);
});
```

**37. getAgentAppEventInfosByAgentId**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentId = 'your-agent-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const actionType = 'your-action-type';
const processingStatus = 'your-processing-status';
agentService.getAgentAppEventInfosByAgentId(agentId, pageLink, actionType, processingStatus).subscribe(agentAppEventInfosByAgents => {
  console.log('List of Agent App Event Infos By Agent Ids:', agentAppEventInfosByAgents);
});
```

**38. mergeForPreview**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const templateVersion = 'your-template-version';
const appType = {  // AgentApplicationType object
  // ... set the fields you need
};
const application = {  // AgentApplication object
  // ... set the fields you need
};
const composeType = 'your-compose-type';
const relatedEntityId = {  // EntityId object
  // ... set the fields you need
};
const actionType = {  // AgentAppEventActionType object
  // ... set the fields you need
};
const setHostValues = true;
agentService.mergeForPreview(templateVersion, appType, application, composeType, relatedEntityId, actionType, setHostValues).subscribe(mergeForPreview => {
  console.log('Merge For Preview:', mergeForPreview);
});
```

**39. assignRelatedEntity**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const relatedEntityId = {  // EntityId object
  // ... set the fields you need
};
agentService.assignRelatedEntity(applicationId, relatedEntityId).subscribe(assignRelatedEntity => {
  console.log('Assign Related Entity:', assignRelatedEntity);
});
```

**40. unassignRelatedEntity**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
agentService.unassignRelatedEntity(applicationId).subscribe(unassignRelatedEntity => {
  console.log('Unassign Related Entity:', unassignRelatedEntity);
});
```

**41. detachFromProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
agentService.detachFromProfile(applicationId).subscribe(detachFromProfile => {
  console.log('Detach From Profile:', detachFromProfile);
});
```

**42. attachToProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const profileId = 'your-profile-id';
agentService.attachToProfile(applicationId, profileId).subscribe(attachToProfile => {
  console.log('Attach To Profile:', attachToProfile);
});
```

**43. getLatestAgentAppTemplate**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = 'your-app-type';
const configType = 'your-config-type';
agentService.getLatestAgentAppTemplate(appType, configType).subscribe(latestAgentAppTemplate => {
  console.log('Get Latest Agent App Template:', latestAgentAppTemplate);
});
```

**44. getAgentAppTemplateByVersion**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = 'your-app-type';
const configType = 'your-config-type';
const version = 'your-version';
agentService.getAgentAppTemplateByVersion(appType, configType, version).subscribe(agentAppTemplateByVersion => {
  console.log('Get Agent App Template By Version:', agentAppTemplateByVersion);
});
```

**45. getAgentAppTemplates**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
agentService.getAgentAppTemplates().subscribe(agentAppTemplates => {
  console.log('Get Agent App Templates:', agentAppTemplates);
});
```

**46. getAgentAppProfilesByAppType**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = 'your-app-type';
agentService.getAgentAppProfilesByAppType(appType).subscribe(agentAppProfilesByAppType => {
  console.log('Get Agent App Profiles By App Type:', agentAppProfilesByAppType);
});
```

**47. getAgentAppTemplatesByAppType**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = 'your-app-type';
const configType = 'value';
agentService.getAgentAppTemplatesByAppType(appType, configType).subscribe(agentAppTemplatesByAppType => {
  console.log('Get Agent App Templates By App Type:', agentAppTemplatesByAppType);
});
```

**48. getAgentAppProfileById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profileId = 'your-profile-id';
agentService.getAgentAppProfileById(profileId).subscribe(agentAppProfileBy => {
  console.log('Get Agent App Profile By Id:', agentAppProfileBy);
});
```

**49. getAgentAppProfileInfoById**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profileId = 'your-profile-id';
agentService.getAgentAppProfileInfoById(profileId).subscribe(agentAppProfileInfoBy => {
  console.log('Get Agent App Profile Info By Id:', agentAppProfileInfoBy);
});
```

**50. saveAgentAppProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profile = {  // AgentAppProfile object
  // ... set the fields you need
};
agentService.saveAgentAppProfile(profile).subscribe(savedAgentAppProfile => {
  console.log('Saved Agent App Profile:', savedAgentAppProfile);
});
```

**51. deleteAgentAppProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profileId = 'your-profile-id';
agentService.deleteAgentAppProfile(profileId).subscribe(result => {
  console.log('Delete Agent App Profile result:', result);
});
```

**52. getTenantAgentAppProfiles**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getTenantAgentAppProfiles(pageLink).subscribe(tenantAgentAppProfiles => {
  console.log('List of Tenant Agent App Profiles:', tenantAgentAppProfiles);
});
```

**53. getAgentAppProfilesByIds**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const profileIds = ['your-profile-i-1', 'your-profile-i-2'];
agentService.getAgentAppProfilesByIds(profileIds).subscribe(agentAppProfilesBys => {
  console.log('Get Agent App Profiles By Ids:', agentAppProfilesBys);
});
```

**54. materializeAgentAppProfile**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const appType = {  // AgentApplicationType object
  // ... set the fields you need
};
const templateVersion = 'your-template-version';
const composeType = 'your-compose-type';
agentService.materializeAgentAppProfile(appType, templateVersion, composeType).subscribe(materializeAgentAppProfile => {
  console.log('Materialize Agent App Profile:', materializeAgentAppProfile);
});
```

**55. mergeProfileForPreview**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const templateVersion = 'your-template-version';
const profile = {  // AgentAppProfile object
  // ... set the fields you need
};
const composeType = 'your-compose-type';
const actionType = {  // AgentAppEventActionType object
  // ... set the fields you need
};
const setHostValues = true;
agentService.mergeProfileForPreview(templateVersion, profile, composeType, actionType, setHostValues).subscribe(mergeProfileForPreview => {
  console.log('Merge Profile For Preview:', mergeProfileForPreview);
});
```

**56. getAgentAppUnits**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const applicationId = 'your-application-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const type = 'type-value';
agentService.getAgentAppUnits(applicationId, pageLink, type).subscribe(agentAppUnits => {
  console.log('List of Agent App Units:', agentAppUnits);
});
```

**57. getAgentBulkAction**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const bulkActionId = 'your-bulk-action-id';
agentService.getAgentBulkAction(bulkActionId).subscribe(agentBulkAction => {
  console.log('Get Agent Bulk Action:', agentBulkAction);
});
```

**58. getAgentProfileBulkActions**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentProfileBulkActions(agentProfileId, pageLink).subscribe(agentProfileBulkActions => {
  console.log('List of Agent Profile Bulk Actions:', agentProfileBulkActions);
});
```

**59. getAgentProfileAppProfileBulkActions**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const agentProfileId = 'your-agent-profile-id';
const applicationProfileId = 'your-application-profile-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
agentService.getAgentProfileAppProfileBulkActions(agentProfileId, applicationProfileId, pageLink).subscribe(agentProfileAppProfileBulkActions => {
  console.log('List of Agent Profile App Profile Bulk Actions:', agentProfileAppProfileBulkActions);
});
```

**60. getAgentBulkActionEventStats**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const bulkActionId = 'your-bulk-action-id';
agentService.getAgentBulkActionEventStats(bulkActionId).subscribe(agentBulkActionEventStats => {
  console.log('Get Agent Bulk Action Event Stats:', agentBulkActionEventStats);
});
```

**61. getAgentBulkActionEvents**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const bulkActionId = 'your-bulk-action-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const actionType = 'your-action-type';
const processingStatus = 'your-processing-status';
agentService.getAgentBulkActionEvents(bulkActionId, pageLink, actionType, processingStatus).subscribe(agentBulkActionEvents => {
  console.log('List of Agent Bulk Action Events:', agentBulkActionEvents);
});
```

**62. getRelatedEntityCandidates**

```javascript
const $injector = self.ctx.$scope.$injector;
const agentService = $injector.get(self.ctx.servicesMap.get('agentService'));
const entityType = {  // EntityType object
  // ... set the fields you need
};
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const currentEntityId = 'your-current-entity-id';
agentService.getRelatedEntityCandidates(entityType, pageLink, currentEntityId).subscribe(relatedEntityCandidates => {
  console.log('List of Related Entity Candidates:', relatedEntityCandidates);
});
```
