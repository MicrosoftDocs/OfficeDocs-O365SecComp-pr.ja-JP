---
title: SharePoint、OneDrive、Microsoft Teams で検出された悪意のあるファイルに関する情報を表示する
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: SharePoint、OneDrive、Teams で検出された悪意のあるファイルに関する情報を表示する方法と、それらのファイルに対してアクションを実行する方法について説明します。
ms.openlocfilehash: 070640d9aa1d28cc1a49a9d8b88e5bf5780d3622
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077583"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams で検出された悪意のあるファイルに関する情報を表示する

[Office 365 ATP For SharePoint、OneDrive、Microsoft Teams](atp-for-spo-odb-and-teams.md)では、組織がドキュメントライブラリおよびチームサイト内の悪意のあるファイルから保護されます。 悪意のあるファイルが検出されると、そのファイルはブロックされるようになり、組織のセキュリティチームによって追加の操作が行われるまで、そのファイルを開いたり、コピー、移動、または共有することができなくなります。 この記事では、検出されたファイルと実行するアクションに関する情報を表示する方法について説明します。 

この記事で説明されているタスクを実行するには、 [Office 365 セキュリティ&amp;コンプライアンスセンターに必要なアクセス許可](permissions-in-the-security-and-compliance-center.md)を持っている必要があります。 
  
## <a name="view-reports-with-information-about-detected-files"></a>検出されたファイルに関する情報をレポートを表示する

Office 365 ATP によって検出されたファイルの状態と詳細情報を表示するには、脅威保護の状態レポートを使用できます。
  
1. [Office 365 セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**ダッシュボード** \>の**脅威保護の状態**を**報告** \>する] を選択します。
    
2. レポートの右上隅で、[**詳細テーブルの表示**] を選択します。
    
3. レポートで検出されたファイルの一覧を表示します。
    
4. リスト内の項目を選択して、実行されたアクション、ファイル名、ファイルパスなどを含む詳細情報を表示します。
    
5. [**詳細分析**] タブを選択して、観測された動作や分析の詳細などの情報を表示します。 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>検疫内のファイルを表示し、処理を実行する

1. &amp; Office 365 セキュリティコンプライアンスセンターで、[**脅威管理** \> **レビュー** \>の**検疫**] を選択します。
    
2. 左上隅で、フィルターを [**電子メール**] から [**コンテンツ**] に変更します。
    
3. リストで項目を選択すると、ファイルの URL などの詳細情報が表示されます。
    
4. 使用可能なアクションを選択します。
    
  - ファイルのブロックを解除するには、[**レポートの解放&amp; ** ] を選択します。 
    
    Microsoft への誤検知としてファイルを報告するには、[ **microsoft にレポートを送信**する] を選択します。 
    
  - [**ファイルのダウンロード**] を選択して、ファイルをさらに調査します。 
    
  - [**削除**] を選択して、検疫されたアイテムのリストからファイルを削除します。 このオプションを選択する場合は、SharePoint Online、OneDrive for Business、または Microsoft Teams の対応するライブラリからもファイルを削除する必要があります。 このオプションでは、ファイルが開かれたり共有されたりすることはブロックされません。 
    
5. [**閉じる**] を選択して、選択したアイテムの詳細を閉じます。 
  
  

