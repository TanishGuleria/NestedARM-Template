# NestedARM-Template 

# incremental Deployment



Run these Commands on Powershell ISE.

Connect-AzureRmAccount 

New-AzureRmResourceGroup -Location CentralUS -Name armdemo
# Create a storage account name it as armdemonested then add blob container and upload the two .json file in the container. 



Set-AzureRmCurrentStorageAccount -ResourceGroupName armdemo -Name armdemonested

$url = (Get-AzureStorageBlob -Container test -Blob Demo1ParentTemplate.json).ICloudBlob.uri.AbsoluteUri

New-AzureRmResourceGroup -Location CentralUS -Name armdemo3

New-AzureRmResourceGroupDeployment -ResourceGroupName armdemo3 -TemplateFile $url
