---
title: Office 365 での特権アクセス管理
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Office 365 での特権アクセス管理の詳細については、このトピックを使用してください。
ms.openlocfilehash: 7547568d6ea2a13de5391d5a827df2921833838c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157329"
---
# <a name="privileged-access-management-in-office-365"></a>Office 365 での特権アクセス管理

> [!IMPORTANT]
> このトピックでは、Office 365 E5 と Advanced コンプライアンス Sku で現在利用可能な機能の展開と構成のガイダンスについて説明します。

特権アクセス管理を使用すると、Office 365 の特権のある管理タスクに対して詳細なアクセス制御を行うことができます。 これにより、既存の特権のある管理者アカウントを使用して機密性の高いデータにアクセスしたり、重要な構成設定にアクセスしたりすることにより、組織を侵害から保護することができます。 特権アクセス管理では、ユーザーはジャストインタイムアクセスを要求して、高度に範囲指定された、時間の制限のある承認ワークフローを通じて、昇格された権限のあるタスクを完了させる必要があります。 これにより、機密データや重要な構成設定が危険にさらされることなく、ユーザーにとってすぐにタスクを実行できるだけの余裕が与えられます。 Office 365 で特権アクセス管理を有効にすることで、組織はゼロに立った権限で運用し、管理アクセスの脆弱性に対する防御層を提供できます。

統合された顧客ロックボックスおよび特権アクセス管理ワークフローの簡単な概要については、「 [Office 365 ビデオ」の「customer のロックボックスと特権アクセス管理](https://go.microsoft.com/fwlink/?linkid=2066800)」を参照してください。

## <a name="layers-of-protection"></a>保護レイヤー

特権アクセス管理は、Office 365 セキュリティアーキテクチャ内の他のデータとアクセス機能の保護を補完します。 セキュリティの統合および階層化手法の一部として特権アクセス管理を含めることで、機密情報および Office 365 の構成設定の保護を最大化するセキュリティモデルが提供されます。 図に示されているように、特権アクセス管理は Office 365 データのネイティブ暗号化、および Office 365 サービスの役割ベースのアクセス制御セキュリティモデルで提供される保護に基づいて構築されています。 [AZURE AD 特権 Id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)と共に使用する場合、この2つの機能により、さまざまなスコープでジャストインタイムのアクセスを使用してアクセス制御を行うことができます。

![Office 365 の階層型の保護](media/pam-layered-protection.png)

Office 365 での特権アクセス管理は、**タスク**レベルで定義され、スコープが設定されていますが、Azure AD Privileged Identity management は、複数のタスクを実行する機能を使用して、**役割**レベルで保護を適用します。 Azure AD 特権 Id 管理は、主に AD の役割および役割グループへのアクセスを管理しますが、Office 365 の特権アクセス管理はタスクレベルでのみ適用されます。

- **Office 365 で特権アクセス管理を有効にしていますが、既に AZURE AD 特権 Id 管理を使用しています。** Office 365 で特権アクセス管理を追加すると、Office 365 データへの特権アクセスのための、より詳細な保護および監査機能が提供されます。

- **Office 365 で既に特権アクセス管理を使用しているときに、AZURE AD 特権 Id 管理を有効にする:** Office 365 で Azure AD 特権 Id 管理を特権アクセス管理に追加すると、主にユーザーロールまたは id によって定義された Office 365 外部のデータへの特権アクセスを拡張できます。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特権アクセス管理アーキテクチャとプロセスフロー

次の各プロセスフローは、特権アクセスのアーキテクチャと、それが Office 365 のサブストレート、Office 365 監査、および Exchange 管理実行空間と対話する方法の概要を示しています。

### <a name="step-1-configure-a-privileged-access-policy"></a>手順 1: 特権アクセスポリシーを構成する

[Microsoft 365 管理センター](https://admin.microsoft.com)または Exchange 管理 PowerShell を使用して、特権アクセスポリシーを構成する場合は、ポリシーおよび特権アクセス機能のプロセスと、Office 365 のサブポリシーの属性を定義します。 アクティビティは、Office 365 セキュリティ/コンプライアンスセンターに記録されます。 これで、ポリシーが有効になり、承認のための受信要求を処理する準備が整いました。

![手順 1: ポリシーの作成](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>手順 2: アクセス要求

[Microsoft 365 管理センター](https://admin.microsoft.com)または Exchange 管理 PowerShell を使用して、ユーザーは昇格されたタスクまたは権限のあるタスクへのアクセスを要求できます。 特権アクセス機能は、構成された特権アクセスポリシーに対して処理するために、Office 365 サブストレートに要求を送信し、Office 365 セキュリティおよびコンプライアンスセンターのログにアクティビティを記録します。

![手順 2: アクセス要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>手順 3: アクセスの承認

承認要求が生成され、保留中の要求通知が承認者に電子メールで送信されます。 承認された場合、特権アクセス要求は承認として処理され、タスクが完了できる状態になります。 拒否された場合、タスクはブロックされ、リクエスターへのアクセスは許可されません。 送信者は、電子メールメッセージを使用して、要求の承認または拒否を通知されます。

![手順 3: アクセスの承認](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>手順 4: Access の処理

承認済みの要求の場合、タスクは Exchange 管理実行空間によって処理されます。 承認は、特権アクセスポリシーに照らしてチェックされ、Office 365 のサブストレートによって処理されます。 タスクのすべてのアクティビティは、Office 365 セキュリティ/コンプライアンスセンターに記録されます。

![手順 4: Access の処理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Office 365 では、どの Sku で特権アクセスを使用できますか?
特権アクセス管理は、Office 365 E5 および高度なコンプライアンス Sku を使用しているお客様が利用できます。

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>特権アクセスが Exchange を超えて Office 365 ワークロードをサポートするのはいつですか?
権限のあるアクセス管理は、近日中に他の Office 365 ワークロードで利用可能になります。 詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>自分の組織では30以上の特権アクセスポリシーが必要ですが、この制限は増加しますか?
はい。 Office 365 組織あたりの特権アクセスポリシーの現在の制限は、機能ロードマップにあります。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Office 365 で特権アクセスを管理するには、グローバル管理者である必要がありますか。
いいえ。 Office 365 で特権アクセスを管理するアカウントには、Exchange 役割管理役割が割り当てられている必要があります。 役割管理役割をスタンドアロンのアカウントアクセス許可として構成しない場合は、グローバル管理者の役割に既定でこの役割が含まれ、特権アクセスを管理できます。 承認者のグループに含まれているユーザーは、グローバル管理者である必要がありません。または、要求を確認して承認するための役割管理役割が割り当てられている必要はありません。

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>お客様のロックボックスに関連する Office 365 での特権アクセス管理について
[カスタマーロックボックス](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)Microsoft がデータにアクセスするときに、組織に対してレベルのアクセス制御を許可します。 Office 365 の特権アクセス管理を使用すると、すべての Office 365 特権タスクに対して、組織内で詳細なアクセス制御を行うことができます。

## <a name="ready-to-get-started"></a>始める準備はいいですか。

[権限のあるアクセス管理の組織の構成を](privileged-access-management-configuration.md)開始します。

## <a name="learn-more"></a>詳細情報

[対話型ガイド: 特権アクセス管理を使用して管理者タスクを監視および制御する](https://content.cloudguides.com/en-us/guides/Privileged%20Access%20Management)