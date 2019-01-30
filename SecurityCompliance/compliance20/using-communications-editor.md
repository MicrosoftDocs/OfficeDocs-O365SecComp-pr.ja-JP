---
title: 通信エディターを使用してください。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 107f45510bcf70942c6f03bdfed0a9090f1d83c0
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608025"
---
# <a name="using-the-communications-editor"></a><span data-ttu-id="0a7b1-102">通信エディターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="0a7b1-102">Using the Communications Editor</span></span>
<span data-ttu-id="0a7b1-103">ポータル コンテンツの内容を定義すると、法的な通知、および関連する通知/エスカレーションの保持、通信エディターを使用して書式を設定し、コンテンツを動的にカスタマイズを活用することができます。</span><span class="sxs-lookup"><span data-stu-id="0a7b1-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="0a7b1-104">リッチ テキスト エディター</span><span class="sxs-lookup"><span data-stu-id="0a7b1-104">Rich-Text Editor</span></span> 

<span data-ttu-id="0a7b1-p101">通信エディターは、エディターのオプションを使用してテキストをカスタマイズするユーザーを許可します。たとえば、ユーザーは、フォントの種類を変更する、箇条書きリスト、強調表示のコンテンツを作成します。</span><span class="sxs-lookup"><span data-stu-id="0a7b1-p101">The Communications Editor allows user to customize the text using the editor options. For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

<<include screenshot>>

## <a name="merge-field-variables"></a><span data-ttu-id="0a7b1-107">フィールド変数をマージします。</span><span class="sxs-lookup"><span data-stu-id="0a7b1-107">Merge Field Variables</span></span>

<span data-ttu-id="0a7b1-p102">メール マージ変数通信の本文に管理者がカスタマイズした属性を埋め込むには、通信エディターからを利用できます。管理者に送信されると、差し込み印刷フィールドは対応するフィールドに入力されます。たとえば、John Smith の管理者に送信されると、差し込み印刷フィールドの [管理者名] 変換される対応する名前を持つ。</span><span class="sxs-lookup"><span data-stu-id="0a7b1-p102">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text. When sent to the custodian, the merge field will be populated with the corresponding field. For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="0a7b1-p103">電子メールの差し込み印刷フィールドを使用するには、リッチ テキスト エディター コントロールの上部にある **[差し込みフィールド**のアイコンを選択します。プレース ホルダーは、ユーザーのカーソルの位置をベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="0a7b1-p103">You can use email merge fields by selecting the **Merge Field** icons on the top of the rich-text editor control. The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="0a7b1-113">差し込み印刷フィールドの変数のリスト</span><span class="sxs-lookup"><span data-stu-id="0a7b1-113">List of Merge Field Variables</span></span>
| <span data-ttu-id="0a7b1-114">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0a7b1-114">Field Name</span></span>                  | <span data-ttu-id="0a7b1-115">フィールドの詳細</span><span class="sxs-lookup"><span data-stu-id="0a7b1-115">Field Details</span></span> | 
| :------------------- | :-------------------: |
| <span data-ttu-id="0a7b1-116">表示名</span><span class="sxs-lookup"><span data-stu-id="0a7b1-116">Display Name</span></span>  | <span data-ttu-id="0a7b1-117">保管担当者の名字と名前</span><span class="sxs-lookup"><span data-stu-id="0a7b1-117">Custodian's first and last name</span></span> | 
| <span data-ttu-id="0a7b1-118">受信確認のリンク</span><span class="sxs-lookup"><span data-stu-id="0a7b1-118">Acknowledgement Link</span></span>                 | <span data-ttu-id="0a7b1-119">各管理者の承認を記録するためのカスタマイズしたリンク</span><span class="sxs-lookup"><span data-stu-id="0a7b1-119">Customized link to record each custodian's acknowledgement</span></span>                 |
| <span data-ttu-id="0a7b1-120">ポータル リンク</span><span class="sxs-lookup"><span data-stu-id="0a7b1-120">Portal Link</span></span>     | <span data-ttu-id="0a7b1-121">コンプライアンス ・ ポータルの管理者のカスタマイズしたリンク</span><span class="sxs-lookup"><span data-stu-id="0a7b1-121">Customized link for the custodian's Compliance Portal</span></span>                 |
| <span data-ttu-id="0a7b1-122">発行責任者</span><span class="sxs-lookup"><span data-stu-id="0a7b1-122">Issuing Officer</span></span>                   | <span data-ttu-id="0a7b1-123">指定した発行責任者の電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="0a7b1-123">Email address of the specified issuing officer</span></span>                   |
| <span data-ttu-id="0a7b1-124">発行日</span><span class="sxs-lookup"><span data-stu-id="0a7b1-124">Issuing Date</span></span>                   | <span data-ttu-id="0a7b1-125">(UTC)、通知が発行された日付</span><span class="sxs-lookup"><span data-stu-id="0a7b1-125">date that the notice was issued (UTC)</span></span>              |