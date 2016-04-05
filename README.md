# open-backup-link
pull links from google spreadsheet and open to initiate backup incrementally. 

node portion of a cron job to run through links in a spreadsheet

links are copied from backWPup wordpress plugin

#how it works
pull from google spreadsheet
for each link - fire phantomjs scraper to post
just opening this link via phantomjs is enough initiate the backup

#todo
better logic for each incremental link open
