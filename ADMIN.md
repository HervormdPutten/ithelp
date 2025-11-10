# Admin

A page with some useful admin scripts

## Local

Run devcontainer with powershell or a container



```
podman run -rm -it mcr.microsoft.com/dotnet/sdk:9.0 pwsh

Install-Module -Name ExchangeOnlineManagement
```

## Sharepoint sites

https://answers.microsoft.com/en-us/msoffice/forum/all/turning-off-email-notification-when-adding-team/ea22f6c7-20f0-4b35-97eb-bf923b353e4f

```pwsh

Connect-ExchangeOnline -UserPrincipalName <username@domain.com>
# Or if no browser is available in the terminal environment
Connect-ExchangeOnline -Device 

# List all groups
Get-UnifiedGroup | ft Name,DisplayName,PrimarySmtpAddress,WelcomeMessageEnabled,HiddenFromAddressListsEnabled

# Change individual group
Get-UnifiedGroup <groupname/id> | Set-UnifiedGroup -UnifiedGroupWelcomeMessageEnabled:$false

# Change all groups (which are not changed yet)
# Hide from addresslist, we don't do that automatically anymore
# Get-UnifiedGroup |   Where-Object { $_.HiddenFromAddressListsEnabled -Eq $False }   |  Set-UnifiedGroup  -HiddenFromAddressListsEnabled $True

# Disable default welcome mail
Get-UnifiedGroup |   Where-Object { $_.WelcomeMessageEnabled -Eq $True } |  Set-UnifiedGroup -UnifiedGroupWelcomeMessageEnabled:$False
# Enable send mail to users of the group
Get-UnifiedGroup |   Where-Object { $_.AutoSubscribeNewMembers -Eq $False }  | Set-UnifiedGroup  -AutoSubscribeNewMembers:$True
```

## Change language and local setting of a (shared) mailbox

https://w365.dk/index.php/2021/07/28/change-language-of-a-shared-mailbox-in-exchange-online/

```pwsh
Get-MailboxRegionalConfiguration -Identity mailbox@domain.com  
Set-MailboxRegionalConfiguration  -LocalizeDefaultFolderName:$true -Language nl-NL -Identity mailbox@domain.com                     
```


## Disable option to create new Groups for all users

https://learn.microsoft.com/nl-nl/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide&redirectSourcePath=%252fen-us%252farticle%252fControl-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618

This is available in beta powershell, but also in beta GraphAPI.
https://learn.microsoft.com/en-us/graph/api/group-post-settings?view=graph-rest-beta&tabs=http

```http request
GET https://graph.microsoft.com/beta/directorySettingTemplates


# Create new settings:
POST https://graph.microsoft.com/beta/settings
{
    "templateId": "62375ab9-6b52-47ed-826b-58e47e0e304b",
    "values": [
        {
            "name": "EnableMSStandardBlockedWords",
            "value": "true"
        },
        {
            "name": "GroupCreationAllowedGroupId",
            "value": "484ac1c2-dfce-4e29-9550-4e7a2b457e0a"
        },
        {
            "name": "EnableGroupCreation",
            "value": "false"
        }
    ]
}

# GET current settings
GET https://graph.microsoft.com/beta/settings
```

For updating settings:
https://learn.microsoft.com/en-us/graph/api/directorysetting-update?view=graph-rest-beta&tabs=http