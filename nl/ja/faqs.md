---



copyright:

  years: 2018

lastupdated: "2018-10-30"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# FAQ
{: #iamfaq}

## {{site.data.keyword.cloud_notm}} Identity and Access Management とは何ですか?  
{: #whatisiam}

Identity and Access Management (IAM) を使用すると、プラットフォーム・サービスについてユーザーを確実に認証でき、{{site.data.keyword.cloud_notm}} プラットフォーム全体でリソースへのアクセスを制御することができます。一連の IBM Cloud サービスでは、アクセス制御に Cloud IAM を使用することができます。それらのサービスは、ユーザーが一度に複数のリソースに素早く簡単にアクセスできるように、アカウント内で複数のリソース・グループに編成されています。ご使用のアカウント内のリソースへのアクセス権限をユーザーおよびサービス ID に割り当てるために、Cloud IAM アクセス・ポリシーが使用されます。 詳しくは、[{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam/index.html#iamoverview) を参照してください。

## IAM 対応サービスとは何ですか?
{: #iam-enabled}

IAM 対応サービスはリソース・グループに含まれている必要があり、そのサービスへのアクセス権限は IAM アクセス・ポリシーを使用して付与されます。IAM 対応サービスをカタログから作成する場合は、それをリソース・グループに割り当てる必要があります。詳しくは、『[リソースとは](/docs/resources/acct_resources.html#resource)』を参照してください。

{{site.data.keyword.containerlong_notm}} は唯一の例外です。IAM でアクセス制御されますが、常にデフォルトのリソース・グループに割り当てられます。したがって、カタログから作成するときにリソース・グループを選択することはできません。また、他のどのリソース・グループにも割り当てることはできません。


## IAM と Cloud Foundry は関連していますか? 
{: #iam-cloudfoundry}

関連していません。Cloud Foundry は、組織、スペース、および Cloud Foundry の役割を使用してアクセス管理を行うオープン・ソース・プラットフォームです。IAM は、リソース・グループと IAM アクセス役割を使用して、プラットフォーム・サービスのユーザーを認証し、{{site.data.keyword.cloud_notm}} プラットフォーム全体のリソースへのアクセスを制御するための安全な方法です。

これらのアクセス管理システムはまったく異なります。IAM リソースはリソース・グループに属しており、Cloud Foundry リソースは組織およびスペースに属しています。IAM アクセス・ポリシーは、リソース・グループ内のリソースへのアクセス権限を付与するために使用されます。一方、Cloud Foundry の組織およびスペースの役割は、スペース内の Cloud Foundry リソースへのアクセス権限をユーザーに付与するために使用されます。IAM は Cloud Foundry スペース内のどのリソースに対するアクセス権限もユーザーに付与することはなく、Cloud Foundry の役割がリソース・グループ内のリソースへのアクセス権限を付与することはできません。

## 自分のアクセス権限を確認するにはどうすればいいですか? 
{: #iam-access}

**「管理」** &gt; **「アクセス (IAM)」**に移動し、「ユーザー」列で自分の名前を選択します。次に、探しているアクセス権限に応じて、以下の各種タブを開きます。

* 自分がどのアクセス・グループにいるかを判別するには、**「アクセス・グループ」**を選択します。
* IAM アクセスの場合は、**「アクセス・ポリシー」**を選択します。
* Cloud Foundry の役割の場合は、**「Cloud Foundry アクセス」**を選択します。

## リソースへのアクセス権限はどのように要求しますか? 
{: #request-access}

アカウント所有者は、アカウント内のどのリソースへのアクセス権限も更新できます。あるいは、サービスまたはサービス・インスタンスで管理者役割が割り当てられている任意のユーザーに連絡することもできます。 

## なぜリソース・グループとアクセス・グループを使用する必要があるのですか?  
{: #resource-groups}

リソース・グループは、リソースの論理コンテナーです。リソースは、作成されるとリソース・グループに割り当てられ、追加された後は移動できません。 

アクセス・グループは、一連のユーザーおよびサービス ID を単一のエンティティーに簡単に編成して、アクセス権限の割り当てを容易にするために使用されます。アクセス・グループに単一のポリシーを割り当てて、それらのアクセス権限をすべてのメンバーに付与することができます。同じアクセス権限を必要とする複数のユーザーまたはサービス ID が存在する場合は、個々のユーザーまたはサービス ID ごとに同じアクセス権限を複数回割り当てるのではなく、アクセス・グループを作成します。

リソース・グループとアクセス・グループの両方を使用することにより、限られた数のポリシーを割り当てることで、アクセス権限割り当てポリシーを簡素化できます。ユーザーおよびサービス ID の特定のグループがアクセスする必要があるすべてのリソースを単一のリソース・グループに編成し、すべてのユーザーまたはサービス ID を 1 つのアクセス・グループにグループ化してから、リソース・グループ内のすべてのリソースへのアクセス権限を付与する単一のポリシーを割り当てることができます。

## ユーザーがリソース・グループ内にリソースを作成できるようにするにはどうすればよいですか?
{: #resources}

リソース・グループ内にリソースを作成するには、ユーザーは 2 つのアクセス・ポリシーを持っている必要があります。1 つはリソース・グループ自体に割り当てられ、もう 1 つはグループ内のリソースに割り当てられます。リソース・グループ自体へのアクセス権限は、単にリソースを編成するコンテナーへのアクセス権限です。このタイプのポリシーでは、ユーザーはグループを表示または編集したり、グループのアクセス権限を管理したりできますが、グループ内のリソースを操作することはできません。リソース・グループ内のサービスへのアクセス権限により、ユーザーはサービス・インスタンスを処理できます。つまり、ユーザーはサービス・インスタンスを作成できます。

したがって、ユーザーは少なくとも以下のアクセス権限を持っている必要があります。

* リソース・グループ自体に対するビューアー以上の役割
* リソース・グループ内の特定のサービスまたはすべてのサービスに対するエディター以上の役割


## 他のユーザーにアクセス権限を付与するには、どのようなアクセス権限が必要ですか? 
{: #user-access}

ユーザーにアクセス権限を割り当てるサービスまたはリソースに対する管理者役割を持っている必要があります。アカウント内のすべてのサービスまたはリソースへのアクセス権限を割り当てる場合は、管理者役割と共に、 すべての ID およびアクセス対応サービスに対するポリシーが必要です。 

## リソース・グループを管理するためのアクセス権限の付与とリソース・グループ内のリソースへのアクセス権限の付与との違いは何ですか?
{: #providing-access}

リソース・グループを管理するアクセス権限がある場合、割り当てられた役割に応じて、リソース・グループ自体の表示、名前の編集、およびアクセスの管理を行うことができます。リソース・グループ自体へのアクセス権限では、ユーザーはグループ内のリソースにはアクセスできません。

リソース・グループ内のリソースへのアクセス権限がある場合は、割り当てられた役割に応じて、インスタンスを編集、削除、および作成したり、リソース・グループ内の指定されたサービスに対するすべての管理アクションを実行したりできます。 

アカウント管理サービスのプラットフォーム管理の役割とアクションの例については、[プラットフォームの役割の表](/docs/iam/users_roles.html#platformrolestable2)を参照してください。

## ユーザーの削除は誰が行えますか? 
{: #remove-users}

アカウント所有者は、いつでもユーザーを追加および削除できます。また、以下の 2 つのポリシー・タイプのいずれかを持つユーザーもユーザーを削除できます。

* すべてのアカウント管理サービスのエディターまたは管理者
* ユーザー管理アカウント管理サービスのエディターまたは管理者

## 多要素認証をオンにするにはどうすればいいですか? 
{: #multi-factor}

**「管理」** &gt; **「アクセス (IAM)」**に移動して、**「設定」**を選択します。
**「多要素認証 (Multi-factor authentication)」**を選択し、**「変更の適用」**をクリックします。 詳しくは、[多要素認証の有効化](/docs/iam/mfa.html#enablemfa)を参照してください。

## サービスの役割とプラットフォームの役割の違いは何ですか?  
{: #service-platform-roles}

サービスの役割とプラットフォームの役割は、2 つの異なるタイプの役割です。 

* プラットフォームの役割は、インスタンスの作成、インスタンスのバインド、サービスへのユーザーのアクセス権限の管理など、アカウント内でのサービスの操作方法です。プラットフォーム・サービスの場合、これらの役割により、ユーザーは例えばリソース・グループを作成し、サービス ID を管理できます。プラットフォームの役割は、管理者、エディター、オペレーター、およびビューアーです。 

* サービスの役割は、サービスに対してアクションを実行する能力を定義し、API 呼び出しの実行や UI へのアクセスなどのすべてのサービスに固有です。サービスの役割は、マネージャー、ライター、およびリーダーです。これらの役割の適用方法について詳しくは、特定のサービスの資料を参照してください。

## リソース・グループと Cloud Foundry の組織およびスペースの違いは何ですか?
{: #groups-organizations}

{{site.data.keyword.Bluemix_notm}} を開始したときには、アクセス制御のためのオープン・ソース・プラットフォーム・サービスと、Cloud Foundry と呼ばれるリソースの編成が、リソースへのアクセスを編成および制御するための単一の方法でした。{{site.data.keyword.Bluemix_notm}} の拡張にしたがって、すべてのタイプのサービスおよびリソースで使用できる新しい方法が必要になりました。現在は、さまざまなタイプのリソースをグループ化および編成するためにリソース・グループが使用されるようになり、サービスおよびリソースへのアクセス権限を一貫して制御するために IAM が使用されるようになりました。多くのサービスが既にリソース・グループと IAM の使用を採用しており、さらに多くのサービスが、時間の経過とともに、リソース編成およびアクセス管理のためにこの新しい方法に移行するでしょう。

リソース・グループと Cloud Foundry の組織およびスペースの主な違いは、アクセス制御とアカウント・リソース編成です。リソース・グループは、IAM 対応サービスを、IAM ポリシーを使用してアクセス制御されるアカウントに編成します。組織とスペースは、アクセス制御に Cloud Foundry の役割を使用して管理され、Cloud Foundry のリソースはスペースに割り当てられます。組織およびスペースは、Cloud Foundry レルム内のみのリソースへのアクセスを編成および制御するために使用できます。一方、リソース・グループと IAM は、{{site.data.keyword.Bluemix_notm}} 全体の複数のタイプのリソースに使用できます。

## ユーザーをアカウント管理者として割り当てるにはどうすればいいですか?  
{: #account-administrator}

IAM ポリシーを使用してアカウント管理者の役割を委任するには、以下の 2 つのポリシーを作成する必要があります。

* すべての ID およびアクセス対応サービスの管理者。これにより、ユーザーはサービス・インスタンスを作成し、アカウント内のすべてのリソースへのアクセス権限をユーザーに割り当てることができます。
* すべてのアカウント管理サービスの管理者。これにより、ユーザーは、ユーザーの招待と削除、アクセス・グループの管理、サービス ID の管理、プライベート・カタログ・オファリングの管理、および請求処理と使用状況の追跡などのタスクを実行できます。