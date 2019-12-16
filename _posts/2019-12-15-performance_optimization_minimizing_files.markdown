---
layout: post
title:      "Performance Optimization: Minimizing Files"
date:       2019-12-15 21:03:38 -0500
permalink:  performance_optimization_minimizing_files
---


As web developers, it is not only important for us to create functioning and attractive web applications, but we must also ensure that our applications are performance optimized. Optimization is important because it affects the loading time of your application. The longer your application takes to load, the more likely a user is to navigate away from your page or app. 

![](https://media1.tenor.com/images/21c0e8dc0259f94a7aae44817bd24b1d/tenor.gif?itemid=5434959)

Luckily there are many ways to increase  your application’s performance and speed, the easiest being to reduce its file size. The more kilobytes that need to be downloaded for your application, the longer your application’s loading time. Thus by minimizing your text files and images, you can drastically enhance the performance of your application or website. 
## Make it Ugly

Minimizing your text files is really simple through the use of [UglifyJS](https://skalman.github.io/UglifyJS-online/). 

UglifyJS takes your text files (HTML, CSS, and JS)  and minifies or "uglifies" the code within. All of the white space and indentation that makes your code easy to read is removed, reducing file size. Clean, readable code is important when working with fellow humans, however, since your code will be read and processed by machines, the readability of your code isn’t important. In fact, the "pretty" code is adding to your application's file size and negatively impacting its performance.  

![](https://i.imgur.com/Y1mWIkX.png)

As you can see in the above photo, by removing the indentation and spacing UglifyJS reduced the text file size by 191 bytes.  Minifying each of your text files will reduce load times and greatly enhance the performance of your application.  

Your application can be further optimized through the reduction of your image files. Image files can be reduced through compression, resizing, and the removal of metadata.   

## Compression

Sites like[ TinyPNG](https://tinypng.com/) and [JPEG Optimizer](http://www.jpeg-optimizer.com/) can be used to quickly and efficiently compress and resize your images.  TinyPNG  works by finding similar colors in your images and combining them. Through this technique known as "quantization", TinyPNG can convert 24-bit PNG files to much smaller 8-bit indexed color images.  Since reducing color count in images leads to huge file savings,  your application's performance will greatly increase as a result.

This process is just as simple with JPEG Optimizer. Upon uploading a photo, select a compression level and width for the new photo and select ‘Optimize Photo’. 

![](https://i.imgur.com/39Vj8HL.png)

Depending on the size of your photo, this process may take a bit of time. Once uploaded, JPEG Optimizer will give you a report of how much savings in filesize was achived. 

![](https://i.imgur.com/tujSJce.png)

Wow! By using JPEG Optimizer, I was able to reduce my image file by over 99%. This simple compression technique can drastically reduce your image sizes and as a result make your application perform much faster.  

## Media Queries

Another great boon to performance is through the resizing of images for different screen sizes.  This resizing can be achieved through a CSS technique called media query.  Media queries use the ` @media`  rule  to specify a block of CSS properties only if a certain condition is true. 

```
@media screen and (min-width: 900px) {
  body {
   background: url('./large-background.jpg');
   background-size:cover
 }
}
```

In this example, the media query is saying that while the screen or browser window is at least 900px wide, the large background image will be loaded.  

```
@media screen and (max-width: 600px) {
  body {
    background-color: lightpink
  }
}
```

But when the screen or browser window becomes smaller than 600px, the background image will be replaced with a light pink color.  

This consideration for screen size greatly enhances performance because the background photo for larger screens will not be downloaded by the browser unless the user is viewing your application on the appropriately sized screen. 

## Removing Metadata

The last tip I have for reducing your image size is through the removal of metadata.  Metadata refers to the meta tags that are automatically saved when most photos are taken. These tags can include information such as the date and time the photo was taken, the device with which the photo was taken, and even the exact GPS location where the photo was taken. Removing these unnecessary meta tags not only removes privacy concerns surrounding your photos, but will also reduce your image file size. 

Through sites like[ Ver Exif](http://www.verexif.com/en/), you can remove the metadata from all of your pictures without having to download any programs.

![](https://media.giphy.com/media/l3vQY4uui06iabkli/giphy.gif)

By reducing the size of your text files and compressing, resizing, and removing metadata from your images you can greatly enhance the performance of your application or website.  Once these steps are taken, you can further optimize your application by improving network latency and backend processing, but that's a lesson for another day.
