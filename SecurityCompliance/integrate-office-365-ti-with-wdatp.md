---
title: Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: Windows Defender 高度な脅威保護の脅威の管理の詳細を表示するには、Office 365 の高度な脅威保護を統合します。
ms.openlocfilehash: e5070e003972ae5308415dcdcca85b069d1163ac
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29382540"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する

組織のセキュリティ チームの一部の場合は、Windows Defender の高度な脅威保護と Office 365 の高度な脅威保護し、脅威のインテリジェンス機能を統合できます。これは、かどうかユーザーのコンピューターは危険に Office 365 の脅威を調査するときに簡単に理解することができます。たとえば、統合を有効にするは、方法として、これらのマシンがある Windows Defender の高度な脅威保護の新しいアラートの数も、検出された電子メール メッセージの受信者によって使用されるコンピューターの一覧を表示することができます。
  
次の図は、表示される Windows Defender の高度な脅威保護の統合を有効にする場合、[**デバイス**] タブを示しています。 
  
![ATP の Windows Defender を有効にすると、アラートがあるコンピューターの一覧を表示できます。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
この例では、警告が、電子メール メッセージの受信者がある 4 つのデバイスを表示できます。デバイスへのリンクをクリックすると Windows Defender の高度な脅威保護のポータルでそのページを開きます。
  
## <a name="requirements"></a>要件

- 組織には、Office 365 の脅威インテリジェンスと Windows Defender の分析ツールが必要です。
    
- Office 365 のグローバル管理者であるかに割り当てられているセキュリティ管理者ロール (セキュリティ管理者など) を持っている必要があります、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)です。(を参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md))
    
- Office 365 の脅威インテリジェンスと高度な脅威保護の Windows Defender のポータルの両方へのアクセスが必要です。
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>Windows Defender の分析ツールと Office 365 の脅威インテリジェンスを統合するには

Windows Defender の高度な脅威保護と Office 365 の脅威インテリジェンスを統合することについては、両方の Office 365 のセキュリティ & コンプライアンス センターとの高度な脅威保護の Windows Defender のポータルを使用して、設定します。
  
1. 移動すると、Office 365 のグローバル管理者またはセキュリティ管理者は、[https://protection.office.com](https://protection.office.com)と Office 365 は、職場または学校のアカウントでサインインします。 
    
2. **脅威の管理**を選択して\>**エクスプ ローラー**です。<br>![脅威の管理] メニューのエクスプ ローラー](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 画面の右上隅では、 **WDATP の設定**を選択します。
    
4. Windows Defender の ATP の接続] ダイアログ ボックスで、ATP の Windows への接続をオンにします。<br>![Windows Defender の ATP の接続](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Windows Defender の高度な脅威保護の接続を有効にします。[Windows Defender の高度な脅威保護のポータルの使用](https://go.microsoft.com/fwlink/?linkid=859690)を参照してください。

  
## <a name="related-topics"></a>関連項目

[Office 365 脅威インテリジェンス](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

