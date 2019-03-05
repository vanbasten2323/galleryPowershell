## Service Release Details

- Is this an Embargoed Preview, A Public Preview, or a General Release?

    - `{ General Release }`

- What is the expected service release date?

    - `{ May 01, 2019 }`

## Contact Information

- Main developer contacts (emails + github aliases)

    - `{ Xiongfei Wei: xiowei@microsoft.com, vanbasten2323 }`
    - `{ Kshitij Agrawal: kagarwal@microsoft.com, KshitijAgrawal }`
    - `{ Jerry Chan: jerch@microsoft.com }`

- PM contact (email + github alias) 

    - `{ Akshay Joshi: Akshaya.Joshi@microsoft.com, axayjo }`

- Other people who should attend a design review (email)

    - `{ Hyonho Lee: Hyonho.Lee@microsoft.com, hylee }`
    - `{ Ferry Susanto: ferrys@microsoft.com, ferrysusanto }`


## High Level Scenarios

- Describe how your feature is intended to be used by customers.
  - Customers should be able to specify the storage account type when they create a gallery image version.


## Sample of end-to-end usage
### Gallery Image Version
#### Create a gallery image version
```
$region1 = @{Name='West US';ReplicaCount=1;StorageAccountType=Standard_LRS}
$region2 = @{Name='East US';ReplicaCount=2;StorageAccountType=Standard_ZRS}
$region3 = @{Name='Central US'}
$targetRegions = @($region1,$region2,$region3)
New-AzureRmGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -GalleryImageDefinitionName $imageDefinitionName -Name $versionName -Location $location -SourceImageId $sourceImageId -ReplicaCount 2 -StorageAccountType Standard_LRS -PublishingProfileExcludeFromLatest -PublishingProfileEndOfLifeDate $endOfLifeDate -TargetRegion $targetRegions
```

## Syntax changes

This should include PowerShell-help style syntax descriptions of all new and changed cmdlets, similar to the syntax portion of PowerShell help (or markdown help), for example:

### Gallery Image Version
#### Changed cmdlet [New-AzureRmGalleryImageVersion](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/New-AzureRmGalleryImageVersion.md)
```
PS C:\> New-AzureRmGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String> [-GalleryImageDefinitionName] <String> [-Name] <String> [-Location] <String> [-SourceImageId] <String> [-Tag <Hashtable>] [-ReplicaCount <Int32>] [-StorageAccountType {Standard_LRS | Standard_ZRS}] [-PublishingProfileExcludeFromLatest] [-PublishingProfileEndOfLifeDate <DateTime>] [-TargetRegion <PSTargetRegionInfo[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```
