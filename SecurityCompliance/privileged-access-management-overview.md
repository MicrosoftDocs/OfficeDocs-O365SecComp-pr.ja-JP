---
title: Office 365 での特権アクセス管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Office 365 での特権アクセス管理の詳細については、このトピックを使用してください。
ms.openlocfilehash: 78107ceb497a546ef4d19ba33b8b72ec1406de1b
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090799"
---
# <a name="privileged-access-management-in-office-365"></a>Office 365 での特権アクセス管理

> [!IMPORTANT]
> このトピックでは、Office 365 E5 と Advanced コンプライアンス sku で現在利用可能な機能の展開と構成のガイダンスについて説明します。

特権アクセス管理を使用すると、Office 365 の特権のある管理タスクに対して詳細なアクセス制御を行うことができます。機密データへの継続的なアクセス、または重要な構成設定へのアクセスを備えた既存の特権のある管理者アカウントを使用する可能性がある侵害から組織を保護するのに役立ちます。特権アクセス管理を有効にした後、ユーザーは、範囲と時間を制限された承認ワークフローを使用して、昇格された権限のあるタスクを完了するためにジャストインタイムアクセスを要求する必要があります。これにより、機密データや重要な構成設定が危険にさらされることなく、ユーザーにとってすぐにタスクを実行できるだけの余裕が与えられます。Office 365 で特権アクセス管理を有効にすることで、組織はゼロの永続的な権限で運用し、そのような管理アクセスのために発生する脆弱性に対する防御層を提供することができます。

統合された顧客のロックボックスおよび特権アクセス管理のエンドツーエンドのワークフローの概要については、「 [Office 365 ビデオ」の「customer のロックボックスと特権アクセス管理](https://go.microsoft.com/fwlink/?linkid=2066800)」を参照してください。

## <a name="layers-of-protection"></a>保護レイヤー

特権アクセス管理は、Office 365 セキュリティアーキテクチャ内の他のデータとアクセス機能の保護を補完します。セキュリティに対する統合アプローチの一部として特権アクセス管理を有効にし、組織を保護することにより、階層型セキュリティモデルを使用して、機密情報および Office 365 の構成設定の保護を最大化することができます。次の図に示すように、特権アクセス管理を有効にすると、office 365 データのネイティブ暗号化、および office 365 サービスのロールベースのアクセス制御セキュリティモデルで提供される保護に基づいて構築できます。[Azure AD 特権 id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)と共に使用する場合、この2つの機能により、さまざまなスコープでのジャストインタイムアクセスを備えたアクセス制御が提供されます。

![Office 365 の階層型の保護](media/pam-layered-protection.png)

Office 365 での特権アクセス管理は、**タスク**レベルで定義およびスコープ設定できますが、Azure AD 特権 id 管理は、複数のタスクを実行する機能を使用して、**役割**レベルで保護を適用します。 Azure ad の特権 id 管理は、主に AD の役割および役割グループへのアクセスを管理し、Office 365 での特権アクセス管理はタスクレベルでのみ適用されます。

- **Office 365 で特権アクセス管理を有効にしていますが、既に Azure AD 特権 id 管理を使用しています。** office 365 で特権アクセス管理を追加すると、office 365 データへの特権アクセスのための、より詳細な保護および監査機能が提供されます。

- **Office 365 で既に特権アクセス管理を使用しているときに、Azure AD 特権 id 管理を有効にする:** office 365 で Azure AD 特権 id 管理を特権アクセス管理に追加すると、主にユーザーのロールまたは id によって定義された office 365 外部のデータへの特権アクセスを拡張できます。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特権アクセス管理アーキテクチャとプロセスフロー

次の各プロセスフローは、priveleged アクセスのアーキテクチャと、それが office 365 のサブストレート、office 365 監査、および Exchange 管理実行空間と対話する方法の概要を示しています。

### <a name="step-1-configuring-a-privileged-access-policy"></a>手順 1: 特権アクセスポリシーを構成する

office 365 管理センターまたは Exchange 管理 PowerShell のいずれかを使用して特権アクセスポリシーを構成する場合は、ポリシーを作成して定義し、特権アクセス機能が office 365 サブのポリシー属性を処理して、Office 365 セキュリティ/コンプライアンスセンターのアクティビティ。これで、ポリシーが有効になり、承認のための受信要求を処理する準備が整いました。

![手順 1-ポリシーの作成](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>手順 2: アクセス要求

ユーザーは、Office 365 管理センターまたは Exchange 管理 PowerShell を使用して、昇格したタスクまたは権限のあるタスクへのアクセスを要求できます。特権アクセス機能は、構成された特権アクセスポリシーに対して処理するために、office 365 サブストレートに要求を送信し、office 365 のセキュリティおよびコンプライアンスセンターのログに sctivity を記録します。

![手順 2-アクセス要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>手順 3: アクセスの承認

承認要求が生成され、保留中の要求の電子メールによって承認グループに通知されます。承認が付与されている場合、特権アクセス要求は承認として処理され、タスクを完了する準備ができています。要求が拒否された場合、タスクはブロックされ、reqeustor へのアクセスは許可されません。送信者は、電子メールメッセージを使用して、要求の承認または拒否を通知されます。

![ステップ 3-アクセス承認](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>手順 4: Access の処理

承認済みの要求の場合、タスクは Exchange 管理実行空間によって処理されます。承認は、特権アクセスポリシーに照らしてチェックされ、Office 365 のサブストレートによって処理されます。タスクのすべてのアクティビティは、Office 365 セキュリティ/コンプライアンスセンターに記録されます。

![ステップ 4-アクセス処理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a>Office 365 で特権アクセスを使用するために必要な sku
特権アクセス管理は、現在、Office 365 E5 および高度なコンプライアンス sku を使用しているお客様のみが利用できます。

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a>Exchange を超えて Office 365 ワークロードで特権アクセスを使用できるようになるのはいつですか?
この機能は、近日中に他の Office 365 ワークロードに提供する予定です。タイムラインを共有する準備ができたら、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)で利用できます。

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a>自分の組織では、30以上の特権アクセスポリシーが必要ですが、この制限は増加しますか?

現時点では、Office 365 組織あたり30の特権アクセスポリシーの現在の制限をさらに増加する予定です。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Office 365 で特権アクセスを管理するには、グローバル管理者である必要がありますか。
いいえ。 Office 365 で特権アクセスを管理するアカウントには、Exchange の役割管理の役割を割り当てる必要があります。ただし、グローバル管理者の役割にはこの役割が既定で含まれており、役割管理の役割をスタンドアロンのアカウントのアクセス許可として構成しない場合に、特権アクセスを管理するために使用できます。承認者のグループに含まれているユーザーは、グローバル管理者である必要がありません。または、要求を確認して承認するための役割管理役割を割り当てられている必要はありません。 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>お客様のロックボックスに関連する Office 365 での特権アクセス管理について
[カスタマーロックボックス](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)を使用すると、組織がサービスプロバイダー (Microsoft など) からデータにアクセスするためのレベルのアクセス制御を行うことができます。office 365 の特権アクセス管理を使用すると、すべての office 365 特権タスクに対して、組織内で詳細なアクセス制御を行うことができます。
