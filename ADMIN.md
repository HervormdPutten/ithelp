# Admin

A page with some useful admin scripts

## Sharepoint sites

https://answers.microsoft.com/en-us/msoffice/forum/all/turning-off-email-notification-when-adding-team/ea22f6c7-20f0-4b35-97eb-bf923b353e4f

```pwsh

Connect-ExchangeOnline -UserPrincipalName <username@domain.com>

# List all groups
Get-UnifiedGroup | ft Name,DisplayName,PrimarySmtpAddress,WelcomeMessageEnabled,HiddenFromAddressListsEnabled

# Change individual group
Get-UnifiedGroup <groupname/id> | Set-UnifiedGroup -UnifiedGroupWelcomeMessageEnabled:$false

# Change all groups (which are not changed yet
# Hide from addresslist
Get-UnifiedGroup |   Where-Object { $_.HiddenFromAddressListsEnabled -Eq $False }   |  Set-UnifiedGroup  -HiddenFromAddressListsEnabled $True
# Disable default welcome mail
Get-UnifiedGroup |   Where-Object { $_.WelcomeMessageEnabled -Eq $True } |  Set-UnifiedGroup -UnifiedGroupWelcomeMessageEnabled:$False

```

## Change language and local setting of a (shared) mailbox

https://w365.dk/index.php/2021/07/28/change-language-of-a-shared-mailbox-in-exchange-online/

```pwsh
Get-MailboxRegionalConfiguration -Identity mailbox@domain.com  
Set-MailboxRegionalConfiguration  -LocalizeDefaultFolderName:$true -Language nl-NL -Identity mailbox@domain.com                     
```