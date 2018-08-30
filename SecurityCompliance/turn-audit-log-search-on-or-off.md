---
title: Office 365 監査ログの検索を有効または無効にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: Office 365 のセキュリティの監査ログの検索機能を有効にできます&amp;コンプライアンス センターです。点を変更する場合にオフの場合はいつでもできます。監査ログの検索をオフにすると、管理者は、組織内ユーザーと管理者のアクティビティを Office 365 の監査ログを検索できません。
ms.openlocfilehash: 4fa6ac095222addce578294813cbd22dfc50a2ab
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532164"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>Office 365 監査ログの検索を有効または無効にする

(または別の管理者) は、Office 365 の監査ログの検索を開始する前に監査ログを記録を有効にする必要があります。Office 365 のセキュリティ ログの検索をすると監査&amp;コンプライアンス センターをオンにして、組織内のユーザーと管理者のアクティビティを監査ログに記録されているし、90 日間保持されます。ただし、組織することも記録し、監査ログのデータを保持します。または監査データへのアクセスをサード ・ パーティ製のセキュリティ情報およびイベント管理 (SIEM) アプリケーションを使用する可能性があります。これらの場合では、グローバル管理者は Office 365 の監査ログの検索をオフにします。
  
## <a name="before-you-begin"></a>はじめに

- 監査ログの役割を割り当てる Exchange オンライン Office 365 組織の監査ログの検索を有効または無効にする必要があります。既定では、この役割は Exchange 管理センターで [**アクセス許可**] ページでのコンプライアンスの管理と組織管理の役割グループに割り当てられます。Office 365 の管理者がグローバル組織の管理役割グループのメンバーで Exchange はオンラインです。 
    
    > [!IMPORTANT]
    > ユーザーは、アクセス許可を割り当てるには、Exchange オンライン監査ログの検索を有効または無効にする必要があります。セキュリティの**アクセス許可**] ページで監査ログの役割をユーザーに割り当てる場合は、&amp;コンプライアンスの中心になる監査ログの検索を有効または無効にすることです。Exchange Online のコマンドレットは、コマンドレットを基になるためにです。 
  
- Office 365 の監査ログの検索を無効にした場合、組織の監査のデータにアクセスするのには Office 365 の管理アクティビティの API も使用できます。この資料の手順に従って、監査ログの検索を無効にすることを意味する結果は返されません、セキュリティを使用して監査ログを検索すると、&amp;コンプライアンス センターまたは Exchange Online の**検索 UnifiedAuditLog**コマンドレットを実行するときPowerShell。ただし場合は、任意のアプリケーションを Office 365 の管理アクティビティの API を使用して、組織の監査のデータにアクセスする権限を与えて、それらのアプリケーションは引き続き機能します。 
    
- Office 365 の検索の詳細については監査ログを参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。
    
## <a name="turn-on-audit-log-search"></a>監査ログの検索を有効にします。

セキュリティを使用することができます&amp;コンプライアンス センターまたは PowerShell は、Office 365 の監査ログの検索を有効にします。監査ログを検索する場合は、結果を返すことができます前に、監査ログの検索を有効にするいくつかの時間がかかる場合があります。監査ログの役割を割り当てる Exchange オンライン監査ログの検索を有効にする必要があります。
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a>セキュリティを使用して、&amp;監査ログの検索を有効にするのにはコンプライアンス センター

1. セキュリティ&amp;コンプライアンス センター] に移動**検索&amp;調査** \> **監査ログの検索**します。
    
2. **ユーザーと管理者の活動の記録を開始**] をクリックします。
    
    ![[ユーザーと管理者の活動記録を開始する] をクリックして、監査を有効にします。](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    ユーザーおよび組織の活動を管理される Office 365 の監査ログに記録されたとレポートの表示に使用できることを示すダイアログ ボックスが表示されます。 
    
3. 監査ログ検索の下で、 **[ユーザーと管理者のアクティビティの記録を開始する]** リンクを選択します (既にこの操作を実行済みの場合は、リンクは表示されません)。
    
    監査ログが準備中し、準備が完了した後の時間のいくつかの検索を実行するにはことを示すメッセージが表示されます。
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>PowerShell を使用して、監査ログの検索を有効にするのには

1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Office 365 の監査ログの検索を有効にするのには次の PowerShell コマンドを実行します。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    変更を反映するには、最大で 60 分がかかる場合がありますというメッセージが表示されます。
  
## <a name="turn-off-audit-log-search"></a>監査ログの検索をオフにします。

監査ログの検索を無効にするのには、オンラインの Exchange 組織に接続されている、リモート PowerShell を使用する必要があります。監査ログの検索を有効にすると同様に、監査ログの役割を割り当てるには、Exchange オンライン監査ログの検索を無効にする必要があります。
  
1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Office 365 の監査ログの検索を無効にするのには次の PowerShell コマンドを実行します。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. しばらくして、その監査ログの検索がオフ (無効) になっているを確認します。これを行う 2 つの方法があります。
    
    - PowerShell で次のコマンドを実行します。

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        値`False` _UnifiedAuditLogIngestionEnabled_のプロパティを示しますその監査ログの検索が無効になっています。 
    
    - セキュリティ&amp;コンプライアンス センター] に移動**検索&amp;調査** \> **監査ログの検索**、し、[**検索**] をクリックします。
    
      監査ログの検索では、有効になっていないことを示すメッセージが表示されます。 
    
      ![監査を無効になっている場合、メッセージは dispayed](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
