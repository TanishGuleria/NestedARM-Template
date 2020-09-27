# NestedARM-Template

Run these Commands on Powershell ISE.

Connect-AzureRmAccount 

Set-AzureRmCurrentStorageAccount -ResourceGroupName armdemo -Name armdemonested
$url = (Get-AzureStorageBlob -Container test -Blob Demo1ParentTemplate.json).ICloudBlob.uri.AbsoluteUri
New-AzureRmResourceGroup -Location CentralUS -Name armdemo3
New-AzureRmResourceGroupDeployment -ResourceGroupName armdemo3 -TemplateFile $url
