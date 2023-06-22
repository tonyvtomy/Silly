Silly
---
🖼 A powerful, easy-to-use image downloading and caching library for **Unity** in Run-Time! 😎 

![](https://github.com/tonyvtomy/Silly/blob/master/Images/image1.gif?raw=true)

Simple usage - Single line of code and ready to go!
```csharp
Silly.get().load(imageUrl).into(image).start();
```

🔴 **Update : Support for any type of Renderer components has been added. now we can download 3D model's textures in run-time!**

![](https://github.com/tonyvtomy/Silly/blob/master/Images/image2.gif?raw=true)


Features
---
### Customizable image placeholders

![](https://github.com/tonyvtomy/Silly/blob/master/Images/image3.gif?raw=true)
```csharp
Silly.get()
    .load(url)
    .setLoadingPlaceholder(loadingTexture)
    .setErrorPlaceholder(errorTexture)
    .into(image)
    .start();
```

### Loading Fade Time

![](https://github.com/tonyvtomy/Silly/blob/master/Images/image4.gif?raw=true)
```csharp
Silly.get()
    .load(url)
    .setFadeTime(2) // 0 for disable fading
    .into(image)
    .start();
```

### Fully access to operation progress and callbacks

![](https://github.com/tonyvtomy/Silly/blob/master/Images/image5.gif?raw=true)
```csharp
Silly.get()
    .load(imageUrl)
    .into(image)
    .withStartAction(() =>
    {
        Debug.Log("Download has been started.");
    })
    .withDownloadProgressChangedAction((progress) =>
    {
        Debug.Log("Download progress: " + progress);
    })
    .withDownloadedAction(() =>
    {
        Debug.Log("Download has been completed.");
    })
    .withLoadedAction(() =>
    {
        Debug.Log("Image has been loaded.");
    })
    .withErrorAction((error) =>
    {
        Debug.Log("Got error : " + error);
    })
    .withEndAction(() =>
    {
        Debug.Log("Operation has been finished.");
    })
    .start();
```

### Caching Control
You can simply cache downloaded images so Davinci won't download it again from the same url. It's cool! Isn't it? 😁
(Default is `True`)

```csharp
Silly.get().load(imageUrl).setCached(true).into(image).start();
```

Also you can clear Davinci cached files: 
```csharp
//For a certain file
Silly.CleareCache(imageUrl);

//For all files
Silly.ClearAllCachedFiles();
```

Also:
- Supports Unity UI Image Component
- Compatible with all platforms and unity versions.

### Supporting Platforms
- Standalone Builds
- Android
- iOS
- WebGl

Usage
----
Clone the project. Open Silly/Assets in unity or import the UnityPackage to your existing project.

You can see lots of examples in Assets/Examples

Please see the Wiki page for more information and examples

TODO
----
 - Add support for textures ✅ 
 - Improvements

License
----
**Silly** is available under the **MIT** license. See the LICENSE file for more info.<br>
**Credit** @Mohammad Shams

