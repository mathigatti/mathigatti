---
title: reviews
---
This is a sample of 6 reviews I received working as a freelance developer and teacher at [codementor](https://www.codementor.io/@mathiasgatti). You can recharge the website to see a new set of reviews.




<iframe src="https://reviews.mathigatti.com/" frameBorder="0" scrolling="no" width="100%" id="ifrm"></iframe>


<script type="text/javascript">
function getDocHeight(doc) {
    doc = doc || document;
    // stackoverflow.com/questions/1145850/
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
    ifrm.style.height = "10px"; // reset to minimal height ...
    // IE opt. for bing/msn needs a bit added or scrollbar appears
    ifrm.style.height = getDocHeight( doc ) + 4 + "px";
    ifrm.style.visibility = 'visible';
}

document.getElementById('ifrm').onload = function() { // Adjust the Id accordingly
    setIframeHeight(this.id);
}
</script>
