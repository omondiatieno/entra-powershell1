---
title: Get-EntraBetaServicePrincipalDelegatedPermissionClassification
description: This article provides details on the Get-EntraBetaServicePrincipalDelegatedPermissionClassification command.

ms.topic: reference
ms.date: 07/18/2024
ms.author: eunicewaweru
ms.reviewer: stevemutungi
manager: CelesteDG
author: msewaweru
external help file: Microsoft.Graph.Entra.Beta-Help.xml
Module Name: Microsoft.Graph.Entra.Beta
online version: https://learn.microsoft.com/powershell/module/Microsoft.Graph.Entra.Beta/Get-EntraBetaServicePrincipalDelegatedPermissionClassification

schema: 2.0.0
---

# Get-EntraBetaServicePrincipalDelegatedPermissionClassification

## Synopsis
Retreive the delegated permission classification objects on a service principal.

## Syntax

### GetQuery (Default)

```powershell
Get-EntraBetaServicePrincipalDelegatedPermissionClassification
 -ServicePrincipalId <String>
 [-Filter <String>]
 [-Property <String[]>]
 [<CommonParameters>]
```

### GetById

```powershell
Get-EntraBetaServicePrincipalDelegatedPermissionClassification
 -ServicePrincipalId <String>
 -Id <String>
 [-Property <String[]>]
 [<CommonParameters>]
```

## Description
The Get-EntraBetaServicePrincipalDelegatedPermissionClassification cmdlet retrieves the delegated permission classifications from a service principal.

## Examples

### Example 1: Get a list of delegated permission classifications
```
PS C:\> Get-EntraBetaServicePrincipalDelegatedPermissionClassification -ServicePrincipalId "95f56359-0165-4f80-bffb-c89d06cf2c6f"

Classification : Low
Id             : 5XBeIKarUkypdm0tRsSAQwE
PermissionId   : 205e70e5-aba6-4c52-a976-6d2d46c48043
PermissionName : Sites.Read.All

Classification : Low
Id             : ntbaFJsJyUKBC9ACmB_uwQE
PermissionId   : 14dad69e-099b-42c9-810b-d002981feec1
PermissionName : profile
```

This command retrieves all delegated permission classifications from the service principal.

### Example 2: Get a delegated permission classifications
```
PS C:\> Get-EntraBetaServicePrincipalDelegatedPermissionClassification -ServicePrincipalId "95f56359-0165-4f80-bffb-c89d06cf2c6f" -Id "5XBeIKarUkypdm0tRsSAQwE"

Classification : Low
Id             : 5XBeIKarUkypdm0tRsSAQwE
PermissionId   : 205e70e5-aba6-4c52-a976-6d2d46c48043
PermissionName : Sites.Read.All
```

This command retrieves the delegated permission classification by Id from the service principal.

### Example 3: Get a delegated permission classification with filter
```
PS C:\> Get-EntraBetaServicePrincipalDelegatedPermissionClassification -ServicePrincipalId "95f56359-0165-4f80-bffb-c89d06cf2c6f" -Filter "PermissionName eq 'Sites.Read.All'"

Classification : Low
Id             : 5XBeIKarUkypdm0tRsSAQwE
PermissionId   : 205e70e5-aba6-4c52-a976-6d2d46c48043
PermissionName : Sites.Read.All
```

This command retrieves the filtered delegated permission classifications from the service principal.

## Parameters

### -ServicePrincipalId
The unique identifier of a service principal object in Azure Active Directory.

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

### -Id
The unique identifier of a delegated permission classification object id.

```yaml
Type: String
Parameter Sets: GetById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Filter
The OData v4.0 filter statement. 
Controls which objects are returned.

```yaml
Type: String
Parameter Sets: GetQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Property

Specifies properties to be returned

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

## Outputs

### Microsoft.Online.Administration.DelegatedPermissionClassification
## Notes
## Related Links
