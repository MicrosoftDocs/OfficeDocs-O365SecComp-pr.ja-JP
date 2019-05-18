---
title: テーマ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: b26b031b767f23504294880f4424be5042350c71
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151439"
---
# <a name="themes"></a><span data-ttu-id="4191d-102">テーマ</span><span class="sxs-lookup"><span data-stu-id="4191d-102">Themes</span></span>
<span data-ttu-id="4191d-103">ユーザーがドキュメントを作成する方法</span><span class="sxs-lookup"><span data-stu-id="4191d-103">How does a person write a document?</span></span> <span data-ttu-id="4191d-104">通常は、ドキュメントに伝えたい1つ以上のアイデアから始め、アイデアに沿った単語を使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="4191d-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="4191d-105">最も普及しているのは、その概念に関連する単語が頻繁に発生する傾向があるということです。</span><span class="sxs-lookup"><span data-stu-id="4191d-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="4191d-106">これにより、ユーザーがドキュメントをどのように使用するかを知ることができます。ドキュメントの閲覧に関する重要な点として、ドキュメントが伝達しようとしているアイデアと、アイデア間の関係について説明します。</span><span class="sxs-lookup"><span data-stu-id="4191d-106">This informs how people consume documents as well; the important thing to get from reading a document is the ideas that the document is trying to convey, and which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="4191d-107">これは、ユーザーが一連のドキュメントを使用する方法に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="4191d-107">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="4191d-108">そのようなアイデアについて、どのようなアイデアがどのドキュメントに含まれているかを確認したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="4191d-108">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="4191d-109">また、関心のある特定のドキュメントが見つかった場合は、同様のアイデアについてのドキュメントを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4191d-109">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="4191d-110">Themes モジュールは、校閲セットに記載されている "テーマ" を分析し、ドキュメントに割り当てることによって、ドキュメントに関する人間の理由を模倣します。</span><span class="sxs-lookup"><span data-stu-id="4191d-110">Themes module tries to mimic how humans reason about documents, by analyzing the "themes" that are discussed in a review set and assigning them to documents.</span></span> <span data-ttu-id="4191d-111">テーマは、さらに1つの手順に進み、ドキュメントごとに "優先テーマ" を示します。つまり、最もよく表示されるテーマ。</span><span class="sxs-lookup"><span data-stu-id="4191d-111">Themes goes one step further and identifies per document the "dominant theme"; i.e. the theme that appears the most.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="4191d-112">テーマはどのように機能しますか?</span><span class="sxs-lookup"><span data-stu-id="4191d-112">How does Themes work?</span></span>
<span data-ttu-id="4191d-113">テーマは、ドキュメント全体にわたって表示される共通のテーマを解析するために、校閲セット内のテキストが含まれるドキュメントを分析します。</span><span class="sxs-lookup"><span data-stu-id="4191d-113">Themes analyzes documents with text in a review set to parse out common themes that appear accross the documents.</span></span> <span data-ttu-id="4191d-114">その後、それらのテーマが表示されるドキュメントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4191d-114">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="4191d-115">また、それぞれのテーマの代表的なドキュメントで使用されている単語にラベル付けします。</span><span class="sxs-lookup"><span data-stu-id="4191d-115">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="4191d-116">ドキュメントには複数の件名が含まれることがあるため、多くの場合、ドキュメントには複数のテーマが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="4191d-116">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="4191d-117">ドキュメントで最も目立つテーマは、優先するテーマとして指定されています。</span><span class="sxs-lookup"><span data-stu-id="4191d-117">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>