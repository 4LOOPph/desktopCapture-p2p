# [TESSA Screen Share extension](https://github.com/4LOOPph/desktopCapture-p2p)

This chrome extension not only captures content of screen, but also provides multi-user peer-to-peer screen streaming.

## How to install?

<a target="_blank" href="https://chrome.google.com/webstore/detail/webrtc-desktop-sharing/klaagnfcilpkdeicdamepejjmaoahple"><img alt="Try it now" src="https://raw.github.com/GoogleChrome/chrome-app-samples/master/tryitnowbutton_small.png" title="Click here to install this sample from the Chrome Web Store"></img></a>

* https://chrome.google.com/webstore/detail/tessa-presentation/abggimbnoanedfgibfmkilplcmehkfln

## How to view screen?

Try any of the below URL. Replace `your_room_id` with real room-id:

```
http://4loopph.github.io/projects/projects/tessa/presentation.html?s=tEs$@486759
```
OR
```
http://tessa.cc/presentation.html?s=tEs$@486759
```

## How to publish yourself?

Make ZIP of the directory. Then navigate to [Chrome WebStore Developer Dashboard](https://chrome.google.com/webstore/developer/dashboard) and click **Add New Item** blue button.

To learn more about how to publish a chrome extension in Google App Store:

* https://developer.chrome.com/webstore/publish

## How to add inline-install button?

**Make sure that you added and verified your webpage/domain using Google WebMaster tools.** Additional instructions available [here](https://support.google.com/webmasters/answer/35179?hl=en).

```html
<!DOCTYPE html>
<html>
    <head>
        <!-- head; this <link> tag MUST be in <head> section -->
        <link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/your-chrome-extension-id">
    </head>
    <body>
        <!-- body; the button element that is used to invoke inline installation -->
        <button onclick="" id="install-button" style="padding: 0;background: none;height: 61px;vertical-align: middle;cursor:pointer;">
            <img src="https://www.webrtc-experiment.com/images/btn-install-chrome-extension.png" alt="Add to Chrome">
        </button>
        
        <script>
            document.querySelector('#inline-install').onclick = function() {
                !!navigator.webkitGetUserMedia 
                    && !!window.chrome 
                    && !!chrome.webstore 
                    && !!chrome.webstore.install && 
                chrome.webstore.install(
                    'https://chrome.google.com/webstore/detail/your-chrome-extension-id', 
                    successCallback, 
                    failureCallback
                );
            };
            
            function successCallback() {
                location.reload();
            }
            
            function failureCallback(error) {
                alert(error);
            }
        </script>
    </body>
</html>
```
