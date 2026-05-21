# ImageService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const imageService = $injector.get(self.ctx.servicesMap.get('ImageService'));
```

**1. uploadImage**

```javascript
imageService.uploadImage('your-file-value', 'your-title-value', 'your-imagesubtype-value').subscribe(result => {
  console.log('upload Image result:', result);
});
```

**2. updateImage**

```javascript
imageService.updateImage('your-type-value', 'your-api-key', 'your-file-value').subscribe(result => {
  console.log('update Image result:', result);
});
```

**3. updateImageInfo**

```javascript
imageService.updateImageInfo('your-imageinfo-value').subscribe(info => {
  console.log('update Image Info info:', info);
});
```

**4. updateImagePublicStatus**

```javascript
imageService.updateImagePublicStatus('your-imageinfo-value', true).subscribe(result => {
  console.log('update Image Public Status result:', result);
});
```

**5. getImages**

```javascript
imageService.getImages(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), 'your-imagesubtype-value').subscribe(result => {
  console.log('Fetched  Images result:', result);
});
```

**6. getImageInfo**

```javascript
imageService.getImageInfo('your-type-value', 'your-api-key').subscribe(info => {
  console.log('Fetched  Image Info info:', info);
});
```

**7. getImageDataUrl**

```javascript
imageService.getImageDataUrl('your-imageurl-value').subscribe(data => {
  console.log('Fetched  Image Data Url data:', data);
});
```

**8. loadImageDataUrl**

```javascript
imageService.loadImageDataUrl('your-imagelink-value').subscribe(data => {
  console.log('load Image Data Url data:', data);
});
```

**9. getImageString**

```javascript
imageService.getImageString('your-imageurl-value').subscribe(result => {
  console.log('Fetched  Image String result:', result);
});
```

**10. resolveImageUrl**

```javascript
imageService.resolveImageUrl('your-imageurl-value').subscribe(result => {
  console.log('resolve Image Url result:', result);
});
```

**11. downloadImage**

```javascript
imageService.downloadImage('your-type-value', 'your-api-key').subscribe(result => {
  console.log('download Image result:', result);
});
```

**12. exportImage**

```javascript
imageService.exportImage('your-type-value', 'your-api-key').subscribe(result => {
  console.log('export Image result:', result);
});
```

**13. importImage**

```javascript
imageService.importImage('your-imagedata-value').subscribe(result => {
  console.log('import Image result:', result);
});
```
