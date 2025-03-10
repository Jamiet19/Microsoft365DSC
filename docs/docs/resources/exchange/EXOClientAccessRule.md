﻿# EXOClientAccessRule

## Parameters

| Parameter | Attribute | DataType | Description | Allowed Values |
| --- | --- | --- | --- | --- |
| **Identity** | Key | String | The Identity parameter specifies the client access rule that you want to modify. ||
| **Action** | Required | String | The Action parameter specifies the action for the client access rule. Valid values for this parameter are AllowAccess and DenyAccess. |AllowAccess, DenyAccess|
| **AnyOfAuthenticationTypes** | Write | StringArray[] | The AnyOfAuthenticationTypes parameter specifies a condition for the client access rule that is based on the client's authentication type. Valid values for this parameter are AdfsAuthentication, BasicAuthentication, CertificateBasedAuthentication, NonBasicAuthentication, OAuthAuthentication. |AdfsAuthentication, BasicAuthentication, CertificateBasedAuthentication, NonBasicAuthentication, OAuthAuthentication|
| **AnyOfClientIPAddressesOrRanges** | Write | StringArray[] | The AnyOfClientIPAddressesOrRanges parameter specifies a condition for the client access rule that is based on the client's IP address. Valid values for this parameter are: A single IP address, an IP address range, a CIDR IP. ||
| **AnyOfProtocols** | Write | StringArray[] | The AnyOfProtocols parameter specifies a condition for the client access rule that is based on the client's protocol. Valid values for this parameter are ExchangeActiveSync,ExchangeAdminCenter,ExchangeWebServices,IMAP4,OfflineAddressBook,OutlookAnywhere,OutlookWebApp,POP3,PowerShellWebServices,RemotePowerShell,REST,UniversalOutlook. |ExchangeActiveSync, ExchangeAdminCenter, ExchangeWebServices, IMAP4, OfflineAddressBook, OutlookAnywhere, OutlookWebApp, POP3, PowerShellWebServices, RemotePowerShell, REST, UniversalOutlook|
| **Enabled** | Write | Boolean | The Enabled parameter specifies whether the client access rule is enabled or disabled. Default is $true. ||
| **ExceptAnyOfAuthenticationTypes** | Write | StringArray[] | The ExceptAnyOfAuthenticationTypes parameter specifies an exception for the client access rule that is based on the client's authentication type. Valid values for this parameter are AdfsAuthentication, BasicAuthentication, CertificateBasedAuthentication, NonBasicAuthentication, OAuthAuthentication. |AdfsAuthentication, BasicAuthentication, CertificateBasedAuthentication, NonBasicAuthentication, OAuthAuthentication|
| **ExceptAnyOfClientIPAddressesOrRanges** | Write | StringArray[] | The ExceptAnyOfClientIPAddressesOrRanges parameter specifies an exception for the client access rule that is based on the client's IP address. Valid values for this parameter are: A single IP address, an IP address range, a CIDR IP. ||
| **ExceptAnyOfProtocols** | Write | StringArray[] | The ExceptAnyOfProtocols parameter specifies an exception for the client access rule that is based on the client's protocol. Valid values for this parameter are ExchangeActiveSync,ExchangeAdminCenter,ExchangeWebServices,IMAP4,OfflineAddressBook,OutlookAnywhere,OutlookWebApp,POP3,PowerShellWebServices,RemotePowerShell,REST,UniversalOutlook. |ExchangeActiveSync, ExchangeAdminCenter, ExchangeWebServices, IMAP4, OfflineAddressBook, OutlookAnywhere, OutlookWebApp, POP3, PowerShellWebServices, RemotePowerShell, REST, UniversalOutlook|
| **ExceptUsernameMatchesAnyOfPatterns** | Write | StringArray[] | The ExceptUsernameMatchesAnyOfPatterns parameter specifies an exception for the client access rule that is based on the user's account name. ||
| **Priority** | Write | UInt32 | The Priority parameter specifies a priority value for the client access rule. A lower integer value indicates a higher priority, and a higher priority rule is evaluated before a lower priority rule. The default value is 1. ||
| **RuleScope** | Write | String | The RuleScope parameter specifies the scope of the client access rule. Valid values are All and Users |All, Users|
| **UserRecipientFilter** | Write | String | The UserRecipientFilter parameter specifies a condition for the client access rule that uses OPath filter syntax to identify the user. ||
| **UsernameMatchesAnyOfPatterns** | Write | StringArray[] | The UsernameMatchesAnyOfPatterns parameter specifies a condition for the client access rule that is based on the user's account name. ||
| **Ensure** | Write | String | Specifies if this Client Access Rule should exist. |Present, Absent|
| **Credential** | Write | PSCredential | Credentials of the Exchange Global Admin ||
| **ApplicationId** | Write | String | Id of the Azure Active Directory application to authenticate with. ||
| **TenantId** | Write | String | Id of the Azure Active Directory tenant used for authentication. ||
| **CertificateThumbprint** | Write | String | Thumbprint of the Azure Active Directory application's authentication certificate to use for authentication. ||
| **CertificatePassword** | Write | PSCredential | Username can be made up to anything but password will be used for CertificatePassword ||
| **CertificatePath** | Write | String | Path to certificate used in service principal usually a PFX file. ||

