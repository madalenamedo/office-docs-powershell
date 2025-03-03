---
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml 
online version: https://docs.microsoft.com/powershell/module/skype/get-cstenant
applicable: Microsoft Teams, Skype for Business Online
title: Get-CsTenant
schema: 2.0.0
manager: bulenteg
author: tomkau
ms.author: tomkau
ms.reviewer:
---

# Get-CsTenant

## SYNOPSIS
Returns information about the Microsoft Teams or Skype for Business Online tenants that have been configured for use in your organization.
Tenants represent groups of online users.

## SYNTAX

```
Get-CsTenant [-Filter <String>] [-DomainController <Fqdn>] [[-Identity] <OUIdParameter>] [-ResultSize <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
In Microsoft Teams or Skype for Business Online, tenants are groups of users who have accounts homed on the service.
Organizations will typically have a single tenant in which to house all their user accounts.

**NOTE:**

Beginning Teams PowerShell Module version 3.0.0 onwards, the following updates are applicable for TeamsOnly customers.

*Deprecated Attributes*

- DisableExoPlanProvisioning
- DistinguishedName
- ExperiencePolicy
- Id
- Identity
- IsByPassValidation
- IsMNC
- IsReadinessUploaded
- IsUpgradeReady
- LastSubProvisionTimeStamp
- MNCEnableTimeStamp
- Name
- ObjectCategory
- ObjectClass
- ObjectState
- OriginalRegistrarPool
- OriginatingServer
- PendingDeletion
- ProvisioningCounter
- PublicProvider
- PublishingCounter
- RegistrarPool
- RemoteMachine
- SubProvisioningCounter
- SubProvisioningStamp
- SyncingCounter
- TenantPoolExtension
- UpgradeRetryCounter
- UserRoutingGroupIds
- XForestMovePolicy
- Guid
- HostedVoiceMailNotProvisioned
- IsO365MNC
- IsValid
- NonPrimarySource
- OcoDomainTracked
- Phone
- ProvisionType
- TeamsUpgradeEligible
- TelehealthEnabled
- TenantNotified
- AssignedLicenses
- OnPremisesImmutableId
- OnPremisesUserPrincipalName
- HostedVoiceMail
- OnPremSecurityIdentifier
- OnPremSamAccountName
- DefaultDataLocation
- DefaultPoolFqdn
- AdminDescription
- AllowedDataLocation
- Description
- DomainUrlMap
- ObjectId
- ProvisioningStamp
- PublishingStamp

*Renamed attributes*
The following attributes have been renamed:

- CountryAbbreviation renamed as CountryLetterCode
- CountryOrRegionDisplayName renamed as Country
- StateOrProvince renamed as State

## EXAMPLES

### -------------------------- Example 1 --------------------------
```
Get-CsTenant
```

The command shown in Example 1 returns information about your tenant.
Organizations will have only one tenant.


## PARAMETERS

### -DomainController
This parameter is not used with Skype for Business Online and will be deprecated in the near future.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Enables you to return data by using Active Directory attributes and without having to specify the full Active Directory distinguished name.
For example, to retrieve a tenant by using the tenant display name, use syntax similar to this:

Get-CsTenant -Filter {DisplayName -eq "FabrikamTenant"}

To return all tenants that use a Fabrikam domain use this syntax:

Get-CsTenant -Filter {Domains -like "*fabrikam*"}

The Filter parameter uses the same Windows PowerShell filtering syntax is used by the `Where-Object` cmdlet.

You cannot use both the Identity parameter and the Filter parameter in the same command.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Unique identifier for the tenant.
For example:

-Identity "bf19b7db-6960-41e5-a139-2aa373474354"

If you do not include either the Identity or the Filter parameter then the `Get-CsTenant` cmdlet will return information about all your tenants.

```yaml
Type: OUIdParameter
Parameter Sets: (All)
Aliases: 
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSize
Enables you to limit the number of records returned by the cmdlet.
For example, to return seven tenants (regardless of the number of tenants that are in your forest) include the ResultSize parameter and set the parameter value to 7.
Note that there is no way to guarantee which 7 users will be returned.

The result size can be set to any whole number between 0 and 2147483647, inclusive.
If set to 0 the command will run, but no data will be returned.
If you set the tenants to 7 but you have only three contacts in your forest, the command will return those three tenants and then complete without error.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).


## INPUTS

### Microsoft.Rtc.Management.ADConnect.Schema.TenantObject or String
The `Get-CsTenant` cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.ADConnect.Schema.TenantObject object as well as string values representing the Identity of the tenant (for example "bf19b7db-6960-41e5-a139-2aa373474354").

## OUTPUTS

### Microsoft.Rtc.Management.ADConnect.Schema.TenantObject

## NOTES

## RELATED LINKS

