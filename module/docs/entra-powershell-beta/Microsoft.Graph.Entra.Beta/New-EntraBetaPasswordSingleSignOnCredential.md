---
external help file: Microsoft.Graph.Entra.Beta-Help.xml
Module Name: Microsoft.Graph.Entra.Beta
online version: https://learn.microsoft.com/powershell/module/Microsoft.Graph.Entra.Beta/New-EntraBetaPasswordSingleSignOnCredential

schema: 2.0.0
---

# New-EntraBetaPasswordSingleSignOnCredential

## Synopsis
Creates the password SSO credentials

## Syntax

```
New-EntraBetaPasswordSingleSignOnCredential -ObjectId <String>
 -PasswordSSOCredential <PasswordSSOCredentials> [<CommonParameters>]
```

## Description
This cmdlet enables users to create their Password Single-sign-on credentials for an application which they are part of.
Admin could create the group credentials as well.

## Examples

### New password single-sign-on credentials
```
PS C:\> $credentials = New-Object -TypeName Microsoft.Open.MSGraph.Model.PasswordSSOCredentials
PS C:\> $credentials.Id = "a4210a97-5e26-4cfe-88f1-118ed4886f27"
PS C:\> $creds1 = [Microsoft.Open.MSGraph.Model.PasswordSSOCredential]@{FieldId="param_1"; Value="foobar@ms.com"; Type="text"}
PS C:\> $creds2 = [Microsoft.Open.MSGraph.Model.PasswordSSOCredential]@{FieldId="param_2"; Value="my-secret"; Type="password"}
PS C:\> $credentials.Credentials = @($creds1, $creds2)

PS C:\> $new_creds_output = New-EntraBetaPasswordSingleSignOnCredential -ObjectId 9ac9883e-0ac5-4c32-8737-4267f56a28cc -PasswordSSOCredential $credentials
```

This command creates the password sso credentials for the given ObjectId and PasswordSSOObjectId.

## Parameters

### -ObjectId
The unique identifier of the object specific Azure Active Directory object

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PasswordSSOCredential
User or group id

```yaml
Type: PasswordSSOCredentials
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

## Outputs

### Microsoft.Online.Administration.PasswordSSOCredentials
## Notes
## Related Links
