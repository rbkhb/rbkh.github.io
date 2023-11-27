---
title: "Teaching experience 2"
collection: teaching
type: "Workshop"
permalink: /teaching/2015-spring-teaching-1
venue: "University 1, Department"
date: 2015-01-01
location: "City, Country"
---

This is a description of a teaching experience. You can use markdown like any other post.

Heading 1
======

Heading 2
======

Heading 3
======

Teaching &#8211; Rebekah Baglini

  WebFontConfig = {"google":{"families":["Source+Sans+Pro:r:latin,latin-ext"]},"api_url":"https:\/\/fonts-api.wp.com\/css"};
  (function() {
    var wf = document.createElement('script');
    wf.src = 'https://s0.wp.com/wp-content/plugins/custom-fonts/js/webfont.js';
    wf.type = 'text/javascript';
    wf.async = 'true';
    var s = document.getElementsByTagName('script')[0];
    s.parentNode.insertBefore(wf, s);
})();
.wf-active h1, .wf-active h2, .wf-active h3, .wf-active h4, .wf-active h5, .wf-active h6{font-family:"Source Sans Pro",sans-serif;font-weight:400;font-style:normal}.wf-active h1{font-style:normal;font-weight:400}.wf-active h2{font-style:normal;font-weight:400}.wf-active h3{font-style:normal;font-weight:400}.wf-active h4{font-style:normal;font-weight:400}.wf-active h5{font-style:normal;font-weight:400}.wf-active h6{font-style:normal;font-weight:400}.wf-active .site-title, .wf-active .entry-title{font-family:"Source Sans Pro",sans-serif;font-weight:400;font-style:normal}.wf-active .widget-title{font-family:"Source Sans Pro",sans-serif;font-style:normal;font-weight:400}@media screen and (min-width: 480px){.wf-active .site-title{font-style:normal;font-weight:400}}@media screen and (min-width: 768px){.wf-active .site-title{font-style:normal;font-weight:400}}.wf-active .site-description{font-family:"Source Sans Pro",sans-serif;font-style:normal;font-weight:400}.wf-active div#jp-relatedposts h3.jp-relatedposts-headline{font-family:"Source Sans Pro",sans-serif;font-style:normal;font-weight:400}.wf-active .site-main .post-navigation .meta-nav{font-family:"Source Sans Pro",sans-serif;font-weight:400;font-style:normal}.wf-active .more-link a{font-weight:400;font-style:normal}.wf-active .comments-title{font-style:normal;font-weight:400}.wf-active .comment-reply-title{font-style:normal;font-weight:400}

var wpcom_remote_login_extra_auth = '';
function wpcom_remote_login_remove_dom_node_id( element_id ) {
var dom_node = document.getElementById( element_id );
if ( dom_node ) { dom_node.parentNode.removeChild( dom_node ); }
}
function wpcom_remote_login_remove_dom_node_classes( class_name ) {
var dom_nodes = document.querySelectorAll( '.' + class_name );
for ( var i = 0; i < dom_nodes.length; i++ ) {
dom_nodes[ i ].parentNode.removeChild( dom_nodes[ i ] );
}
}
function wpcom_remote_login_final_cleanup() {
wpcom_remote_login_remove_dom_node_classes( "wpcom_remote_login_msg" );
wpcom_remote_login_remove_dom_node_id( "wpcom_remote_login_key" );
wpcom_remote_login_remove_dom_node_id( "wpcom_remote_login_validate" );
wpcom_remote_login_remove_dom_node_id( "wpcom_remote_login_js" );
wpcom_remote_login_remove_dom_node_id( "wpcom_request_access_iframe" );
wpcom_remote_login_remove_dom_node_id( "wpcom_request_access_styles" );
}

// Watch for messages back from the remote login
window.addEventListener( "message", function( e ) {
if ( e.origin === "https://r-login.wordpress.com" ) {
var data = {};
try {
data = JSON.parse( e.data );
} catch( e ) {
wpcom_remote_login_final_cleanup();
return;
}

if ( data.msg === 'LOGIN' ) {
// Clean up the login check iframe
wpcom_remote_login_remove_dom_node_id( "wpcom_remote_login_key" );

var id_regex = new RegExp( /^[0-9]+$/ );
var token_regex = new RegExp( /^.*|.*|.*$/ );
if (
token_regex.test( data.token )
&& id_regex.test( data.wpcomid )
) {
// We have everything we need to ask for a login
var script = document.createElement( "script" );
script.setAttribute( "id", "wpcom_remote_login_validate" );
script.src = '/remote-login.php?wpcom_remote_login=validate'

+ '&wpcomid=' + data.wpcomid
+ '&token=' + encodeURIComponent( data.token )
+ '&host=' + window.location.protocol
+ '//' + window.location.hostname
+ '&postid=29'
+ '&is_singular=';
  document.body.appendChild( script );
  }

return;
}

// Safari ITP, not logged in, so redirect
if ( data.msg === 'LOGIN-REDIRECT' ) {
window.location = 'https://wordpress.com/log-in?redirect_to=' + window.location.href;
return;
}

// Safari ITP, storage access failed, remove the request
if ( data.msg === 'LOGIN-REMOVE' ) {
var css_zap = 'html { -webkit-transition: margin-top 1s; transition: margin-top 1s; } /* 9001 */ html { margin-top: 0 !important; } * html body { margin-top: 0 !important; } @media screen and ( max-width: 782px ) { html { margin-top: 0 !important; } * html body { margin-top: 0 !important; } }';
var style_zap = document.createElement( 'style' );
style_zap.type = 'text/css';
style_zap.appendChild( document.createTextNode( css_zap ) );
document.body.appendChild( style_zap );

var e = document.getElementById( 'wpcom_request_access_iframe' );
e.parentNode.removeChild( e );

document.cookie = 'wordpress_com_login_access=denied; path=/; max-age=31536000';

return;
}

// Safari ITP
if ( data.msg === 'REQUEST_ACCESS' ) {
console.log( 'request access: safari' );

// Check ITP iframe enable/disable knob
if ( wpcom_remote_login_extra_auth !== 'safari_itp_iframe' ) {
return;
}

// If we are in a "private window" there is no ITP.
var private_window = false;
try {
var opendb = window.openDatabase( null, null, null, null );
} catch( e ) {
private_window = true;
}

if ( private_window ) {
console.log( 'private window' );
return;
}

var iframe = document.createElement( 'iframe' );
iframe.id = 'wpcom_request_access_iframe';
iframe.setAttribute( 'scrolling', 'no' );
iframe.setAttribute( 'sandbox', 'allow-storage-access-by-user-activation allow-scripts allow-same-origin allow-top-navigation-by-user-activation' );
iframe.src = 'https://r-login.wordpress.com/remote-login.php?wpcom_remote_login=request_access&origin=' + encodeURIComponent( data.origin ) + '&wpcomid=' + encodeURIComponent( data.wpcomid );

var css = 'html { -webkit-transition: margin-top 1s; transition: margin-top 1s; } /* 9001 */ html { margin-top: 46px !important; } * html body { margin-top: 46px !important; } @media screen and ( max-width: 660px ) { html { margin-top: 71px !important; } * html body { margin-top: 71px !important; } #wpcom_request_access_iframe { display: block; height: 71px !important; } } #wpcom_request_access_iframe { border: 0px; height: 46px; position: fixed; top: 0; left: 0; width: 100%; min-width: 100%; z-index: 99999; background: #23282d; } ';

var style = document.createElement( 'style' );
style.type = 'text/css';
style.id = 'wpcom_request_access_styles';
style.appendChild( document.createTextNode( css ) );
document.body.appendChild( style );

document.body.appendChild( iframe );
}

if ( data.msg === 'DONE' ) {
wpcom_remote_login_final_cleanup();
}
}
}, false );

// Inject the remote login iframe after the page has had a chance to load
// more critical resources
window.addEventListener( "DOMContentLoaded", function( e ) {
var iframe = document.createElement( "iframe" );
iframe.style.display = "none";
iframe.setAttribute( "scrolling", "no" );
iframe.setAttribute( "id", "wpcom_remote_login_key" );
iframe.src = "https://r-login.wordpress.com/remote-login.php"

+ "?wpcom_remote_login=key"
+ "&origin=aHR0cHM6Ly9yYmtoLm5ldA%3D%3D"
+ "&wpcomid=55637676"
+ "&time=1701025840";
  document.body.appendChild( iframe );
  }, false );

