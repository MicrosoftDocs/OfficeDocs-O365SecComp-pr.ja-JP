---
title: Windows Defender advanced threat protection を使用して Office 365 advanced threat protection を統合する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Windows Defender advanced threat protection を使用して Office 365 advanced threat protection を統合し、より詳細な脅威管理情報を表示します。
ms.openlocfilehash: bbbb42c9d0f37ab33323b2fa1dd071bd5ee16829
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30523981"
---
# <a name="integrate-office-365-advanced-threat-protection-with-windows-defender-advanced-threat-protection"></a>Windows Defender advanced threat protection を使用して Office 365 advanced threat protection を統合する

組織のセキュリティチームに参加している場合は、Windows Defender advanced threat protection を使用して Office 365 advanced threat protection と関連調査および応答機能を統合することができます。 これは、Office 365 で脅威を調査しているときに、ユーザーのコンピューターが危険にさらされているかどうかをすばやく理解するのに役立ちます。 たとえば、統合が有効になると、検出された電子メールメッセージの受信者によって使用されるコンピューターの一覧と、それらのコンピューターが Windows Defender Advanced Threat Protection で保持している最近の通知の数も表示できます。
  
次の図は、Windows Defender Advanced Threat Protection の統合が有効になっている場合に表示される [**デバイス**] タブを示しています。 
  
![Windows Defender ATP が有効になっている場合は、アラートがあるコンピューターの一覧を表示できます。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
この例では、電子メールメッセージの受信者に4つのデバイスがあり、1つに通知があることがわかります。 デバイスのリンクをクリックすると、Windows Defender Advanced Threat Protection ポータルのページが開きます。
  
## <a name="requirements"></a>要件

- 組織では、office 365 Advanced Threat Protection プラン 2 (または office 365 E5) と Windows Defender ATP を所有している必要があります。
    
- Office 365 グローバル管理者であるか、セキュリティ管理者の役割 (セキュリティ管理者など) が[ &amp;セキュリティコンプライアンスセンター](https://protection.office.com)で割り当てられている必要があります。 ( [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照してください)
    
- Security & コンプライアンスセンターおよび Windows Defender Advanced threat Protection ポータルで、Office 365 の脅威エクスプローラーの両方にアクセスできる必要があります。
    
## <a name="to-integrate-office-365-advanced-threat-protection-with-windows-defender-atp"></a>Office 365 Advanced Threat Protection を Windows Defender ATP と統合するには

office 365 advanced threat protection with windows defender advanced threat protection は、office 365 Security & コンプライアンスセンターと windows defender advanced threat protection ポータルの両方を使用してセットアップされます。
  
1. office 365 全体管理者またはセキュリティ管理者として[https://protection.office.com](https://protection.office.com) 、に移動して、office 365 の職場または学校アカウントでサインインします。 
    
2. [**脅威管理** \> **エクスプローラー**] を選択します。<br>![脅威管理メニューのエクスプローラー](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 画面の右上にある [ **wdatp 設定**] を選択します。
    
4. [windows Defender atp 接続] ダイアログボックスで、[windows ATP への接続] をオンにします。<br>![Windows Defender ATP 接続](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Windows Defender Advanced Threat Protection で接続を有効にします。 「 [Windows Defender Advanced Threat Protection ポータルの使用](https://go.microsoft.com/fwlink/?linkid=859690)」を参照してください。

  
## <a name="related-topics"></a>関連項目

[Office 365 の脅威の調査と対応](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

