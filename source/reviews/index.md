---
title: reviews
---
This is a sample of 6 reviews I received working as a freelance developer and teacher at [codementor](https://www.codementor.io/@mathiasgatti). You can recharge the website to see a new set of reviews.




<iframe src="https://reviews.mathigatti.com/" frameBorder="0" scrolling="no" width="100%" id="ifrm"></iframe>


<script type="text/javascript">
let frame = document.getElementById('ifrm');
frame.contentWindow.postMessage(1, 'https://mathigatti.com');

window.addEventListener('message', event => {
    // IMPORTANT: check the origin of the data! 
    if (event.origin.includes('mathigatti.com')) {
        // The data was sent from your site.
        // Data sent with postMessage is stored in event.data:
        console.log(event.data); 
    } else {
        // The data was NOT sent from your site! 
        // Be careful! Do not use it. This else branch is
        // here just for clarity, you usually shouldn't need it.
        return; 
    } 
});

function getDocHeight(doc) {
    doc = doc || document;
    var body = doc.body, html = doc.documentElement;
    var height = Math.max( body.scrollHeight, body.offsetHeight, 
        html.clientHeight, html.scrollHeight, html.offsetHeight );
    return height;
}

function setIframeHeight(id) {
    var ifrm = document.getElementById(id);
    var doc = ifrm.contentDocument? ifrm.contentDocument: 
        ifrm.contentWindow.document;
    ifrm.style.visibility = 'hidden';
    ifrm.style.height = "10px";
    ifrm.style.height = getDocHeight( doc ) + 4 + "px";
    ifrm.style.visibility = 'visible';
}

document.getElementById('ifrm').onload = function() {
    setIframeHeight(this.id);
}
</script>
