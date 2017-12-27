<h1>System Monitoring Commands</h1>

Prints Current Real Memmory used
<pre>ps -caxm -orss,comm | sed -n '1!p' | awk '{ print$1*1024}' | paste -s -d+ - | bc | awk '{print $1/1024/1024 " MB"}'</pre>

Lists the size contents(including folders) in a user-friendly format
<pre>du -sh * | sort -h</pre>

Finds all duplicate files with MD5 matching
<pre>find -type f -exec md5sum '{}' ';' | sort | uniq --all-repeated=separate -w 33 | cut -c 35-</pre>
