---
external help file: sharepointonline.xml
applicable: SharePoint Online
title: Set-SPOSite
schema: 2.0.0
author: vesajuvonen
ms.author: vesaj
ms.reviewer:
---

# Set-SPOSite

## SYNOPSIS
Sets or updates one or more properties' values for a site collection.


## SYNTAX

### ParamSet1
```powershell
Set-SPOSite [-Identity] <SpoSitePipeBind> [-AllowSelfServiceUpgrade <Boolean>] [-Confirm]
 [-DenyAddAndCustomizePages <Boolean>] [-LocaleId <UInt32>] [-LockState <String>] [-NoWait] [-Owner <String>]
 [-ResourceQuota <Double>] [-ResourceQuotaWarningLevel <Double>]
 [-SandboxedCodeActivationCapability <SandboxedCodeActivationCapabilities>]
 [-SharingCapability <SharingCapabilities>] [-StorageQuota <Int64>] [-StorageQuotaWarningLevel <Int64>]
 [-Title <String>] [-WhatIf] [-BlockDownloadOfNonViewableFiles <Boolean>]
 [-CommentsOnSitePagesDisabled <Boolean>] [-SocialBarOnSitePagesDisabled <Boolean>]
 [-DisableAppViews <AppViewsPolicy>]
 [-DisableCompanyWideSharingLinks <CompanyWideSharingLinksPolicy>] [-DisableFlows <FlowsPolicy>]
 [-DisabledWebpartIds <Guid>]
 [-RestrictedToGeo <RestrictedToRegion>] [-SharingAllowedDomainList <String>]
 [-SharingBlockedDomainList <String>] [-SharingDomainRestrictionMode <SharingDomainRestrictionModes>]
 [-ShowPeoplePickerSuggestionsForGuestUsers <Boolean>] [-StorageQuotaReset] 
 [-DefaultSharingLinkType] [-DefaultLinkPermission] [<CommonParameters>]
 [-ConditionalAccessPolicy <SPOConditionalAccessPolicyType>]
```
### ParamSet2
```powershell
Set-SPOSite [-Identity] <SpoSitePipeBind> -EnablePWA <Boolean> [-Confirm] [-WhatIf] [<CommonParameters>]
```



### ParamSet3
```powershell
Set-SPOSite [-Identity] <SpoSitePipeBind> [-Confirm] [-DisableSharingForNonOwners] [-WhatIf]
 [<CommonParameters>]
```

### ParamSet4 (valid for Group Site Collection)
```powershell
Set-SPOSite [-Identity] <SpoSitePipeBind> [-AllowSelfServiceUpgrade <Boolean>] [-Confirm]
 [-DenyAddAndCustomizePages <Boolean>] [-LocaleId <UInt32>] [-LockState <String>] [-NoWait] [-Owner <String>]
 [-ResourceQuota <Double>] [-ResourceQuotaWarningLevel <Double>]
 [-SandboxedCodeActivationCapability <SandboxedCodeActivationCapabilities>]
 [-SharingCapability <SharingCapabilities>] [-StorageQuota <Int64>] [-StorageQuotaWarningLevel <Int64>]
 [<CommonParameters>]
```


## DESCRIPTION
For any parameters that are passed in, the `Set-SPOSite` cmdlet sets or updates the setting for the site collection identified by parameter Identity.

You must be a SharePoint Online global administrator and a site collection administrator to run the cmdlet.

For permissions and the most current information about Windows PowerShell for SharePoint Online, see the online documentation at http://go.microsoft.com/fwlink/p/?LinkId=251832.


## EXAMPLES

### -----------------------EXAMPLE 1-----------------------------
```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com/sites/site1 -Owner joe.healy@contoso.com -NoWait
```

Example 1 updates the owner of site collection https://contoso.sharepoint.com/sites/site1 to the person whose email address is joe.healy@contoso.com. This cmdlet is executed immediately without delay.


### -----------------------EXAMPLE 2-----------------------------
```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com/sites/site1 -ResourceQuota 0 -StorageQuota 1024
```

Example 2 updates the settings of site collection https://contoso.sharepoint.com/sites/site1. The storage quota is updated to 1024 megabytes (1 GB) and the resource quota is updated to 0 megabytes. 


### -----------------------EXAMPLE 3-----------------------------
```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com -StorageQuota 1500 -StorageQuotaWarningLevel 1400000
```

This example updates the settings of site collection https://contoso.sharepoint.com. The storage quota is updated to 1500 megabytes and the storage quota warning level is updated to 1400000 megabytes. 


### -----------------------EXAMPLE 4-----------------------------
```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com -DisableSharingForNonOwners
```

Example 4 prevents non-owners of a site from inviting new users to the site.


### -----------------------EXAMPLE 5-----------------------------
```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com/sites/groupname -StorageQuota 3000 -StorageQuotaWarningLevel 2000
```

