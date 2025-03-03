---
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
online version: https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy
applicable: Exchange Online, Exchange Online Protection
title: New-HostedContentFilterPolicy
schema: 2.0.0
author: chrisda
ms.author: chrisda
ms.reviewer:
---

# New-HostedContentFilterPolicy

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the New-HostedContentFilterPolicy cmdlet to create spam filter policies (content filter policies) in your cloud-based organization.

**Note**: We recommend that you use the Exchange Online PowerShell V2 module to connect to Exchange Online PowerShell. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://docs.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-HostedContentFilterPolicy [-Name] <String>
 [-AddXHeaderValue <String>]
 [-AdminDisplayName <String>]
 [-AllowedSenderDomains <MultiValuedProperty>]
 [-AllowedSenders <MultiValuedProperty>]
 [-BlockedSenderDomains <MultiValuedProperty>]
 [-BlockedSenders <MultiValuedProperty>]
 [-BulkQuarantineTag <String>]
 [-BulkSpamAction <SpamFilteringAction>]
 [-BulkThreshold <Int32>]
 [-Confirm]
 [-DownloadLink <Boolean>]
 [-EnableEndUserSpamNotifications <Boolean>]
 [-EnableLanguageBlockList <Boolean>]
 [-EnableRegionBlockList <Boolean>]
 [-EndUserSpamNotificationCustomFromAddress <SmtpAddress>]
 [-EndUserSpamNotificationCustomFromName <String>]
 [-EndUserSpamNotificationCustomSubject <String>]
 [-EndUserSpamNotificationFrequency <Int32>]
 [-EndUserSpamNotificationLanguage <EsnLanguage>]
 [-EndUserSpamNotificationLimit <Int32>]
 [-HighConfidencePhishAction <PhishFilteringAction>]
 [-HighConfidencePhishQuarantineTag <String>]
 [-HighConfidenceSpamAction <SpamFilteringAction>]
 [-HighConfidenceSpamQuarantineTag <String>]
 [-IncreaseScoreWithBizOrInfoUrls <SpamFilteringOption>]
 [-IncreaseScoreWithImageLinks <SpamFilteringOption>]
 [-IncreaseScoreWithNumericIps <SpamFilteringOption>]
 [-IncreaseScoreWithRedirectToOtherPort <SpamFilteringOption>]
 [-InlineSafetyTipsEnabled <Boolean>]
 [-LanguageBlockList <MultiValuedProperty>]
 [-MarkAsSpamBulkMail <SpamFilteringOption>]
 [-MarkAsSpamEmbedTagsInHtml <SpamFilteringOption>]
 [-MarkAsSpamEmptyMessages <SpamFilteringOption>]
 [-MarkAsSpamFormTagsInHtml <SpamFilteringOption>]
 [-MarkAsSpamFramesInHtml <SpamFilteringOption>]
 [-MarkAsSpamFromAddressAuthFail <SpamFilteringOption>]
 [-MarkAsSpamJavaScriptInHtml <SpamFilteringOption>]
 [-MarkAsSpamNdrBackscatter <SpamFilteringOption>]
 [-MarkAsSpamObjectTagsInHtml <SpamFilteringOption>]
 [-MarkAsSpamSensitiveWordList <SpamFilteringOption>]
 [-MarkAsSpamSpfRecordHardFail <SpamFilteringOption>]
 [-MarkAsSpamWebBugsInHtml <SpamFilteringOption>]
 [-ModifySubjectValue <String>]
 [-PhishQuarantineTag <String>]
 [-PhishSpamAction <SpamFilteringAction>]
 [-PhishZapEnabled <Boolean>
 [-QuarantineRetentionPeriod <Int32>]
 [-RecommendedPolicyType <RecommendedPolicyType>]
 [-RedirectToRecipients <MultiValuedProperty>]
 [-RegionBlockList <MultiValuedProperty>]
 [-SpamAction <SpamFilteringAction>]
 [-SpamQuarantineTag <String>]
 [-SpamZapEnabled <Boolean>]
 [-TestModeAction <SpamFilteringTestModeAction>]
 [-TestModeBccToRecipients <MultiValuedProperty>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

For more information about the limits for allowed and blocked senders, see [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## EXAMPLES

### Example 1
```powershell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

This example creates a spam filter policy named Contoso Executives with the following settings:

- Quarantine messages when the spam filtering verdict is spam or high confidence spam.
- BCL 6 triggers the action for a bulk email spam filtering verdict.

## PARAMETERS

### -Name
The Name parameter specifies a unique name for the spam filter policy. If the value contains spaces, enclose the value in quotation marks (").

Don't use the following characters in the name value: `\ % & * + / = ? { } | < > ( ) ; : [ ] , "`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddXHeaderValue
The AddXHeaderValue parameter specifies the X-header name (not value) to add to spam messages when a spam filtering verdict parameter is set to the value AddXHeader. The following spam filtering verdict parameters can use the AddXHeader action:

- BulkSpamAction
- HighConfidenceSpamAction
- PhishSpamAction
- SpamAction

The maximum length is 255 characters, and the value can't contain spaces or colons (:).

For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`

If you enter a value that contains spaces or colons (:), the value is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).

Note that this setting is independent of the AddXHeader value of the TestModeAction parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdminDisplayName
The AdminDisplayName parameter specifies a description for the policy. The maximum length is 256 characters. If the value contains spaces, enclose the value in quotation marks (").

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedSenderDomains
The AllowedSenderDomains parameter specifies trusted domains that aren't processed by the spam filter. Messages from senders in these domains are stamped with `SFV:SKA` in the `X-Forefront-Antispam-Report header` and receive a spam confidence level (SCL) of -1, so the messages are delivered to the recipient's inbox. Valid values are one or more SMTP domains.

**Caution**: Think very carefully before you add domains here. For more information, see [Create safe sender lists in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedSenders
The AllowedSenders parameter specifies a list of trusted senders that skip spam filtering. Messages from these senders are stamped with SFV:SKA in the X-Forefront-Antispam-Report header and receive an SCL of -1, so the messages are delivered to the recipient's inbox. Valid values are one or more SMTP email addresses.

**Caution**: Think very carefully before you add senders here. For more information, see [Create safe sender lists in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlockedSenderDomains
The BlockedSenderDomains parameter specifies domains that are always marked as spam sources. Messages from senders in these domains are stamped with `SFV:SKB` value in the `X-Forefront-Antispam-Report` header and receive an SCL of 6 (spam). Valid values are one or more SMTP domains.

**Note**: Manually blocking domains isn't dangerous, but it can increase your administrative workload. For more information, see [Create block sender lists in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-block-sender-lists-in-office-365?).

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlockedSenders
The BlockedSenders parameter specifies senders that are always marked as spam sources. Messages from these senders are stamped with `SFV:SKB` in the `X-Forefront-Antispam-Report` header and receive an SCL of 6 (spam). Valid values are one or more SMTP email addresses.

**Note**: Manually blocking senders isn't dangerous, but it can increase your administrative workload. For more information, see [Create block sender lists in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-block-sender-lists-in-office-365?).

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BulkQuarantineTag
The BulkQuarantineTag parameter specifies the quarantine policy that's used on messages that are quarantined as bulk email (the BulkSpamAction parameter value is Quarantine). You can use any value that uniquely identifies the quarantine policy. For example:

- Name
- Distinguished name (DN)
- GUID

Quarantine policies define what users are able to do to quarantined messages based on why the message was quarantined. To view the list of available quarantine policies, run the following command: `Get-QuarantinePolicy | Format-List Name,EndUser*,AdminNotification*`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BulkSpamAction
The BulkSpamAction parameter specifies the action to take on messages that are marked as bulk email (also known as gray mail) based on the bulk complaint level (BCL) of the message, and the BCL threshold you configure in the BulkThreshold parameter. Valid values are:

- AddXHeader: Add the AddXHeaderValue parameter value to the message header and deliver the message.
- Delete: Delete the message during filtering. Use caution when selecting this value, because you can't recover the deleted message.
- ModifySubject: Add the ModifySubject parameter value to the beginning of the subject line, deliver the message, and move the message to the Junk Email folder (same caveats as MoveToJmf).
- MoveToJmf: This is the default value. Deliver the message to the recipient's mailbox, and move the message to the Junk Email folder. In Exchange Online, The message is moved only if the junk email rule is enabled on the mailbox (it's enabled by default). For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes). In standalone Exchange Online Protection environments, you need to configure mail flow rules in your on-premises Exchange organization. For instructions, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](https://docs.microsoft.com/microsoft-365/security/office-365-security/ensure-that-spam-is-routed-to-each-user-s-junk-email-folder).
- NoAction
- Quarantine: Move the message to quarantine. By default, messages that are quarantined as bulk email are available to the intended recipients and admins. Or, you can use the BulkQuarantineTag parameter to specify what end-users are allowed to do on quarantined messages.
- Redirect: Redirect the message to the recipients specified by the RedirectToRecipients parameter.

```yaml
Type: SpamFilteringAction
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BulkThreshold
The BulkThreshold parameter specifies the BCL on messages that triggers the action specified by the BulkSpamAction parameter (greater than or equal to the specified BCL value). A valid value is an integer from 1 to 9. The default value is 7, which means a BCL of 7, 8, or 9 on messages will trigger the action that's specified by the BulkSpamAction parameter.

A higher BCL indicates the message is more likely to generate complaints (and is therefore more likely to be spam). For more information, see [Bulk complaint level (BCL) in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/bulk-complaint-level-values).

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.
- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DownloadLink
The DownloadLink parameter shows or hides a link in end-user spam quarantine notifications to download the Junk Email Reporting Tool for Outlook. Valid values are:

- $true: end-user spam quarantine notifications contain a link to download the Junk Email Reporting Tool for Outlook.
- $false: end-user spam quarantine notifications don't contain the link. This is the default value.

This parameter is only meaningful only when the EnableEndUserSpamNotifications parameter value is $true.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableEndUserSpamNotifications
The EnableEndUserSpamNotification parameter enables for disables sending end-user spam quarantine notifications. Valid values are:

- $true: End-users periodically receive notifications when a messages that was supposed to be delivered to them was quarantined as spam. When you use this value, you can also use the EndUserSpamNotificationCustomSubject, EndUserSpamNotificationFrequency, and EndUserSpamNotificationLanguage parameters.
- $false: end-user spam quarantine notifications are disabled. This is the default value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLanguageBlockList
The EnableLanguageBlockList parameter enables or disables marking messages that were written in specific languages as spam. Valid values are:

- $true: Mark messages hat were written in the languages specified by the LanguageBlockList parameter as spam.
- $false: Don't mark messages as spam solely based on their languages. This is the default value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableRegionBlockList
The EnableRegionBlockList parameter enables or disables marking messages that are sent from specific countries or regions as spam. Valid values are:

- $true: Mark messages from senders in the RegionBlockList parameter as spam.
- $false: Don't mark messages as spam solely based on the source country or region. This is the default value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndUserSpamNotificationCustomFromAddress
This parameter has been deprecated and is no longer used.

```yaml
Type: SmtpAddress
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndUserSpamNotificationCustomFromName
This parameter has been deprecated and is no longer used.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndUserSpamNotificationCustomSubject
The EndUserSpamNotificationCustomSubject parameter specifies a custom subject for end-user spam notification messages. If the value includes spaces, enclose the value in quotation marks (").

This parameter is meaningful only when the EnableEndUserSpamNotifications parameter value is $true.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndUserSpamNotificationFrequency
The EndUserSpamNotificationFrequency parameter specifies the repeat interval in days that end-user spam quarantine notifications are sent. A valid value is an integer between 1 and 15. The default value is 3.

This parameter is meaningful only when the EnableEndUserSpamNotifications parameter value is $true.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndUserSpamNotificationLanguage
The EndUserSpamNotificationLanguage parameter specifies the language of end-user spam quarantine notifications. Valid values are:

Default, Amharic, Arabic, Basque, BengaliIndia, Bulgarian, Catalan, ChineseSimplified, ChineseTraditional, Croatian, Cyrillic, Czech, Danish, Dutch, English, Estonian, Filipino, Finnish, French, Galician, German, Greek, Gujarati, Hebrew, Hindi, Hungarian, Icelandic, Indonesian, Italian, Japanese, Kannada, Kazakh, Korean, Latvian, Lithuanian, Malay, Malayalam, Marathi, Norwegian, NorwegianNynorsk, Odia, Persian, Polish, Portuguese, PortuguesePortugal, Romanian, Russian, Serbian, SerbianCyrillic, Slovak, Slovenian, Spanish, Swahili, Swedish, Tamil, Telugu, Thai, Turkish, Ukrainian, Urdu, and Vietnamese.

The default value is Default, which means English.

This parameter is meaningful only when the EnableEndUserSpamNotifications parameter value is $true.

```yaml
Type: EsnLanguage
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndUserSpamNotificationLimit
This parameter is reserved for internal Microsoft use.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighConfidencePhishAction
The HighConfidencePhishAction parameter specifies the action to take on messages that are marked as high confidence phishing (not phishing). Phishing messages use fraudulent links or spoofed domains to get personal information. Valid values are:

- MoveToJmf: Deliver the message to the recipient's mailbox, and move the message to the Junk Email folder. The message is moved only if the junk email rule is enabled on the mailbox (it's enabled by default). For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).
- Redirect: Redirect the message to the recipients specified by the RedirectToRecipients parameter.
- Quarantine: Move the message to quarantine. By default, messages that are quarantined as high confidence phishing are available only to admins. Or, you can use the HighConfidencePhishQuarantineTag parameter to specify what end-users are allowed to do on quarantined messages.

```yaml
Type: PhishFilteringAction
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighConfidencePhishQuarantineTag
The HighConfidencePhishQuarantineTag parameter specifies the quarantine policy that's used on messages that are quarantined as high confidence phishing (the HighConfidencePhishAction parameter value is Quarantine). You can use any value that uniquely identifies the quarantine policy. For example:

- Name
- Distinguished name (DN)
- GUID

Quarantine policies define what users are able to do to quarantined messages based on why the message was quarantined. To view the list of available quarantine policies, run the following command: `Get-QuarantinePolicy | Format-List Name,EndUser*,AdminNotification*`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighConfidenceSpamAction
The HighConfidenceSpamAction parameter specifies the action to take on messages that are marked as high confidence spam (not spam, bulk email, phishing, or high confidence phishing). Valid values are:

- AddXHeader: Add the AddXHeaderValue parameter value to the message header, deliver the message, and move the message to the Junk Email folder (same caveats as MoveToJmf).
- Delete: Delete the message during filtering. Use caution when selecting this value, because you can't recover the deleted message.
- ModifySubject: Add the ModifySubject parameter value to the beginning of the subject line, deliver the message, and move the message to the Junk Email folder (same caveats as MoveToJmf).
- MoveToJmf: Deliver the message to the recipient's mailbox, and move the message to the Junk Email folder. In Exchange Online, the message is only moved if the junk email rule is enabled on the mailbox (it's enabled by default). For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes). In standalone Exchange Online Protection environments, you need to configure mail flow rules in your on-premises Exchange organization. For instructions, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](https://docs.microsoft.com/microsoft-365/security/office-365-security/ensure-that-spam-is-routed-to-each-user-s-junk-email-folder).
- Quarantine: Move the message to quarantine. By default, messages that are quarantined as high confidence spam are available to the intended recipients and admins. Or, you can use the HighConfidenceSpamQuarantineTag parameter to specify what end-users are allowed to do on quarantined messages.
- Redirect: Redirect the message to the recipients specified by the RedirectToRecipients parameter.

```yaml
Type: SpamFilteringAction
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighConfidenceSpamQuarantineTag
The HighConfidenceSpamQuarantineTag parameter specifies the quarantine policy that's used on messages that are quarantined as high confidence spam (the HighConfidenceSpamAction parameter value is Quarantine). You can use any value that uniquely identifies the quarantine policy. For example:

- Name
- Distinguished name (DN)
- GUID

Quarantine policies define what users are able to do to quarantined messages based on why the message was quarantined. To view the list of available quarantine policies, run the following command: `Get-QuarantinePolicy | Format-List Name,EndUser*,AdminNotification*`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncreaseScoreWithBizOrInfoUrls
**Note**: This setting is part of Advanced Spam Filtering (ASF) and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The IncreaseScoreWithBizOrInfoUrls parameter increases the spam score of messages that contain links to .biz or .info domains. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain links to .biz or .info domains are given the SCL 5 or 6 (spam), and the X-header `X-CustomSpam: URL to .biz or .info websites` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncreaseScoreWithImageLinks
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The IncreaseScoreWithImageLinks parameter increases the spam score of messages that contain image links to remote websites. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain image links to remote websites are given the SCL 5 or 6 (spam), and the X-header `X-CustomSpam: Image links to remote sites` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncreaseScoreWithNumericIps
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The IncreaseScoreWithNumericIps parameter increases the spam score of messages that contain links to IP addresses. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain links to IP addresses are given the SCL 5 or 6 (spam), and the X-header `X-CustomSpam: Numeric IP in URL` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncreaseScoreWithRedirectToOtherPort
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The IncreaseScoreWithRedirectToOtherPort parameter increases the spam score of messages that contain links that redirect to TCP ports other than 80 (HTTP), 8080 (alternate HTTP), or 443 (HTTPS). Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain links that redirect to other TCP ports are given the SCL 5 or 6 (spam), and the X-header `X-CustomSpam: URL redirect to other port` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InlineSafetyTipsEnabled
The InlineSafetyTipsEnabled parameter specifies whether to enable or disable safety tips that are shown to recipients in messages. Valid values are:

- $true: Safety tips are enabled. This is the default value.
- $false: Safety tips are disabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LanguageBlockList
The LanguageBlockList parameter specifies the email content languages that are marked as spam when the EnableLanguageBlockList parameter value is $true. A valid value is a supported ISO 639-1 two-letter language code:

af, ar, az, be, bg, bn, br, bs, ca, cs, cy, da, de, el, en, eo, es, et, eu, fa, fi, fo, fr, fy, ga, gl, gu, ha, he, hi, hr, hu, hy, id, is, it, ja, ka, kk, kl, kn, ko, ku, ky, la, lb, lt, lv, mi, mk, ml, mn, mr, ms, mt, nb, nl, nn, pa, pl, ps, pt, rm, ro, ru, se, sk, sl, sq, sr, sv, sw, ta, te, th, tl, tr, uk, ur, uz, vi, wen, yi, zh-cn, zh-tw, and zu.

A reference for two-letter language codes is available at [ISO 639-2](https://www.loc.gov/standards/iso639-2/php/code_list.php). Note that not all possible language codes are available as input for this parameter.

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

To empty the list, use the value $null.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamBulkMail
The MarkAsSpamBulkMail parameter allows spam filtering to act on bulk email messages. Valid values are:

- Off: The message is stamped with the BCL, but no action is taken for a bulk email filtering verdict. In effect, the values of the BulkThreshold and BulkSpamAction parameters are irrelevant.
- On: This is the default value. A BCL that's greater than the BulkThreshold value is converted to an SCL 6 that corresponds to a filtering verdict of spam, and the BulkSpamAction value is taken on the message.
- Test: This value is available, but isn't used for this parameter.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamEmbedTagsInHtml
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamEmbedTagsInHtml parameter marks a message as spam when the message contains HTML \<embed\> tags. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain HTML \<embed\> tags are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: Embed tag in html` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamEmptyMessages
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamEmptyMessages parameter marks a message as spam when the message contains no subject, no content in the message body, and no attachments. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Empty messages are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: Empty Message` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamFormTagsInHtml
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamFormTagsInHtml parameter marks a message as spam when the message contains HTML \<form\> tags. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain HTML \<form\> tags are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: Form tag in html` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamFramesInHtml
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamFramesInHtml parameter marks a message as spam when the message contains HTML \<frame\> or \<iframe\> tags. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain HTML \<frame\> or \<iframe\> tags are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: IFRAME or FRAME in HTML` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamFromAddressAuthFail
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamFromAddressAuthFail parameter marks a message as spam when Sender ID filtering encounters a hard fail. This setting combines an Sender Policy Framework (SPF) check with a Sender ID check to help protect against message headers that contain forged senders. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages where Sender ID filtering encounters a hard fail are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: SPF From Record Fail` is added to the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamJavaScriptInHtml
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamJavaScriptInHtml parameter marks a message as spam when the message contains JavaScript or VBScript. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain JavaScript or VBScript are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: Javascript or VBscript tags in HTML` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamNdrBackscatter
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamNdrBackscatter parameter marks a message as spam when the message is a non-delivery report (also known as an NDR or bounce messages) sent to a forged sender (known as *backscatter*). Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Backscatter is given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: Backscatter NDR` is added to the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamObjectTagsInHtml
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamObjectTagsInHtml parameter marks a message as spam when the message contains HTML \<object\> tags. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain HTML \<object\> tags are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: Object tag in html` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamSensitiveWordList
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamSensitiveWordList parameter marks a message as spam when the message contains words from the sensitive words list. Microsoft maintains a dynamic but non-editable list of words that are associated with potentially offensive messages. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain words from the sensitive word list in the subject or message body are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: Sensitive word in subject/body` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamSpfRecordHardFail
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamSpfRecordHardFail parameter marks a message as spam when SPF record checking encounters a hard fail. Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages sent from an IP address that isn't specified in the SPF Sender Policy Framework (SPF) record in DNS are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: SPF Record Fail` is added to the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MarkAsSpamWebBugsInHtml
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you leave this setting turned off.

The MarkAsSpamWebBugsInHtml parameter marks a message as spam when the message contains web bugs (also known as web beacons). Valid values are:

- Off: The setting is disabled. This is the default value, and we recommend that you don't change it.
- On: The setting is enabled. Messages that contain web bugs are given the SCL 9 (high confidence spam), and the X-header `X-CustomSpam: Web bug` is added to the message.
- Test: The action specified by the TestModeAction parameter is taken on the message.

```yaml
Type: SpamFilteringOption
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModifySubjectValue
The ModifySubjectValue parameter specifies the text to prepend to the existing subject of messages when a spam filtering verdict parameter is set to the value ModifySubject. The following spam filtering verdict parameters can use the ModifySubject action:

- BulkSpamAction
- HighConfidenceSpamAction
- PhishSpamAction
- SpamAction

If the value contains spaces, enclose the value in quotation marks (").

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhishQuarantineTag
The PhishQuarantineTag parameter specifies the quarantine policy that's used on messages that are quarantined as phishing (the PhishSpamAction parameter value is Quarantine). You can use any value that uniquely identifies the quarantine policy. For example:

- Name
- Distinguished name (DN)
- GUID

Quarantine policies define what users are able to do to quarantined messages based on why the message was quarantined. To view the list of available quarantine policies, run the following command: `Get-QuarantinePolicy | Format-List Name,EndUser*,AdminNotification*`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhishSpamAction
The PhishSpamAction parameter specifies the action to take on messages that are marked as phishing (not high confidence phishing). Phishing messages use fraudulent links or spoofed domains to get personal information. Valid values are:

- AddXHeader: Add the AddXHeaderValue parameter value to the message header and deliver the message.
- Delete: Delete the message during filtering. Use caution when selecting this value, because you can't recover the deleted message.
- ModifySubject: Add the ModifySubject parameter value to the beginning of the subject line, deliver the message, and move the message to the Junk Email folder (same caveats as MoveToJmf).
- MoveToJmf: Deliver the message to the recipient's mailbox, and move the message to the Junk Email folder. The message is moved only if the junk email rule is enabled on the mailbox (it's enabled by default). For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).
- Quarantine: Move the message to the quarantine. This is the default value. The quarantined message is available to the intended recipients (as of April, 2020) and admins.
- Quarantine: Move the message to quarantine. By default, messages that are quarantined as phishing are available to admins and (as of April 2020) the intended recipients. Or, you can use the PhishQuarantineTag parameter to specify what end-users are allowed to do on quarantined messages.
- Redirect: Redirect the message to the recipients specified by the RedirectToRecipients parameter.

```yaml
Type: SpamFilteringAction
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhishZapEnabled
The PhishZapEnabled parameter enables or disables zero-hour auto purge (ZAP) to detect phishing in already delivered messages in Exchange Online mailboxes. Valid values are:

- $true: ZAP for phishing messages is enabled. This is the default value. The result depends on the spam filtering verdict action for phishing messages: MoveToJmf = Read and unread phishing messages are moved to the Junk Email folder. Delete, Redirect, or Quarantine = Read and unread phishing messages are quarantined. AddXHeader or ModifySubject = no action is taken on the message.
- $false: ZAP for phishing messages is disabled.

You configure ZAP for spam with the SpamZapEnabled parameter.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QuarantineRetentionPeriod
The QuarantineRetentionPeriod parameter specifies the number of days that spam messages remain in quarantine when a spam filtering verdict parameter is set to the value Quarantine. All spam filtering verdict parameters can use the Quarantine action:

- BulkSpamAction
- HighConfidencePhishAction
- HighConfidenceSpamAction
- PhishSpamAction
- SpamAction

A valid value is an integer between 1 and 30. The default value is 15.

After the time period expires, the message is deleted.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecommendedPolicyType
The RecommendedPolicyType parameter is used for Standard and Strict policy creation as part of [Preset security policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/preset-security-policies). Don't use this parameter yourself.

```yaml
Type: RecommendedPolicyType
Parameter Sets: (All)
Aliases:
Accepted values: Custom, Standard, Strict
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectToRecipients
The RedirectToRecipients parameter specifies the email addresses of replacement recipients when a spam filtering verdict parameter is set to the value Redirect. The following spam filtering verdict parameters can use the Redirect action:

- BulkSpamAction
- HighConfidenceSpamAction
- PhishSpamAction
- SpamAction

You can specify multiple email addresses separated by commas.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegionBlockList
The RegionBlockList parameter specifies the source countries or regions that are marked as spam when the EnableRegionBlockList parameter value is $true. A valid value is a supported ISO 3166-1 two-letter country code:

AD, AE, AF, AG, AI, AL, AM, AO, AQ, AR, AS, AT, AU, AW, AX, AZ, BA, BB, BD, BE, BF, BG, BH, BI, BJ, BL, BM, BN, BO, BQ, BR, BS, BT, BV, BW, BY, BZ, CA, CC, CD, CF, CG, CH, CI, CK, CL, CM, CN, CO, CR, CU, CV, CW, CX, CY, CZ, DE, DJ, DK, DM, DO, DZ, EC, EE, EG, ER, ES, ET, FI, FJ, FK, FM, FO, FR, GA, GB, GD, GE, GF, GG, GH, GI, GL, GM, GN, GP, GQ, GR, GS, GT, GU, GW, GY, HK, HM, HN, HR, HT, HU, ID, IE, IL, IM, IN, IO, IQ, IR, IS, IT, JE, JM, JO, JP, KE, KG, KH, KI, KM, KN, KP, KR, KW, KY, KZ, LA, LB, LC, LI, LK, LR, LS, LT, LU, LV, LY, MA, MC, MD, ME, MF, MG, MH, MK, ML, MM, MN, MO, MP, MQ, MR, MS, MT, MU, MV, MW, MX, MY, MZ, NA, NC, NE, NF, NG, NI, NL, NO, NP, NR, NU, NZ, OM, PA, PE, PF, PG, PH, PK, PL, PM, PN, PR, PS, PT, PW, PY, QA, RE, RO, RS, RU, RW, SA, SB, SC, SD, SE, SG, SH, SI, SJ, SK, SL, SM, SN, SO, SR, ST, SV, SX, SY, SZ, TC, TD, TF, TG, TH, TJ, TK, TL, TM, TN, TO, TR, TT, TV, TW, TZ, UA, UG, UM, US, UY, UZ, VA, VC, VE, VG, VI, VN, VU, WF, WS, XE, XJ, XS, YE, YT, ZA, ZM, and ZW.

A reference for two-letter country codes is available at [Country Codes List](https://www.nationsonline.org/oneworld/country_code_list.htm).

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

To empty the list, use the value $null.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SpamAction
The SpamAction parameter specifies the action to take on messages that are marked as spam (not high confidence spam, bulk email, phishing, or high confidence phishing). Valid values are:

- AddXHeader: Add the AddXHeaderValue parameter value to the message header, deliver the message, and move the message to the Junk Email folder (same caveats as MoveToJmf).
- Delete : Delete the message during filtering. Use caution when selecting this value, because you can't recover the deleted message.
- ModifySubject: Add the ModifySubject parameter value to the beginning of the subject line, deliver the message, and move the message to the Junk Email folder (same caveats as MoveToJmf).
- MoveToJmf: This is the default value. Deliver the message to the recipient's mailbox, and move the message to the Junk Email folder. In Exchange Online, the message is only moved if the junk email rule is enabled on the mailbox (it's enabled by default). For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes). In standalone Exchange Online Protection environments, you need to configure mail flow rules in your on-premises Exchange organization. For instructions, see [Configure standalone EOP to deliver spam to the  k Email folder in hybrid environments](https://docs.microsoft.com/microsoft-365/security/office-365-security/ensure-that-spam-is-routed-to-each-user-s-junk-email-folder).
- Quarantine: Move the message to quarantine. By default, messages that are quarantined as spam are available to the intended recipients and admins. Or, you can use the SpamQuarantineTag parameter to specify what end-users are allowed to do on quarantined messages.
- Redirect: Redirect the message to the recipients specified by the RedirectToRecipients parameter.

```yaml
Type: SpamFilteringAction
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SpamQuarantineTag
The SpamQuarantineTag parameter specifies the quarantine policy that's used on messages that are quarantined as spam (the SpamAction parameter value is Quarantine). You can use any value that uniquely identifies the quarantine policy. For example:

- Name
- Distinguished name (DN)
- GUID

Quarantine policies define what users are able to do to quarantined messages based on why the message was quarantined. To view the list of available quarantine policies, run the following command: `Get-QuarantinePolicy | Format-List Name,EndUser*,AdminNotification*`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SpamZapEnabled
The SpamZapEnabled parameter enables or disables zero-hour auto purge (ZAP) to detect spam in already delivered messages in Exchange Online mailboxes. Valid values are:

- $true: ZAP for spam is enabled. This is the default value. The result depends on the spam filtering verdict action for spam messages: MoveToJmf = Unread spam messages are moved to the Junk Email folder. Delete, Redirect, or Quarantine = Unread spam messages are quarantined. AddXHeader or ModifySubject = no action is taken on the message.
- $false: ZAP for spam is disabled.

You configure ZAP for phishing messages with the PhishZapEnabled parameter.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestModeAction
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you don't use this setting.

The TestModeAction parameter specifies the additional action to take on messages when one or more IncreaseScoreWith\* or MarkAsSpam\* ASF parameters are set to the value Test. Valid values are:

- None: This is the default value, and we recommend that you don't change it.
- AddXHeader: The X-header value `X-CustomSpam: This message was filtered by the custom spam filter option` is added to the message.
- BccMessage: Redirect the message to the recipients specified by the TestModeBccToRecipients parameter.

```yaml
Type: SpamFilteringTestModeAction
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestModeBccToRecipients
**Note**: This setting is part of ASF and will be deprecated. The functionality of this setting will be incorporated into other parts of the filtering stack. We recommend that you don't use this setting.

The TestModeBccToRecipients parameter specifies the blind carbon copy (Bcc) recipients to add to spam messages when the TestModeAction ASF parameter is set to the value BccMessage.

Valid input for this parameter is an email address. Separate multiple email addresses with commas.

This parameter is meaningful only when the value of the TestModeAction parameter is BccMessage, and when the value of one or more IncreaseScoreWith\* or MarkAsSpam\* parameters is Test.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
The WhatIf switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: Exchange Online, Exchange Online Protection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

###  
To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

###  
To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS
