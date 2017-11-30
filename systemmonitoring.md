<h1>System Monitoring commands</h1>

<pre>ps -caxm -orss,comm | sed -n '1!p' | awk '{ print$1*1024}' | paste -s -d+ - | bc | awk '{print $1/1024/1024 " MB"}'</pre>

Prints Current Real Memmory used.
