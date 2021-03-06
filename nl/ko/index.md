---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} Identity and Access Management
{: #iamoverview}

## Cloud IAM 개념

{{site.data.keyword.Bluemix_notm}} Identity and Access Management(IAM)를 사용하면 두 플랫폼 서비스 모두에 대해 안전하게 사용자를 인증하고 {{site.data.keyword.Bluemix_notm}} 플랫폼에서 일관되게 리소스에 대한 액세스를 제어할 수 있습니다. {{site.data.keyword.Bluemix_notm}} 서비스 세트는 액세스 제어를 위해 Cloud IAM을 사용할 수 있으며, 한 번에 둘 이상의 리소스에 대한 빠르고 손쉬운 액세스를 사용자에게 제공할 수 있도록 계정 내에서 [리소스 그룹](/docs/account/resourcegroups.html)으로 구성되어 있습니다. Cloud IAM 액세스 정책을 사용하면 계정 내에서 리소스에 대한 사용자 및 서비스 ID 액세스를 지정할 수 있습니다. 사용자 및 서비스 ID 세트를 [액세스 그룹](/docs/iam/groups.html)으로 그룹화하여 그룹 내 모든 엔티티에 동일한 레벨 액세스를 쉽게 제공할 수 있습니다.

정책은 대상에 대한 액세스 범위를 정의하는 속성의 조합으로 하나 이상의 역할을 사용자 또는 [서비스 ID](/docs/iam/serviceid.html#serviceids) 또는 액세스 그룹에 해당하는 주체(Subject)에 지정합니다. 정책은 인스턴스 레벨까지 단일 서비스에 대한 액세스를 제공하거나, 리소스 그룹의 함께 구성된 리소스 세트 또는 계정 관리 서비스에 적용될 수 있습니다. 지정된 [IAM 역할](/docs/iam/users_roles.html#iamusermanrol)에 따라, 주체(Subject)에는 API 호출을 완료하거나 UI를 사용하여 서비스에 액세스하거나 서비스 인스턴스에 대한 작업을 수행하거나 계정 관리 태스크를 완료하기 위한 다양한 레벨의 액세스가 허용됩니다.

![계정의 액세스 제어를 위한 IAM](images/iam-diagram.svg "IAM을 사용하여 계정에서 액세스를 관리하는 방법")

액세스 관리를 위한 Cloud IAM 정책 작성을 지원하지 않는 서비스의 경우에는 [Cloud Foundry 액세스](/docs/iam/cfaccess.html#cfaccess)를 사용할 수 있습니다.


## Cloud IAM에서 제공하는 기능
{: #features}

<dl>
<dt>사용자 관리</dt>
<dd>통합 사용자 관리를 사용하면 플랫폼 및 인프라 서비스 모두에 대해 계정의 사용자를 추가하고 삭제할 수 있습니다. 또한 한 번에 둘 이상의 사용자에 대한 액세스 지정을 빠르고 쉽게 처리할 수 있도록 액세스 그룹이라고 하는 사용자 그룹을 작성할 수 있습니다.</dd>
<dt>세분화된 액세스 제어</dt>
<dd>사용자, 서비스 ID, 액세스 그룹에 대한 액세스는 정책으로 정의됩니다. 정책 내에서 사용자, 서비스 ID 또는 액세스 그룹에 대한 액세스 범위는 리소스 그룹, 단일 리소스 또는 계정 관리 서비스에서 리소스 세트에 지정할 수 있습니다. 범위가 설정된 후에는 액세스 역할을 선택하여 정책의 제목에서 허용하는 조치를 정의할 수 있습니다. 역할은 계정 내에서 플랫폼 관리 태스크인지, 서비스의 UI에 액세스하는지, API 호출을 완료하는 것인지 여부에 따라 대상 정책에서 조치를 수행하기 위해 정책 주체(Subject)에 부여되는 액세스 레벨을 조정하는 방법을 제공합니다.</dd>
<dt>사용자 인증을 위한 API 키</dt>
<dd>사용자가 키 회전 시나리오를 지원할 수 있도록 다중 API 키의 작성이 가능하며, 동일한 키를 다중 서비스를 액세스하는 데 사용할 수 있습니다. 플랫폼 사용자 API 키를 사용하여 2단계 인증이나 연합 ID를 사용하는 사용자는 명령행에서 인증을 자동화할 수 있습니다.</dd>
<dt>서비스 ID</dt>
<dd>서비스 ID는 사용자 ID가 사용자를 식별하는 방법과 비슷하게 서비스 또는 애플리케이션을 식별합니다. {{site.data.keyword.Bluemix_notm}} 서비스를 인증하기 위해 애플리케이션에서 사용할 수 있는 ID가 있습니다. 정책은 서비스 ID를 사용하여 애플리케이션에서 허용하는 액세스 레벨을 제어하기 위해 각각의 서비스 ID에 지정될 수 있으며, 인증을 사용하기 위해 API 키를 작성할 수 있습니다.</dd>
</dl>


## Cloud IAM 사용법

{{site.data.keyword.Bluemix_notm}}용 ID 및 액세스 UI 또는 CLI를 통해 Cloud IAM에 액세스하고 이를 사용할 수 있습니다.

UI를 사용하여 Cloud IAM에 액세스하려면 **관리** &gt; **보안** &gt; **ID 및 액세스**로 이동하십시오.

CLI를 사용하여 Cloud IAM에 액세스하려면 [API 키 및 정책 관리를 위한 명령](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_commands_iam)을 참조하십시오.
