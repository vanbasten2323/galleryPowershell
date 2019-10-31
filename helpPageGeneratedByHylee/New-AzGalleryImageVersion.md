---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/en-us/powershell/module/Az.compute/new-Azgalleryimageversion
schema: 2.0.0
---

# New-AzGalleryImageVersion

## SYNOPSIS
Create a gallery image version.

## SYNTAX

```
New-AzGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String> [-GalleryImageDefinitionName] <String> [-Name] <String> [-Location] <String> [-SourceId <String>] [-SourceImageId <String>] [-OSDiskImage PSOSDiskInfo] [-DataDiskImage <PSDataDiskInfo[]>] [-Tag <Hashtable>] [-ReplicaCount <Int32>] [-StorageAccountType {Standard_LRS | Standard_ZRS}] [-PublishingProfileExcludeFromLatest] [-PublishingProfileEndOfLifeDate <DateTime>] [-TargetRegion <PSTargetRegionInfo[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Create a gallery image version.

## EXAMPLES

### Example 1
```powershell
$region1 = @{Name='West US';ReplicaCount=1;StorageAccountType=Standard_LRS}
$region2 = @{Name='East US';ReplicaCount=2;StorageAccountType=Standard_ZRS}
$region3 = @{Name='Central US'}
$targetRegions = @($region1,$region2,$region3)
New-AzGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -GalleryImageDefinitionName $imageDefinitionName -Name $versionName -Location $location -SourceId $SourceId -ReplicaCount 2 -StorageAccountType Standard_LRS -PublishingProfileExcludeFromLatest -PublishingProfileEndOfLifeDate $endOfLifeDate -TargetRegion $targetRegions
```

### Example 2
```powershell
$osDiskImage = @{Id='https://bogus:122/subscriptions/000000e4-dbcb-4235-bd41-76deb9bd189d/resourceGroups/Mock_CrpRgName/providers/Microsoft.Compute/snapshots/dummyOsSnapshot'}
$dataDiskImage1 = @{Id='https://bogus:122/subscriptions/000000e4-dbcb-4235-bd41-76deb9bd189d/resourceGroups/Mock_CrpRgName/providers/Microsoft.Compute/snapshots/dummyDataDiskSnapshot1';Lun=1}
$dataDiskImage2 = @{Id='https://bogus:122/subscriptions/000000e4-dbcb-4235-bd41-76deb9bd189d/resourceGroups/Mock_CrpRgName/providers/Microsoft.Compute/snapshots/dummyDataDiskSnapshot2';Lun=2}
$dataDiskImage = @($dataDiskImage1,$dataDiskImage2)
New-AzGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -GalleryImageDefinitionName $imageDefinitionName -Name $versionName -Location $location -OSDiskImage $osDiskImage -DataDiskImage $dataDiskImage
```

Create a gallery image version.

## PARAMETERS

### -ResourceGroupName
The name of the resource group.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GalleryName
The name of the gallery.

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

### -GalleryImageDefinitionName
The name of the gallery image definition.

```yaml
Type: String
Parameter Sets: (All)
Aliases: GalleryImageName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The name of the gallery image version

```yaml
Type: String
Parameter Sets: (All)
Aliases: GalleryImageVersionName

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Resource location

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceId
The managed artifact id of the source.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceImageId
The managed artifact id of the source. To be deprecated.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSDiskImage
The OS disk information of the source.

```yaml
Type: PSOSDiskInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DataDiskImage
The data disk information of the source.

```yaml
Type: PSDataDiskInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicaCount
This is the number of source blob copies in the region.

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

### -StorageAccountType
This is the storage account type to be used in the region.

```yaml
Type: StorageAccountType
Parameter Sets: (All)
Aliases:
Accepted values: Standard_LRS, Standard_ZRS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishingProfileExcludeFromLatest
The flag means that if it is set to true, people deploying VMs with 'latest' as version will not use this version.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishingProfileEndOfLifeDate
The end of life date of the gallery image version.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetRegion
The regions where the artifact is going to be published.

```yaml
Type: PSTargetRegionInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Run cmdlet in the background

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Microsoft.Azure.Commands.Compute.Automation.Models.PSGalleryImageVersion

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSGalleryImageVersion

## NOTES

## RELATED LINKS

