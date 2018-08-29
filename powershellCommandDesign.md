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

    - ` New cmdlets to create a gallery. `
      - New-AzureRmGallery
    - ` New cmdlets to update a gallery. `
      - Update-AzureRmGallery
    - ` New cmdlets to get a gallery or list galleries. `
      - Get-AzureRmGallery
    - ` New cmdlets to delete a gallery. `
      - Remove-AzureRmGallery
    - ` New cmdlets to create a gallery image. `
      - New-AzureRmGalleryImage
    - ` New cmdlets to update a gallery image. `
      - Update-AzureRmGalleryImage
    - ` New cmdlets to get a gallery image or list gallery images. `
      - Get-AzureRmGalleryImage
    - ` New cmdlets to delete a gallery image. `
      - Remove-AzureRmGalleryImage
    - ` New cmdlets to create a gallery image version config. `
      - New-AzureRmGalleryImageVersionConfig
    - ` New cmdlets to add a target region to a gallery image version config. `
      - Add-AzureRmGalleryImageVersionTargetRegion
    - ` New cmdlets to create a gallery image version. `
      - New-AzureRmGalleryImageVersion
    - ` New cmdlets to update a gallery image version. `
      - Update-AzureRmGalleryImageVersion
    - ` New cmdlets to get a gallery image version or list gallery image versions. `
      - Get-AzureRmGalleryImageVersion
    - ` New cmdlets to delete a gallery image version. `
      - Remove-AzureRmGalleryImageVersion
    
## Piping scenarios / how these cmdlets are used with existing cmdlets
    - Get-AzureRmGallery -ResourceGroupName $resourceGroupName -GalleryName $galleryName | Remove-AzureRmGallery
    - Get-AzureRmGallery -ResourceGroupName $resourceGroupName -GalleryName $galleryName | Update-AzureRmGallery  -Description $galleryDescription
   
## Sample of end-to-end usage
### Create a gallery
```
New-AzureRmGallery [-ResourceGroupName] $resourceGroupName [-GalleryName] $galleryName [-Location] $location [[-Description] $galleryDescription]
```
### Update a gallery
```
Update-AzureRmGallery [-ResourceGroupName] $resourceGroupName [-GalleryName] $galleryName [-Location] $location [[-Description] $galleryDescription] 
```
### Get a gallery
```
Get-AzureRmGallery [[-ResourceGroupName] $resourceGroupName] [[-GalleryName] $galleryName]
```
### Delete a gallery
```
Remove-AzureRmGallery [-ResourceGroupName] $resourceGroupName [-GalleryName] $galleryName]
```
### Create a gallery image
```
New-AzureRmGalleryImage [-ResourceGroupName] $resourceGroupName [-GalleryName] $galleryName [-GalleryImageName] $galleryImageName [-Location] $location [-IdentifierPublisher] $publisherName [-IdentifierOffer] $offerName [-IdentifierSku] $skuName [-OsState] "Generalized" [-OsType] "Linux" [[-Description] $description] [[-Eula] $eula] [[-PrivacyStatementUri] $privacyStatementUri] [[-ReleaseNoteUri] $releaseNoteUri] [-DisallowedDiskType $disallowedDiskTypes] [-EndOfLifeDate $endOfLifeDate] [-MinimumMemory $minMemory] [-MaximumMemory $maxMemory] [-MinimumVCPU $minVCPU] [-MaximumVCPU $maxVCPU] [-PurchasePlanName $purchasePlanName] [-PurchasePlanProduct $purchasePlanProduct] [-PurchasePlanPublisher $purchasePlanPublisher]
```
### Update a gallery image
```
Update-AzureRmGalleryImage [-ResourceGroupName] $resourceGroupName [-GalleryName] $galleryName [-GalleryImageName] $galleryImageName [-Location] $location [-IdentifierPublisher] $publisherName [-IdentifierOffer] $offerName [-IdentifierSku] $skuName [-OsState] "Generalized" [-OsType] "Linux" [[-Description] $description] [[-Eula] $eula] [[-PrivacyStatementUri] $privacyStatementUri] [[-ReleaseNoteUri] $releaseNoteUri] [-DisallowedDiskType $disallowedDiskTypes] [-EndOfLifeDate $endOfLifeDate] [-MinimumMemory $minMemory] [-MaximumMemory $maxMemory] [-MinimumVCPU $minVCPU] [-MaximumVCPU $maxVCPU]  [-PurchasePlanName $purchasePlanName] [-PurchasePlanProduct $purchasePlanProduct] [-PurchasePlanPublisher $purchasePlanPublisher]
```
### Get a gallery image
```
Get-AzureRmGalleryImage -ResourceGroupName $rgname -GalleryName $gallery -GalleryImageName $image
```
### Delete a gallery image
```
Remove-AzureRmGalleryImage -ResourceGroupName $rgname -GalleryName $gallery -GalleryImageName $image
```
### Create a gallery image version config
```
New-AzureRmGalleryImageVersionConfig -Location $location -SourceImageId $sourceImageId -ReplicaCount 2 -PublishingProfileExcludeFromLatest $excludeFromLatest -PublishingProfileEndOfLifeDate $endOfLifeDate
```
### Add a target region to a gallery image version config
```
New-AzureRmGalleryImageVersionConfig | Add-AzureRmGalleryImageVersionRegion -Name "West US" -RegionalReplicaCount 2 | Add-AzureRmGalleryImageVersionRegion -Name "East US"
```
### Create a gallery image version
```
New-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -GalleryImageName $imageName -GalleryImageVersionName $versionName -GalleryImageVersion $galleryImageVersionObject
```
### Update a gallery image version
```
Update-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -GalleryImageName $imageName -GalleryImageVersionName $versionName -GalleryImageVersion $galleryImageVersionObject
```
### Get a gallery image version
```

```
### Delete a gallery image version
```

```

