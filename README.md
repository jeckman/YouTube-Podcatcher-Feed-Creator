YouTube-Podcatcher-Feed-Creator
===============================

Creates a Podcatcher-compatible feed (with enclosures) to treat a YouTube user's channel as a video podcast

Configure feed_parser.php with the details of a specific YouTube
feed - for example, all videos by a given username - and it will return an xml
doc usable in a podcatcher, with the links to the videos turned into proper xml
enclosure links. (I use this with Downcast app on an iPad - your mileage may 
vary if you use other podcatchers - in particular iTunes is quite picky about 
what it considers valid feeds). 

Once feed_parser.php is working well when called directly from a web browser,
configure a cron job to output the rss to a file:

For example, my crontab has this line:

* 3 * * * /usr/bin/php /var/www/example.com/feed_parser.php > /var/www/example.com/feed.xml

(Your mileage will vary, as you'll need to set the right path to your php
file and the right path to the directory where it can write). 

Then configure podcatcher clients to point at the feed.xml

Set the cronjob to the desired frequency - every time it runs, it will
overwrite the feed.xml with new content. 
  
Enjoy!

John
