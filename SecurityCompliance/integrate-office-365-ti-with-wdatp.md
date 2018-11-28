---
title: Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: Windows Defender 高度な脅威保護の脅威の管理の詳細を表示するには、Office 365 の高度な脅威保護を統合します。
ms.openlocfilehash: 1198f53c47811d69b93106c413e3d3a09d83e736
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706141"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する

組織のセキュリティ チームの一部は、の Windows Defender 高度な脅威保護 (ATP) を Office 365 に統合できます。これは、かどうかユーザーのコンピューターは危険に Office 365 の脅威を調査するときに簡単に理解することができます。などの統合を有効にするを参照してください、検出された電子メール メッセージの受信者によって使用されるコンピューターの一覧にも多く最近受信したアラートの分析ツールを Windows Defender でのこれらのマシンがあるどのようにすることができます。
  
次の図は、表示される Windows Defender の ATP の統合を有効にする場合、[**デバイス**] タブを示しています。 
  
![ATP の Windows Defender を有効にすると、アラートがあるコンピューターの一覧を表示できます。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
この例では、アラートの分析ツールを Windows Defender では、電子メール メッセージの受信者がある 4 つのマシンを表示できます。コンピューターへのリンクをクリックすると新しいタブで Windows Defender の ATP のマシンのページを開きます。
  
## <a name="requirements"></a>要件

- 組織には、Office 365 の脅威インテリジェンスと Windows Defender の分析ツールが必要です。
    
- Office 365 のグローバル管理者であるかに割り当てられているセキュリティ管理者の役割を持っている必要があります、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)です。(を参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md))
    
- Office 365 の脅威インテリジェンスと、Windows Defender の ATP ポータルの両方へのアクセスが必要です。
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>Windows Defender の分析ツールと Office 365 の脅威インテリジェンスを統合するには

Windows Defender の分析ツールと Office 365 の脅威インテリジェンスを統合することは、Office 365 と、Windows Defender の ATP ポータルの両方を設定します。
  
1. 移動すると、Office 365 のグローバル セキュリティ管理者は、[https://security.microsoft.com](https://security.microsoft.com)と Office 365 は、職場または学校のアカウントでサインインします。 
    
2. **脅威の管理**を選択して\>**脅威のエクスプ ローラー**です。
    
3. [**詳細**] メニューには、 **WDATP の設定**を選択します。
    
4. **ATP の Windows への接続**を選択します。
    
Office 365 内の設定を変更した後は、Windows Defender の ATP からの接続を有効にする必要があります。[Windows Defender の高度な脅威保護のポータルの使用](https://go.microsoft.com/fwlink/?linkid=859690)を参照してください。
  
## <a name="related-topics"></a>関連項目

[Office 365 脅威インテリジェンス](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

