---
title: Office 365 でサードパーティのデータをアーカイブする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理者は、ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートできます。 これにより、Office 365 で Facebook、Twitter、およびその他のサードパーティのデータソースからデータをアーカイブすることができます。 その後、サードパーティデータの Office 365 コンプライアンス機能 (法的情報保留、電子情報開示、インプレースアーカイブ、アイテム保持ポリシーなど) を使用して適用することができます。
ms.openlocfilehash: 33ce9c0d648d0c247abcaac8838e351d413a1990
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152086"
---
# <a name="archive-third-party-data-in-office-365"></a><span data-ttu-id="37b39-105">Office 365 でサードパーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="37b39-105">Archive third-party data in Office 365</span></span>

<span data-ttu-id="37b39-106">Office 365 を使用すると、管理者はソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="37b39-106">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization.</span></span> <span data-ttu-id="37b39-107">Office 365 にインポートできるサードパーティのデータソースの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="37b39-107">Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="37b39-108">**ソーシャル**Twitter、Facebook、Yammer、および LinkedIn</span><span class="sxs-lookup"><span data-stu-id="37b39-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="37b39-109">**インスタントメッセージング**-Yahoo メッセンジャー、GoogleTalk、および Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="37b39-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="37b39-110">**ドキュメントのコラボレーション**-ボックスとドロップボックス</span><span class="sxs-lookup"><span data-stu-id="37b39-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="37b39-111">**垂直産業**-顧客関係管理 (Salesforce チャターなど)、金融サービス (Bloomberg、Thomson Reuters など)</span><span class="sxs-lookup"><span data-stu-id="37b39-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span> 
    
- <span data-ttu-id="37b39-112">**SMS/text messaging** -BlackBerry</span><span class="sxs-lookup"><span data-stu-id="37b39-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="37b39-113">サードパーティのデータがインポートされた後は、訴訟ホールド、電子情報開示、インプレースアーカイブ、監査、監督、Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能をこのデータに適用できます。</span><span class="sxs-lookup"><span data-stu-id="37b39-113">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies—to this data.</span></span> <span data-ttu-id="37b39-114">たとえば、メールボックスが訴訟ホールドに配置されると、サード パーティ のデータは保存されます。</span><span class="sxs-lookup"><span data-stu-id="37b39-114">For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved.</span></span> <span data-ttu-id="37b39-115">Microsoft eDiscovery ツールを使用して、サードパーティのデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="37b39-115">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="37b39-116">Microsoft のデータの場合と同じように、アーカイブ ポリシーと保持ポリシーをサード パーティのデータに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="37b39-116">Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="37b39-117">簡単に言えば、Office 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="37b39-117">In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="37b39-118">Office 365 でサードパーティのデータをインポートしてアーカイブするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="37b39-118">There are two ways to import and archive third-party data in Office 365:</span></span>

- <span data-ttu-id="37b39-119">**セキュリティ _AMP_ コンプライアンスセンターでサードパーティのデータコネクタを使用**します。 Office 365 のセキュリティ _AMP_ コンプライアンスセンターで利用可能なカスタムデータコネクタを使用します。</span><span class="sxs-lookup"><span data-stu-id="37b39-119">**Use a third-party data connector in the Security & Compliance Center** - Use a custom data connector that's available in the Security & Compliance Center in Office 365.</span></span> <span data-ttu-id="37b39-120">コネクタをセットアップして構成すると、サードパーティのデータソースに接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、Office 365 のメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="37b39-120">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Office 365.</span></span> <span data-ttu-id="37b39-121">現在、サンプルコネクタを実装して、Facebook のビジネスページと Twitter からデータをインポートおよびアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="37b39-121">Currently, you can implement sample connectors to import and archive data from Facebook Business pages and Twitter.</span></span> <span data-ttu-id="37b39-122">コネクタを設定するための詳しい手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37b39-122">For the step-by-step instructions to set up a connector, see:</span></span>
   
   - <span data-ttu-id="37b39-123">**Facebook** - [でサンプルコネクタを使用して Office 365 で Facebook データをアーカイブする (プレビュー)](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="37b39-123">**Facebook** - [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md)</span></span>
  
   - <span data-ttu-id="37b39-124">**Twitter** - [サンプルコネクタを使用して Office 365 で twitter データをアーカイブする (プレビュー)](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="37b39-124">**Twitter** - [Use a sample connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md)</span></span>

- <span data-ttu-id="37b39-125">**Microsoft パートナーと協力**して、組織は、サードパーティのデータソースからアイテムを抽出するように構成されたカスタムコネクタを (定期的に)、Microsoft のパートナーと連携させることができます。サードパーティ API を行い、それらのアイテムを Office 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="37b39-125">**Work with a Microsoft partner** - Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source (on a regular basis) and then connect to the Microsoft cloud by a third-party API and import those items to Office 365.</span></span> <span data-ttu-id="37b39-126">また、パートナーコネクタは、アイテムのコンテンツをサードパーティのデータソースから電子メールメッセージに変換し、それを Office 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="37b39-126">The partner connector also converts the content of an item from the third-party data source to an email message and then imports them to a mailbox in Office 365.</span></span> <span data-ttu-id="37b39-127">この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「Office を使用して[サードパーティデータをアーカイブする 365](work-with-partner-to-archive-third-party-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37b39-127">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>