/* <![CDATA[ */
function addLoadEvent(func) {
var oldonload = window.onload;
if (typeof window.onload != 'function') {
window.onload = func;
} else {
window.onload = function () {
oldonload();
func();
}
}
}
/* ]]> */

/* <![CDATA[ */
window._wpemojiSettings = {"baseUrl":"https:\/\/s0.wp.com\/wp-content\/mu-plugins\/wpcom-smileys\/twemoji\/2\/72x72\/","ext":".png","svgUrl":"https:\/\/s0.wp.com\/wp-content\/mu-plugins\/wpcom-smileys\/twemoji\/2\/svg\/","svgExt":".svg","source":{"concatemoji":"https:\/\/s0.wp.com\/wp-includes\/js\/wp-emoji-release.min.js?m=1677072837i&ver=6.4.1-RC1-57094"}};
/*! This file is auto-generated */
!function(i,n){var o,s,e;function c(e){try{var t={supportTests:e,timestamp:(new Date).valueOf()};sessionStorage.setItem(o,JSON.stringify(t))}catch(e){}}function p(e,t,n){e.clearRect(0,0,e.canvas.width,e.canvas.height),e.fillText(t,0,0);var t=new Uint32Array(e.getImageData(0,0,e.canvas.width,e.canvas.height).data),r=(e.clearRect(0,0,e.canvas.width,e.canvas.height),e.fillText(n,0,0),new Uint32Array(e.getImageData(0,0,e.canvas.width,e.canvas.height).data));return t.every(function(e,t){return e===r[t]})}function u(e,t,n){switch(t){case"flag":return n(e,"\ud83c\udff3\ufe0f\u200d\u26a7\ufe0f","\ud83c\udff3\ufe0f\u200b\u26a7\ufe0f")?!1:!n(e,"\ud83c\uddfa\ud83c\uddf3","\ud83c\uddfa\u200b\ud83c\uddf3")&&!n(e,"\ud83c\udff4\udb40\udc67\udb40\udc62\udb40\udc65\udb40\udc6e\udb40\udc67\udb40\udc7f","\ud83c\udff4\u200b\udb40\udc67\u200b\udb40\udc62\u200b\udb40\udc65\u200b\udb40\udc6e\u200b\udb40\udc67\u200b\udb40\udc7f");case"emoji":return!n(e,"\ud83e\udef1\ud83c\udffb\u200d\ud83e\udef2\ud83c\udfff","\ud83e\udef1\ud83c\udffb\u200b\ud83e\udef2\ud83c\udfff")}return!1}function f(e,t,n){var r="undefined"!=typeof WorkerGlobalScope&&self instanceof WorkerGlobalScope?new OffscreenCanvas(300,150):i.createElement("canvas"),a=r.getContext("2d",{willReadFrequently:!0}),o=(a.textBaseline="top",a.font="600 32px Arial",{});return e.forEach(function(e){o[e]=t(a,e,n)}),o}function t(e){var t=i.createElement("script");t.src=e,t.defer=!0,i.head.appendChild(t)}"undefined"!=typeof Promise&&(o="wpEmojiSettingsSupports",s=["flag","emoji"],n.supports={everything:!0,everythingExceptFlag:!0},e=new Promise(function(e){i.addEventListener("DOMContentLoaded",e,{once:!0})}),new Promise(function(t){var n=function(){try{var e=JSON.parse(sessionStorage.getItem(o));if("object"==typeof e&&"number"==typeof e.timestamp&&(new Date).valueOf()<e.timestamp+604800&&"object"==typeof e.supportTests)return e.supportTests}catch(e){}return null}();if(!n){if("undefined"!=typeof Worker&&"undefined"!=typeof OffscreenCanvas&&"undefined"!=typeof URL&&URL.createObjectURL&&"undefined"!=typeof Blob)try{var e="postMessage("+f.toString()+"("+[JSON.stringify(s),u.toString(),p.toString()].join(",")+"));",r=new Blob([e],{type:"text/javascript"}),a=new Worker(URL.createObjectURL(r),{name:"wpTestEmojiSupports"});return void(a.onmessage=function(e){c(n=e.data),a.terminate(),t(n)})}catch(e){}c(n=f(s,u,p))}t(n)}).then(function(e){for(var t in e)n.supports[t]=e[t],n.supports.everything=n.supports.everything&&n.supports[t],"flag"!==t&&(n.supports.everythingExceptFlag=n.supports.everythingExceptFlag&&n.supports[t]);n.supports.everythingExceptFlag=n.supports.everythingExceptFlag&&!n.supports.flag,n.DOMReady=!1,n.readyCallback=function(){n.DOMReady=!0}}).then(function(){return e}).then(function(){var e;n.supports.everything||(n.readyCallback(),(e=n.source||{}).concatemoji?t(e.concatemoji):e.wpemoji&&e.twemoji&&(t(e.twemoji),t(e.wpemoji)))}))}((window,document),window._wpemojiSettings);
/* ]]> */

img.wp-smiley, img.emoji {
display: inline !important;
border: none !important;
box-shadow: none !important;
height: 1em !important;
width: 1em !important;
margin: 0 0.07em !important;
vertical-align: -0.1em !important;
background: none !important;
padding: 0 !important;
}

.has-text-align-justify {
text-align:justify;
}
.wp-block-cover__image-background.has-parallax {
background-size: cover;
}

