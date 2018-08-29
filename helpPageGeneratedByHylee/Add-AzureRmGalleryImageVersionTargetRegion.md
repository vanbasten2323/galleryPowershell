---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/add-azurermgalleryimageversiontargetregion
schema: 2.0.0
---

# Add-AzureRmGalleryImageVersionTargetRegion

## SYNOPSIS
Add a target region to a gallery image version config:  New-AzureRmGalleryImageVersionConfig | Add-AzureRmGalleryImageVersionRegion -Name $regionName -RegionalReplicaCount $regionalReplicaCount

## SYNTAX

```
Add-AzureRmGalleryImageVersionTargetRegion -GalleryImageVersion <PSGalleryImageVersion> -Name <String> [-RegionalReplicaCount <Int32>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Add a target region to a gallery image version config:  New-AzureRmGalleryImageVersionConfig | Add-AzureRmGalleryImageVersionRegion -Name $regionName -RegionalReplicaCount $regionalReplicaCount

## EXAMPLES

### Example 1
```powershell
PS C:\> Add-AzureRmGalleryImageVersionTargetRegion -GalleryImageVersion $galleryImageVersionConfig -Name $regionName -RegionalReplicaCount $regionalReplicaCount
PS C:\> New-AzureRmGalleryImageVersionConfig | Add-AzureRmGalleryImageVersionRegion -Name "West US" -RegionalReplicaCount 2 | Add-AzureRmGalleryImageVersionRegion -Name "East US"
```

Add a target region to a gallery image version config.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GalleryImageVersion
The gallery image version config.

```yaml
Type: PSGalleryImageVersion
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Target region name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegionalReplicaCount
Regional replica count.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Microsoft.Azure.Commands.Compute.Automation.Models.PSGallery

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSGallery

## NOTES

## RELATED LINKS
