# IMAGE SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

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
