---
title: SharePoint、OneDrive、およびマイクロソフトのチームに対して Office 365 の分析ツールを有効に
ms.author: derng
author: derng
manager: laurawi
ms.date: 5/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
description: SharePoint、OneDrive、および検出されたファイルについての警告を設定する方法など、チーム分析ツールを有効にする方法を説明します。
ms.openlocfilehash: bb99aee0887f15f065a47d691c59ce47639bdc32
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972239"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、およびマイクロソフトのチームに対して Office 365 の分析ツールを有効に

[SharePoint、OneDrive、およびマイクロソフトのチームの office 365 の分析ツール](atp-for-spo-odb-and-teams.md)は、悪意のあるファイルを誤って共有から組織を保護します。悪意のあるファイルが検出されると、そのファイルを開く、コピー、移動、またはそれ以降の操作は、組織のセキュリティ チームによって実行されるまで、共有できる誰にするためにブロックされます。SharePoint の分析ツールを有効にするには、この資料を参照するには、OneDrive、チーム、検出されたファイルを通知する警告を設定し、次の手順を実行します。 
  
> [!TIP]
> この資料で説明するタスクを実行するために Office 365 では、セキュリティでの割り当てに必要なアクセス許可が必要&amp;コンプライアンス センターです。
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP を SharePoint、OneDrive、Microsoft Teams で有効にする

 **この手順を開始する前に、監査ログが有効になって、Office 365 環境の確認**をします。これは通常、Exchange のオンラインを割り当てられている監査ログのロールを持つユーザーによって行います。詳細については、[オンまたはオフ、Office 365 を有効にする監査ログの検索](turn-audit-log-search-on-or-off.md)を参照してください。
  
1. グローバル管理者またはセキュリティ管理者には、 [https://protection.office.com](https://protection.office.com)、および、職場、学校のアカウントでサインインします。
    
2. Office 365 のセキュリティで&amp;コンプライアンス センターでは、**脅威の管理**の下で、左側のナビゲーション ペインで**ポリシー**を選択する\>**安全な添付ファイル**です。
    
    ![セキュリティ&amp;コンプライアンス センターでは、脅威の管理を選択して\>ポリシー](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. **SharePoint、OneDrive、およびマイクロソフトのチームの分析ツールを有効にする**を選択します。
    
    ![オンライン、ビジネス、およびマイクロソフトのチームの OneDrive の SharePoint の高度な脅威保護を有効に](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. **[保存]** をクリックします。
    
5. 確認 (および、必要に応じて編集)、組織の[安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)と[ポリシーの安全なリンク](set-up-atp-safe-links-policies.md)です。
    
6. (推奨)グローバル管理者または SharePoint Online 管理者は、 **DisallowInfectedFileDownload**パラメーターが*true*に設定を使用して**[セット SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** コマンドレットを実行します。 <br/><br/>*真*のブロックのパラメーター (削除) を除くすべてのアクションを設定すると、ファイルが検出されました。人ことはできませんを開く、移動、コピー、または検出されたファイルを共有します。<br/><br/>パラメーターを*false*に設定すると、削除し、ダウンロードを除くすべてのアクションがブロックされます。リスクを受け入れるし、検出されたファイルをダウンロードするユーザーを選択できます。<br/><br/>パラメーターを*true*に設定することをお勧めします。 
   
7. 最大 30 分間のすべての Office 365 のデータ センターに展開するのには、変更を許可します。
    
8. (推奨)によって検出されたファイルの通知の設定に進みます。
    
> [!TIP]
> Office 365 で、PowerShell を使用する方法の詳細については、 [PowerShell での Office 365 の管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)を参照してください。> として、悪意のあるファイルが検出されたときのユーザー エクスペリエンスの詳細についてを参照してください[SharePoint のオンライン、OneDrive、またはマイクロソフトのチームで悪意のあるファイルが見つかった場合の対処方法](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)です。 
  
## <a name="set-up-alerts-for-detected-files"></a>によって検出されたファイルの通知を設定します。

ビジネス、またはマイクロソフトのチームの SharePoint のオンライン、OneDrive のファイルが悪意のあるものとして確認されたときに通知を受信するには、アラートを設定できます。
  
1. Office 365 のセキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**通知の管理**。
    
2. **新しいアラート ・ ポリシー**を選択します。
    
3. 警告の名前を指定します。たとえば、ライブラリで悪意のあるファイルを入力します。
    
4. アラートの説明を入力します。たとえば、SharePoint のオンライン、OneDrive、またはマイクロソフトのチームで悪意のあるファイルが検出された場合は通知の管理者を入力します。
    
5. **. のときは、このアラートを送信**] セクションでは、次の操作を行います。 
    
  - **活動**] ボックスの一覧で、**ファイルにマルウェアを検出しました**を選択します。
    
  - **ユーザー**のフィールドは空のままにします。 
    
6. **. このアラートを送信**] セクションで、グローバル管理者、セキュリティ管理者、または悪意のあるファイルが検出されたときに通知を受信する必要がありますセキュリティの読者の 1 つまたは複数を選択します。 
    
7. **[保存]** をクリックします。
    
> [!TIP]
> 警告に関する詳細についてを参照してください[では、Office 365 のセキュリティ アクティビティのアラートを作成&amp;コンプライアンス センター](create-activity-alerts.md)です。 
  
## <a name="next-steps"></a>次の手順

- [SharePoint、OneDrive、またはマイクロソフトのチームで検出された、悪意のあるファイルに関する情報を表示](malicious-files-detected-in-spo-odb-or-teams.md)
    
- [Office 365 の管理者として検疫されたメッセージやファイルを管理します。](manage-quarantined-messages-and-files.md)
    
## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Office 365 の高度な脅威保護のレポートを表示します。](view-reports-for-atp.md)
  
[Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)
  

