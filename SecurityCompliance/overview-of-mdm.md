---
title: Office 365 でモバイル デバイス管理 (MDM) の概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365M_MDMConfigDomains
- O365E_MDMConfigDomains
- ms.o365.cc.DevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: faa7d8e5-645d-4d59-839c-c8d4c1869e4a
description: 管理し、Office 365 でモバイル デバイス管理を使用して、Office 365 の組織に接続しているときにモバイル デバイスをセキュリティで保護できます。モバイル デバイスなどのスマート フォンやタブレットの仕事の電子メール、予定表、連絡先にアクセスするために使用して、ドキュメントは、従業員が、作業をどこからでも、いつでも完了を取得することを確認する大きな役割を果たします。ユーザーがデバイスを使用すると、組織の情報の保護に役立てることが重要です。デバイスのセキュリティ ポリシーとアクセス ルールを設定するのには、紛失や盗難にしている場合は、モバイル デバイスをワイプするのには、Office 365 の MDM を使用できます。
ms.openlocfilehash: f06cef11b68ee0673f13c54738f07f4556495fdd
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272492"
---
# <a name="overview-of-mobile-device-management-mdm-for-office-365"></a>Office 365 でモバイル デバイス管理 (MDM) の概要

管理し、Office 365 でモバイル デバイス管理を使用して、Office 365 の組織に接続しているときにモバイル デバイスをセキュリティで保護できます。モバイル デバイスなどのスマート フォンやタブレットの仕事の電子メール、予定表、連絡先にアクセスするために使用して、ドキュメントは、従業員が、作業をどこからでも、いつでも完了を取得することを確認する大きな役割を果たします。ユーザーがデバイスを使用すると、組織の情報の保護に役立てることが重要です。デバイスのセキュリティ ポリシーとアクセス ルールを設定するのには、紛失や盗難にしている場合は、モバイル デバイスをワイプするのには、Office 365 の MDM を使用できます。
  
![MDM Android の電話で](media/69b9a9f6-13ac-4e36-99ca-95e82e0375aa.png)
  
## <a name="what-types-of-devices-can-you-manage"></a>管理できるデバイスの種類

Office 365 の MDM を使用するにはさまざまな種類の Windows Phone、Android、iPhone、iPad などのモバイル デバイスを管理します。人ごとに、組織内のユーザーが使用するモバイル デバイスを管理するには、適用可能な Office 365 ライセンスを取得して必要があり、そのデバイスは、Office 365 の MDM に登録する必要があります。 
  
デバイスの種類ごとにサポートする Office 365 の MDM を表示するには、[機能のモバイル デバイスの管理](capabilities-of-mobile-device-management.md)を参照してください。
  
## <a name="setup-steps-for-mdm"></a>MDM のセットアップの手順を実行します。

グローバル管理者が Office 365 をアクティブにし、Office 365 の MDM を設定するには、次の手順を完了する必要があります。[Office 365 の MDM の設定](set-up-mobile-device-management.md)の詳細な手順を参照してください」の指示に従います。簡単な概要を以下に示します。 
  
> 手順 1: は、次の[設定をモバイル デバイス管理 (MDM) Office 365 で](set-up-mobile-device-management.md)の手順に従って、Office 365 の MDM を有効にします。
    
> 手順 2: MDM に対して設定によって、Office 365 などの iOS デバイスを管理するのには、Apn の証明書を作成し、Windows の電話をサポートするドメインのドメイン ネーム システム (DNS) レコードを追加します。
    
> 手順 3: は、デバイス ポリシーを作成し、ユーザーのグループに適用します。これを行うと、ユーザーは、[登録メッセージをデバイス上](enroll-your-mobile-device.md)に表示されます。デバイスに設定したポリシーによって制約されることにより、登録が完了したら、ときに。
    
    ![Creating an MDN device policy under Device security policies](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
## <a name="device-management-tasks"></a>デバイス管理タスク

Office 365 のセットアップの MDM があれば、ユーザーはそのデバイスを登録した後、デバイスの管理へのアクセスをブロックしたりが必要な場合に、デバイスをワイプできます。などの[一般的なデバイス管理タスク](manage-devices-in-mdm.md)のタスクを完了する場所について説明します。
  
## <a name="other-ways-to-manage-devices-and-apps"></a>デバイスとアプリケーションを管理する別の方法

必要がある場合は、Office 365 の MDM よりもより多くの機能が含まれています、チェック アウトこの[mdm サーバーと Microsoft Intune の機能の比較](choose-between-mdm-and-intune.md)Intune サブスクリプションは、組織のニーズを満たすかどうかを参照してください。 
  
モバイル アプリケーション管理 (MAM) だけが必要な場合、人が自分のデバイス上の作業プロジェクトを更新 Intune は登録して、デバイスを管理するだけでなく他のオプションを提供します。Intune サブスクリプションを使用すると、他のユーザーのデバイスは、Intune に登録されていない場合でも、Azure ポータルを使用して、MAM のポリシーを設定できます。[MAM のポリシーを使用するアプリケーション データを保護](https://go.microsoft.com/fwlink/?LinkId=825439)を参照してください。 
  
## <a name="see-also"></a>関連項目

[MDM によって管理されているデバイスの詳細情報を取得します。](get-details-about-mdm-managed-devices.md)

[Office 365 の MDM を設定します。](set-up-mobile-device-management.md)
  
[MDM でのモバイル デバイスを登録します。](enroll-your-mobile-device.md)
  
[MDM に登録されているデバイスを管理します。](manage-devices-in-mdm.md)

