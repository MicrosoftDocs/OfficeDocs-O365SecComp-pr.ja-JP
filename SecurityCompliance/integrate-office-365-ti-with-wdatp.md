---
title: Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合する
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合し、より詳細な脅威管理情報を表示します。
ms.openlocfilehash: 640c073e9ef5b32ffaa8d38a426d86b60d80d2aa
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599053"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合する

組織のセキュリティチームに参加している場合は、 [Microsoft Defender Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して[Office 365 advanced threat protection](office-365-atp.md)と関連調査および応答機能を統合することができます。 これは、Office 365 で脅威を調査しているときに、ユーザーのコンピューターが危険にさらされているかどうかをすばやく理解するのに役立ちます。 たとえば、統合が有効になると、検出された電子メールメッセージの受信者によって使用されるコンピューターの一覧、およびそれらのコンピューターが Microsoft Defender Advanced Threat Protection で保持している最近の通知の数を確認できます。
  
次の図は、Microsoft Defender ATP 統合が有効になっている場合に表示される [**デバイス**] タブを示しています。
  
![Microsoft Defender ATP が有効になっている場合は、アラートがあるコンピューターの一覧を表示できます。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
この例では、電子メールメッセージの受信者に4つのデバイスがあり、1つに通知があることがわかります。 デバイスのリンクをクリックすると、Microsoft Defender セキュリティセンターにそのページが表示されます。
  
## <a name="requirements"></a>要件

- 組織では、Office 365 ATP Plan 2 (または Office 365 E5) と Microsoft Defender ATP を所有している必要があります。
    
- Office 365 グローバル管理者であるか、セキュリティ管理者の役割 (セキュリティ管理者など) が[ &amp;セキュリティコンプライアンスセンター](https://protection.office.com)で割り当てられている必要があります。 ( [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照してください)
    
- セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方の[エクスプローラー (またはリアルタイム検出)](threat-explorer.md)にアクセスできる必要があります。
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Microsoft Defender ATP を使用して Office 365 ATP を統合するには

Microsoft Defender ATP との Office 365 ATP の統合は、セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方を使用してセットアップされています。
  
1. Office 365 全体管理者またはセキュリティ管理者として[https://protection.office.com](https://protection.office.com) 、に移動して、office 365 の職場または学校アカウントでサインインします。
    
2. [**脅威管理** \> **エクスプローラー**] を選択します。<br>![脅威管理メニューのエクスプローラー](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 画面の右上にある [ **Wdatp 設定**] を選択します。
    
4. [Windows Defender ATP 接続] ダイアログボックスで、[Windows ATP への接続] をオンにします。<br>![Microsoft Defender ATP 接続](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Microsoft Defender セキュリティセンターで接続を有効にします。

  
## <a name="related-topics"></a>関連項目

[Office 365 の脅威の調査と対応](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

