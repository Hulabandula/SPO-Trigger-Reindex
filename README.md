# SPO Trigger Re-index scripts by [@mikaelsvenson]
## Scripts
- reindex-users.ps1 - Script to mark SharePoint user profiles to be picked up at the next crawl.
- reindex-users-v2.ps1 - More efficient script to mark SharePoint online content to be picked up at the next crawl.

## Re-indexing of user profiles
See [How to trigger re-indexing of user profiles in SharePoint On-line] for an explanation of user profile indexing

This script will iterate all user profiles in SPO to force a trigger of re-indexing of the profiles on the next crawl.

Monitoring has shown that indexing of user profiles happens
at approximately a **4 hour interval** (per December 10th 2014). I have seen as low as **2h** (night time) and as high as **8h** (daytime).

Example 1

    .\reindex-users.ps1 -url https://contoso-admin.sharepoint.com # admin site required

You can also add the switch *-changeProperty* to choose if you want to use *SPS-Birthday* or *Department* (now default) as your change property.

Example 2

    .\reindex-users-v2.ps1 -url https://contoso.sharepoint.com # any non-admin site

[How to trigger re-indexing of user profiles in SharePoint On-line]:http://techmikael.blogspot.com/2014/12/how-to-trigger-re-indexing-of-user.html
