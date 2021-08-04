# new_tab_inactive

very simple chrome extension you can link with your websites to open new tab and dont focus on it,

ex: open mail and don't loose socket connection...

to call the extension on your projects when you do an action:

window.chrome.runtime.sendMessage('get_extension_id', { data });


You can create you own key and extension ID for the manifest:

openssl genrsa 2048 | openssl pkcs8 -topk8 -nocrypt -out key.pem

Key:

openssl rsa -in key.pem -pubout -outform DER | openssl base64 -A

Extension ID:

openssl rsa -in key.pem -pubout -outform DER | shasum -a 256 | head -c32 | tr 0-9a-f a-p