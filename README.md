# Recast Web Chat addon for Hybris Commerce

# Version
0.1

# Deployment
1. cd to bin/custom of your Hybris Commerce directory
2. clone
```bash
git clone https://github.wdf.sap.corp/hybris-se-na/recastwebchataddon.git
```
3. Update config/localextensions.xml to include this addon
```xml
    <extension name='recastwebchataddon' />
```
4. Execute addoninstall ant command
```bash
ant addoninstall -Daddonnames="recastwebchataddon" -DaddonStorefront.yacceleratorstorefront="yacceleratorstorefront"
```
5. build by ant
```bash
ant
```
6. Update on hAC with following options (This will take time)
```
UNCHECK: Update running system 
UNCHECK: Clear the hMC configuration from the database
UNCHECK: Create essential data
UNCHECK: Localize types
CHECK:   recastwebchataddon
CHECK:   electronicsstore
         NO:  Import Core Data
         YES: Import Sample Data
         NO:  Activate Solr Cron Jobs
CHECK:   apparelstore
         NO:  Import Core Data
         YES: Import Sample Data
         NO:  Activate Solr Cron Jobs
```
7. Modify project.properties in recastwebchataddon extension or config/local.properties, then add following parameters.
You can find each value in Web Chat configuration of Connect tab.
```properties
recastwebchataddon.channelid=YOUR_RECAST_CONFIG_CHANNEL_ID
recastwebchataddon.token=YOUR_RECAST_CONFIG_TOKEN
```
