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
ms.openlocfilehash: 4b6236a7eaac4fa061d1cfbb770efd0a721804aa
ms.sourcegitcommit: a550519ca8f2a54712bf0a43be7f954e55675dac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "35902459"
---
# <a name="archive-third-party-data-in-office-365"></a><span data-ttu-id="bcfde-105">Office 365 でサードパーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="bcfde-105">Archive third-party data in Office 365</span></span>

<span data-ttu-id="bcfde-106">Office 365 を使用すると、管理者はソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="bcfde-106">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization.</span></span> <span data-ttu-id="bcfde-107">Office 365 にインポートできるサードパーティのデータソースの例としては、次のサービスがあります。</span><span class="sxs-lookup"><span data-stu-id="bcfde-107">Examples of third-party data sources that you can import to Office 365 include the following services:</span></span> 
  
- <span data-ttu-id="bcfde-108">**ソーシャル:** Facebook、LinkedIn、Twitter、Yammer</span><span class="sxs-lookup"><span data-stu-id="bcfde-108">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span> 
    
- <span data-ttu-id="bcfde-109">**インスタントメッセージング:** Yahoo! メッセンジャー、GoogleTalk、および Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="bcfde-109">**Instant messaging:** Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="bcfde-110">**ドキュメントの共同作業:** Box および DropBox</span><span class="sxs-lookup"><span data-stu-id="bcfde-110">**Document collaboration:** Box and DropBox</span></span> 
    
- <span data-ttu-id="bcfde-111">**縦型の業種:** 顧客関係管理 (Salesforce チャターなど)、金融サービス (Bloomberg、Thomson Reuters など)</span><span class="sxs-lookup"><span data-stu-id="bcfde-111">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span> 
    
- <span data-ttu-id="bcfde-112">**SMS/テキストメッセージング:** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="bcfde-112">**SMS/text messaging:** BlackBerry</span></span> 
    
<span data-ttu-id="bcfde-113">サードパーティのデータをインポートした後、訴訟ホールド、電子情報開示、インプレースアーカイブ、監査、監督、Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能をこのデータに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="bcfde-113">After third-party data is imported, you can apply Office 365 compliance features – such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies – to this data.</span></span> <span data-ttu-id="bcfde-114">たとえば、メールボックスが訴訟ホールドの対象となっている場合、サードパーティのデータは保持されます。</span><span class="sxs-lookup"><span data-stu-id="bcfde-114">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="bcfde-115">Microsoft eDiscovery ツールを使用して、サードパーティのデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="bcfde-115">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="bcfde-116">また、Microsoft データの場合と同じように、アーカイブポリシーとアイテム保持ポリシーをサードパーティデータに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="bcfde-116">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="bcfde-117">簡単に言えば、Office 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="bcfde-117">In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="bcfde-118">Office 365 でサードパーティのデータをインポートしてアーカイブするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="bcfde-118">There are two ways to import and archive third-party data in Office 365:</span></span>

- <span data-ttu-id="bcfde-119">**セキュリティ & コンプライアンスセンターで、サードパーティのデータコネクタを使用します。** Office 365 のセキュリティ & コンプライアンスセンターで利用可能なカスタムデータコネクタを使用します。</span><span class="sxs-lookup"><span data-stu-id="bcfde-119">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Security & Compliance Center in Office 365.</span></span> <span data-ttu-id="bcfde-120">コネクタをセットアップして構成すると、サードパーティのデータソースに接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、Office 365 のメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="bcfde-120">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Office 365.</span></span> <span data-ttu-id="bcfde-121">現時点では、Facebook のビジネスページ、企業 Twitter アカウント、インスタント Bloomberg、LinkedIn からデータをインポートしてアーカイブするためのコネクタを実装できます。</span><span class="sxs-lookup"><span data-stu-id="bcfde-121">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, Instant Bloomberg, and LinkedIn.</span></span> <span data-ttu-id="bcfde-122">コネクタを設定するための詳しい手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfde-122">For the step-by-step instructions to set up a connector, see:</span></span>
   
   - <span data-ttu-id="bcfde-123">**Facebook:**[サンプルコネクタを使用して Office 365 で Facebook データをアーカイブする](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="bcfde-123">**Facebook:** [Use a sample connector to archive Facebook data in Office 365](archive-facebook-data-with-sample-connector.md)</span></span>
  
   - <span data-ttu-id="bcfde-124">**Twitter:**[サンプルコネクタを使用して Office 365 で Twitter データをアーカイブする](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="bcfde-124">**Twitter:** [Use a sample connector to archive Twitter data in Office 365](archive-twitter-data-with-sample-connector.md)</span></span>
    
   - <span data-ttu-id="bcfde-125">**LinkedIn:**[Office 365 で LinkedIn データをアーカイブするためのコネクタの設定](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="bcfde-125">**LinkedIn:** [Set up a connector to archive LinkedIn data in Office 365](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="bcfde-126">**インスタント Bloomberg:**[Office 365 でインスタント Bloomberg データをアーカイブするためのコネクタを設定する](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="bcfde-126">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data in Office 365](archive-instant-bloomberg-data.md)</span></span>

- <span data-ttu-id="bcfde-127">**Microsoft パートナーと連携する:** 組織は、サードパーティのデータソースからアイテムを定期的に抽出するように構成されるカスタムコネクタを提供する Microsoft パートナーと連携して、サードパーティの API によって Microsoft クラウドに接続し、それらのアイテムをインポートします。Office 365</span><span class="sxs-lookup"><span data-stu-id="bcfde-127">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Office 365.</span></span> <span data-ttu-id="bcfde-128">また、パートナーコネクタは、アイテムのコンテンツをサードパーティのデータソースから電子メールメッセージに変換し、それを Office 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="bcfde-128">The partner connector also converts the content of an item from the third-party data source to an email message and then imports them to a mailbox in Office 365.</span></span> <span data-ttu-id="bcfde-129">この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「Office を使用して[サードパーティデータをアーカイブする 365](work-with-partner-to-archive-third-party-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcfde-129">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>
