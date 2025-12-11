# SAP AI CORE Model Deployment steps
## API deployment
Please refer to the SAP documentation https://help.sap.com/docs/sap-ai-core/sap-ai-core-service-guide/deploy-models?locale=en-US
## AI Launchpad
1. Login to SAP AI Launchpad and go to **Generative AI Hub -> Model**

   <img width="1449" height="707" alt="SAP AI Launchpad" src="https://github.com/user-attachments/assets/79d09b5f-def3-4375-93ca-a7d0556c1fb3" />

2. Select the model you want to deploy (in my case Clause Sonnet 4.5)

  <img width="1550" height="372" alt="AI Core model deployment" src="https://github.com/user-attachments/assets/658423cf-dce3-4615-89a1-173edc0dea19" />

3. Click **"Deploy"** button, deployment can start
4. Go to Deployment **ML Operations -> Deployment** section when you can check the status of the deployment. It can take a while to finish the deplyoment before first use
   - before 
   <img width="1894" height="687" alt="AI Core ML Operations" src="https://github.com/user-attachments/assets/dc96dae4-6c23-46f2-b9f8-e93d8cf87c77" />
   - after
   <img width="1570" height="274" alt="AI Core ML Operations" src="https://github.com/user-attachments/assets/0249dc5c-6d73-44da-906d-36b4b3fdf9aa" />

> [!NOTE]
> You must wait until deplyoyment has status RUNNING before the usage

5. You can then copy generated URL
<img width="1594" height="802" alt="AL Core Model generated" src="https://github.com/user-attachments/assets/2c628bfe-0147-4b35-b6c5-2fd3ea290936" />
