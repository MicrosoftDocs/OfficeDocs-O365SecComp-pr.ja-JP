---
title: office 365 の分離とアクセス制御 (office 365)
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '概要: Office 365 のさまざまなアプリケーションでの分離とアクセス制御について説明します。'
ms.openlocfilehash: 734c92a6f3185a25faf9aade1ba235444ed762da
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216857"
---
# <a name="isolation-and-access-control-in-office-365"></a>Office 365 での分離とアクセス制御

Azure Active Directory と Office 365 では、非常に複雑なデータモデルが使用されています。これには、数百のエンティティ、数千件の関係、および数万の属性 (エンティティ、リレーションシップ、属性は、アプリケーションに固有のもの) が含まれています。高レベルでは、Azure Active Directory とサービスディレクトリがテナントと受信者のコンテナーになり、状態ベースのレプリケーションプロトコルを使用して同期されたままになります。Azure Active directory 内に保持されているディレクトリ情報に加えて、各サービスにも独自のディレクトリサービスインフラストラクチャがあります (例: Exchange online ディレクトリサービス、SharePoint Online ディレクトリサービスなど)。 
 
![Office 365 テナントデータ同期](media/office-365-isolation-tenant-data-sync.png)

このモデルでは、ディレクトリデータの単一のソースはありません。個々のデータの各部分は特定のシステムによって所有されますが、すべてのデータが1つのシステムに保持されるわけではありません。Office 365 サービスは、Azure Active Directory と連携してデータモデルを実現します。Azure Active Directory は、共有データの "真実のシステム" です。通常、すべてのサービスで頻繁に使用される小さなデータおよび静的データです。Office 365 および Azure Active Directory 内で使用されているフェデレーションモデルは、データの共有ビューを提供します。

Office 365 は、物理ストレージと Azure クラウドストレージの両方を使用します。exchange online (exchange online Protection を含む) および Skype for business は、お客様のデータに独自のストレージを使用します。SharePoint Online では、SQL Server ストレージと Azure ストレージの両方を活用しているため、ストレージレベルでお客様のデータをさらに分離する必要があります。

## <a name="exchange-online"></a>Exchange Online
Exchange Online は、メールボックスデータベースと呼ばれる拡張記憶域エンジン (ESE) データベース内でホストされているメールボックス内に顧客データを格納します。これには、ユーザーメールボックス、リンクされたメールボックス、共有メールボックス、およびパブリックフォルダーメールボックスが含まれます。ユーザーメールボックスには、会話の履歴など、保存された Skype for business コンテンツを含めることもできます。ユーザーメールボックスのコンテンツには、メール、電子メールの添付ファイル、予定表と空き時間情報、連絡先、タスク、メモ、グループ、および推論データが含まれます。

Exchange Online 内の各メールボックスデータベースには、複数のテナントからのメールボックスが含まれています。すべてのメールボックスは、テナント内などの認証コードで保護されています。Exchange の社内展開と同様に、既定では、割り当てられたユーザーのみがメールボックスにアクセスできます。メールボックスをセキュリティで保護するアクセス制御リスト (ACL) には、テナントレベルで Azure Active Directory によって認証された id が含まれています。特定のテナントのメールボックスは、そのテナントの認証プロバイダーに対して認証された id に制限されます。これには、そのテナントのユーザーのみが含まれます。TenantA によって明示的に承認されていない限り、TenantA に属するコンテンツは、tenantb でユーザーが取得することはできません。

