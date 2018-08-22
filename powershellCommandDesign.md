

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
    - ` New cmdlets to delete a gallery `
      - Remove-AzureRmGallery
    
## Piping scenarios / how these cmdlets are used with existing cmdlets
    - Get-AzureRmGallery -ResourceGroupName $resourceGroupName -GalleryName $galleryName | Remove-AzureRmGallery
    - Get-AzureRmGallery -ResourceGroupName $resourceGroupName -GalleryName $galleryName | Update-AzureRmGallery  -Description $galleryDescription
   
## Sample of end-to-end usage
### Create a gallery
```
New-AzureRmGallery [-ResourceGroupName] $resourceGroupName [-GalleryName] $galleryName [[-Description] $galleryDescription] [-Location] $location 
```
### Update a gallery
```
Update-AzureRmGallery [-ResourceGroupName] $resourceGroupName [-GalleryName] $galleryName [[-Description] $galleryDescription] [-Location] $location
```
### Get a gallery
```
Get-AzureRmGallery [[-ResourceGroupName] $resourceGroupName] [[-GalleryName] $galleryName]
```
### Delete a gallery
```
Remove-AzureRmGallery [-ResourceGroupName] $resourceGroupName [-GalleryName] $galleryName
```

## Syntax changes

This should include PowerShell-help style syntax descriptions of all new and changed cmdlets, similar to the syntax portion of PowerShell help (or markdown help), for example:


### New Cmdlet [New-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/New-AzureRmGallery.md)


``` powershell
PS C:\> New-AzureRmGallery [-ResourceGroupName] <String> [-GalleryName] <String> [[-Description] <String>] [-Location] <String>
```

### New Cmdlet [Update-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Update-AzureRmGallery.md)


``` powershell
PS C:\> Update-AzureRmGallery [-ResourceGroupName] <String> [-GalleryName] <String> [[-Description] <String>] [-Location] <String>
```

### New Cmdlet [Get-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Get-AzureRmGallery.md)


``` powershell
PS C:\> Get-AzureRmGallery [[-ResourceGroupName] <String>] [[-GalleryName] <String>] 
```
### New Cmdlet [Remove-AzureRmGallery](https://github.com/vanbasten2323/galleryPowershell/blob/master/helpPageGeneratedByHylee/Remove-AzureRmGallery.md)


``` powershell
PS C:\> Remove-AzureRmGallery [-ResourceGroupName] <String> [-GalleryName] <String>
```
