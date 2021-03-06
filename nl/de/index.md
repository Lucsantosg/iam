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

## Was ist Cloud IAM?

{{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) ermöglicht Ihnen die sichere Authentifizierung von Benutzern für Plattformservices und die einheitliche Steuerung des Zugriffs auf Ressourcen innerhalb der {{site.data.keyword.Bluemix_notm}}-Plattform. Ein Set von {{site.data.keyword.Bluemix_notm}}-Services sind für die Nutzung von Cloud IAM zur Zugriffssteuerung aktiviert und in [Ressourcengruppen](/docs/account/resourcegroups.html) innerhalb Ihres Kontos organisiert. Auf diese Weise erhalten Benutzer den schnellen und einfachen Zugriff auf mehrere Ressourcen gleichzeitig. Die Cloud IAM-Zugriffsrichtlinien werden verwendet, um Benutzern und Service-IDs die Zugriffsberechtigungen für die Ressourcen innerhalb Ihres Kontos zuzuweisen. Sie können eine Gruppe von Benutzern und Service-IDs in eine [Zugriffsgruppe](/docs/iam/groups.html) gruppieren, um allen Entitäten in der Gruppe ohne großen Aufwand einen Zugriff derselben Ebene zu ermöglichen.

Eine Richtlinie weist ein Subjekt (das ein Benutzer, eine [Service-ID](/docs/iam/serviceid.html#serviceids) oder Zugriffsgruppe sein kann) einer oder mehreren Rollen zu, zusammen mit einer Kombination von Attributen, die den Geltungsbereich für die Zugriffsberechtigung auf ein Ziel definieren. Die Richtlinie kann Zugriff auf einen einzelnen Service bis hinunter zur Instanzebene erteilen, auf ein Set von Ressourcen, die in einer Ressourcengruppe organisiert sind, oder auf Kontoverwaltungsservices. Abhängig von den [IAM-Rollen](/docs/iam/users_roles.html#iamusermanrol), die Sie zuweisen, werden dem Subjekt unterschiedliche Zugriffsebenen für die Durchführung von Kontoverwaltungstasks, die Arbeit mit Serviceinstanzen, den Zugriff auf einen Service über die Benutzerschnittstelle oder die Ausführung von API-Aufrufen erteilt.

![IAM zur Zugriffssteuerung in einem Konto](images/iam-diagram.svg "Informationen zum Zugriffsmanagement in einem Konto mit IAM")

Für Services, die die Erstellung von Cloud IAM-Richtlinien für die Verwaltung von Zugriffsberechtigungen nicht unterstützen, können Sie den [Cloud Foundry-Zugriff](/docs/iam/cfaccess.html#cfaccess) verwenden.


## Welche Funktionen bietet Cloud IAM?
{: #features}

<dl>
<dt>Benutzermanagement</dt>
<dd>Das einheitliche Benutzermanagement ermöglicht Ihnen das Hinzufügen und Löschen von Benutzern in einem Konto sowohl für Plattform- als auch für Infrastrukturservices. Sie können eine als Zugriffsgruppe bezeichnete Gruppe von Benutzern erstellen und so die Zuweisung von gleichzeitigem Zugriff auf mehrere Benutzer beschleunigen und vereinfachen.</dd>
<dt>Differenzierte Zugriffssteuerung</dt>
<dd>Der Zugriff für Benutzer, Service-IDs und Zugriffsgruppen wird durch eine Richtlinie definiert. Innerhalb der Richtlinie kann der Geltungsbereich des Zugriffs für einen Benutzer, eine Service-ID oder eine Zugriffsgruppe einem Set von Ressourcen in einer Ressourcengruppe, einer einzelnen Ressource oder Kontoverwaltungsservices zugewiesen werden. Nachdem der Geltungsbereich festgelegt wurde, können Sie definieren, welche Aktionen für das Subjekt der Richtlinie zulässig sind, indem Sie die Zugriffsrollen auswählen. Rollen bieten eine Möglichkeit zur Anpassung der für das Richtliniensubjekt erteilten Zugriffsebene, um Aktionen für das Ziel der Richtlinie auszuführen, seien es Plattformmanagement-Tasks innerhalb des Kontos, der Zugriff auf die Benutzerschnittstelle eines Service oder die Ausführung von API-Aufrufen.</dd>
<dt>API-Schlüssel für Benutzerauthentifizierung</dt>
<dd>Es können mehrere API-Schlüssel für einen Benutzer erstellt werden, um Schlüsselrotationsszenarios zu unterstützen, und der gleiche Schlüssel kann für den Zugriff auf mehrere Services verwendet werden. Die API-Schlüssel von Plattformbenutzern bieten Benutzern, die eine Zwei-Faktor-Authentifizierung oder eine eingebundene ID verwenden, die Möglichkeit, die Authentifizierung über die Befehlszeile zu automatisieren.</dd>
<dt>Service-IDs</dt>
<dd>Eine Service-ID dient (ähnlich wie eine Benutzer-ID, die einen Benutzer identifiziert) zur Identifikation eines Service oder einer Anwendung. Es existieren IDs, die von Anwendungen zur Authentifizierung bei einem {{site.data.keyword.Bluemix_notm}}-Service verwendet werden können. Jeder Service-ID können Richtlinien zugewiesen werden, um die Zugriffsebene zu steuern, die von einer Anwendung mit der Service-ID zugelassen wird. Zur Aktivierung der Authentifizierung kann ein API-Schlüssel erstellt werden.</dd>
</dl>


## Wie nutze ich Cloud IAM?

Sie können auf Cloud IAM zugreifen und Cloud IAM nutzen, indem Sie auf die Identity and Access Management-Benutzerschnittstelle oder die Befehlszeilenschnittstelle für {{site.data.keyword.Bluemix_notm}} zugreifen.

Um auf Cloud IAM über die Benutzerschnittstelle zuzugreifen, rufen Sie **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** auf.

Um auf Cloud IAM über die CLI zuzugreifen, machen Sie sich mit den Informationen in [Befehle zur Verwaltung von API-Schlüsseln und Richtlinien](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_commands_iam) vertraut.
