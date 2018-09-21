## Service Release Details

- Is this an Embargoed Preview, A Public Preview, or a General Release?

    - `{ Public Preview }`

- What is the expected service release date?

    - `{ Sep 24, 2018 }`

## Contact Information

- Main developer contacts (emails + github aliases)

    - `{ Xiongfei Wei: xiowei@microsoft.com, vanbasten2323 }`
    - `{ Kshitij Agrawal: kagarwal@microsoft.com, KshitijAgrawal }`

- PM contact (email + github alias) 

    - `{ Kay Singh: Kay.Singh@microsoft.com, singhkays }`

- Other people who should attend a design review (email)

    - `{ Hyonho Lee: Hyonho.Lee@microsoft.com, hylee }`
    - `{ Ferry Susanto: ferrys@microsoft.com, ferrysusanto }`


## High Level Scenarios

- Describe how your feature is intended to be used by customers.
  - Gallery
    - ` New cmdlets to create a gallery. `
      - New-AzureRmGallery
    - ` New cmdlets to update a gallery. `
      - Update-AzureRmGallery
    - ` New cmdlets to get a gallery or list galleries. `
      - Get-AzureRmGallery
    - ` New cmdlets to delete a gallery. `
      - Remove-AzureRmGallery
  - Gallery Image Definition
    - ` New cmdlets to create a gallery image definition. `
      - New-AzureRmGalleryImageDefinition
    - ` New cmdlets to update a gallery image definition. `
      - Update-AzureRmGalleryImageDefinition
    - ` New cmdlets to get a gallery image definition or list gallery image definitions. `
      - Get-AzureRmGalleryImageDefinition
    - ` New cmdlets to delete a gallery image definition. `
      - Remove-AzureRmGalleryImageDefinition
  - Gallery Image Version
    - ` New cmdlets to create a gallery image version. `
      - New-AzureRmGalleryImageVersion
    - ` New cmdlets to update a gallery image version. `
      - Update-AzureRmGalleryImageVersion
    - ` New cmdlets to get a gallery image version or list gallery image versions. `
      - Get-AzureRmGalleryImageVersion
    - ` New cmdlets to delete a gallery image version. `
      - Remove-AzureRmGalleryImageVersion
    

## Piping scenarios / how these cmdlets are used with existing cmdlets
  - Gallery
    - Get-AzureRmGallery -ResourceGroupName $resourceGroupName -Name $galleryName | Remove-AzureRmGallery
    - Get-AzureRmGallery -ResouggceGroupName $resourceGroupName | Remove-AzureRmGallery
    - Get-AzureRmGallery | Remove-AzureRmGallery
    - Get-AzureRmGallery -ResourceGroupName $resourceGroupName -Name $galleryName | Update-AzureRmGallery -Description $galleryDescription

  - Gallery Image
    - Get-AzureRmGalleryImageDefinition -ResourceGroupName $resourceGroupName -GalleryName $galleryName -Name $galleryImageDefinitionName | Remove-AzureRmGalleryImageDefinition
    - Get-AzureRmGalleryImageDefinition -ResourceGroupName $resourceGroupName -GalleryName $galleryName | Remove-AzureRmGalleryImageDefinition
    - Get-AzureRmGalleryImageDefinition -ResourceGroupName $resourceGroupName -GalleryName $galleryName -Name $galleryImageDefinitionName | Update-AzureRmGalleryImageDefinition -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState Generalized -OsType Linux -Description $description -Eula $eula -PrivacyStatementUri $privacyStatementUri -ReleaseNoteUri $releaseNoteUri -DisallowedDiskType $disallowedDiskTypes -EndOfLifeDate $endOfLifeDate -MinimumMemory $minMemory -MaximumMemory $maxMemory -MinimumVCPU $minVCPU -MaximumVCPU $maxVCPU -PurchasePlanName $purchasePlanName -PurchasePlanProduct $purchasePlanProduct -PurchasePlanPublisher $purchasePlanPublisher
    
  - Gallery Image Version    
    - Get-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $gallery -ImageDefinitionName $image -Name $version | Remove-AzureRmGalleryImageVersion
    - Get-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $gallery -ImageDefinitionName $image | Remove-AzureRmGalleryImageVersion
    - Get-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $gallery -ImageDefinitionName $image -Name $version | Update-AzureRmGalleryImageVersion -Location $location -SourceImageId $sourceImageId -ReplicaCount 2 -PublishingProfileExcludeFromLatest -PublishingProfileEndOfLifeDate $endOfLifeDate -TargetRegion $targetRegions
   