This example sets the quota for the site.



> [!NOTE] 
> If Site Collection Storage Management is enabled for the tenant, you will not be able to set quota and will have a generic error returned. To workaround this issue, set the site collection storage management to "manual" temporarily, set your quotas and then set the site collection storage management setting back to its original setting.  


### -----------------------EXAMPLE 6-----------------------------
```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com/sites/site1 -EnablePWA $true
```

Example 6 enables the site "site1" to create  Project Web Applications (PWA).

## PARAMETERS

### -EnablePWA
Determines whether site can include Project Web App.
For more information about Project Web App, see Plan SharePoint groups in Project Server.


```yaml
Type: Boolean
Parameter Sets: ParamSet2
Aliases: 
Applicable: SharePoint Online

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies the URL of the site collection to update.


```yaml
Type: SpoSitePipeBind
Parameter Sets: (All)
Aliases: 
Applicable: SharePoint Online

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AllowSelfServiceUpgrade
Determines whether site collection administrators can upgrade their site collections.


```yaml
Type: Boolean
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
PARAMVALUE: SwitchParameter


```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DenyAddAndCustomizePages
Determines whether the Add And Customize Pages right is denied on the site collection.
For more information about permission levels, see User permissions and permission levels in SharePoint.


```yaml
Type: Boolean
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableSharingForNonOwners
This parameter prevents non-owners from invited new users to the site.

This parameter is available only in SharePoint Online Management Shell Version 16.0.4613.1211 or later.


```yaml
Type: SwitchParameter
Parameter Sets: ParamSet3
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisabledWebpartIds
This parameter is used for enabling disabled web parts that use third-party service (Amazon Kindle, YouTube, Twitter).  The GUIDs that can be used are 46698648-fcd5-41fc-9526-c7f7b2ace919 (Amazon Kindle), 544dd15b-cf3c-441b-96da-004d5a8cea1d (YouTube), f6fdf4f8-4a24-437b-a127-32e66a5dd9b4 (Twitter).

