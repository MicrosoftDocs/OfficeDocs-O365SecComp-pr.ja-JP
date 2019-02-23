---
title: Office 365 のコンテンツを検索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/4/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Office 365 セキュリティ&amp;コンプライアンスセンターのコンテンツ検索電子情報開示ツールを使用すると、Exchange メールボックス内の電子メール、SharePoint サイトと OneDrive の場所のドキュメント、および Skype for business でのインスタントメッセージングの会話をすばやく見つけることができます。
ms.openlocfilehash: 255ddbde4488ab5e7d13872cea95398ed5fd4d75
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214537"
---
# <a name="search-for-content-in-office-365"></a>Office 365 のコンテンツを検索

セキュリティ&amp;コンプライアンスセンターのコンテンツ検索ツールを使用すると、Exchange メールボックス内の電子メール、SharePoint サイトと OneDrive の場所にあるドキュメント、および Skype for business でのインスタントメッセージングの会話をすばやく見つけることができます。コンテンツ検索ツールを使用して、Microsoft Teams や office 365 グループなどの office 365 コラボレーションツールで、電子メール、ドキュメント、インスタントメッセージの会話を検索することができます。
  
## <a name="search-for-content"></a>コンテンツを検索する

最初の手順として、コンテンツ検索ツールを使用して、検索するコンテンツの場所を選択し、特定のアイテムを検索するキーワードクエリを構成します。または、クエリを空白のままにして、対象の場所にあるすべてのアイテムを返すこともできます。
  
- コンテンツ検索を[作成して実行](content-search.md)する 
    
- [検索クエリを作成し、条件を使用](keyword-queries-and-search-conditions.md)して検索を絞り込む 
    
- 電子情報開示管理者が組織内のメールボックスまたはサイトのサブセットのみを検索できるように、[検索アクセス許可フィルターを構成](permissions-filtering-for-content-search.md)する 
    
- [ID リスト検索を実行](csv-file-for-an-id-list-content-search.md)して特定の電子メールメッセージを検索する 
    
- Office 365 でオンプレミスのユーザーの[クラウドベースのメールボックスを検索](search-cloud-based-mailboxes-for-on-premises-users.md)する

- 検索結果の[キーワード統計を表示](view-keyword-statistics-for-content-search.md)し、必要に応じてクエリを修正します。 
    
- 組織が Office 365 にインポートした[サードパーティのデータを検索](use-content-search-to-search-third-party-data-that-was-imported.md)する 
    
- 複数の検索のためにクエリとコンテンツの場所を[一括編集](bulk-edit-content-searches.md)する 
    
- [Bcc の受信者を保持](https://docs.microsoft.com/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members)して検索できるようにする 

## <a name="perform-actions-on-content-you-find"></a>検索したコンテンツに対してアクションを実行する

検索を実行し、必要に応じて絞り込みを行うと、次の手順は検索で返された結果を使用して何らかの処理を行います。結果をローカルコンピューターにエクスポートしてダウンロードできます。または、組織で電子メールを攻撃した場合は、ユーザーのメールボックスから検索結果を削除することができます。
  
- [コンテンツ検索の結果をエクスポート](export-search-results.md)して、ローカルコンピューターにダウンロードする 
    
- [電子メールメッセージの検索と削除](search-for-and-delete-messages-in-your-organization.md)(ウイルスに感染したメッセージ、危険な添付ファイルまたはフィッシングメッセージなど) 
    
- 実際の結果をエクスポートせずに、コンテンツ検索の結果に関する[レポートをエクスポートする](export-a-content-search-report.md) 
    
- 検索結果をエクスポートするときに[ダウンロード速度を上げる](increase-download-speeds-when-exporting-ediscovery-results.md) 
    
## <a name="learn-more-about-content-search"></a>コンテンツ検索の詳細情報

コンテンツ検索は簡単に使用できますが、強力なツールでもあります。舞台裏では、多くのことが進行しています。it の理解を深め、その動作とその制限を理解すると、組織の検索と調査のニーズに合わせて使用できるようになりました。次の項目について説明します。
  
- [Exchange と SharePoint の部分的にインデックス](partially-indexed-items-in-content-search.md)が作成されたアイテム、および検索結果をエクスポートおよびダウンロードするときにそれらを含めるか除外するかを指定します。 
    
- [部分的にインデックス](investigating-partially-indexed-items-in-ediscovery.md)が作成されたアイテムを調べて、組織のリスクを確認する 
    
- [コンテンツ検索ツールの制限](limits-for-content-search.md)(一度に実行できる検索の最大数、および単一の検索に含めることができるコンテンツの場所の最大数など) 
    
- 検索結果をエクスポートしてダウンロードするときに、[予想および実際の検索結果](differences-between-estimated-and-actual-ediscovery-search-results.md)とそれらの間に違いがある理由 
    
- 検索の結果である電子メールメッセージをエクスポートするときに有効にできる[検索結果の重複除外](de-duplication-in-ediscovery-search-results.md) 
    
## <a name="use-scripts-for-advanced-scenarios"></a>高度なシナリオでスクリプトを使用する

より高度で複雑で反復的なコンテンツ検索タスクを実行する必要がある場合があります。このような場合は、セキュリティ&amp; /コンプライアンスセンターで PowerShell コマンドを使用する方が簡単で高速です。これを簡単にするために、多数のセキュリティ&amp;コンプライアンスセンター PowerShell スクリプトを作成し、複雑なコンテンツ検索関連タスクを完了できるようにしました。
  
- [特定のメールボックスおよびサイトフォルダーを検索](use-content-search-for-targeted-collections.md)する(対象の*コレクション*と呼ばれます) ケースに応答するアイテムがそのフォルダー内にあることを確信している場合 
    
- [メールボックスおよび OneDrive の場所](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md)でユーザーの一覧を検索する 
    
- [複数の検索を作成、レポート、および削除](create-report-on-and-delete-multiple-content-searches.md)して、検索データを迅速かつ効率的に識別し、選別する 
    
- [コンテンツ検索を複製](clone-a-content-search.md)し、同じコンテンツの場所で実行されるさまざまなキーワード検索クエリの結果をすばやく比較します。または、新しい検索を作成するときに大量のコンテンツの場所を再入力する必要がないため、スクリプトを使用して時間を節約することができます。 
    

