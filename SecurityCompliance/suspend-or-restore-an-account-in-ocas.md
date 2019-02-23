---
title: Office 365 Cloud App Security でユーザー アカウントを停止または復元する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Office 365 Cloud App Security では、ユーザーアカウントの中断または停止解除を行うことができるガバナンスアクションがあります。 '
ms.openlocfilehash: 3650a5304af0440dc537610994c4bd827f599989
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215097"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a>Office 365 Cloud App Security でユーザー アカウントを停止または復元する

|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |[展開を開始する](turn-on-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
Office 365 用の組織のユーザーアカウントのいずれかが侵害されたという警告が表示されたとします。または、ユーザーアカウントで問題が発生したことを示す通知を受信したとします。Office 365 Cloud App Security では、受信した通知を調査した後、ユーザーアカウントを中断してから復元することができます。
  
> [!NOTE]
> office 365 Cloud App Security は office 365 Enterprise E5 で利用できます。組織で別の office 365 Enterprise サブスクリプションを使用している場合、office 365 Cloud App Security をアドオンとして購入することができます。(全体管理者として、Office 365 管理センターで、[**課金** \>の**サブスクリプションの追加**] を選択します。)詳細については、「office 365 プラットフォームサービスの説明」を参照してください[。 office 365 セキュリティ&amp;コンプライアンスセンター](https://technet.microsoft.com/en-us/library/dn933793.aspx)で、 [office 365 for business のアドオンを購入または編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)します。 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a>Office 365 Cloud App Security でユーザーアカウントを中断するには

ユーザーアカウントを中断すると、ユーザーが再度サインインするのを防ぐことができます。Office 365 で直接ユーザーアカウントを編集して、サインインが**ブロック**されるようにサインイン状態を設定するのと同じです。
  
> [!NOTE]
> ユーザーが office 365 にサインインすることを禁止している場合、中止することによって、またはサインイン状態を編集することによって、ユーザーのすべてのデバイスとクライアント ([Office 365 でユーザーを編集または変更](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)する) が有効になるまでに時間がかかる場合があることに注意してください。ユーザーが office 365 にサインインしている場合、office 365 が再度サインインする必要がある場合は常にブロックが有効になります。 
  
1. [全体管理者またはセキュリティ管理者](permissions-in-the-security-and-compliance-center.md)とし[https://protection.office.com](https://protection.office.com)て、に移動し、職場または学校のアカウントを使用してサインインします。(これにより、セキュリティ&amp;コンプライアンスセンターに移動できます。) 
    
2. セキュリティ&amp; /コンプライアンスセンターで、[**警告** \>の**管理] [詳細通知の管理**] を選択します。
    
3. [ **Office 365 Cloud App Security に移動**] を選択します。<br>![セキュリティ&amp; /コンプライアンスセンターで、[高度な通知の管理] を選択して Office 365 Cloud App Security に移動します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>
  
4. 画面上部のナビゲーションバーで、[**通知**] を選択します。
    
5. [**警告**] 列で、特定のユーザーアカウントに関連する警告をダブルクリックします。 
    
6. [**アカウント**] の [**状態**] 列で、 ![[設定](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \>の設定] アイコン [**中断ユーザー**] を選択します。
    
## <a name="to-restore-a-user-account"></a>ユーザーアカウントを復元するには

「 [Office のユーザーの復元 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1) 」を参照してください。
  
## <a name="next-steps"></a>次の手順

- [Office 365 Cloud App Security の警告の確認と処理](review-office-365-cas-alerts.md)
    
- [Office 365 Cloud App Security を使用して OAuth アプリを管理する](manage-app-permissions-in-ocas.md)
    
- [Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する
    