The Set-SPOTenant cmdlet is used for disabling these web parts with third-party services. 

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases:
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -LocaleId
Specifies the language of this site collection.
For more information, see Locale IDs Assigned by Microsoft (http://go.microsoft.com/fwlink/p/?LinkId=242911).


```yaml
Type: UInt32
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockState
Sets the lock state on a site.
Valid values are: NoAccess and Unlock.
When the lock state of a site is NoAccess, all traffic to the site will be blocked.
If parameter NoAccessRedirectUrl in the `Set-SPOTenant` cmdlet is set, traffic to sites that have a lock state NoAccess will be redirected to that URL.
If parameter NoAccessRedirectUrl is not set, a 403 error will be returned.


```yaml
Type: String
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Specifies to continue executing script immediately.


```yaml
Type: SwitchParameter
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Owner
Specifies the owner of the site collection.


```yaml
Type: String
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceQuota
Specifies the resource quota in megabytes of the site collection.
The default value is 0.
For more information, see Resource Usage Limits on Sandboxed Solutions in SharePoint (http://msdn.microsoft.com/en-us/library/gg615462.aspx).


```yaml
Type: Double
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceQuotaWarningLevel
Specifies the warning level in megabytes of the site collection to warn the site collection administrator that the site is approaching the resource quota.


```yaml
Type: Double
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SandboxedCodeActivationCapability
PARAMVALUE: Unknown | Check | Disabled | Enabled


```yaml
Type: SandboxedCodeActivationCapabilities
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharingCapability
Determines what level of sharing is available for the site.
The possible values are: Disabled - don't allow sharing outside your organization, ExistingExternalUserSharingOnly - Allow sharing only with the external users that already exist in your organization's directory, ExternalUserSharingOnly - allow external users who accept sharing invitations and sign in as authenticated users, or ExternalUserAndGuestSharing - allow sharing with all external users, and by using anonymous access links.

For more information about sharing, see Turn external sharing on or off for SharePoint Online (https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).


```yaml
Type: SharingCapabilities
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageQuota
Specifies the storage quota in megabytes of the site collection.


```yaml
Type: Int64
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageQuotaWarningLevel
Specifies the warning level in megabytes of the site collection to warn the site collection administrator that the site is approaching the storage quota.


```yaml
Type: Int64
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title
Specifies the title of the site collection.


```yaml
Type: String
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
PARAMVALUE: SwitchParameter


```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowLimitedAccess
{{Fill AllowLimitedAccess Description}}

```yaml
Type: Boolean
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlockDownloadOfNonViewableFiles
{{Fill BlockDownloadOfNonViewableFiles Description}}

```yaml
Type: Boolean
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommentsOnSitePagesDisabled
PARAMVALUE: $true | $false


```yaml
Type: Boolean
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -SocialBarOnSitePagesDisabled
Disables or enables the Social Bar for Site Collection.

The Social Bar will appear on all modern SharePoint pages with the exception of the home page of a site. It will give users the ability to like a page, see the number of views, likes, and comments on a page, and see the people who have liked a page.

PARAMVALUE: $true | $false


```yaml
Type: Boolean
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAppViews
PARAMVALUE: Unknown | Disabled | NotDisabled


```yaml
Type: AppViewsPolicy
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCompanyWideSharingLinks
PARAMVALUE: Unknown | Disabled | NotDisabled


```yaml
Type: CompanyWideSharingLinksPolicy
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableFlows
PARAMVALUE: Unknown | Disabled | NotDisabled


```yaml
Type: FlowsPolicy
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestrictedToGeo
PARAMVALUE: NoRestriction | BlockMoveOnly | BlockFull | Unknown


```yaml
Type: RestrictedToRegion
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharingAllowedDomainList
Specifies a list of email domains that is allowed for sharing with the external collaborators. Use the space character as the delimiter for entering multiple values. For example, “contoso.com fabrikam.com”. 

For additional information about how to restrict a domain sharing, see Restricted Domains Sharing in Office 365 SharePoint Online and OneDrive for Business.


```yaml
Type: String
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharingBlockedDomainList
Specifies a list of email domains that is blocked or prohibited for sharing with the external collaborators. Use space character as the delimiter for entering multiple values. For example, “contoso.com fabrikam.com”. 

For additional information about how to restrict a domain sharing, see Restricted Domains Sharing in Office 365 SharePoint Online and OneDrive for Business.


```yaml
Type: String
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharingDomainRestrictionMode
Specifies the external sharing mode for domains.

The following values are:

None

AllowList

BlockList

For additional information about how to restrict a domain sharing, see Restricted Domains Sharing in Office 365 SharePoint Online and OneDrive for Business.


```yaml
Type: SharingDomainRestrictionModes
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowPeoplePickerSuggestionsForGuestUsers
To enable the option to search for existing guest users at Site Collection Level, set this parameter to $true.


```yaml
Type: Boolean
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageQuotaReset
Resets the OneDrive for Business storage quota to the tenant’s new default storage space. 


```yaml
Type: SwitchParameter
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```



### -DefaultSharingLinkType 

The default link type for the site collection

PARAMVALUE: None | AnonymousAccess | Internal | Direct

None - Respect the organization default sharing link type
AnonymousAccess - Sets the default sharing link for this site to an Anonymous Access or Anyone link
Internal - Sets the default sharing link for this site to the “organization” link or company shareable link
Direct - Sets the default sharing link for this site to the “Specific people” link


```yaml
Type: SharingLinkType
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -DefaultLinkPermission

The default link permission for the site collection

PARAMVALUE: None | View | Edit

None - Respect the organization default link permission
View - Sets the default link permission for the site to “view” permissions
Edit - Sets the default link permission for the site to “edit” permissions

```yaml
Type: SharingPermissionType
Parameter Sets: ParamSet1
Aliases: 
Applicable: SharePoint Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConditionalAccessPolicy  
PARAMVALUE: AllowFullAccess | LimitedAccess | BlockAccess
Please read documentation here to understand Conditional Access Policy usage in SharePoint Online "https://docs.microsoft.com/en-us/sharepoint/control-access-from-unmanaged-devices"
```powershell
Set-SPOSite -identity <url> -ConditionalAccessPolicy AllowLimitedAccess 
```

### -AllowEditing  
PARAMVALUE: $true | $false 
Prevents users from editing Office files in the browser and copying and pasting Office file contents out of the browser window.
```powershell
Set-SPOSite -identity <url> -ConditionalAccessPolicy AllowLimitedAccess -AllowEditing $false
```

### -LimitedAccessFileType 
PARAMVALUE: OfficeOnlineFilesOnly | WebPreviewableFiles | OtherFiles
The following parameters can be used with -ConditionalAccessPolicy AllowLimitedAccess for both the organization-wide setting and the site-level setting. 
-OfficeOnlineFilesOnly Allows users to preview only Office files in the browser. This option increases security but may be a barrier to user productivity.
-LimitedAccessFileType WebPreviewableFiles (default) Allows users to preview Office files and other file types (such as PDF files and images) in the browser. Note that the contents of file types other than Office files are handled in the browser. This option optimizes for user productivity but offers less security for files that aren't Office files.
-LimitedAccessFileType OtherFiles Allows users to download files that can't be previewed, such as .zip and .exe. This option offers less security.
```powershell
Set-SPOSite -identity <url> -ConditionalAccessPolicy AllowLimitedAccess -LimitedAccessFileType <OfficeOnlineFilesOnly | WebPreviewableFiles | OtherFiles>
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Set-SPOTenant](Set-SPOTenant.md)
