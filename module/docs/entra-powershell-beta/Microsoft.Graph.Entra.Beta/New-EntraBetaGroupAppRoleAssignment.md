---
title: New-EntraBetaGroupAppRoleAssignment.
description: This article provides details on the New-EntraBetaGroupAppRoleAssignment command.


ms.topic: reference
ms.date: 07/24/2024
ms.author: eunicewaweru
ms.reviewer: stevemutungi
manager: CelesteDG
author: msewaweru

external help file: Microsoft.Graph.Entra.Beta-Help.xml
Module Name: Microsoft.Graph.Entra.Beta
online version: https://learn.microsoft.com/powershell/module/Microsoft.Graph.Entra.Beta/New-EntraBetaGroupAppRoleAssignment

schema: 2.0.0
---

# New-EntraBetaGroupAppRoleAssignment

## Synopsis

Assign a group of users to an application role.

## Syntax

```powershell
New-EntraBetaGroupAppRoleAssignment 
 -ResourceId <String> 
 -Id <String> 
 -ObjectId <String> 
 -PrincipalId <String>
 [<CommonParameters>]
```

## Description

The `New-EntraBetaGroupAppRoleAssignment` cmdlet assigns a group of users to an application role in Microsoft Entra ID.

## Examples

### Example 1: Assign a group of users to an application

```powershell
Connect-Entra -Scopes 'AppRoleAssignment.ReadWrite.All'
$appname = 'Box'
$spo = Get-EntraBetaServicePrincipal -Filter "Displayname eq '$appname'"
$group = Get-EntraBetaGroup -SearchString 'Contoso Team'
New-EntraBetaGroupAppRoleAssignment -ObjectId $group.ObjectId -PrincipalId $group.ObjectId -ResourceId $spo.ObjectId -Id $spo.Approles[1].id
```

```Output
DeletedDateTime        Id                                          AppRoleId                            CreatedDateTime      PrincipalDisplayName PrincipalId
---------------        --                                          ---------                            ---------------      -------------------- -----------
                      AaBbCcDdEeFfGgHhIiJjKkLlMmNnOo1 00000000-0000-0000-0000-000000000000 3/13/2024 4:41:43 AM Contoso Team         aaaaaaaa-bbbb-cccc-1111-222222222222
3/13/2024 4:45:00 AM  BbCcDdEeFfGgHhIiJjKkLlMmNnOoPp2 00000000-0000-0000-0000-000000000000 3/13/2024 4:45:00 AM Finance Group        bbbbbbbb-cccc-dddd-2222-333333333333
```

This example demonstrates how to assign a group of users to an application role in Microsoft Entra ID.  

- `-ObjectId` parameter specifies the ID of a group to which you're assigning the app role.
- `-PrincipalId` parameter specifies the ID of a group to which you're assigning the app role.
- `-ResourceId` parameter specifies the ID of a resource service Principal, which has defined the app role.
- `-Id` parameter specifies the ID of a appRole (defined on the resource service principal) to assign to the group.

## Parameters

### -Id

Specifies the ID of the app role (defined on the resource service principal) to assign.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId

Specifies the ID of a user (as a UserPrincipalName or ObjectId) in Microsoft Entra ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PrincipalId

Specifies the principal ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId

The unique identifier (ID) for the resource service principal for which the assignment is made.  
Required on create. Supports $filter (eq only).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

## Outputs

## Notes

## Related Links

[Get-EntraBetaGroupAppRoleAssignment](Get-EntraBetaGroupAppRoleAssignment.md)

[Remove-EntraBetaGroupAppRoleAssignment](Remove-EntraBetaGroupAppRoleAssignment.md)
