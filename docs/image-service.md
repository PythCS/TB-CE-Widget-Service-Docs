# IMAGE SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
```

**1. uploadImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const file = {  // File object
  // ... set the fields you need
};
const title = 'title-value';
const imageSubType = 'value';
imageService.uploadImage(file, title, imageSubType).subscribe(savedImage => {
  console.log('Saved Image:', savedImage);
});
```

**2. updateImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const type = {  // ImageResourceType object
  // ... set the fields you need
};
const key = 'key-value';
const file = {  // File object
  // ... set the fields you need
};
imageService.updateImage(type, key, file).subscribe(savedImage => {
  console.log('Saved Image:', savedImage);
});
```

**3. updateImageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageInfo = {  // ImageResourceInfo object
  // ... set the fields you need
};
imageService.updateImageInfo(imageInfo).subscribe(savedImageInfo => {
  console.log('Saved Image Info:', savedImageInfo);
});
```

**4. updateImagePublicStatus**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageInfo = {  // ImageResourceInfo object
  // ... set the fields you need
};
const isPublic = true;
imageService.updateImagePublicStatus(imageInfo, isPublic).subscribe(savedImagePublicStatus => {
  console.log('Saved Image Public Status:', savedImagePublicStatus);
});
```

**5. getImages**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
const imageSubType = 'value';
imageService.getImages(pageLink, imageSubType).subscribe(images => {
  console.log('List of Images:', images);
});
```

**6. getImageInfo**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const type = {  // ImageResourceType object
  // ... set the fields you need
};
const key = 'key-value';
imageService.getImageInfo(type, key).subscribe(imageInfo => {
  console.log('Get Image Info:', imageInfo);
});
```

**7. getImageDataUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
imageService.getImageDataUrl(imageUrl).subscribe(imageDataUrl => {
  console.log('Get Image Data Url:', imageDataUrl);
});
```

**8. getLoginImageDataUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
const faviconElseLogo = true;
imageService.getLoginImageDataUrl(imageUrl, faviconElseLogo).subscribe(loginImageDataUrl => {
  console.log('Get Login Image Data Url:', loginImageDataUrl);
});
```

**9. loadImageDataUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageLink = 'your-image-link';
imageService.loadImageDataUrl(imageLink).subscribe(imageDataUrl => {
  console.log('Load Image Data Url:', imageDataUrl);
});
```

**10. getImageString**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
imageService.getImageString(imageUrl).subscribe(imageString => {
  console.log('Get Image String:', imageString);
});
```

**11. resolveImageUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
imageService.resolveImageUrl(imageUrl).subscribe(resolveImageUrl => {
  console.log('Resolve Image Url:', resolveImageUrl);
});
```

**12. resolveLoginImageUrl**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageUrl = 'your-image-url';
const faviconElseLogo = true;
imageService.resolveLoginImageUrl(imageUrl, faviconElseLogo).subscribe(resolveLoginImageUrl => {
  console.log('Resolve Login Image Url:', resolveLoginImageUrl);
});
```

**13. downloadImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const type = {  // ImageResourceType object
  // ... set the fields you need
};
const key = 'key-value';
imageService.downloadImage(type, key).subscribe(downloadImage => {
  console.log('Download Image:', downloadImage);
});
```

**14. exportImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const type = {  // ImageResourceType object
  // ... set the fields you need
};
const key = 'key-value';
imageService.exportImage(type, key).subscribe(exportImage => {
  console.log('Export Image:', exportImage);
});
```

**15. importImage**

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('imageService'));
const imageData = {  // ImageExportData object
  // ... set the fields you need
};
imageService.importImage(imageData).subscribe(importImage => {
  console.log('Import Image:', importImage);
});
```
