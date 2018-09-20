---
title: 特権にアクセス、Office 365 の管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: 権限に関する詳細については、このトピックを使用して Office 365 の管理のアクセス
ms.openlocfilehash: 063d291005ec40c21e55188e4ee7c6c8ed6594e8
ms.sourcegitcommit: d31904e81f81d0fba75309a2bc8bbfb05565a0b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2018
ms.locfileid: "24055262"
---
# <a name="privileged-access-management-in-office-365"></a>特権にアクセス、Office 365 の管理

> [!IMPORTANT]
> このトピックでは、Office 365 の E5 と高度なコンプライアンスの Sku でのみ現在利用できる機能の展開と構成のガイダンスについて説明します。

管理者アクセス権を Office 365 の管理により、きめ細かなアクセス特権の管理タスクを制御します。 機密性の高いデータへのアクセスを位置または重要な構成設定へのアクセス権を持つ既存の権限を持つ管理者アカウントを使用するための侵害から組織を保護するために役立ちます。アクセス権限の管理を有効にすると、ユーザーは、承認のワークフローは、高度なスコープ設定と期限付きでの管理者特権、特権のあるタスクを完了する、ジャスト ・ イン ・ タイムのアクセス権を要求する必要があります。これにより、ユーザーだけからだけアクセスできる機密データや重要な構成設定の露出を危険にさらさず、当面のタスクを実行します。Office 365 にアクセス権限の管理を有効にすると、ゼロ位置の特権で実行され、このような地位の管理アクセスのために起因する脆弱性に対する防御層を提供する組織が有効になります。 

## <a name="layers-of-protection"></a>レイヤーの保護

管理者アクセス権の管理は、Office 365 のセキュリティ ・ アーキテクチャ内で他のデータとアクセスの機能保護を補完するものです。セキュリティに統合されたアプローチの一部としてのアクセス権限の管理を有効にすると、組織を保護、機密性の高い情報と Office 365 の構成設定の保護を最大化する階層型のセキュリティ モデルを使用できます。特権を有効にする、次の図に示すように Office 365 のデータのネイティブの暗号化と Office 365 サービスの役割に基づいたアクセス制御のセキュリティ モデルで提供される保護のアクセス管理の支援を構築します。[Azure AD 管理者の Id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)と連携して使用する場合、これら 2 つの機能は、さまざまなスコープでジャスト ・ イン ・ タイムのアクセスとアクセス制御を提供します。

![Office 365 の階層型の保護](media/pam-layered-protection.jpg)

管理者アクセス権を Office 365 の管理を定義し、Azure AD 管理者の Id 管理が複数のタスクを実行する機能を持つ**ロール**レベルでの保護を適用中に、**タスク**レベルのスコープです。 Azure AD 特権 Id 管理主に AD の役割と役割グループのアクセスを管理する、タスク レベルでのみ Office 365 の管理が適用される権限にアクセスできます。

- **特権を有効にする既に Azure AD 管理者の Id 管理を使用しているときに Office 365 の管理のアクセス:** Office 365 にアクセス権限の管理を追加する別の Office 365 のデータへのアクセス権限の保護と監査の機能の細分化された層を提供します。

- **を既に使用しているときに、Azure AD の特権の有効にすると Id 管理特権を Office 365 にアクセス管理:** Azure AD 管理者の Id 管理を追加する特権を Office 365 でのアクセス管理は、Office 365 ユーザーのロールまたは id によって主に定義されている外部データへのアクセス権限を拡張できます。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>アクセス権限管理のアーキテクチャとプロセスのフロー

次のプロセス ・ フローの各権限の少ないアクセスし、Office 365 の基板、Office 365 は、次の監査、および Exchange の管理の実行空間との対話方法のアーキテクチャの概要を説明します。

### <a name="step-1-configuring-a-privileged-access-policy"></a>手順 1: 管理者のアクセス ポリシーの構成

特権アクセス機能は、Office 365 の基板とログのポリシーの属性を処理および作成し、ポリシーを定義する、Office 365 管理者センターまたは Exchange 管理の PowerShell を使用してアクセス権限ポリシーを構成するとき、Office 365 のセキュリティとコンプライアンス センターでの活動です。ポリシーが有効になりますし、承認のための着信要求を処理する準備ができています。

![ステップ 1 - ポリシーの作成](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>手順 2: アクセス権の要求

Office 365 管理センターまたは Exchange 管理 PowerShell を使用すると、ユーザーは管理者特権または管理者のタスクへのアクセスを要求できます。特権アクセス機能は、Office 365 基板に対して構成されている特権のアクセス ポリシーの処理のために要求を送信し、Office 365 のセキュリティでは、sctivity を記録し、コンプライアンス センターをログに記録します。

![ステップ 2 - アクセス権の要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>手順 3: アクセスの承認

承認要求が生成され、承認グループに保留中の要求の電子メールで通知されます。承認が付与される場合は、承認とアクセス権限要求を処理し、タスクを完了する準備ができました。要求が拒否された場合、タスクは、ブロックと、reqeustor へのアクセスは許可されません。要求者の要求の承認または拒否メッセージを電子メール経由で通知されます。

![ステップ 3 - アクセスの承認](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>手順 4: アクセスの処理

承認された要求は、Exchange の管理の実行空間で、タスクが処理されます。承認はアクセス権限ポリシーに照らしてチェックや、Office 365 の基板で処理します。Office 365 のセキュリティとコンプライアンスのセンターでは、タスクのすべてのアクティビティが記録されます。

![ステップ 4 - アクセスの処理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a>Office 365 にアクセス権限を使用する必要があるどのような Sku をしますか。
管理者アクセス権を Office 365 の管理は、現在のみ E5 と高度なコンプライアンスの Sku をご利用できます。

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a>特権を持つアクセス可能になります Exchange 以外の Office 365 の作業負荷でしょうか。
その他の Office 365 のワークロードでは、この機能をすぐに提供する予定です。タイムラインを共有する準備ができました、Office 365 のロードマップを使用可能ながあります。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Office 365 の管理者のアクセスを管理するためのグローバル管理者である必要がありますか。
Office 365 の管理者のアクセスを管理することができるグローバル管理者特権が必要です。承認者のグループに含まれるユーザーに確認および承認の要求をグローバル管理者である必要はありません。 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>ロック ボックスの顧客に関連する Office 365 にアクセス権限の管理ですか。
[お客様のロック ボックス](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)は、組織では、サービス プロバイダー、つまり Microsoft によってデータにアクセスするためのアクセス制御のレベルを使用できます。管理者アクセス権をすべての Office 365 の管理者権限を持って作業を組織内で、きめ細かなアクセス制御により、Office 365 の管理。