/*! This file is auto-generated */
.wp-block-button__link{color:#fff;background-color:#32373c;border-radius:9999px;box-shadow:none;text-decoration:none;padding:calc(.667em + 2px) calc(1.333em + 2px);font-size:1.125em}.wp-block-file__button{background:#32373c;color:#fff;text-decoration:none}

body{--wp--preset--color--black: #000000;--wp--preset--color--cyan-bluish-gray: #abb8c3;--wp--preset--color--white: #ffffff;--wp--preset--color--pale-pink: #f78da7;--wp--preset--color--vivid-red: #cf2e2e;--wp--preset--color--luminous-vivid-orange: #ff6900;--wp--preset--color--luminous-vivid-amber: #fcb900;--wp--preset--color--light-green-cyan: #7bdcb5;--wp--preset--color--vivid-green-cyan: #00d084;--wp--preset--color--pale-cyan-blue: #8ed1fc;--wp--preset--color--vivid-cyan-blue: #0693e3;--wp--preset--color--vivid-purple: #9b51e0;--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple: linear-gradient(135deg,rgba(6,147,227,1) 0%,rgb(155,81,224) 100%);--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan: linear-gradient(135deg,rgb(122,220,180) 0%,rgb(0,208,130) 100%);--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange: linear-gradient(135deg,rgba(252,185,0,1) 0%,rgba(255,105,0,1) 100%);--wp--preset--gradient--luminous-vivid-orange-to-vivid-red: linear-gradient(135deg,rgba(255,105,0,1) 0%,rgb(207,46,46) 100%);--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray: linear-gradient(135deg,rgb(238,238,238) 0%,rgb(169,184,195) 100%);--wp--preset--gradient--cool-to-warm-spectrum: linear-gradient(135deg,rgb(74,234,220) 0%,rgb(151,120,209) 20%,rgb(207,42,186) 40%,rgb(238,44,130) 60%,rgb(251,105,98) 80%,rgb(254,248,76) 100%);--wp--preset--gradient--blush-light-purple: linear-gradient(135deg,rgb(255,206,236) 0%,rgb(152,150,240) 100%);--wp--preset--gradient--blush-bordeaux: linear-gradient(135deg,rgb(254,205,165) 0%,rgb(254,45,45) 50%,rgb(107,0,62) 100%);--wp--preset--gradient--luminous-dusk: linear-gradient(135deg,rgb(255,203,112) 0%,rgb(199,81,192) 50%,rgb(65,88,208) 100%);--wp--preset--gradient--pale-ocean: linear-gradient(135deg,rgb(255,245,203) 0%,rgb(182,227,212) 50%,rgb(51,167,181) 100%);--wp--preset--gradient--electric-grass: linear-gradient(135deg,rgb(202,248,128) 0%,rgb(113,206,126) 100%);--wp--preset--gradient--midnight: linear-gradient(135deg,rgb(2,3,129) 0%,rgb(40,116,252) 100%);--wp--preset--font-size--small: 13px;--wp--preset--font-size--medium: 20px;--wp--preset--font-size--large: 36px;--wp--preset--font-size--x-large: 42px;--wp--preset--font-family--albert-sans: 'Albert Sans';--wp--preset--font-family--alegreya: Alegreya;--wp--preset--font-family--arvo: Arvo;--wp--preset--font-family--bodoni-moda: 'Bodoni Moda';--wp--preset--font-family--cabin: Cabin;--wp--preset--font-family--chivo: Chivo;--wp--preset--font-family--commissioner: Commissioner;--wp--preset--font-family--cormorant: Cormorant;--wp--preset--font-family--courier-prime: 'Courier Prime';--wp--preset--font-family--crimson-pro: 'Crimson Pro';--wp--preset--font-family--dm-mono: 'DM Mono';--wp--preset--font-family--dm-sans: 'DM Sans';--wp--preset--font-family--domine: Domine;--wp--preset--font-family--eb-garamond: 'EB Garamond';--wp--preset--font-family--epilogue: Epilogue;--wp--preset--font-family--figtree: Figtree;--wp--preset--font-family--fira-sans: 'Fira Sans';--wp--preset--font-family--fraunces: Fraunces;--wp--preset--font-family--ibm-plex-mono: 'IBM Plex Mono';--wp--preset--font-family--ibm-plex-sans: 'IBM Plex Sans';--wp--preset--font-family--inter: Inter;--wp--preset--font-family--josefin-sans: 'Josefin Sans';--wp--preset--font-family--jost: Jost;--wp--preset--font-family--libre-baskerville: 'Libre Baskerville';--wp--preset--font-family--libre-franklin: 'Libre Franklin';--wp--preset--font-family--literata: Literata;--wp--preset--font-family--lora: Lora;--wp--preset--font-family--merriweather: Merriweather;--wp--preset--font-family--montserrat: Montserrat;--wp--preset--font-family--newsreader: Newsreader;--wp--preset--font-family--nunito: Nunito;--wp--preset--font-family--open-sans: 'Open Sans';--wp--preset--font-family--overpass: Overpass;--wp--preset--font-family--petrona: Petrona;--wp--preset--font-family--piazzolla: Piazzolla;--wp--preset--font-family--playfair-display: 'Playfair Display';--wp--preset--font-family--plus-jakarta-sans: 'Plus Jakarta Sans';--wp--preset--font-family--poppins: Poppins;--wp--preset--font-family--raleway: Raleway;--wp--preset--font-family--roboto-slab: 'Roboto Slab';--wp--preset--font-family--roboto: Roboto;--wp--preset--font-family--rubik: Rubik;--wp--preset--font-family--sora: Sora;--wp--preset--font-family--source-sans-pro: 'Source Sans Pro';--wp--preset--font-family--source-serif-pro: 'Source Serif Pro';--wp--preset--font-family--space-mono: 'Space Mono';--wp--preset--font-family--texturina: Texturina;--wp--preset--font-family--work-sans: 'Work Sans';--wp--preset--spacing--20: 0.44rem;--wp--preset--spacing--30: 0.67rem;--wp--preset--spacing--40: 1rem;--wp--preset--spacing--50: 1.5rem;--wp--preset--spacing--60: 2.25rem;--wp--preset--spacing--70: 3.38rem;--wp--preset--spacing--80: 5.06rem;--wp--preset--shadow--natural: 6px 6px 9px rgba(0, 0, 0, 0.2);--wp--preset--shadow--deep: 12px 12px 50px rgba(0, 0, 0, 0.4);--wp--preset--shadow--sharp: 6px 6px 0px rgba(0, 0, 0, 0.2);--wp--preset--shadow--outlined: 6px 6px 0px -3px rgba(255, 255, 255, 1), 6px 6px rgba(0, 0, 0, 1);--wp--preset--shadow--crisp: 6px 6px 0px rgba(0, 0, 0, 1);}:where(.is-layout-flex){gap: 0.5em;}:where(.is-layout-grid){gap: 0.5em;}body .is-layout-flow > .alignleft{float: left;margin-inline-start: 0;margin-inline-end: 2em;}body .is-layout-flow > .alignright{float: right;margin-inline-start: 2em;margin-inline-end: 0;}body .is-layout-flow > .aligncenter{margin-left: auto !important;margin-right: auto !important;}body .is-layout-constrained > .alignleft{float: left;margin-inline-start: 0;margin-inline-end: 2em;}body .is-layout-constrained > .alignright{float: right;margin-inline-start: 2em;margin-inline-end: 0;}body .is-layout-constrained > .aligncenter{margin-left: auto !important;margin-right: auto !important;}body .is-layout-constrained > :where(:not(.alignleft):not(.alignright):not(.alignfull)){max-width: var(--wp--style--global--content-size);margin-left: auto !important;margin-right: auto !important;}body .is-layout-constrained > .alignwide{max-width: var(--wp--style--global--wide-size);}body .is-layout-flex{display: flex;}body .is-layout-flex{flex-wrap: wrap;align-items: center;}body .is-layout-flex > *{margin: 0;}body .is-layout-grid{display: grid;}body .is-layout-grid > *{margin: 0;}:where(.wp-block-columns.is-layout-flex){gap: 2em;}:where(.wp-block-columns.is-layout-grid){gap: 2em;}:where(.wp-block-post-template.is-layout-flex){gap: 1.25em;}:where(.wp-block-post-template.is-layout-grid){gap: 1.25em;}.has-black-color{color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-color{color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-color{color: var(--wp--preset--color--white) !important;}.has-pale-pink-color{color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-color{color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-color{color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-color{color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-color{color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-color{color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-color{color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-color{color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-color{color: var(--wp--preset--color--vivid-purple) !important;}.has-black-background-color{background-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-background-color{background-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-background-color{background-color: var(--wp--preset--color--white) !important;}.has-pale-pink-background-color{background-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-background-color{background-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-background-color{background-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-background-color{background-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-background-color{background-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-background-color{background-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-background-color{background-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-background-color{background-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-background-color{background-color: var(--wp--preset--color--vivid-purple) !important;}.has-black-border-color{border-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-border-color{border-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-border-color{border-color: var(--wp--preset--color--white) !important;}.has-pale-pink-border-color{border-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-border-color{border-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-border-color{border-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-border-color{border-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-border-color{border-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-border-color{border-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-border-color{border-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-border-color{border-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-border-color{border-color: var(--wp--preset--color--vivid-purple) !important;}.has-vivid-cyan-blue-to-vivid-purple-gradient-background{background: var(--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple) !important;}.has-light-green-cyan-to-vivid-green-cyan-gradient-background{background: var(--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan) !important;}.has-luminous-vivid-amber-to-luminous-vivid-orange-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange) !important;}.has-luminous-vivid-orange-to-vivid-red-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-orange-to-vivid-red) !important;}.has-very-light-gray-to-cyan-bluish-gray-gradient-background{background: var(--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray) !important;}.has-cool-to-warm-spectrum-gradient-background{background: var(--wp--preset--gradient--cool-to-warm-spectrum) !important;}.has-blush-light-purple-gradient-background{background: var(--wp--preset--gradient--blush-light-purple) !important;}.has-blush-bordeaux-gradient-background{background: var(--wp--preset--gradient--blush-bordeaux) !important;}.has-luminous-dusk-gradient-background{background: var(--wp--preset--gradient--luminous-dusk) !important;}.has-pale-ocean-gradient-background{background: var(--wp--preset--gradient--pale-ocean) !important;}.has-electric-grass-gradient-background{background: var(--wp--preset--gradient--electric-grass) !important;}.has-midnight-gradient-background{background: var(--wp--preset--gradient--midnight) !important;}.has-small-font-size{font-size: var(--wp--preset--font-size--small) !important;}.has-medium-font-size{font-size: var(--wp--preset--font-size--medium) !important;}.has-large-font-size{font-size: var(--wp--preset--font-size--large) !important;}.has-x-large-font-size{font-size: var(--wp--preset--font-size--x-large) !important;}
:where(.wp-block-columns.is-layout-flex){gap: 2em;}:where(.wp-block-columns.is-layout-grid){gap: 2em;}
.wp-block-pullquote{font-size: 1.5em;line-height: 1.6;}
.wp-block-navigation a:where(:not(.wp-element-button)){color: inherit;}
:where(.wp-block-post-template.is-layout-flex){gap: 1.25em;}:where(.wp-block-post-template.is-layout-grid){gap: 1.25em;}

:root { --font-headings: unset; --font-base: unset; --font-headings-default: -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Oxygen-Sans,Ubuntu,Cantarell,"Helvetica Neue",sans-serif; --font-base-default: -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Oxygen-Sans,Ubuntu,Cantarell,"Helvetica Neue",sans-serif;}

/* <![CDATA[ */
var videopressAjax = {"ajaxUrl":"https:\/\/rbkhdotnet.wordpress.com\/wp-admin\/admin-ajax.php","bridgeUrl":"\/wp-content\/mu-plugins\/jetpack-plugin\/moon\/jetpack_vendor\/automattic\/jetpack-videopress\/build\/lib\/token-bridge.js","post_id":"29"};
/* ]]> */

/* <![CDATA[ */
var actionbardata = {"siteID":"55637676","postID":"29","siteURL":"https:\/\/rbkh.net","xhrURL":"https:\/\/rbkh.net\/wp-admin\/admin-ajax.php","nonce":"9703fc5eed","isLoggedIn":"","statusMessage":"","subsEmailDefault":"instantly","proxyScriptUrl":"https:\/\/s0.wp.com\/wp-content\/js\/wpcom-proxy-request.js?ver=20211021","shortlink":"https:\/\/wp.me\/P3LrTS-t","i18n":{"followedText":"New posts from this site will now appear in your [Reader<\/a>","foldBar":"Collapse this bar","unfoldBar":"Expand this bar"}};
/* ]]> */

/* <![CDATA[ */
window.addEventListener( 'DOMContentLoaded', function() {
rltInitialize( {"token":null,"iframeOrigins":["https:\/\/widgets.wp.com"]} );
} );
/* ]]> */

.recentcomments a {
display: inline !important;
padding: 0 !important;
margin: 0 !important;
}

table.recentcommentsavatartop img.avatar, table.recentcommentsavatarend img.avatar {
border: 0px;
margin: 0;
}

table.recentcommentsavatartop a, table.recentcommentsavatarend a {
border: 0px !important;
background-color: transparent !important;
}

td.recentcommentsavatarend, td.recentcommentsavatartop {
padding: 0px 0px 1px 0px;
margin: 0px;
}

td.recentcommentstextend {
border: none !important;
padding: 0px 0px 2px 10px;
}

.rtl td.recentcommentstextend {
padding: 0px 10px 2px 0px;
}

td.recentcommentstexttop {
border: none;
padding: 0px 0px 0px 10px;
}

.rtl td.recentcommentstexttop {
padding: 0px 10px 0px 0px;
}

.wordads-ad-wrapper {
display:none;
font: normal 11px Arial, sans-serif;
letter-spacing: 1px;
text-decoration: none;
width: 100%;
margin: 25px auto;
padding: 0;
clear: both;
}
.wordads-ad-title {
margin: 0 auto 5px auto;
}
.wordads-ad-controls {
margin: 5px auto 0 auto;
text-align: right;
}
.wordads-ad-controls span {
cursor: pointer;
}
.wordads-ad {
width: 300px;
max-width: 580px;
margin: 0 auto;
}
.wordads-ad.wordads-ad-responsive {
width: 100%;
}

var wa_smart = { 'network_id': 3905, 'site_id': 474853, 'page_id': 1572546, 'formats': [ { 'id': 110354, 'tagId': 'sas_110354' } ], 'blog_id': 55637676, 'theme': 'pub/plane', 'target': 'wp_blog_id=55637676;language=en', 'inline': { 'title': 'Advertisement', 'gdpr': '<span onclick="__tcfapi( \'showUi\' )">Privacy Settings</span>', 'format_id': 110354, 'max_slots': 20, 'max_blaze_slots': 1, 'enabled': false, 'adflow_enabled': false } };
wa_smart.cmd = [];

var sas = sas || {};
sas.cmd = sas.cmd || [];

window.sas_fallback = window.sas_fallback || [];
window.sas_fallback.push( { tag: "&lt;div class=&quot;OUTBRAIN wa-ob-widget&quot;data-ob-contentUrl=&quot;https://rbkh.net/teaching/&quot;data-widget-id=&quot;AR_2&quot;data-ob-installation-key=&quot;WORDP263NC92GIANECJP6HEPM&quot;data-ob-psub=&quot;&quot;&gt;&lt;/div&gt;&lt;script&gt;window._stq = window._stq || [];window._stq.push( [ \'extra\', { x_wordads_outbrain: \'widget_render_ar_2\', }, ] );&lt;/script&gt;&lt;script src=&quot;https://widgets.outbrain.com/outbrain.js&quot;&gt;&lt;/script&gt;", type: 'belowpost' } );

function __ATA_CC() {var v = document.cookie.match('(^|;) ?personalized-ads-consent=([^;]*)(;|$)');return v ? 1 : 0;}
var __ATA_PP = { 'pt': 2, 'ht': 0, 'tn': 'plane', 'uloggedin': 0, 'amp': false, 'consent': __ATA_CC(), 'gdpr_applies': true, 'ad': { 'label': { 'text': 'Advertisements' }, 'reportAd': { 'text': 'Report this ad' }, 'privacySettings': { 'text': 'Privacy', 'onClick': function() { window.__tcfapi && window.__tcfapi( 'showUi' ) } } }, 'disabled_slot_formats': [], 'siteid': 8982, 'blogid': 55637676, 'js_hint': 'tcf2_test' };
var __ATA = __ATA || {};
__ATA.cmd = __ATA.cmd || [];
__ATA.criteo = __ATA.criteo || {};
__ATA.criteo.cmd = __ATA.criteo.cmd || [];

(function(){var g=Date.now||function(){return+new Date};function h(a,b){a:{for(var c=a.length,d="string"==typeof a?a.split(""):a,e=0;e<c;e++)if(e in d&&b.call(void 0,d[e],e,a)){b=e;break a}b=-1}return 0>b?null:"string"==typeof a?a.charAt(b):a[b]};function k(a,b,c){c=null!=c?"="+encodeURIComponent(String(c)):"";if(b+=c){c=a.indexOf("#");0>c&&(c=a.length);var d=a.indexOf("?");if(0>d||d>c){d=c;var e=""}else e=a.substring(d+1,c);a=[a.substr(0,d),e,a.substr(c)];c=a[1];a[1]=b?c?c+"&"+b:b:c;a=a[0]+(a[1]?"?"+a[1]:"")+a[2]}return a};var l=0;function m(a,b){var c=document.createElement("script");c.src=a;c.onload=function(){b&&b(void 0)};c.onerror=function(){b&&b("error")};a=document.getElementsByTagName("head");var d;a&&0!==a.length?d=a[0]:d=document.documentElement;d.appendChild(c)}function n(a){var b=void 0===b?document.cookie:b;return(b=h(b.split("; "),function(c){return-1!=c.indexOf(a+"=")}))?b.split("=")[1]:""}function p(a){return"string"==typeof a&&0<a.length}
function r(a,b,c){b=void 0===b?"":b;c=void 0===c?".":c;var d=[];Object.keys(a).forEach(function(e){var f=a[e],q=typeof f;"object"==q&&null!=f||"function"==q?d.push(r(f,b+e+c)):null!==f&&void 0!==f&&(e=encodeURIComponent(b+e),d.push(e+"="+encodeURIComponent(f)))});return d.filter(p).join("&")}function t(a,b){a||((window.__ATA||{}).config=b.c,m(b.url))}var u=Math.floor(1E13*Math.random()),v=window.__ATA||{};window.__ATA=v;window.__ATA.cmd=v.cmd||[];v.rid=u;v.createdAt=g();var w=window.__ATA||{},x="s.pubmine.com";
w&&w.serverDomain&&(x=w.serverDomain);var y="//"+x+"/conf",z=window.top===window,A=window.__ATA_PP&&window.__ATA_PP.gdpr_applies,B="boolean"===typeof A?Number(A):null,C=window.__ATA_PP||null,D=z?document.referrer?document.referrer:null:null,E=z?window.location.href:document.referrer?document.referrer:null,F,G=n("__ATA_tuuid");F=G?G:null;var H=window.innerWidth+"x"+window.innerHeight,I=n("usprivacy"),J=r({gdpr:B,pp:C,rid:u,src:D,ref:E,tuuid:F,vp:H,us_privacy:I?I:null},"",".");
(function(a){var b=void 0===b?"cb":b;l++;var c="callback__"+g().toString(36)+"_"+l.toString(36);a=k(a,b,c);window[c]=function(d){t(void 0,d)};m(a,function(d){d&&t(d)})})(y+"?"+J);}).call(this);

var sas_fallback = sas_fallback || [];
sas_fallback.push(
{ tag: "&lt;div id=&quot;atatags-26942-65639830a0a68&quot;&gt;&lt;/div&gt;&lt;script&gt;__ATA.cmd.push(function() {__ATA.initDynamicSlot({id: \'atatags-26942-65639830a0a68\',location: 120,formFactor: \'001\',label: {text: \'Advertisements\',},creative: {reportAd: {text: \'Report this ad\',},privacySettings: {text: \'Privacy\',onClick: function() { window.__tcfapi &amp;&amp; window.__tcfapi( \'showUi\' ); },}}});});&lt;/script&gt;", type: 'belowpost' },
{ tag: "&lt;div id=&quot;atatags-26942-{{unique_id}}&quot;&gt;&lt;/div&gt;&lt;script&gt;__ATA.cmd.push(function() {__ATA.initDynamicSlot({id: \'atatags-26942-{{unique_id}}\',location: 310,formFactor: \'001\',label: {text: \'Advertisements\',},creative: {reportAd: {text: \'Report this ad\',},privacySettings: {text: \'Privacy\',onClick: function() { window.__tcfapi &amp;&amp; window.__tcfapi( \'showUi\' ); },}}});});&lt;/script&gt;", type: 'inline' }
);

window.doNotSellCallback = function() {

var linkElements = [
'a[href="https://wordpress.com/?ref=footer_blog"]',
'a[href="https://wordpress.com/?ref=footer_website"]',
'a[href="https://wordpress.com/?ref=vertical_footer"]',
'a[href^="https://wordpress.com/?ref=footer_segment_"]',
].join(',');

var dnsLink = document.createElement( 'a' );
dnsLink.href = 'https://wordpress.com/advertising-program-optout/';
dnsLink.classList.add( 'do-not-sell-link' );
dnsLink.rel = 'nofollow';
dnsLink.style.marginLeft = '0.5em';
dnsLink.textContent = 'Do Not Sell or Share My Personal Information';

var creditLinks = document.querySelectorAll( linkElements );

if ( 0 === creditLinks.length ) {
return false;
}

Array.prototype.forEach.call( creditLinks, function( el ) {
el.insertAdjacentElement( 'afterend', dnsLink );
});

return true;
};

{"gvlVersion":"28","consentLanguage":"EN","locale":"en","vendorsAll":"EGpq_4__7a_t_y9e_T9ujzGr_vsffdiGIML5Nn3AuRd635OC--wmRom3VtTBUyJAl2bIJCAto5M6iKsUKVECteY9jEgzkCZpRPwMkA5iLWzrAQvN8zFsbyBTPP9P7u7_Oyf_v7t_27ueefos9-73p8zsrhUTqXPto_8_7aJTf3ZD3v3f3_F-ntv9cm37yat__r19_ev139v____v_v_4AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAg","vendorsLegInterest":"EGoAsw0LiAPsiQkItAwigQAiCsICKBAAAACQNEBACQMCnYGAS6wkQAgRQADBACAAFGQAIAABIAEIgAkAKBAABAIBAAAAAAIBAAwMAA4ALQQCAAEB0DFMKABQLCBIjIiFMCEKBIICWygQSAoEFcIAgwwIoBETAQAIAkAFYAAALFYDAEgJWJBAllBtAAAQAIBRShUIpOjAEMCZstVOKJtAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAAAAg","ajaxNonce":"ee8541c723","modulePath":"https:\/\/s0.wp.com\/wp-content\/blog-plugins\/wordads-classes\/js\/cmp\/v2\/","gvlPath":"https:\/\/public-api.wordpress.com\/wpcom\/v2\/sites\/55637676\/cmp\/v3\/vendors\/en\/","_":{"title":"Privacy & Cookies","intro":"We, WordPress.com, and our 766 advertising partners store and\/or access information on your device and also process personal data, like unique identifiers, browsing activity, and other standard information sent by your device including your IP address. This information is collected over time and used for personalised ads, ad measurement, audience insights, and product development specific to our ads program. If this sounds good to you, select \"I Agree!\" below. Otherwise, you can get more information, customize your consent preferences, or decline consent by selecting \"Learn More\". Note that your preferences apply to all websites in the <a href=\"https:\/\/automattic.com\/cookies\/#user-ads-consent\" target=\"_blank\">WordPress.com network<\/a>, and if you change your mind in the future you can update your preferences anytime by visiting the Privacy link displayed under each ad. One last thing, our partners may process some of your data based on legitimate interests instead of consent but you can object to that by choosing \"Learn More\" and then disabling the Legitimate Interests toggle under any listed Purpose or Partner.","config":"Learn More","accept":"I Agree!","viewPartners":"View Partners","error":"We're sorry but an unexpected error occurred. Please try again later."}}    .site-main .post-navigation a:hover {
        background-color: transparent !important;
    }

    @media only screen and (min-width: 767px) {
        .nav-menu ul ul a {
            color: #333;
        }
    }
    
    @media only screen and (max-width: 767px) {
        .nav-menu ul ul li:hover > a,
        .nav-menu ul ul li.current_page_item > a,
        .nav-menu ul ul li.current-menu-item > a,
        .nav-menu ul ul li.current-menu-ancestor > a,
        .nav-menu ul ul li.current_page_ancestor > a,
        .nav-menu ul ul li.current-post-parent > a {
            opacity: 1;
        }
    }

.site-footer, .footer-widget-area .widget-title, .site-footer a:hover { color: #FFFFFF;}
.nav-menu > ul > li > a { color: #FFFFFF;}
.site-title a, .site-title a:hover { color: #3A3A3A;}
.site-main .post-navigation a:hover, .site-main .post-navigation a:focus { background: #f7f7f7;}
blockquote p { color: #828a8c;}
blockquote cite { color: #384750;}
.site-description { color: #323C42;}
.site-top, .site-footer, .search-expand { background-color: #59453e;}
h1, h2, h3, h4, h5, h6, .entry-title a { color: #59453E;}
.entry-meta a:hover, .entry-meta a:focus, .page-links a { color: #59453E;}
.site-main .comment-navigation a, .site-main .paging-navigation a, .site-main .post-navigation a, .site-main .post-navigation .meta-nav { color: #59453E;}
.widget-title a { color: #59453E;}
a, .site-main .post-navigation a, .entry-meta, .comment-meta { color: #3F7871;}
.widget_flickr #flickr_badge_uber_wrapper td a:last-child { color: #3B716B;}
button, input[type="button"], input[type="reset"], input[type="submit"], #infinite-handle span { background-color: #BF3F5B;}
.more-link a:hover, .more-link a:focus, .page-links a:hover, .page-links a:focus { background-color: #BF3F5B;}
.site-main .comment-navigation a:hover,
            .site-main .comment-navigation a:focus,
            .site-main .paging-navigation a:hover,
            .site-main .paging-navigation a:focus,
            .site-main .post-navigation a:hover,
            .site-main .post-navigation a:focus { background-color: #BF3F5B;}
a:hover,
            a:active,
            .menu ul ul li > a:hover,
            .nav-menu ul ul li:hover > a,
            .nav-menu ul ul li.focus a,
            .nav-menu ul ul li.current_page_item > a,
            .nav-menu ul ul li.current-menu-item > a,
            .nav-menu ul ul li.current-menu-ancestor > a,
            .nav-menu ul ul li.current_page_ancestor > a,
            .nav-menu ul ul li.current-post-parent > a,
            .entry-title a:hover,
            .entry-title a:focus { color: #BF3F5B;}
.site-main .post-navigation a:hover, .site-main .post-navigation a:focus { color: #B73D57;}
.widget_flickr #flickr_badge_uber_wrapper td a:last-child:hover { color: #B73D57;}
.site-header  { background-color: #bfac9d;}
.site-footer a { color: #CEC0B4;}
.footer-widget-area .widget_flickr #flickr_badge_uber_wrapper td a:last-child { color: #CEC0B4;}

window.google_analytics_uacct = "UA-52447-2";

var _gaq = _gaq || [];
_gaq.push(['_setAccount', 'UA-52447-2']);
_gaq.push(['_gat._anonymizeIp']);
_gaq.push(['_setDomainName', 'none']);
_gaq.push(['_setAllowLinker', true]);
_gaq.push(['_initData']);
_gaq.push(['_trackPageview']);

(function() {
var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js';
(document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(ga);
})();

](\"https:\/\/wordpress.com\/read\")

Primary Menu

<ul id="menu-top-menubar" class="menu"><li id="menu-item-225" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-home menu-item-225"><a href="https://rbkh.net/">Home</a>
<li id="menu-item-227" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-227"><a href="https://rbkh.net/cv/">CV</a>
<li id="menu-item-228" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-228"><a href="https://rbkh.net/fieldwork/">Fieldwork</a>
<li id="menu-item-359" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-359"><a href="https://rbkh.net/publications/">Publications</a>
<li id="menu-item-230" class="menu-item menu-item-type-post_type menu-item-object-page current-menu-item page_item page-item-29 current_page_item menu-item-230"><a href="https://rbkh.net/teaching/" aria-current="page">Teaching</a>

Search

Search for:

[](https://rbkh.net/)[Rebekah Baglini](https://rbkh.net/)
Linguist at Aarhus University

[

Teaching

Descriptions of courses I have taught are found below. Course syllabi and teaching materials are available by request](null).
**At Aarhus University**
[Natural Language Processing](https://aunlp.github.io/mdwikiNLP/) (CogSci MSc)
[Computational Linguistics](https://kursuskatalog.au.dk/en/course/101936/Computational-Linguistics) (Linguistics MA)
[Language and Computers](https://aunlp.github.io/LaC20/#!index.md) (Linguistics MA)
Cognition and Human Meaning Making (BA Elective)
Text Analysis (Linguistics BA)

**At Stanford University**

Formal Semantics of African Languages
Audience: graduate students
The last decade has seen an explosion of interest in variation as a source of explananda in semantic theory. As a result, African languages&#8211;comprising a third of the world&#8217;s living tongues&#8211;have enjoyed unprecedented attention in the formal semantics literature. In this seminar, we will explore recent research on African language phenomena including quantification, NP semantics and number, reported speech, tense-aspect-modality, and gradable expressions from the perspective of crosslinguistic formal semantics. Our discussions will be guided by several questions: What patterns do African languages show us that more commonly-studied languages do not? Is variation in meaning reflected systematically in morphosyntactic patterns? What can looking at variation tell us about the meaning component of grammar and its interfaces? In addition to engaging with these questions, we will also consider the methodological basis of crosslinguistic semantic research and the role played by fieldwork.

Linguistic Field Methods I
Audience: graduate students
This is the first half of a two-quarter course designed to give you hands-on experience with collecting, processing and analyzing raw linguistic data for the purpose of language description. The main goals are to gain experience with the methodological and analytical issues that arise in linguistic fieldwork, drawing upon all of your linguistic training to date; and to gain understanding about a particular language;
This course will also address ethics and collaborative aspects of linguistic fieldwork, as well as technological aspects of language documentation (data management, tools for transcription and annotation, and issues with the archiving and preservation of data), as they become relevant to the class.
This class will give you basic tools to embark on your own field research project. If field research is not in your immediate future, this class will provide you with insights on how to approach any project where you are not dealing with your own linguistic intuitions.

Linguistic Field Methods II
Audience: graduate students
This is the second half of a two-quarter course designed to give you hands-on experience with collecting, processing and analyzing raw linguistic data for the purpose of language description.
This quarter we will continue to uncover basic structures of Amharic, building upon this present class&#8217; materials and findings. The following will be covered:
Topics from the existing Amharic linguistics literature (we will no longer avoid references on the language and closely related varieties).
Specialized topics in field research. Possibilities: issues in semantic field research, documenting prosody, and experimental methodologies in the field. These topics will be partially dependent on choice of individual projects.
The use and development of fieldwork resource manuals and stimuli. You will develop elicitation materials to further your own research goals and to share publicly with colleagues. As for a research topic, you may continue a particular topic or chose a different one. The goal in this second quarter is to move beyond basic documentation to learn about field methods in the larger landscape of linguistic science.

Design + Argument

**At the University of California, San Diego**

Event Semantics
Audience: graduate students
There is now considerable agreement that ordinary discourse involves implicit reference to events. Yet the precise characterization and formal representation of events remains the focus of many debates among linguists, philosophers, and psycholinguists. What are events and what role to they play in human language? In addition to providing background in the classic literature on events in the Davidsonian tradition, this course will discuss the role of the event argument in the semantic analysis of many different phenomena, including adverbial modification, anaphora, and temporal and aspectual interpretation. We will also consider events alongside other abstract elements in the larger semantic ontology, including states, times, and degrees.

Introduction to African Languages
Audience: undergraduate students
Home to over 1000 languages, the continent of Africa presents a fascinating array of linguistic phenomena, some of which are not found in other areas of the world. This class introduces students to the structural richness of African languages, to the basics of linguistic fieldwork, and to the ways in which language is used in African society. The class is divided into three main sections:
In weeks 1-4, we will focus on learning the structural properties of African languages, with an emphasis on sound systems and word-formation. This will be the most technical part of the course, but it has a secondary purpose: to prepare for the second section, in which we study African languages with the help of native speakers.
In weeks 4-7, we will have four fieldwork sessions with speakers of two different African languages, interspersed with more discussion of word formation and syntax. This will give students an entry into how linguists conduct fieldwork, and to demonstrate (live) the language features that are discussed in the book and in the class.
In weeks 8-10, we will study African language use in society—the expressive uses of language, language games, the social impact of multi-lingualism, and how different styles or ‘registers’ of language signify social class or caste membership. We will also address the issue of official language policy in African countries, and how this impacts education.

Introduction to Morphology
Audience: undergraduate students
This course is about morphology, the study of word structure. The goals of the course are as follows:

* To achieve a basic understanding of the variety of morphological patterns and phenomena in the world’s languages.
* To address questions this variety raises for morphological theory.
* To explore the tools and analytic techniques of morphological research.
* To address the often problematic criteria for defining words, morphemes, inflection, derivation, and other “basic” morphological concepts.

Introduction to Semantics
Audience: undergraduate students
This course is an introduction to semantics, that part of linguistics that studies how human languages convey meaning.
The course addresses issues like the nature of meaning, the basic data that semantics aims to account for (ambiguity, synonymy, contradiction, entailment), some simple formal tools that semantics makes use of (sets and related notions), aspects of the interaction between syntax and semantics (scope and the meaning of various syntactic categories), and issues like implicatures and presuppositions, that are usually taken to be part of pragmatics (the subfield of linguistics that studies how meaning depends on context).
The main goal of the class is to introduce students to some core aspects of linguistic meaning that we know more about and give an idea of how they can be accounted for by using precise rules and simple formal tools.

Introduction to Linguistics
Audience: undergraduate students
Linguistics is the scientific study of language. The course will introduce you, both in theory and in practice, to the core ideas and methods involved in linguistic analysis. Our investigation will be based around the three major subsystems of grammar: sound (phonetics and phonology); structure (morphology and syntax); and meaning (semantics and pragmatics). The goal is to have you learn to think and reason like a linguist, by surveying the methods, findings, and problems in many major areas of modern linguistics:

1. Morphology: the structure and formation of words
2. Syntax: how words are combined to form phrases
3. Semantics and pragmatics: the analysis of linguistic meaning and use
4. Phonetics: the production and representation of speech
5. Phonology: how sounds function and pattern together
6. Sociolinguistics: the study of use of language in social contexts
7. Experimental methods in linguistics: how linguists test theories about language

You will also be equipped with some basic and not-so-basic facts about the world’s languages, a fundamental prerequisite to understanding the nature of human language. We will look at the diversity of languages across space and time, their fundamental similarities, and other puzzles. We will address a range of questions about language through an exploration of the following areas: language families and historical relationships, linguistic typology and language universals, sound and structural features of the world’s languages, among others.
By the end of the course, you should be able to:

* Describe and give examples of the ways in which human languages are alike and how they differ.
* Use and understand basic linguistic terminology.
* Apply the tools of linguistic analysis to the sounds, words, and sentences of a language.
* Identify languages in terms of their linguistic features and genetic affiliation.

Research Practicum

**At the University of Chicago**

Introduction to Linguistics
Audience: undergraduate students
Linguistics is the scientific study of language. The course will introduce you, both in theory and in practice, to the core ideas and methods involved in linguistic analysis. Our investigation will be based around the three major subsystems of grammar: sound (phonetics and phonology); structure (morphology and syntax); and meaning (semantics and pragmatics). The goal is to have you learn to think and reason like a linguist, by surveying the methods, findings, and problems in many major areas of modern linguistics:

1. Morphology: the structure and formation of words
2. Syntax: how words are combined to form phrases
3. Semantics and pragmatics: the analysis of linguistic meaning and use
4. Phonetics: the production and representation of speech
5. Phonology: how sounds function and pattern together
6. Sociolinguistics: the study of use of language in social contexts
7. Experimental methods in linguistics: how linguists test theories about language

You will also be equipped with some basic and not-so-basic facts about the world’s languages, a fundamental prerequisite to understanding the nature of human language. We will look at the diversity of languages across space and time, their fundamental similarities, and other puzzles. We will address a range of questions about language through an exploration of the following areas: language families and historical relationships, linguistic typology and language universals, sound and structural features of the world’s languages, among others.
By the end of the course, you should be able to:

* Describe and give examples of the ways in which human languages are alike and how they differ.
* Use and understand basic linguistic terminology.
* Apply the tools of linguistic analysis to the sounds, words, and sentences of a language.
* Identify languages in terms of their linguistic features and genetic affiliation.

Language and the Human I (Writing instructor)

__ATA.cmd.push(function() {
__ATA.initVideoSlot('atatags-370373-65639830a4078', {
sectionId: '370373',
format: 'inread'
});
});

<div class="OUTBRAIN wa-ob-widget"
data-ob-contentUrl="https://rbkh.net/teaching/"
data-widget-id="AR_2"
data-ob-installation-key="WORDP263NC92GIANECJP6HEPM"
data-ob-psub=""
>

window._stq = window._stq || [];
window._stq.push( [ 'extra', { x_wordads_outbrain: 'widget_render_ar_2', }, ] );

[
|IMG|](null)
[ContactInteracting Minds Centre
Aarhus University 
Building 1443-323 
Jens Chr. Skous Vej 4  
8000 Aarhus C Denmark ](null)rbkh@cc.au.dk[TwitterMy Tweets](null)

__ATA.cmd.push(function() {
__ATA.initDynamicSlot({
id: 'atatags-286348-65639830ad8e6',
location: 140,
formFactor: '003',
label: {
text: 'Advertisements',
},
creative: {
reportAd: {
text: 'Report this ad',
},
privacySettings: {
text: 'Privacy',
onClick: function() { window.__tcfapi && window.__tcfapi( 'showUi' ); },
}
}
});
});

[
Create a website or blog at WordPress.com

](https://wordpress.com/?ref=footer_custom_svg)

/* <![CDATA[ */
var WPGroHo = {"my_hash":""};
/* ]]> */

// Initialize and attach hovercards to all gravatars
( function() {
function init() {
if ( typeof Gravatar === 'undefined' ) {
return;
}

if ( typeof Gravatar.init !== 'function' ) {
return;
}

Gravatar.profile_cb = function ( hash, id ) {
WPGroHo.syncProfileData( hash, id );
};

Gravatar.my_hash = WPGroHo.my_hash;
Gravatar.init(
'body',
'#wp-admin-bar-my-account',
{
i18n: {
'Edit your profile': 'Edit your profile',
'View profile': 'View profile',
'Sorry, we are unable to load this Gravatar profile.': 'Sorry, we are unable to load this Gravatar profile.',
'Sorry, we are unable to load this Gravatar profile. Please check your internet connection.': 'Sorry, we are unable to load this Gravatar profile. Please check your internet connection.',
},
}
);
}

if ( document.readyState !== 'loading' ) {
init();
} else {
document.addEventListener( 'DOMContentLoaded', init );
}
} )();

( function() {
function init() {
document.body.addEventListener( 'is.post-load', function() {
if ( typeof __ATA.insertInlineAds === 'function' ) {
__ATA.insertInlineAds();
}
} );
}

if ( document.readyState !== 'loading' ) {
init();
} else {
document.addEventListener( 'DOMContentLoaded', init );
}
} )();

( function () {

var setupPrivacy = function() {

// Minimal Mozilla Cookie library
// https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie/Simple_document.cookie_framework
var cookieLib = window.cookieLib = {getItem:function(e){return e&&decodeURIComponent(document.cookie.replace(new RegExp("(?:(?:^|.*;)\\s*"+encodeURIComponent(e).replace(/[\-\.\+\*]/g,"\\$&")+"\\s*\\=\\s*([^;]*).*$)|^.*$"),"$1"))||null},setItem:function(e,o,n,t,r,i){if(!e||/^(?:expires|max\-age|path|domain|secure)$/i.test(e))return!1;var c="";if(n)switch(n.constructor){case Number:c=n===1/0?"; expires=Fri, 31 Dec 9999 23:59:59 GMT":"; max-age="+n;break;case String:c="; expires="+n;break;case Date:c="; expires="+n.toUTCString()}return"rootDomain"!==r&&".rootDomain"!==r||(r=(".rootDomain"===r?".":"")+document.location.hostname.split(".").slice(-2).join(".")),document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(o)+c+(r?"; domain="+r:"")+(t?"; path="+t:"")+(i?"; secure":""),!0}};

// Implement IAB USP API.
window.__uspapi = function( command, version, callback ) {

// Validate callback.
if ( typeof callback !== 'function' ) {
return;
}

// Validate the given command.
if ( command !== 'getUSPData' || version !== 1 ) {
callback( null, false );
return;
}

// Check for GPC. If set, override any stored cookie.
if ( navigator.globalPrivacyControl ) {
callback( { version: 1, uspString: '1YYN' }, true );
return;
}

// Check for cookie.
var consent = cookieLib.getItem( 'usprivacy' );

// Invalid cookie.
if ( null === consent ) {
callback( null, false );
return;
}

// Everything checks out. Fire the provided callback with the consent data.
callback( { version: 1, uspString: consent }, true );
};

// Initialization.
document.addEventListener( 'DOMContentLoaded', function() {

// Internal functions.
var setDefaultOptInCookie = function() {
var value = '1YNN';
var domain = '.wordpress.com' === location.hostname.slice( -14 ) ? '.rootDomain' : location.hostname;
cookieLib.setItem( 'usprivacy', value, 365 * 24 * 60 * 60, '/', domain );
};

var setDefaultOptOutCookie = function() {
var value = '1YYN';
var domain = '.wordpress.com' === location.hostname.slice( -14 ) ? '.rootDomain' : location.hostname;
cookieLib.setItem( 'usprivacy', value, 24 * 60 * 60, '/', domain );
};

var setDefaultNotApplicableCookie = function() {
var value = '1---';
var domain = '.wordpress.com' === location.hostname.slice( -14 ) ? '.rootDomain' : location.hostname;
cookieLib.setItem( 'usprivacy', value, 24 * 60 * 60, '/', domain );
};

var setCcpaAppliesCookie = function( applies ) {
var domain = '.wordpress.com' === location.hostname.slice( -14 ) ? '.rootDomain' : location.hostname;
cookieLib.setItem( 'ccpa_applies', applies, 24 * 60 * 60, '/', domain );
}

var maybeCallDoNotSellCallback = function() {
if ( 'function' === typeof window.doNotSellCallback ) {
return window.doNotSellCallback();
}

return false;
}

// Look for usprivacy cookie first.
var usprivacyCookie = cookieLib.getItem( 'usprivacy' );

// Found a usprivacy cookie.
if ( null !== usprivacyCookie ) {

// If the cookie indicates that CCPA does not apply, then bail.
if ( '1---' === usprivacyCookie ) {
return;
}

// CCPA applies, so call our callback to add Do Not Sell link to the page.
maybeCallDoNotSellCallback();

// We're all done, no more processing needed.
return;
}

// We don't have a usprivacy cookie, so check to see if we have a CCPA applies cookie.
var ccpaCookie = cookieLib.getItem( 'ccpa_applies' );

// No CCPA applies cookie found, so we'll need to geolocate if this visitor is from California.
// This needs to happen client side because we do not have region geo data in our $SERVER headers,
// only country data -- therefore we can't vary cache on the region.
if ( null === ccpaCookie ) {

var request = new XMLHttpRequest();
request.open( 'GET', 'https://public-api.wordpress.com/geo/', true );

request.onreadystatechange = function () {
if ( 4 === this.readyState ) {
if ( 200 === this.status ) {

// Got a geo response. Parse out the region data.
var data = JSON.parse( this.response );
var region      = data.region ? data.region.toLowerCase() : '';
var ccpa_applies = ['california', 'colorado', 'connecticut', 'utah', 'virginia'].indexOf( region ) > -1;
// Set CCPA applies cookie. This keeps us from having to make a geo request too frequently.
setCcpaAppliesCookie( ccpa_applies );

// Check if CCPA applies to set the proper usprivacy cookie.
if ( ccpa_applies ) {
if ( maybeCallDoNotSellCallback() ) {
// Do Not Sell link added, so set default opt-in.
setDefaultOptInCookie();
} else {
// Failed showing Do Not Sell link as required, so default to opt-OUT just to be safe.
setDefaultOptOutCookie();
}
} else {
// CCPA does not apply.
setDefaultNotApplicableCookie();
}
} else {
// Could not geo, so let's assume for now that CCPA applies to be safe.
setCcpaAppliesCookie( true );
if ( maybeCallDoNotSellCallback() ) {
// Do Not Sell link added, so set default opt-in.
setDefaultOptInCookie();
} else {
// Failed showing Do Not Sell link as required, so default to opt-OUT just to be safe.
setDefaultOptOutCookie();
}
}
}
};

// Send the geo request.
request.send();
} else {
// We found a CCPA applies cookie.
if ( ccpaCookie === 'true' ) {
if ( maybeCallDoNotSellCallback() ) {
// Do Not Sell link added, so set default opt-in.
setDefaultOptInCookie();
} else {
// Failed showing Do Not Sell link as required, so default to opt-OUT just to be safe.
setDefaultOptOutCookie();
}
} else {
// CCPA does not apply.
setDefaultNotApplicableCookie();
}
}
} );
};

// Kickoff initialization.
if ( window.defQueue && defQueue.isLOHP && defQueue.isLOHP === 2020 ) {
defQueue.items.push( setupPrivacy );
} else {
setupPrivacy();
}

} )();

<div id="actionbar" style="display: none;"
class="actnbr-pub-plane actnbr-has-follow">

<li class="actnbr-btn actnbr-hidden no-display" onclick="javascript:__tcfapi( 'showUi' );">
<a class="actnbr-action actnbr-actn-privacy" href="#">
<svg class="gridicon gridicons-info-outline" height="20" width="20" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g><path d="M13 9h-2V7h2v2zm0 2h-2v6h2v-6zm-1-7c-4.41 0-8 3.59-8 8s3.59 8 8 8 8-3.59 8-8-3.59-8-8-8m0-2c5.523 0 10 4.477 10 10s-4.477 10-10 10S2 17.523 2 12 6.477 2 12 2z"/></g></svg><span>Privacy</span>
</a>

<li class="actnbr-ellipsis actnbr-hidden">
<svg class="gridicon gridicons-ellipsis" height="24" width="24" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g><path d="M7 12c0 1.104-.896 2-2 2s-2-.896-2-2 .896-2 2-2 2 .896 2 2zm12-2c-1.104 0-2 .896-2 2s.896 2 2 2 2-.896 2-2-.896-2-2-2zm-7 0c-1.104 0-2 .896-2 2s.896 2 2 2 2-.896 2-2-.896-2-2-2z"/></g></svg><div class="actnbr-popover tip tip-top-left actnbr-more">
<div class="tip-arrow"></div>
<div class="tip-inner">
<ul>
<li class="actnbr-sitename">
<a href="https://rbkh.net">
|IMG|Rebekah Baglini</a>

<li class="actnbr-folded-customize">
<a href="https://rbkhdotnet.wordpress.com/wp-admin/customize.php?url=https%3A%2F%2Frbkhdotnet.wordpress.com%2Fteaching%2F">
<svg class="gridicon gridicons-customize" height="20" width="20" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g><path d="M2 6c0-1.505.78-3.08 2-4 0 .845.69 2 2 2 1.657 0 3 1.343 3 3 0 .386-.08.752-.212 1.09.74.594 1.476 1.19 2.19 1.81L8.9 11.98c-.62-.716-1.214-1.454-1.807-2.192C6.753 9.92 6.387 10 6 10c-2.21 0-4-1.79-4-4zm12.152 6.848l1.34-1.34c.607.304 1.283.492 2.008.492 2.485 0 4.5-2.015 4.5-4.5 0-.725-.188-1.4-.493-2.007L18 9l-2-2 3.507-3.507C18.9 3.188 18.225 3 17.5 3 15.015 3 13 5.015 13 7.5c0 .725.188 1.4.493 2.007L3 20l2 2 6.848-6.848c1.885 1.928 3.874 3.753 5.977 5.45l1.425 1.148 1.5-1.5-1.15-1.425c-1.695-2.103-3.52-4.092-5.448-5.977z"/></g></svg><span>Customize</span>
</a>

<li class="actnbr-signup"><a href="https://wordpress.com/start/">Sign up</a>
<li class="actnbr-login"><a href="https://wordpress.com/log-in?redirect_to=https%3A%2F%2Fr-login.wordpress.com%2Fremote-login.php%3Faction%3Dlink%26back%3Dhttps%253A%252F%252Frbkh.net%252Fteaching%252F">Log in</a>
<li class="actnbr-shortlink"><a href="https://wp.me/P3LrTS-t">Copy shortlink</a>
<li class="flb-report">
<a href="http://en.wordpress.com/abuse/?report_url=https://rbkh.net/teaching/" target="_blank">
Report this content</a>

<li class="actnbr-subs">
<a href="https://subscribe.wordpress.com/">Manage subscriptions</a>

window.addEventListener( "load", function( event ) {
var link = document.createElement( "link" );
link.href = "https://s0.wp.com/wp-content/mu-plugins/actionbar/actionbar.css?v=20231122";
link.type = "text/css";
link.rel = "stylesheet";
document.head.appendChild( link );

var script = document.createElement( "script" );
script.src = "https://s0.wp.com/wp-content/mu-plugins/actionbar/actionbar.js?v=20231122";
script.defer = true;
document.body.appendChild( script );
} );

// <![CDATA[
(function() {
try{
  if ( window.external &&'msIsSiteMode' in window.external) {
    if (window.external.msIsSiteMode()) {
      var jl = document.createElement('script');
      jl.type='text/javascript';
      jl.async=true;
      jl.src='/wp-content/plugins/ie-sitemode/custom-jumplist.php';
      var s = document.getElementsByTagName('script')[0];
      s.parentNode.insertBefore(jl, s);
    }
  }
}catch(e){}
})();
// ]]>

_tkq = window._tkq || [];
_stq = window._stq || [];
_tkq.push(['storeContext', {'blog_id':'55637676','blog_tz':'1','user_lang':'en','blog_lang':'en','user_id':'0'}]);
_stq.push(['view', {'blog':'55637676','v':'wpcom','tz':'1','user_id':'0','post':'29','subd':'rbkhdotnet'}]);
_stq.push(['extra', {'crypt':'UE5XaGUuOTlwaD85flAmcm1mcmZsaDhkV11YdWtpP0NsWnVkPS9sL0ViLndld3BTeHZ0JnhyR1Q9SkFlek04N3lbdjJRSDF4cTJweXhuT0lNeFJic1NRSjU9VFFSamE9UixUMFRfN3BHcUJPT1hwczUsN1tSLjZra04wWFI5V0FYSUg0Qi5dfnMvckJRT1VXJmhqJjJQazJ1azArRTVWRUVFLTFbWXBsejdYZmNtTVVIfjlJRz1URE5oZV8lXV1uQnxwT0VCRWJZXXBUdF1Wc0xlaVFtWC9RJU4zYUJJTFM2anM4aSZvXy1fZm9oW2MyOEE3Zn5BYW1OYzRJZzE9NzdXNGN3Tz0lJWQsTEZqJX5ZekotXUVXYyU/b1M0WCVS'}]);
_stq.push([ 'clickTrackerInit', '55637676', '29' ]);

![](https://rbkhdotnet.files.wordpress.com/2022/06/linkedin.jpg?w=1024)

if ( 'object' === typeof wpcom_mobile_user_agent_info ) {

wpcom_mobile_user_agent_info.init();
var mobileStatsQueryString = "";

if( false !== wpcom_mobile_user_agent_info.matchedPlatformName )
mobileStatsQueryString += "&x_" + 'mobile_platforms' + '=' + wpcom_mobile_user_agent_info.matchedPlatformName;

if( false !== wpcom_mobile_user_agent_info.matchedUserAgentName )
mobileStatsQueryString += "&x_" + 'mobile_devices' + '=' + wpcom_mobile_user_agent_info.matchedUserAgentName;

if( wpcom_mobile_user_agent_info.isIPad() )
mobileStatsQueryString += "&x_" + 'ipad_views' + '=' + 'views';

if( "" != mobileStatsQueryString ) {
new Image().src = document.location.protocol + '//pixel.wp.com/g.gif?v=wpcom-no-pv' + mobileStatsQueryString + '&baba=' + Math.random();
}

}
