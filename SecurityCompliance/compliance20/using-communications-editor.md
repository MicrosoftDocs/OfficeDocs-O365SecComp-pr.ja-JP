---
title: 通信エディターを使用する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c2957c88217bce4c9a34f8d3f9a9e291f1223cc9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241244"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="922b2-102">通信エディターを使用する</span><span class="sxs-lookup"><span data-stu-id="922b2-102">Use the communications editor</span></span>

<span data-ttu-id="922b2-103">ポータルコンテンツ、法的情報保留通知、および関連する事前通知/エスカレーションの内容を定義する際に、コミュニケーションエディターを活用して、コンテンツの書式設定や動的なカスタマイズを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="922b2-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="922b2-104">リッチテキストエディター</span><span class="sxs-lookup"><span data-stu-id="922b2-104">Rich text editor</span></span> 

<span data-ttu-id="922b2-105">コミュニケーションエディターを使用すると、ユーザーはエディターのオプションを使用してテキストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="922b2-105">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="922b2-106">たとえば、ユーザーはフォントの種類を変更したり、箇条書きのリストを作成したり、コンテンツを強調表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="922b2-106">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="922b2-107">差し込みフィールドの変数</span><span class="sxs-lookup"><span data-stu-id="922b2-107">Merge field variables</span></span>

<span data-ttu-id="922b2-108">コミュニケーションエディターから電子メールの宛名差し込み変数を活用して、カスタマイズされた保管担当者属性をコミュニケーションの本文テキストに埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="922b2-108">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="922b2-109">保管担当者に送信されると、対応するフィールドが差し込み印刷フィールドに設定されます。</span><span class="sxs-lookup"><span data-stu-id="922b2-109">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="922b2-110">たとえば、保管担当者 John Smith に送信された場合、差し込み印刷フィールド [保管担当者 Name] は対応する名前に変換されます。</span><span class="sxs-lookup"><span data-stu-id="922b2-110">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="922b2-111">電子メールの宛名差し込みフィールドを使用するには、リッチテキストエディターコントロールの上部にある**差し込み印刷フィールド**アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="922b2-111">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="922b2-112">プレースホルダーは、ユーザーのカーソルの位置に基づいて追加されます。</span><span class="sxs-lookup"><span data-stu-id="922b2-112">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="922b2-113">差し込みフィールドの変数の一覧</span><span class="sxs-lookup"><span data-stu-id="922b2-113">List of merge field variables</span></span>

| <span data-ttu-id="922b2-114">フィールド名</span><span class="sxs-lookup"><span data-stu-id="922b2-114">Field name</span></span>                  | <span data-ttu-id="922b2-115">フィールドの詳細</span><span class="sxs-lookup"><span data-stu-id="922b2-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="922b2-116">表示名</span><span class="sxs-lookup"><span data-stu-id="922b2-116">Display Name</span></span>  | <span data-ttu-id="922b2-117">保管担当者の姓と名。</span><span class="sxs-lookup"><span data-stu-id="922b2-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="922b2-118">確認のリンク</span><span class="sxs-lookup"><span data-stu-id="922b2-118">Acknowledgement Link</span></span> | <span data-ttu-id="922b2-119">各保管担当者の受信確認を記録するためのカスタマイズされたリンク。</span><span class="sxs-lookup"><span data-stu-id="922b2-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="922b2-120">ポータルリンク</span><span class="sxs-lookup"><span data-stu-id="922b2-120">Portal Link</span></span>     | <span data-ttu-id="922b2-121">保管担当者のコンプライアンスポータル用のカスタマイズされたリンク。</span><span class="sxs-lookup"><span data-stu-id="922b2-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="922b2-122">発行責任者</span><span class="sxs-lookup"><span data-stu-id="922b2-122">Issuing Officer</span></span>                   | <span data-ttu-id="922b2-123">指定した発行担当者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="922b2-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="922b2-124">発行日</span><span class="sxs-lookup"><span data-stu-id="922b2-124">Issuing Date</span></span>                   | <span data-ttu-id="922b2-125">通知が発行された日付 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="922b2-125">The date that the notice was issued (UTC).</span></span>              |