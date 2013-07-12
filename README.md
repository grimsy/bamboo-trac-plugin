# Bamboo Trac Integration Plugin #
## Description ##

Integrate ​Bamboo build results into the Trac timeline and (optionally) provide a navbar menu to link to the Bamboo instance.

This plugin works very similar to the HudsonTracPlugin (and was almost completely based on it), LuntbuildTracIntegration plugin and the Trac Continuum plugin. The build results are obtained from one of the RSS feeds Bamboo provides.

## Dependencies ##

This plugin requires that the ​python-feedparser library is installed on your system.

## Installation ##

easy_install http://trac-hacks.org/svn/bambootracplugin/0.11/
Enable the plugin in trac.ini.
```
[components]
bambootrac.bambootracplugin.* = enabled
```

## Configuration ##

At a minimum, you need the feed_url parameter
```
[bamboo]
feed_url= http://localhost/bamboo/rss/createAllBuildsRssFeed.action?feedType=rssAll&os_username=user&os_password=pass
```
If you're using basic authentication on your bamboo installation, you should be able to use the following configuration

```
[bamboo]
feed_url= http://localhost/bamboo/rss/createAllBuildsRssFeed.action?feedType=rssAll&os_authType=basic
username = yourusername
password = yourpassword
```
Please note that I haven't tested the Basic authentication, and just used the same code that the HudsonTracPlugin was using