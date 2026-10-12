# AI CHAT SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const aiChatService = $injector.get(self.ctx.servicesMap.get('aiChatService'));
```

**1. listChats**

```javascript
aiChatService.listChats().subscribe(chats => {
  console.log('List Chats:', chats);
});
```

**2. createChat**

```javascript
aiChatService.createChat('your-chat-value').subscribe(chat => {
  console.log('Create Chat:', chat);
});
```

**3. updatedChat**

```javascript
aiChatService.updatedChat('your-chat-id', 'your-chat-value').subscribe(result => {
  console.log('Updated Chat:', result);
});
```

**4. deleteChat**

```javascript
aiChatService.deleteChat('your-chat-id').subscribe(result => {
  console.log('Delete Chat:', result);
});
```

**5. getChatMessages**

```javascript
aiChatService.getChatMessages('your-chat-id').subscribe(chatMessages => {
  console.log('Get Chat Messages:', chatMessages);
});
```

**6. generateDashboard**

```javascript
aiChatService.generateDashboard('your-device-id', 'your-timeserieskeys-value').subscribe(dashboard => {
  console.log('Generate Dashboard:', dashboard);
});
```

**7. resolveToolApproval**

```javascript
aiChatService.resolveToolApproval('your-result-value').subscribe(resolveToolApproval => {
  console.log('Resolve Tool Approval:', resolveToolApproval);
});
```

**8. sendChatMessage**

```javascript
aiChatService.sendChatMessage('your-chat-id', 'your-request-value').subscribe(chatMessage => {
  console.log('Send Chat Message:', chatMessage);
});
```

**9. parseEventStrings**

```javascript
aiChatService.parseEventStrings('your-input-value').subscribe(parseEventStrings => {
  console.log('Parse Event Strings:', parseEventStrings);
});
```

**10. parseSingleEvent**

```javascript
aiChatService.parseSingleEvent('your-input-value').subscribe(parseSingleEvent => {
  console.log('Parse Single Event:', parseSingleEvent);
});
```