## Sample of end-to-end usage
### Gallery
#### Create a gallery
```
New-AzureRmGallery -ResourceGroupName $rgname -Name $galleryName -Location $location -Description $galleryDescription 
```
#### Update a gallery
```
Update-AzureRmGallery -ResourceGroupName $rgname -Name $galleryName -Description $galleryDescription
```
#### Get a gallery
```
Get-AzureRmGallery -ResourceGroupName $rgname -Name $galleryName
Get-AzureRmGallery -ResourceGroupName $rgname
Get-AzureRmGallery
```
#### Delete a gallery
```
Remove-AzureRmGallery -ResourceGroupName $rgname -Name $galleryName
```

### Gallery Image Definition
#### Create a gallery image definition
```
New-AzureRmGalleryImageDefinition -ResourceGroupName $resourceGroupName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -Description $description -Eula $eula -PrivacyStatementUri $privacyStatementUri -ReleaseNoteUri $releaseNoteUri -DisallowedDiskType $disallowedDiskTypes -EndOfLifeDate $endOfLifeDate -MinimumMemory $minMemory -MaximumMemory $maxMemory -MinimumVCPU $minVCPU -MaximumVCPU $maxVCPU -PurchasePlanName $purchasePlanName -PurchasePlanProduct $purchasePlanProduct -PurchasePlanPublisher $purchasePlanPublisher
```
#### Update a gallery image definition
```
Update-AzureRmGalleryImageDefinition -ResourceGroupName $resourceGroupName -GalleryName $galleryName -Name $galleryImageDefinitionName -Description $description -Eula $eula -PrivacyStatementUri $privacyStatementUri -ReleaseNoteUri $releaseNoteUri -DisallowedDiskType $disallowedDiskTypes -EndOfLifeDate $endOfLifeDate -MinimumMemory $minMemory -MaximumMemory $maxMemory -MinimumVCPU $minVCPU -MaximumVCPU $maxVCPU
```
#### Get a gallery image definition
```
Get-AzureRmGalleryImageDefinition -ResourceGroupName $rgname -GalleryName $gallery -Name $galleryImageDefinitionName
Get-AzureRmGalleryImageDefinition -ResourceGroupName $rgname -GalleryName $gallery
```
#### Delete a gallery image definition
```
Remove-AzureRmGalleryImageDefinition -ResourceGroupName $rgname -GalleryName $gallery -Name $galleryImageDefinitionName
```

### Gallery Image Version
#### Create a gallery image version
```
$region1 = @{Name='West US';ReplicaCount=1}
$region2 = @{Name='East US';ReplicaCount=2}
$region3 = @{Name='Central US'}
$targetRegions = @($region1,$region2,$region3)
New-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -ImageDefinitionName $imageDefinitionName -Name $versionName -Location $location -SourceImageId $sourceImageId -ReplicaCount 2 -PublishingProfileExcludeFromLatest -PublishingProfileEndOfLifeDate $endOfLifeDate -TargetRegion $targetRegions
```
#### Update a gallery image version
```
$region1 = @{Name='West US';ReplicaCount=1}
$region2 = @{Name='East US';ReplicaCount=2}
$region3 = @{Name='Central US'}
$targetRegions = @($region1,$region2,$region3)
Update-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -ImageDefinitionName $imageDefinitionName -Name $versionName -ReplicaCount 2 -PublishingProfileExcludeFromLatest -PublishingProfileEndOfLifeDate $endOfLifeDate -TargetRegion $targetRegions
```
#### Get a gallery image version
```
Get-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $gallery -ImageDefinitionName $imageDefinitionName -Name $version
Get-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $gallery -ImageDefinitionName $imageDefinitionName
```
#### Delete a gallery image version
```
Remove-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $gallery -ImageDefinitionName $imageDefinitionName -Name $version
```


## Syntax changes

This should include PowerShell-help style syntax descriptions of all new and changed cmdlets, similar to the syntax portion of PowerShell help (or markdown help), for example:

