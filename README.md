# try_platform_aws_azure_for_machine_learning
Why am I trying this different platform? Since I only used machine learning and deep learning model for researches or non-profit projects use. At that time, we built our own cloud server with our GPU Nvidia 1080Ti and 2080Ti/ local gpu or cpu, so I didn't use neither Azure Databricks or AWS SageMaker. While in industries, these main platforms are widely used for design and deployment.

## Amazon SageMaker

### Select role and create id
Role: DataScientist
Description: <br/>Besides process S3 data, perform experiments and produce models, also manage part of pipeline.
<br/>Try - Automate end-to-end ML workflows

#### Encryption(optional)
Make encryption customization available to use data and volume encryption keys.
Add [key](https://eu-north-1.console.aws.amazon.com/kms/home?region=eu-north-1#/kms/keys/create), more [info](https://docs.aws.amazon.com/kms/latest/developerguide/key-types.html#symm-asymm-choose).

### Configure ML activities of your role
Here are my choices:
| Permission Category                       | Description                                                                 |
|-------------------------------------------|-----------------------------------------------------------------------------|
| Run Studio Applications                   | Permissions to operate within a Studio environment. Required for domain and user-profile execution roles. |
| Manage ML Jobs                            | Permissions to manage SageMaker jobs across their lifecycles.                |
| Manage Models                             | Permissions to manage SageMaker models and Model Registry.                   |
| Manage Endpoints                          | Permissions to manage SageMaker Endpoint deployments and updates.            |
| Manage Pipelines                          | Permissions to manage SageMaker Pipelines and pipeline executions.           |
| Manage Experiments                        | Permissions to manage experiments and trials.                                |
| Search and visualize experiments          | Permissions to audit, query lineage and visualize experiments.               |
| Manage Model Monitoring                   | Permissions to manage monitoring schedules for SageMaker Model Monitor.      |

### Add additional policy
It will guide you to [Identity and Access Management (IAM) Dashboard](https://eu-north-1.console.aws.amazon.com/iamv2/home#/home) and I used Google Authenticator for Having multi-factor authentication (MFA) for the root use.
<br/>I chose these two policies that aligned with my role and activities:<br/>
```
AmazonSageMakerPipelinesIntegrations
```
```
AmazonSageMakerFullAccess
```
For the pipeline policy, I cannot added it directly when I created the role, but I managed to add the policy througn [IAM Dashboard] - [policy].

