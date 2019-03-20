---
title: EOP の機能アクセス許可
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Microsoft Exchange Online Protection (EOP) を管理するタスクを実行するために必要なアクセス許可は、管理している機能に応じて異なります。
ms.openlocfilehash: 08753d537982e49e735a1f81796f4709882c2be9
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692076"
---
# <a name="feature-permissions-in-eop"></a>EOP の機能アクセス許可

Microsoft Exchange Online Protection (EOP) を管理するタスクを実行するために必要なアクセス許可は、管理している機能に応じて異なります。 
  
EOP をセットアップするには、Office 365 グローバル管理者、または Exchange 社内管理者 (Organization Management 役割グループ) であることが必要です。
  
## <a name="exchange-online-protection-permissions"></a>Exchange Online Protection アクセス許可

EOP 機能を管理するために必要なアクセス許可は、次の表で確認してください。機能が複数の役割グループを示している場合、その機能を使用する役割グループを 1 つだけが割り当てる必要があります。
  
|**機能**|**必要なアクセス許可**|
|:-----|:-----|
|マルウェア対策  <br/> |[組織の管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [検疫管理](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|スパム対策  <br/> |[組織の管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [検疫管理](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|メール フロー ルール  <br/> |[組織の管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Records Management](http://technet.microsoft.com/library/0e0c95ce-6109-4591-b86d-c6cfd44d21f5.aspx) <br/> |
|ドメイン  <br/> |[組織の管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> |
|Advanced Threat Protection (ATP)  <br/> |[組織の管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [検疫管理](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|Office 365 コネクタ  <br/> |[組織の管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> |
|メッセージ トレース  <br/> |[組織の管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> |
|組織の構成  <br/> |[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> |
|検疫  <br/> |[組織の管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|ユーザー、連絡先、および役割グループ  <br/> |[組織の管理](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|配布グループとセキュリティ グループ  <br/> |[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|レポートの表示  <br/> |[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)- ユーザーはメールボックス保護レポートにアクセスできます。  <br/> [View-Only Recipients](http://technet.microsoft.com/library/37e66b92-81d3-412f-b7a9-e1bb8cbeb468.aspx)- ユーザーはメールボックス保護レポートにアクセスできます。  <br/> [Compliance Management](http://technet.microsoft.com/library/b91b23a4-e9c7-4bd0-9ee3-ec5cb498da15.aspx) - ユーザーはメール保護レポートおよびデータ損失防止 (DLP) レポート (サブスクリプションに DLP 機能が含まれている場合) にアクセスできます。  <br/> |
   

