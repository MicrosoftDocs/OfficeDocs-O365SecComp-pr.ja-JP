---
title: Office 365 ATP for SharePoint、OneDrive、Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection を SharePoint Online、OneDrive for Business、Microsoft Teams のファイルに拡張して、組織にとってより安全なコラボレーションを可能にします。
ms.openlocfilehash: 1a9fbf54b1393f250bc259ecb2e8bb9fd36f2ae0
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598643"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP for SharePoint、OneDrive、Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams の Office 365 ATP の概要

ユーザーは、SharePoint、OneDrive、Microsoft Teams を使用して、ファイルを定期的に共有し、共同作業を行うことができます。 [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、組織は安全な方法で共同作業を行うことができます。 ATP は、チームサイトおよびドキュメントライブラリで悪意のあるものとして識別されたファイルを検出およびブロックするのに便利です。  
  
## <a name="how-it-works"></a>メカニズム

SharePoint Online、OneDrive for Business、および Microsoft Teams のファイルが悪意のあるものとして識別されると、そのファイルをロックするために、ATP はファイルストアと直接統合されます。 次の図は、ライブラリ内で検出された悪意のあるファイルの例を示しています。
  
[![悪意のあるものとして検出された OneDrive for Business のファイル](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
ブロックされたファイルは、ドキュメントライブラリ、web、モバイル、またはデスクトップの各アプリケーションに表示されたままですが、ブロックされたファイルを開く、コピー、移動、または共有することはできません。 ただし、ユーザーはブロックされたファイルを削除できます。 ユーザーのモバイルデバイスに表示されるものの例を次に示します。
  
[![Onedrive モバイルアプリから OneDrive for business からブロックされたファイルを削除する](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Office 365 の構成方法によっては、ブロックされたファイルをダウンロードすることができるかどうかはユーザーによって異なる場合があります。 ブロックされたファイルをダウンロードすると、ユーザーのモバイルデバイスで次のように表示されます。
  
[![OneDrive for Business でブロックされたファイルをダウンロードする](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
詳細については、「 [Turn On Office 365 ATP For SharePoint, OneDrive, And Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。
  
## <a name="keep-these-points-in-mind"></a>これらの点を念頭に置いてください。

- ATP では、SharePoint Online、OneDrive for Business、または Microsoft Teams のすべてのファイルがスキャンされるわけではありません。 これは仕様どおりです。 ファイルは、共有とゲストアクティビティイベントを使用するプロセスによって非同期でスキャンされ、スマートヒューリスティックおよび脅威信号を使用して悪意のあるファイルを識別します。

- SharePoint サイトが[モダンな環境](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)を使用するように構成されていることを確認します。 ファイルが悪意のあるものとして認識され、ブロックされると、これがモダンな機能で発生していることがわかりますが、クラシックビューでは表示されません。 ATP 保護は、モダンな表示とクラシック表示のどちらを使用するかに適用されます。ただし、ファイルがブロックされているという視覚インジケーターは、モダンな環境でのみ表示されます。
    
- SharePoint Online、OneDrive for Business、または Microsoft Teams で悪意のあるものとして識別されたファイルは、 [Office 365 Advanced Threat Protection](view-reports-for-atp.md)および[Explorer (およびリアルタイム検出)](threat-explorer.md)のレポートで表示されます。
    
- ATP は、組織の全体的な脅威保護戦略の一部であり、スパム対策とマルウェア対策の保護、および安全なリンクと安全な添付ファイルが含まれます。 詳細については、「 [Office 365 の脅威から保護](protect-against-threats.md)する」を参照してください。
    
- SharePoint Online 管理者は、悪意のあるものとして検出されたファイルをユーザーがダウンロードできるようにするかどうかを決定できます。 これを行うには、DisallowInfectedFileDownload パラメーターを使用して Set-spotenant PowerShell コマンドレットを実行します (「 [Turn On Office 365 ATP For SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください)。
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>SharePoint Online、OneDrive for Business、Microsoft Teams 用の ATP での検疫

 2018年5月の初期[](quarantine-email-messages.md)段階では、セキュリティ&amp; /コンプライアンスセンターの検疫機能が、SharePoint Online、OneDrive For business、MICROSOFT Teams 用の ATP に拡張されています。
  
SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるものとして識別されると、そのファイルは、検疫されたアイテムの一覧に含まれています。 &amp; (セキュリティコンプライアンスセンターで、[**脅威管理** \> **レビュー** \> ] [**コンテンツ**の**検疫**とフィルター] に移動します。) 
  
組織の Office 365 セキュリティチームに属していて、 [office 365 セキュリティ&amp;コンプライアンスセンターで必要なアクセス許可が割り当てら](permissions-in-the-security-and-compliance-center.md)れている場合は、ATP によって悪意があると検出されたファイルをダウンロード、リリース、レポート、および削除することができます。検疫から。
  
- ファイルを**リリースおよびレポートすると**、SharePoint、OneDrive、Microsoft Teams の各チームサイトまたはドキュメントライブラリにあるファイルの ATP ブロックが削除されます。 その後、ユーザーはファイルを開いて、共有し、ダウンロードすることができます。 そして、[ **microsoft にレポートを送信**] オプションが選択されている場合、ファイルは誤検知として microsoft に報告されます。 
    
- **ファイルを削除する**と、検疫からファイルが削除されます。ただし、ファイルは開いたり共有したりすることはブロックされたままです。 また、ファイルは、対応するドキュメントライブラリまたはチームサイト (SharePoint Online、OneDrive for Business、または Microsoft Teams) で削除する必要があります。 
    
- **ファイルをダウンロード**すると、誤検知のためにファイルをダウンロードして分析することができます。 
    
## <a name="next-steps"></a>次のステップ

1. [SharePoint、OneDrive、Microsoft Teams の Office 365 ATP を有効にする](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [SharePoint、OneDrive、Microsoft Teams で検出された悪意のあるファイルに関する情報を表示する](malicious-files-detected-in-spo-odb-or-teams.md)
    