## Syntax changes

This should include PowerShell-help style syntax descriptions of all new and changed cmdlets, similar to the syntax portion of PowerShell help (or markdown help), for example:


### New Cmdlet [New-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/New-AzureRmGallery.md)


``` powershell
PS C:\> New-AzureRmGallery [-ResourceGroupName] <String> [-GalleryName] <String> [-Location] <String> [[-Description] <String>] [-Tag <Hashtable>] 
```

### New Cmdlet [Update-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Update-AzureRmGallery.md)


``` powershell
PS C:\> Update-AzureRmGallery [-ResourceGroupName] <String> [-GalleryName] <String> [[-Description] <String>] [-Location] <String> [-Tag <Hashtable>] 
```

### New Cmdlet [Get-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Get-AzureRmGallery.md)


``` powershell
PS C:\> Get-AzureRmGallery [[-ResourceGroupName] <String>] [[-GalleryName] <String>] 
```
### New Cmdlet [Remove-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Remove-AzureRmGallery.md)


``` powershell
PS C:\> Remove-AzureRmGallery [-ResourceGroupName] <String> [-GalleryName] <String>
```

### New Cmdlet [New-AzureRmGalleryImage](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/New-AzureRmGalleryImage.md)


``` powershell
PS C:\> New-AzureRmGalleryImage [-ResourceGroupName] <String> [-GalleryName] <String> [-GalleryImageName] <String> [-Location] <String> [-IdentifierPublisher] <String> [-IdentifierOffer] <String> [-IdentifierSku] <String> [-OsState] {Generalized | Specialized} [-OsType] {Windows | Linux} [[-Description] <String>] [[-Eula] <String>] [[-PrivacyStatementUri] <String>] [[-ReleaseNoteUri] <String>] [-DisallowedDiskType <String[]>] [-EndOfLifeDate <DateTime>] [-MinimumMemory <Int32>] [-MaximumMemory <Int32>] [-MinimumVCPU <Int32>] [-MaximumVCPU <Int32>] [-VCPU <ResourceRange>] [-PurchasePlanName <String>] [-PurchasePlanProduct <String>] [-PurchasePlanPublisher <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>] [-Tag <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### New Cmdlet [Update-AzureRmGalleryImage](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Update-AzureRmGalleryImage.md)


``` powershell
PS C:\> Update-AzureRmGalleryImage [-ResourceGroupName] <String> [-GalleryName] <String> [-GalleryImageName] <String> [-Location] <String> [-IdentifierPublisher] <String> [-IdentifierOffer] <String> [-IdentifierSku] <String> [-OsState] {Generalized | Specialized} [-OsType] {Windows | Linux} [[-Description] <String>] [[-Eula] <String>] [[-PrivacyStatementUri] <String>] [[-ReleaseNoteUri] <String>] [-DisallowedDiskType <String[]>] [-EndOfLifeDate <DateTime>] [-MinimumMemory $minMemory] [-MaximumMemory $maxMemory] [-MinimumVCPU $minVCPU] [-MaximumVCPU $maxVCPU] [-PurchasePlanName <String>] [-PurchasePlanProduct <String>] [-PurchasePlanPublisher <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>] [-Tag <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### New Cmdlet [Get-AzureRmGalleryImage](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Get-AzureRmGalleryImage.md)


``` powershell
PS C:\> Get-AzureRmGalleryImage [-ResourceGroupName] <String> [-GalleryName] <String> [[-GalleryImageName] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>] 
```
### New Cmdlet [Remove-AzureRmGalleryImage](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Remove-AzureRmGalleryImage.md)


``` powershell
PS C:\> Remove-AzureRmGalleryImage [-ResourceGroupName] <String> [-GalleryName] <String> [-GalleryImageName] <String> [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### New Cmdlet [New-AzureRmGalleryImageVersionConfig]()


``` powershell
PS C:\> New-AzureRmGalleryImageVersionConfig [-Location] <String> [-SourceImageId] <String> [-Tag <Hashtable>] [-ReplicaCount <Int32>] [-PublishingProfileExcludeFromLatest <Boolean>] [-PublishingProfileEndOfLifeDate <DateTime>] [-TargetRegions <TargetRegion[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```
### New Cmdlet [Add-AzureRmGalleryImageVersionTargetRegion]()


``` powershell
PS C:\> Add-AzureRmGalleryImageVersionTargetRegion -GalleryImageVersion <PSGalleryImageVersion> -Name <String> [-RegionalReplicaCount <Int32>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```
### New Cmdlet [New-AzureRmGalleryImageVersion]()


``` powershell
PS C:\> New-AzureRmGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String> [-GalleryImageName] <String> [-GalleryImageVersionName] <String> [-GalleryImageVersion] <PSGalleryImageVersion> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```### New Cmdlet [Update-AzureRmGalleryImageVersion]()


``` powershell
PS C:\> Update-AzureRmGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String> [-GalleryImageName] <String> [-GalleryImageVersionName] <String> [-GalleryImageVersion] <PSGalleryImageVersion> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```
```### New Cmdlet [Get-AzureRmGalleryImageVersion]()


``` powershell
```
```### New Cmdlet [Remove-AzureRmGalleryImageVersion]()


``` powershell
```