# EXOClientAccessRule

### Description

This resource configures Client Access sRules.
Client Access Rules help you control access to your organization based
on the properties of the connection.

Note: Not all authentication types are supported for all protocols.

The supported authentication types per protocol can be found here:
https://docs.microsoft.com/en-us/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules

## Parameters

Ensure

- Required: No (Defaults to 'Present')
- Description: Specifies whether the configured Client Access Rule
  should be Present or Absent.

Credential

- Required: Yes
- Description: Credentials of the Office 365 Global Admin

Identity

- Required: Yes
- Description: The Identity parameter specifies the Client Access Rule
  that you want to modify.
  You can use any value that uniquely identifies the Client Access Rule.

Action

- Required: Yes
- Description: The Action parameter specifies the action for the
  client access rule.
  Valid values for this parameter are AllowAccess and DenyAccess.

AnyOfAuthenticationTypes

- Required: No
- Description: The AnyOfAuthenticationTypes parameter specifies a
  condition for the client access rule that's based on the client's
  authentication type.
  Valid values for this parameter are:
      AdfsAuthentication
      BasicAuthentication
      CertificateBasedAuthentication
      NonBasicAuthentication
      OAuthAuthentication

AnyOfClientIPAddressesOrRanges

- Required: No
- Description: The AnyOfClientIPAddressesOrRanges parameter specifies a
  condition for the client access rule that's based on the
  client's IP address.
  Valid values for this parameter are:
      A single IP address: For example, 192.168.1.1
      An IP address range: For example, 192.168.0.1-192.168.0.254
      Classless Inter-Domain Routing (CIDR) IP: e.g 192.168.3.1/24

AnyOfProtocols

- Required: No
- Description: The AnyOfProtocols parameter specifies a condition for
  the client access rule that's based on the client's protocol.
  Valid values for this parameter are:
      ExchangeActiveSync
      ExchangeAdminCenter
      ExchangeWebServices
      IMAP4
      OfflineAddressBook
      OutlookAnywhere
      OutlookWebApp
      POP3
      PowerShellWebServices
      RemotePowerShell
      REST
      UniversalOutlook

Enabled

- Required: No
- Description: The Enabled parameter specifies whether the client access
  rule is enabled or disabled.
  Valid values for this parameter are $true or $false. Default is $true

ExceptAnyOfAuthenticationTypes

- Required: No
- Description: The ExceptAnyOfAuthenticationTypes parameter specifies
  an exception for the client access rule that's based on the client's
  authentication type.
  Valid values for this parameter are:
      AdfsAuthentication
      BasicAuthentication
      CertificateBasedAuthentication
      NonBasicAuthentication
      OAuthAuthentication

ExceptAnyOfClientIPAddressesOrRanges

- Required: No
- Description: The ExceptAnyOfClientIPAddressesOrRanges parameter
  specifies an exception for the client access rule that's based on the
  client's IP address.
  Valid values for this parameter are:
      A single IP address: For example, 192.168.1.1
      An IP address range: For example, 192.168.0.1-192.168.0.254
      Classless Inter-Domain Routing (CIDR) IP: e.g. 192.168.3.1/24

