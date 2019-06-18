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
ms.openlocfilehash: 796ad0314374dca60d1ff5f6b9317be491b757a1
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014606"
---
# <a name="archive-third-party-data-in-office-365"></a><span data-ttu-id="025d5-105">Office 365 でサードパーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="025d5-105">Archive third-party data in Office 365</span></span>

<span data-ttu-id="025d5-106">Office 365 を使用すると、管理者はソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="025d5-106">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization.</span></span> <span data-ttu-id="025d5-107">Office 365 にインポートできるサードパーティのデータソースの例としては、次のサービスがあります。</span><span class="sxs-lookup"><span data-stu-id="025d5-107">Examples of third-party data sources that you can import to Office 365 include the following services:</span></span> 
  
- <span data-ttu-id="025d5-108">**Social** – Facebook、LinkedIn、Twitter、Yammer</span><span class="sxs-lookup"><span data-stu-id="025d5-108">**Social** – Facebook, LinkedIn, Twitter, and Yammer</span></span> 
    
- <span data-ttu-id="025d5-109">**インスタントメッセージング**– Yahoo メッセンジャー、GoogleTalk、および Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="025d5-109">**Instant messaging** – Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="025d5-110">**ドキュメントのコラボレーション**-ボックスとドロップボックス</span><span class="sxs-lookup"><span data-stu-id="025d5-110">**Document collaboration** – Box and DropBox</span></span> 
    
- <span data-ttu-id="025d5-111">**縦型産業**–顧客関係管理 (Salesforce チャターなど) や金融サービス (Bloomberg、Thomson Reuters など)</span><span class="sxs-lookup"><span data-stu-id="025d5-111">**Vertical industries** – Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span> 
    
- <span data-ttu-id="025d5-112">**SMS/text messaging** – BlackBerry</span><span class="sxs-lookup"><span data-stu-id="025d5-112">**SMS/text messaging** – BlackBerry</span></span> 
    
<span data-ttu-id="025d5-113">サードパーティのデータがインポートされた後は、訴訟ホールド、電子情報開示、インプレースアーカイブ、監査、監督、Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能をこのデータに適用できます。</span><span class="sxs-lookup"><span data-stu-id="025d5-113">After third-party data is imported, you can apply Office 365 compliance features — such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies — to this data.</span></span> <span data-ttu-id="025d5-114">たとえば、メールボックスが訴訟ホールドに配置されると、サード パーティ のデータは保存されます。</span><span class="sxs-lookup"><span data-stu-id="025d5-114">For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved.</span></span> <span data-ttu-id="025d5-115">Microsoft eDiscovery ツールを使用して、サードパーティのデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="025d5-115">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="025d5-116">Microsoft のデータの場合と同じように、アーカイブ ポリシーと保持ポリシーをサード パーティのデータに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="025d5-116">Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="025d5-117">簡単に言えば、Office 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="025d5-117">In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="025d5-118">Office 365 でサードパーティのデータをインポートしてアーカイブするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="025d5-118">There are two ways to import and archive third-party data in Office 365:</span></span>

- <span data-ttu-id="025d5-119">**セキュリティ & コンプライアンスセンターでサードパーティのデータコネクタを使用**する-Office 365 のセキュリティ & コンプライアンスセンターで利用可能なカスタムデータコネクタを使用します。</span><span class="sxs-lookup"><span data-stu-id="025d5-119">**Use a third-party data connector in the Security & Compliance Center** – Use a custom data connector that's available in the Security & Compliance Center in Office 365.</span></span> <span data-ttu-id="025d5-120">コネクタをセットアップして構成すると、サードパーティのデータソースに接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、Office 365 のメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="025d5-120">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Office 365.</span></span> <span data-ttu-id="025d5-121">現時点では、Facebook のビジネスページ、企業 Twitter アカウント、インスタント Bloomberg、LinkedIn からデータをインポートしてアーカイブするためのコネクタを実装できます。</span><span class="sxs-lookup"><span data-stu-id="025d5-121">At this time, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, Instant Bloomberg, and LinkedIn.</span></span> <span data-ttu-id="025d5-122">コネクタを設定するための詳しい手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="025d5-122">For the step-by-step instructions to set up a connector, see:</span></span>
   
   - <span data-ttu-id="025d5-123">**Facebook** –[サンプルコネクタを使用して Office 365 で Facebook データをアーカイブする](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="025d5-123">**Facebook** – [Use a sample connector to archive Facebook data in Office 365](archive-facebook-data-with-sample-connector.md)</span></span>
  
   - <span data-ttu-id="025d5-124">**Twitter** –[サンプルコネクタを使用して Office 365 で Twitter データをアーカイブする](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="025d5-124">**Twitter** – [Use a sample connector to archive Twitter data in Office 365](archive-twitter-data-with-sample-connector.md)</span></span>
    
   - <span data-ttu-id="025d5-125">**Linkedin** – [Office 365 で linkedin データをアーカイブするためのコネクタの設定](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="025d5-125">**LinkedIn** – [Set up a connector to archive LinkedIn data in Office 365](archive-linkedin-data.md)</span></span>

- <span data-ttu-id="025d5-126">**Microsoft パートナーと連携**する-組織は、サードパーティのデータソースからアイテムを抽出するように構成されたカスタムコネクタを (定期的に) 提供する microsoft パートナーと連携して、次に microsoft クラウドに接続します。サードパーティ API を行い、それらのアイテムを Office 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="025d5-126">**Work with a Microsoft partner** – Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source (on a regular basis) and then connect to the Microsoft cloud by a third-party API and import those items to Office 365.</span></span> <span data-ttu-id="025d5-127">また、パートナーコネクタは、アイテムのコンテンツをサードパーティのデータソースから電子メールメッセージに変換し、それを Office 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="025d5-127">The partner connector also converts the content of an item from the third-party data source to an email message and then imports them to a mailbox in Office 365.</span></span> <span data-ttu-id="025d5-128">この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「Office を使用して[サードパーティデータをアーカイブする 365](work-with-partner-to-archive-third-party-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="025d5-128">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>