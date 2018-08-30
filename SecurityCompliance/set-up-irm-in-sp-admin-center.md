---
title: SharePoint 管理センターでの情報権利管理 (IRM) を設定します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: SharePoint オンライン IRM を通じて Microsoft Azure Active Directory Rights Management サービス (RMS) を使用して SharePoint リストおよびドキュメント ライブラリを保護する方法について説明します。
ms.openlocfilehash: dea8c71ce67207b3c40a1f934f90e63740f70f29
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532151"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>SharePoint 管理センターでの情報権利管理 (IRM) を設定します。

SharePoint Online では、内のリストやライブラリ レベルでファイルに IRM 保護が適用されます。組織が IRM 保護を使用する前に権限の管理を設定する必要があります。IRM では、Azure の情報保護を暗号化し、使用率の制限を割り当てるから Azure の権限の管理サービスに依存しています。Azure アクセス権の管理がすべてではなく、一部の Office 365 のプランが含まれます。詳細についてを参照して[どのように Office アプリケーションおよびサービスは、Azure の権利管理をサポート](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)します。
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>SharePoint 管理センターを使用して IRM サービスを有効にします。

組織には、IRM で保護する SharePoint リストおよびライブラリことができます、前にまず、組織の権限の管理サービスを有効にする必要があります。については、どのように[Azure アクセス権の管理をアクティブにする](https://docs.microsoft.com/information-protection/deploy-use/activate-service)を参照してください。権限管理サービスを有効にするのには Office 365 のグローバル管理者権限のある職場、学校のアカウントを使用する必要があります。それ以外の場合、SharePoint Online で IRM 機能を使用することはできません。
  
権限管理サービスをアクティブにした後、IRM を有効にするのには SharePoint の管理センターにサインインします。
  
1. グローバル管理者または SharePoint 管理者として Office 365 にサインインします。
    
2. 左上のアプリ起動ツール アイコン ![Office 365 のアプリ起動ツール アイコン](media/e5aee650-c566-4100-aaad-4cc2355d909f.png)を選択し、**[管理者]** を選択して、Office 365 管理センターを開きます。([管理] タイルが表示されない場合は、組織内で Office 365 管理者権限を持っていません。) 
    
3. 左側のウィンドウで [**管理者の中央に配置**」を選択します\> **SharePoint**。
    
4. 左側のウィンドウで**設定**を選択します。
    
5. **情報権利管理 (IRM)** セクションで、**構成では、指定された IRM サービスを使用して**、選択し、 **IRM の設定を更新**します。IRM の設定を更新すると、組織内のユーザー、SharePoint リストおよびドキュメント ライブラリで IRM を使用して開始できます。ただし、オプションこれを行うにかかる場合があります 1 時間ライブラリの設定と設定の一覧に表示します。
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM を有効にする SharePoint ドキュメント ライブラリとリスト
<a name="__toc220831191"> </a>

IRM の設定を更新すると、サイトの所有者は、SharePoint リストに [IRM で保護することができ、ドキュメント ライブラリです。詳細については、[リストまたはライブラリの情報権利管理の適用](apply-irm-to-a-list-or-library.md)を参照してください。
  
サイトの所有者は、リストまたはライブラリの IRM を有効にすると、は、そのリストまたはライブラリでサポートされているファイルの種類を保護することができます。ライブラリに対して IRM を有効に、権限の管理は、そのライブラリ内のファイルのすべてに適用されます。リストに対して IRM を有効にすると、実際のリスト アイテムではなくリスト アイテムに関連付けられているファイルにのみアクセス権管理が適用されます。
  
ユーザーは、IRM が有効なリストやライブラリ内のファイルをダウンロードするとき、ファイルが暗号化されるため、承認されたユーザーのみが表示ことができます。各権限が管理されたファイルには、ファイルを表示できるユーザーの制限を課する発行ライセンスも含まれています。典型的な制限、ファイルを読み取り専用にする、ローカル コピーを保存し、ファイルの印刷を禁止するから人を防止する、テキストのコピーを無効にします。IRM 対応のファイル タイプを読み取ることができるクライアント プログラムは、権限が管理されたファイル内でこれらの制限を適用するのに発行ライセンスを使用します。ダウンロードされた後にもに権限が管理されたファイルが、保護を保持する方法です。をリストまたはライブラリに IRM を有効にするのには、[リストまたはライブラリの情報権利管理の適用](apply-irm-to-a-list-or-library.md)を参照してください。
  
作成または Office オンラインを使用して、IRM が有効なライブラリのドキュメントを編集することはできません。代わりに、一度に 1 人のユーザーは、ダウンロードして、IRM で暗号化されたファイルを編集します。複数のユーザー間でチェックインし、*共同編集*を管理するためにチェック アウトまたはオーサリングを使用します。 
  
IRM で保護されたライブラリから PDF ファイルをダウンロードすると、Office 365 は、保護された PDF ファイルを作成します。ファイルの拡張子は変更されませんが、ファイルが保護されています。このファイルを表示する必要があります Azure の情報保護のビューアー、Azure の情報保護、完全なクライアント、または保護された PDF ファイルの表示をサポートしている別のアプリケーションです。 
  
SharePoint Online には、次のファイルの種類の暗号化がサポートされています。
  
- PDF
    
- 次の Microsoft Office プログラムの 97-2003 ファイル形式: Word、Excel、および PowerPoint
    
- 次の Microsoft Office プログラムの Office オープン XML の書式を設定します Word、Excel、および PowerPoint。
    
- XML 用紙仕様 (XPS) 形式
    
## <a name="next-steps"></a>次の手順
<a name="__toc220831191"> </a>

SharePoint Online の IRM を有効にして、リストやライブラリにアクセス権管理を適用することを開始できます。については、[リストまたはライブラリの情報権利管理の適用](apply-irm-to-a-list-or-library.md)を参照してください。
  
Windows 用の新しい OneDrive 同期クライアントでは、IRM で保護された SharePoint ドキュメント ライブラリおよび OneDrive の場所である限り、ライブラリの IRM 設定は、ドキュメントのアクセス権を期限切れに設定されていない) の同期をサポートしています。詳細については、または、新しい同期クライアントの展開を開始するには、 [Windows 用の新しい OneDrive 同期クライアントの展開](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668)を参照してください。
  
[ページの一番上](set-up-irm-in-sp-admin-center.md#__top)
  

