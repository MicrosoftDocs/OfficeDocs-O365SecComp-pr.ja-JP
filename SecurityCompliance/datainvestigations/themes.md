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
ms.openlocfilehash: 398ad007f62e340bd10114810d5efabbb329e00e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153569"
---
# <a name="themes"></a><span data-ttu-id="9768d-102">テーマ</span><span class="sxs-lookup"><span data-stu-id="9768d-102">Themes</span></span>

<span data-ttu-id="9768d-103">ユーザーがドキュメントを合成するときに、ランダムに単語を選択することはありません。これらのユーザーは、いくつかのアイデアや概念を伝えるようにしており、それに応じて単語が選択されます。</span><span class="sxs-lookup"><span data-stu-id="9768d-103">When someone composes a document, they do not choose words randomly; they are trying to convey some ideas or concepts, and the words are chosen accordingly.</span></span> <span data-ttu-id="9768d-104">Themes モジュールは、同じような主題について議論するドキュメントをクラスター化し、校閲者がドキュメントをより効率的に進めることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="9768d-104">Themes modules clusters documents that discuss similar subject matters so that reviewers can be more efficient in going through documents.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="9768d-105">テーマはどのように機能しますか?</span><span class="sxs-lookup"><span data-stu-id="9768d-105">How does Themes work?</span></span>

<span data-ttu-id="9768d-106">テーマは、ドキュメント全体にわたって表示される共通のテーマを解析するために、作業セット内のテキストが含まれるドキュメントを分析します。</span><span class="sxs-lookup"><span data-stu-id="9768d-106">Themes analyzes documents with text in a working set to parse out common themes that appear accross the documents.</span></span> <span data-ttu-id="9768d-107">その後、それらのテーマが表示されるドキュメントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9768d-107">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="9768d-108">また、それぞれのテーマの代表的なドキュメントで使用されている単語にラベル付けします。</span><span class="sxs-lookup"><span data-stu-id="9768d-108">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="9768d-109">ドキュメントには複数の件名が含まれることがあるため、多くの場合、ドキュメントには複数のテーマが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="9768d-109">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="9768d-110">ドキュメントで最も目立つテーマは、優先するテーマとして指定されています。</span><span class="sxs-lookup"><span data-stu-id="9768d-110">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>