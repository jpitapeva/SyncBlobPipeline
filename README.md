# SyncBlobPipeline

Pipeline em azure devops para syncar imagens do repositório para dentro no azure blob;

# yaml 

```
jobs:
- job:
  displayName: SyncImages
  pool:
    vmImage: windows-latest

  steps:
  - checkout: self
    persistCredentials: true

  - task: AzureFileCopy@6
    inputs:
      SourcePath: './images' #caminho dos arquivos das imagens
      azureSubscription: 'portal' #nome do devops service connection
      Destination: 'AzureBlob'  #tipo de destino
      storage: 'storagesteste' #nome do storage account
      ContainerName: 'img' #nome do container
```

# Evidência
![image](https://github.com/user-attachments/assets/628a554e-31c9-4ad4-b2ff-fde4a8f6a0e2)


# Referências
- https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/azure-file-copy-v6?view=azure-pipelines
- https://learn.microsoft.com/en-us/azure/devops/pipelines/library/service-endpoints?view=azure-devops

