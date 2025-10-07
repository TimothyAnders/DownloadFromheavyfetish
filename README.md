# DownloadFromheavyfetish
Basically, you need CORS turned off, E.G (chrome):    
`start 'C:\Program Files\Google\Chrome\Application\chrome.exe' '--user-data-dir="c:\tmp\chrome_Dev_Test" --disable-web-security'`    

Then, get the file URL by looking at the source code via developer tools..    
Then run this command:    

```
var file = null; var blobb = null;
var x = await fetch(YOUR_URL_HERE, {
  "headers": {
    "accept": "*/*",
    "accept-language": "en-US,en;q=0.9",
    "cache-control": "no-cache",
    "pragma": "no-cache",
    "priority": "i",
    "sec-ch-ua": "\"Google Chrome\";v=\"141\", \"Not?A_Brand\";v=\"8\", \"Chromium\";v=\"141\"",
    "sec-ch-ua-mobile": "?0",
    "sec-ch-ua-platform": "\"Windows\"",
    "sec-fetch-mode": "no-cors",
    "sec-fetch-site": "cross-site",
    "sec-fetch-dest": "video",
    "sec-fetch-storage-access": "active"
  },
  "referrer": "https://heavyfetish.com/",
  "body": null,
  "method": "POST",
  "mode": "cors",
  "credentials": "include"
}).then( res => res.blob() )
  .then( blob => {
      blobb = blob;
    file =  URL.createObjectURL(blob);
    // window.location.assign(file);
  });
```

Then, you can use:
`file.src` and put that into a browser to download the video! (takes a while to load file, it will be undefined/null for a moment)            
