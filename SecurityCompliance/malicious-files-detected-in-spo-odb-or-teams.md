---
title: SharePoint、OneDrive、またはマイクロソフトのチームで検出された、悪意のあるファイルに関する情報を表示
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
description: SharePoint、OneDrive、またはチームで検出された、悪意のあるファイルに関する情報を表示する場所とそれらのファイルに対してアクションを実行する方法について説明します。
ms.openlocfilehash: c22e57e34cccafa3dd30a77a5a6011f2999f708c
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706201"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>SharePoint、OneDrive、またはマイクロソフトのチームで検出された、悪意のあるファイルに関する情報を表示

[SharePoint、OneDrive、およびマイクロソフトのチームの office 365 の分析ツール](atp-for-spo-odb-and-teams.md)は、ドキュメント ライブラリ、およびチーム サイト内の悪意のあるファイルから組織を保護します。悪意のあるファイルが検出されると、そのファイルを開く、コピー、移動、またはそれ以降の操作は、組織のセキュリティ チームによって実行されるまで、共有できる誰にするためにブロックされます。によって検出されたファイルに関する情報を表示する方法とどのような措置を説明するには、この資料を参照してください。 

この資料で説明するタスクを実行するために、必要なを設定する必要があります[Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。 
  
## <a name="view-reports-with-information-about-detected-files"></a>によって検出されたファイルに関する情報をレポートの表示

状態と Office 365 の分析ツールによって検出されたファイルに関する詳細情報を表示するには、脅威の保護の状態レポートを使用できます。
  
1. [Office 365 のセキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)で**レポート**を選択\>**ダッシュ ボード** \> **脅威保護の状態**です。
    
2. レポートの右上隅の**ビューの詳細テーブル**を選択します。
    
3. レポート内で検出されたファイルの一覧を表示します。
    
4. 詳細については、実行されたアクションを含む、ファイル名、ファイルのパスなどを表示するのには、ボックスの一覧で項目を選択します。
    
5. 観察された現象と分析の詳細などの情報を表示するのには、**高度な分析**] タブを選択します。 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>表示し、検査中のファイルに対してアクションを実行

1. Office 365 のセキュリティで&amp;コンプライアンス センターでは、**脅威の管理**を選択して\>**レビュー** \> **検査**します。
    
2. 左上隅で、**メール**から**コンテンツ**にフィルターを変更します。
    
3. ファイルの URL を含む、詳細情報を表示するのには、ボックスの一覧で項目を選択します。
    
4. 使用可能なアクションを選択します。
    
  - 選択**リリース&amp;レポート**ファイルのブロックを解除します。 
    
    誤認としてファイルをマイクロソフトに報告を**マイクロソフトにレポートを送信する**を選択します。 
    
  - さらにファイルを調査する**ファイルのダウンロード**を選択してください。 
    
  - 検疫済みのアイテムの一覧からファイルを削除する**削除**をクリックします。このオプションを選択する場合は、ビジネス、またはマイクロソフトのチームの SharePoint のオンライン、OneDrive で、それぞれのライブラリからファイルを削除する必要がありますもします。このオプションがないブロックを解除されてからファイルを共有を開くか。 
    
5. 選択したアイテムの詳細を閉じるに**閉じる**を選択します。 
  
  

