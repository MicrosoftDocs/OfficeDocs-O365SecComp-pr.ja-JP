---
title: Office 365 Cloud App Security でユーザー アカウントを停止または復元する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Office 365 のクラウド アプリケーションのセキュリティ、実行できる管理操作を一時停止またはユーザー アカウントの一時中断を解除するのには。 '
ms.openlocfilehash: a5c75edefc6ddb87b5676c4253aafe04817f6a1d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531742"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a>Office 365 Cloud App Security でユーザー アカウントを停止または復元する

セキュリティ管理の高度な office 365 は、Office 365 のクラウド アプリケーションのセキュリティをされます。
  
|評価 * *\>**|計画 * *\>**|配置 * *\>**|使用率。|
|:-----|:-----|:-----|:-----|
|[評価を開始します。](office-365-cas-overview.md) <br/> |[計画の開始します。](get-ready-for-office-365-cas.md) <br/> |[展開を開始します。](turn-on-office-365-cas.md) <br/> |コースです!  <br/> [次の手順](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
Office 365 の組織のユーザー アカウントのいずれかが侵害されている警告が表示されると仮定します。または、ユーザー アカウントに問題があることを示すアラートを受信したと仮定します。Office 365 のクラウド アプリケーションのセキュリティ、ユーザー アカウントを中断でき、後で受信するアラートを調査した後に復元できます。
  
> [!NOTE]
> Office 365 のクラウド アプリケーションのセキュリティは、Office 365 エンタープライズ E5 に使用できます。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合、Office 365 のクラウド アプリケーションのセキュリティがアドオンとして購入できます。(グローバル管理者は、Office 365 管理センターを選択して**請求** \> **サブスクリプションを追加**します)。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://technet.microsoft.com/en-us/library/dn933793.aspx) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a>Office 365 のクラウド アプリケーションのセキュリティでユーザー アカウントを中断するのには

ユーザー アカウントを一時停止するとから、もう一度サインイン ユーザーを防止します。直接**では、署名ブロック**にサインインしている状態を設定するのには Office 365 でユーザー アカウントを編集と同じです。
  
> [!NOTE]
> ユーザーがそれらを中断するか、サインイン状態を編集することによって、Office 365 にサインインをブロックする場合は、かかる場合が 1 時間、またはすべてのユーザーのデバイスとクライアント ([編集または Office 365 のユーザーを変更する](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)) を有効にするために注意します。場合は、ユーザーは、Office 365 にサインインしている、Office 365 でもう一度サインインするのには必要なときに、ブロックが反映されます。 
  
1. [グローバル アドミニストレーターまたはセキュリティ管理者](permissions-in-the-security-and-compliance-center.md)に移動します。[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用してサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。 
    
2. セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。
    
3. **Office 365 のクラウド アプリケーションのセキュリティ**を選択します。
    
    ![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. 画面の上部にナビゲーション ・ バーの**アラート**を選択します。
    
5. [**アラート**] 列で、特定のユーザー アカウントに関連する警告をダブルクリックします。 
    
6. [**アカウント**] で、[**状態**] 列の設定を選択![の設定アイコン](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **ユーザーの一時停止**します。
    
## <a name="to-restore-a-user-account"></a>ユーザー アカウントを復元するには

[Office 365 のユーザーを復元する](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)を参照してください。
  
## <a name="next-steps"></a>次の手順

- [Office 365 Cloud App Security の警告の確認と処理](review-office-365-cas-alerts.md)
    
- [Office 365 Cloud App Security を使用してアプリのアクセス許可を管理する](manage-app-permissions-in-ocas.md)
    
- [Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。
    

