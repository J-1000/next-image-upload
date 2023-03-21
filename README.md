## Image upload using cloudinary

Sign up on [Cloudinary](https://cloudinary.com/)

Go to the dashboard you need the `cloudname`

Then go to settings -> upload and add a new upload preset. You need to copy the name and you need to set it to `unsigned`.

Everything happens in index.js in this example

Add your preset name and cloudname here 

```js
formData.append('upload_preset', '<your name of the preset>');

const data = await fetch('https://api.cloudinary.com/v1_1/<your cloud name>/image/upload', {
	method: 'POST',
	body: formData
}).then(r => r.json());
```

The url of the uploaded image is in the data of the response `secure_url` - this url would be stored in mongodb. You could make another request to an api route to do that.
