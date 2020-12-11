# ARM-template

Deployment of 2 linux VMs along with other associated resources to Azure using ARM templates.  
One is Application VM and second is Database VM.

Pre-requisites:  
      1. VS Code  
      2. Azure account  

Steps to follow:  
      1. Install ARM tool extension to VS code.  
       -Quick Open(ctr + P)   
       -Paste the command and enter  
           ext install azurerm-vscode-tools    
      2. Clone the repo to VS code.  
       - (ctr + sht +p)    
       - https://github.com/prasad53/ARM-template    
      3.On terminal, go to repo folder and follow the azure commands.  
                 1] Install azure cli:    
                       **curl -L https://aka.ms/InstallAzureCli | bash**     
                 2] **az login**   
                 3]Create resource group:    
                       **az group create --name demoRG --location "East US"**    
                 4]Validate the template:  
                   **az deployment group validate --name UItemplate --resource-group demoRG --template-file ./azurevm.json --parameter ./azurevm.parameters.json**                      
                  ProvisioningState:Succeeded ===>>>   shows a valid template  
                  5]Deploy the template:   
                    **az deployment group create --name UItemplate --resource-group demoRG --template-file ./azurevm.json --parameter ./azurevm.parameters.json**    
                        ProvisioningState:Succeeded ===>>>   shows a successfull deployment    
                  6]Check on azure portal for deployment verification.    
                  7]Delete resource group:  
                     **az group delete --resource-group demoRG**  
