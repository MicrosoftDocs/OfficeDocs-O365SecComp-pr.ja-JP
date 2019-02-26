---
title: Office 365 ATP の安全なリンクの警告ページ
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: IT Pro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fc4e6ebb-5acc-4bc5-bad8-4f3407d1d3f4
description: Office 365 Advanced Threat Protection が機能している場合に表示される可能性がある警告ページの概要を取得します。
ms.openlocfilehash: e11592c5db0909171627cd163593d7e49cc6a5de
ms.sourcegitcommit: 5b5bbced1577701bdb6befc8ed252e9d9e776529
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2019
ms.locfileid: "30245593"
---
# <a name="office-365-atp-safe-links-warning-pages"></a>Office 365 ATP の安全なリンクの警告ページ

> [!IMPORTANT]
> この記事は、Office 365 Enterprise のお客様を対象としています。Outlook.com、office 365 Home、または office 365 Personal を使用していて、Outlook での安全なリンクに関する情報をお探しの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

[Office 365 Advanced Threat Protection](office-365-atp.md)(atp) は、 [atp の安全なリンク](atp-safe-links.md)、atp の安全な[添付ファイル](atp-safe-attachments.md)、[フィッシング対策保護](anti-phishing-protection.md)などの機能を介して組織をフィッシングやマルウェアから保護するのに役に立ちます。保護が設定されている場合、電子メールメッセージと Office ドキュメント内のリンク (url) はチェックされます。url が疑わしいまたは悪意のあるものとして識別された場合、その url をクリックしても url を開くことがブロックされることがあります。直接サイトに移行するのではなく、警告ページが表示されることがあります。 
  
この記事では、表示される可能性がある[警告ページの例](atp-safe-links-warning-pages.md#examples)と、[警告ページに対する最新の更新プログラム](atp-safe-links-warning-pages.md#updates)を確認しています。
  
## <a name="examples-of-warning-pages"></a>警告ページの例

### <a name="atp-is-scanning-the-link"></a>ATP がリンクをスキャンしています

ATP の安全なリンクによって、URL がスキャンされています。リンクを再度試すには、しばらく待つ必要がある場合があります。

![ATP がリンクをスキャンしています](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="a-url-is-in-a-suspicious-email-message"></a>疑わしい電子メールメッセージ内の URL

この URL は、疑わしいと思われる他の電子メールメッセージに類似した電子メールメッセージに含まれています。サイトに進む前に、電子メールメッセージをもう一度確認することをお勧めします。

![この URL は疑わしい電子メールメッセージに含まれています](media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="a-url-is-in-a-message-identified-as-a-phishing-attempt"></a>フィッシングの試行として識別されたメッセージ内の URL

この URL は、フィッシング攻撃として識別された電子メールメッセージに含まれています。その結果、電子メールメッセージ内のすべての url がブロックされます。サイトに進まないことをお勧めします。

![この URL は、フィッシングとして識別されたメッセージ内にあります。](media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="a-site-has-been-identified-as-malicious"></a>サイトが悪意のあるものとして識別された

URL は、悪意があると識別されたサイトを指しています。  <br/> サイトに進まないことをお勧めします。

![このサイトは悪意のあるものとして識別されています。](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="a-site-is-blocked"></a>サイトがブロックされている

組織の URL がブロックされています。URL がブロックされる理由はいくつかあります。組織の Office 365 管理者に連絡することをお勧めします。

![このサイトはブロックされています](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="an-error-has-occurred"></a>エラーが発生しました

何らかのエラーが発生し、URL を開くことができません。

![エラーが発生しました](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

## <a name="recent-updates-to-warning-pages"></a>警告ページに対する最新の更新プログラム

Office 365 ATP のために最近更新された警告ページがいくつかあります。更新されたページがまだ表示されていない場合は、間もなく表示されます。更新には、新しい配色、詳細、および指定された警告と推奨事項にかかわらずサイトに進む機能が含まれています。

### <a name="url-scan-in-progress"></a>進行中の URL スキャン

元の警告ページ:

![進行中の URL スキャンに関する元の警告ページ](media/04368763-763f-43d6-94a4-a48291d36893.png)

更新された警告ページ:

![ATP がリンクをスキャンしています](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="malicious-site-warning"></a>悪意のあるサイトの警告

元の警告ページ:

![悪意のあるサイトに関する元の警告ページ](media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

更新された警告ページ:

![このサイトは悪意のあるものとして識別されています。](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="blocked-url-warning"></a>ブロックされた URL の警告

元の警告ページ:

![ブロックされた URL に関する元の警告ページ](media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

更新された警告ページ:

![このサイトはブロックされています](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="error-occurred-warning-page"></a>"エラーが発生しました" の警告ページ

元の警告ページ:

![元の "エラーが発生しました" という警告ページ](media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)

更新された警告ページ:

![エラーが発生しました](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)
   
