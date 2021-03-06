# TFJS Corona FaceMask Detector 
Corona Face Mask Detection with Custom Vision and Tensorflow.js

![](https://cdn-images-1.medium.com/max/1800/1*PgkwI-Id6jYEFRnDJR_Yjw.png)

# Training
This model was trained using the Azure Custom Vision Service. For more details check out the associated [blog post](https://medium.com/microsoftazure/corona-face-mask-detection-with-custom-vision-and-tensorflow-js-86e5fff84373)!

# Usage 
This Tensorflow.js model for Corona Face Mask Detection can be evaluated using the [Custom Vision Tensorflow.js API](https://github.com/microsoft/customvision-tfjs)

### Object Detection
```js
import * as cvstfjs from '@microsoft/customvision-tfjs';

let model = new cvstfjs.ObjectDetectionModel();
await model.loadModelAsync('model.json');
const image = document.getElementById('image');
const result = await model.executeAsync(image);
```

The result has 3 arrays.
```js

[
	[[0.1, 0.3, 0.4, 0.3], [0.2, 0.4, 0.8, 0.9]], // bounding boxes (x1, y1, x2, y2)
	[0.2, 0.3], // probabilities
	[1, 4] // class ids
]
```