### Gallery
#### New Cmdlet [New-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/New-AzureRmGallery.md)
``` 
PS C:\> New-AzureRmGallery [-ResourceGroupName] <String> [-Name] <String> [-Location] <String> [[-Description] <String>] [[-Tag] <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

#### New Cmdlet [Update-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Update-AzureRmGallery.md)
```
PS C:\> Update-AzureRmGallery [-ResourceGroupName] <String> [-Name] <String> [[-Description] <String>] [[-Tag] <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

#### New Cmdlet [Get-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Get-AzureRmGallery.md)
```
PS C:\> Get-AzureRmGallery [[-ResourceGroupName] <String>] [[-Name] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

#### New Cmdlet [Remove-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Remove-AzureRmGallery.md)
```
PS C:\> Remove-AzureRmGallery [-ResourceGroupName] <String> [-Name] <String> [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>] 
```

### Gallery Image Definition
#### New Cmdlet [New-AzureRmGalleryImageDefinition](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/New-AzureRmGalleryImageDefinition.md)
```
PS C:\> New-AzureRmGalleryImageDefinition [-ResourceGroupName] <String> [-GalleryName] <String> [-Name] <String> [-Location] <String> [-Publisher] <String> [-Offer] <String> [-Sku] <String> [-OsState] {Generalized | Specialized} [-OsType] {Windows | Linux} [-Description <String>] [-Eula <String>] [-PrivacyStatementUri <String>] [-ReleaseNoteUri <String>] [-DisallowedDiskType <String[]>] [-EndOfLifeDate <DateTime>] [-MinimumMemory <Int32>] [-MaximumMemory <Int32>] [-MinimumVCPU <Int32>] [-MaximumVCPU <Int32>] [-VCPU <ResourceRange>] [-PurchasePlanName <String>] [-PurchasePlanProduct <String>] [-PurchasePlanPublisher <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>] [-Tag <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

#### New Cmdlet [Update-AzureRmGalleryImageDefinition](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Update-AzureRmGalleryImageDefinition.md)
```
PS C:\> Update-AzureRmGalleryImageDefinition [-ResourceGroupName] <String> [-GalleryName] <String> [-Name] <String> [-Description <String>] [-Eula <String>] [-PrivacyStatementUri <String>] [-ReleaseNoteUri <String>] [-DisallowedDiskType <String[]>] [-EndOfLifeDate <DateTime>] [-MinimumMemory <Int32>] [-MaximumMemory <Int32>] [-MinimumVCPU <Int32>] [-MaximumVCPU <Int32>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>] [-Tag <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

#### New Cmdlet [Get-AzureRmGalleryImageDefinition](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Get-AzureRmGalleryImageDefinition.md)
```
PS C:\> Get-AzureRmGalleryImageDefinition [-ResourceGroupName] <String> [-GalleryName] <String> [-Name <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

#### New Cmdlet [Remove-AzureRmGalleryImageDefinition](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Remove-AzureRmGalleryImageDefinition.md)
```
PS C:\> Remove-AzureRmGalleryImageDefinition [-ResourceGroupName] <String> [-GalleryName] <String> [-Name] <String> [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Gallery Image Version
#### New Cmdlet [New-AzureRmGalleryImageVersion](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/New-AzureRmGalleryImageVersion.md)
```
PS C:\> New-AzureRmGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String> [-ImageDefinitionName] <String> [-Name] <String> [-Location] <String> [-SourceImageId] <String> [-Tag <Hashtable>] [-ReplicaCount <Int32>] [-PublishingProfileExcludeFromLatest] [-PublishingProfileEndOfLifeDate <DateTime>] [-TargetRegion <PSTargetRegionInfo[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### New Cmdlet [Update-AzureRmGalleryImageVersion](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Update-AzureRmGalleryImageVersion.md)
```
PS C:\> Update-AzureRmGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String> [-ImageDefinitionName] <String> [-Name] <String> [-Tag <Hashtable>] [-ReplicaCount <Int32>] [-PublishingProfileExcludeFromLatest] [-PublishingProfileEndOfLifeDate <DateTime>] [-TargetRegion <PSTargetRegionInfo[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

#### New Cmdlet [Get-AzureRmGalleryImageVersion](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Get-AzureRmGalleryImageVersion.md)
```
PS C:\> Get-AzureRmGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String> [-ImageDefinitionName] <String> [[-Name] <String>] [[-Expand] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

#### New Cmdlet [Remove-AzureRmGalleryImageVersion](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Remove-AzureRmGalleryImageVersion.md)
```
PS C:\> Remove-AzureRmGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String> [-ImageDefinitionName] <String> [-Name] <String> [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```
