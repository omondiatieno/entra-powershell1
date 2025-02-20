---
title: Set-EntraBetaUserLicense
description: This article provides details on the Set-EntraBetaUserLicense command.


ms.topic: reference
ms.date: 06/26/2024
ms.author: eunicewaweru
ms.reviewer: stevemutungi
manager: CelesteDG
author: msewaweru

external help file: Microsoft.Graph.Entra.Beta-Help.xml
Module Name: Microsoft.Graph.Entra.Beta
online version: https://learn.microsoft.com/powershell/module/Microsoft.Graph.Entra.Beta/Set-EntraBetaUserLicense

schema: 2.0.0
---

# Set-EntraBetaUserLicense

## Synopsis
Adds or removes licenses for a Microsoft online service to the list of assigned licenses for a user.

## Syntax

```powershell
Set-EntraBetaUserLicense 
    -ObjectId <String> 
    -AssignedLicenses <AssignedLicenses>
 [<CommonParameters>]
```

## Description
The **Set-EntraBetaUserLicense** adds or removes licenses for a Microsoft online service to the list of assigned licenses for a user.

## Examples

### Example 1: Add a license to a user based on a template user
```powershell
PS C:\> $LicensedUser = Get-EntraBetaUser -ObjectId "TemplateUser@contoso.com"  
PS C:\> $User = Get-EntraBetaUser -ObjectId "User@contoso.com"  
PS C:\> $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
PS C:\> $License.SkuId = $LicensedUser.AssignedLicenses.SkuId 
PS C:\> $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
PS C:\> $Licenses.AddLicenses = $License 
PS C:\> Set-EntraBetaUserLicense -ObjectId $User.ObjectId -AssignedLicenses $Licenses
```

The first command gets a user by using the [Get-EntraBetaUser](./Get-EntraBetaUser.md) cmdlet, and then stores it in the $LicensedUser variable.  

The second command gets another user by using Get-EntraBetaUser, and then stores it in the $User variable.  

The third command creates an AssignedLicense type, and then stores it in the $License variable.  

The fourth command set the SkuId property of $License to the same value as the SkuId property of $LicensedUser.  

The fifth command creates an AssignedLicenses object, and stores it in the $Licenses variable.  

The sixth command adds the license in $License to $Licenses.  

The final command assigns the licenses in $Licenses to the user in $User.  

The licenses in $Licenses includes $License from the third and fourth commands.

## Parameters

### -AssignedLicenses
Specifies a list of licenses to assign or remove.

```yaml
Type: AssignedLicenses
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ObjectId
Specifies the ID of a user (as a UPN or ObjectId) in Microsoft Entra ID.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

## Outputs

## Notes

## Related Links

[Get-EntraBetaUser](Get-EntraBetaUser.md)

