# IMAGE SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

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

**8. getLoginImageDataUrl**

```javascript
imageService.getLoginImageDataUrl('your-imageurl-value', true).subscribe(loginImageDataUrl => {
  console.log('Get Login Image Data Url:', loginImageDataUrl);
});
```

**9. loadImageDataUrl**

```javascript
imageService.loadImageDataUrl('your-imagelink-value').subscribe(loadImageDataUrl => {
  console.log('Load Image Data Url:', loadImageDataUrl);
});
```

**10. getImageString**

```javascript
imageService.getImageString('your-imageurl-value').subscribe(imageString => {
  console.log('Get Image String:', imageString);
});
```

**11. resolveImageUrl**

```javascript
imageService.resolveImageUrl('your-imageurl-value').subscribe(resolveImageUrl => {
  console.log('Resolve Image Url:', resolveImageUrl);
});
```

**12. resolveLoginImageUrl**

```javascript
imageService.resolveLoginImageUrl('your-imageurl-value', true).subscribe(resolveLoginImageUrl => {
  console.log('Resolve Login Image Url:', resolveLoginImageUrl);
});
```

**13. downloadImage**

```javascript
imageService.downloadImage('your-type-value', 'your-key-value').subscribe(downloadImage => {
  console.log('Download Image:', downloadImage);
});
```

**14. exportImage**

```javascript
imageService.exportImage('your-type-value', 'your-key-value').subscribe(image => {
  console.log('Export Image:', image);
});
```

**15. importImage**

```javascript
imageService.importImage('your-imagedata-value').subscribe(image => {
  console.log('Import Image:', image);
});
```