ExceptAnyOfProtocols

- Required: No
- Description: The ExceptAnyOfProtocols parameter specifies an exception
  for the client access rule that's based on the client's protocol.
  Valid values for this parameter are:
      ExchangeActiveSync
      ExchangeAdminCenter
      ExchangeWebServices
      IMAP4
      OfflineAddressBook
      OutlookAnywhere
      OutlookWebApp
      POP3
      PowerShellWebServices
      RemotePowerShell
      REST
      UniversalOutlook

ExceptUsernameMatchesAnyOfPatterns

- Required: No
- Description: The ExceptUsernameMatchesAnyOfPatterns parameter
  specifies an exception for the client access rule that's based on the
  user's account name in the format [Domain]\[UserName]
  (for example, contoso.com\jeff).
  This parameter accepts text and the wildcard character (*)
  (for example, *jeff*, but not jeff*).

Priority

- Required: No
- Description: The Priority parameter specifies a priority value for
  the client access rule. A lower integer value indicates a higher
  priority, and a higher priority rule is evaluated before a lower
  priority rule. The default value is 1.

RuleScope

- Required: No
- Description: The RuleScope parameter specifies the scope of the
  client access rule.
  Valid values are:
      All: The rule applies to all connections
      (end-users and middle-tier apps).
      Users: The rule only applies to end-user connections.

UserRecipientFilter

- Required: No
- Description: The UserRecipientFilter parameter specifies a condition
  for the client access rule that uses OPath filter syntax to identify
  the user. For example, {City -eq "Redmond"}.
  The filterable attributes that you can use with this parameter are:
      City
      Company
      CountryOrRegion
      CustomAttribute1 to CustomAttribute15
      Department
      Office
      PostalCode
      StateOrProvince
      StreetAddress

## Example

```PowerShell
EXOClientAccessRule CliendAccessRuleExampleConfig {
    Ensure                               = 'Present'
    Identity                             = 'ExampleCASRule'
    Credential                           = $Credential
    Action                               = 'AllowAccess'
    AnyOfAuthenticationTypes             = @('AdfsAuthentication', 'BasicAuthentication')
    AnyOfClientIPAddressesOrRanges       = @('192.168.1.100', '10.1.1.0/24', '172.16.5.1-172.16.5.150')
    AnyOfProtocols                       = @('ExchangeAdminCenter', 'OutlookWebApp')
    Enabled                              = $false
    ExceptAnyOfClientIPAddressesOrRanges = @('10.1.1.13', '172.16.5.2')
    ExceptUsernameMatchesAnyOfPatterns   = @('*ThatGuy*', 'contoso\JohnDoe')
    Priority                             = 1
    RuleScope                            = 'Users'
    UserRecipientFilter                  = '{City -eq "Redmond"}'
}
```

## Examples

### Example 1

This example is used to test new resources and showcase the usage of new resources being worked on.
It is not meant to use as a production baseline.

```powershell
Configuration Example
{
    param(
        [Parameter(Mandatory = $true)]
        [PSCredential]
        $credsGlobalAdmin
    )
    Import-DscResource -ModuleName Microsoft365DSC

    node localhost
    {
        EXOClientAccessRule 'ConfigureClientAccessRule'
        {
            Action                               = "AllowAccess"
            UserRecipientFilter                  = $null
            ExceptAnyOfAuthenticationTypes       = @()
            ExceptUsernameMatchesAnyOfPatterns   = @()
            AnyOfAuthenticationTypes             = @()
            UsernameMatchesAnyOfPatterns         = @()
            Identity                             = "Always Allow Remote PowerShell"
            Priority                             = 1
            AnyOfProtocols                       = @("RemotePowerShell")
            Enabled                              = $True
            ExceptAnyOfProtocols                 = @()
            ExceptAnyOfClientIPAddressesOrRanges = @()
            AnyOfClientIPAddressesOrRanges       = @()
            Ensure                               = "Present"
            Credential                           = $GlobalAdmin
        }
    }
}
```

