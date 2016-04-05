# wp-node-open-backup-link
-pull links from google spreadsheet and open to initiate backup incrementally. 

-node portion of a cron job to run through links in a spreadsheet

-links are copied from backWPup wordpress plugin

#how it works
pull from google spreadsheet -
for each link - fire phantomjs scraper to post - 
just opening this link via phantomjs is enough initiate the backup

#todo
better logic for each incremental link open -
create .sh containing 'node open-links.js' - 
create cron to open .sh on certain days

#todo optional
- add field in excel sheet to type the word "run" when first inserting backup link
- another script to run every day midnight to check row[cell] for the word run and pull link - 
- and update accordingly - and change text to 'ran' along with date/time
