---
title: ユーザーとデバイス アクセスの保護
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: O365 データおよびサービスへのアクセスを保護するためのランディングページ
ms.openlocfilehash: 7cddedfbb5b0b7789f370f0445be167b6d4e187d
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852741"
---
# <a name="protect-user-and-device-access"></a>ユーザーとデバイス アクセスの保護

Office 365 のデータおよびサービスへのアクセスを保護することは、サイバー攻撃を防御し、データ損失を防ぐために不可欠です。 同じ保護を、環境内の他の SaaS アプリケーション、および Azure Active Directory アプリケーションプロキシで公開されているオンプレミスアプリケーションにも適用できます。
  
## <a name="step-1-review-recommendations"></a>手順 1: 推奨事項を確認する

Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>手順 2: 管理者アカウントとアクセスを保護する
Office 365 環境を管理するために使用する管理アカウントには、昇格された特権が含まれています。 これらは、ハッカーおよびサイバー犯罪者にとって重要な目標です。 

管理者アカウントのみを使用して開始します。 管理者は、管理者ではない通常の使用に対して個別のユーザーアカウントを持っている必要があります。ジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ、管理アカウントを使用してください。

多要素認証および条件付きアクセスを使用して管理者アカウントを保護します。 詳細については、「[管理者アカウントを保護](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)する」を参照してください。 

次に、Office 365 で特権アクセス管理を構成します。 特権アクセス管理を使用すると、Office 365 の特権のある管理タスクに対して詳細なアクセス制御を行うことができます。 機密データへの継続的なアクセス、または重要な構成設定へのアクセスを備えた既存の特権のある管理者アカウントを使用する可能性がある侵害から組織を保護するのに役立ちます。

- [特権アクセス管理の概要](privileged-access-management-overview.md)
- [特権アクセス管理を構成する](privileged-access-management-configuration.md)

もう1つの主要な推奨事項は、管理作業用に構成されたワークステーションを使用することです。 これらは、管理タスクのみに使用される専用デバイスです。 「[権限](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)のあるアクセスの保護」を参照してください。

最後に、テナント内に2つ以上の緊急アクセスアカウントを作成することによって、不注意による管理アクセスが行われない影響を軽減できます。 「 [AZURE AD でエマージェンシーアクセスアカウントを管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)する」を参照してください。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>手順 3: 推奨される id とデバイスアクセスポリシーを構成する
多要素認証 (MFA) と条件付きアクセスポリシーは、侵害されたアカウントおよび権限のないアクセスを軽減するための強力なツールです。 一緒にテストされたポリシーのセットを実装することをお勧めします。 展開の手順を含む詳細については、「 [id とデバイスのアクセス構成](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations)」を参照してください。

 これらのポリシーは、次の機能を実装します。
- Mult 認証
- 条件付きアクセス
- Intune アプリの保護 (デバイス用のアプリとデータの保護)
- Intune デバイスのコンプライアンス
- Azure AD Identity Protection

Implemetning Intune デバイスコンプライアンスには、デバイスの登録が必要です。 デバイスを管理することにより、環境内のリソースへのアクセスを許可する前に、それらを正常かつ準拠していることを確認できます。 「 [Intune で管理用のデバイスを登録する](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)」を参照してください。

## <a name="step-4-configure-sharepoint-device-access-policies"></a>手順 4: SharePoint デバイスアクセスポリシーを構成する

Microsoft では、デバイスアクセス制御を使用して、機密および規制の厳しいコンテンツを持つ SharePoint サイトのコンテンツを保護することをお勧めします。 詳細については、「 [SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)」を参照してください。



    