## <a name="skype-for-business"></a>Skype for Business
Skype for business は、さまざまな場所にデータを格納します。
- 接続エンドポイント、テナント id、ダイヤルプラン、ローミング設定、プレゼンス状態、連絡先リストなどが含まれるユーザーおよびアカウント情報は、skype for business の Active Directory サーバーに格納されるほか、さまざまな skype for business データベースに保存されます。サーバ.ユーザーが両方の製品に対して有効になっている場合、またはユーザーがいない場合、Skype for business サーバーでユーザーの Exchange Online メールボックスに連絡先リストが格納されます。Skype for business データベースサーバーはテナントごとにパーティション分割されませんが、マルチテナントのデータの分離は RBAC によって実行されます。
- Skype for business 会議中にコンテンツユーザーがアップロードするなどの会議コンテンツは、分散ファイルシステム共有に保存されます。このコンテンツは、Exchange Online でアーカイブすることもできます。アーカイブは有効になっています。DFS 共有はテナントごとにパーティション分割されませんが、コンテンツは acl で保護され、マルチテナントは RBAC を介して適用されます。
- 通話の詳細レコード (通話履歴、im セッション、アプリケーション共有、IM 履歴など) を Exchange Online に格納することもできますが、ほとんどの通話詳細レコードは、通話詳細記録 (CDR) サーバーに一時的に格納されます。コンテンツはテナントごとにパーティション分割されませんが、マルチテナントは RBAC を介して適用されます。

## <a name="sharepoint-online"></a>SharePoint Online
SharePoint Online には、データの分離を提供する、いくつかの独立したメカニズムがあります。SharePoint Online は、オブジェクトをアプリケーションデータベース内に抽象化されたコードとして格納します。たとえば、ユーザーがファイルを SharePoint Online にアップロードすると、そのファイルは逆アセンブルされてアプリケーションコードに変換され、複数のデータベースにわたって複数のテーブルに格納されます。

ユーザーがデータが格納されているストレージに直接アクセスできる場合、そのコンテンツは、人間または SharePoint Online 以外のシステムには解釈されません。これらのメカニズムには、セキュリティアクセス制御およびプロパティが含まれます。前述したように、すべての SharePoint Online リソースは、テナント内の認証コードおよび RBAC ポリシーによって保護されています。リソースを保護するアクセス制御リスト (ACL) には、テナントレベルで認証された id が含まれています。SharePoint online では、Exchange online と同様に、特定のテナントのデータは、そのテナントの認証プロバイダーに対して認証された id に制限されます。これには、そのテナントのユーザーのみが含まれます。

acl に加えて、認証プロバイダ (テナント固有の Azure Active Directory) を指定するテナントレベルのプロパティは一度書き込まれます。一度設定すると、設定後に変更することはできません。テナントに対して認証プロバイダのテナントプロパティを設定すると、テナントに公開されている api を使用して変更することはできません。

一意の*SubscriptionId*はテナントごとにも使用されます。すべての顧客サイトはテナントで所有され、テナントに固有の*SubscriptionId*が割り当てられます。サイトの*SubscriptionId*プロパティは一度だけ書き込まれ、変更することはできません。サイトは、テナントに割り当てられた後、コンテンツストア API を使用して後で別のテナントに移動することはできません。*SubscriptionId*は、認証プロバイダーのセキュリティスコープを作成するために使用されるキーでもあり、テナントに関連付けられています。

SharePoint Online は、コンテンツの格納に SQL Server と Azure ストレージを使用します。SQL レベルでは、コンテンツストアのパーティションキーは*SiteId*化されます。SQL クエリを実行すると、SharePoint Online はテナントレベルの*SubscriptionId*チェックの一部として確認された*SiteId*を使用します。

SharePoint Online は、Microsoft Azure でファイルバイナリ blob (ファイルストリームなど) を格納します。各 SharePoint Online ファームには独自の Microsoft Azure アカウントがあり、Azure に保存されているすべての blob は、SQL コンテンツストアに格納されているキーを使用して個別に暗号化されます。暗号化キーはエンドユーザーに直接公開されず、承認レイヤーによってコードで保護されます。最後に、SharePoint Online では、HTTP 要求が複数のテナントに対してデータを読み書きするタイミングを検出するためのリアルタイム監視が行われています。これは、アクセスされるリソースの*subscriptionid*に対して、要求 id の*subscriptionid*を追跡することによって行われます。複数のテナントのリソースにアクセスする要求は、エンドユーザーによって発生することはありません。これはマルチテナント環境でのサービス要求に対して発生する可能性があります。たとえば、検索クローラーは、データベース全体に対するコンテンツの変更を一度に1つずつ取得します。通常、1つのサービス要求で複数のテナントのサイトに対してクエリを実行する必要があります。これは、効率性上の理由によります。
