---
title: Office 365 の ATP の安全なリンク警告ページ
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: IT Pro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fc4e6ebb-5acc-4bc5-bad8-4f3407d1d3f4
description: 作業が Office 365 の高度な脅威保護の場合を参照する可能性があります警告ページの概要を取得します。
ms.openlocfilehash: 9cda3421a394de70dfcb759a20e13aa40f84eb2f
ms.sourcegitcommit: c35fc431a315ee8e411a95d3da20d2a44c2e6be3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23485977"
---
# <a name="office-365-atp-safe-links-warning-pages"></a>Office 365 の ATP の安全なリンク警告ページ

[Office 365 の高度な脅威保護](office-365-atp.md)(ATP) は、フィッシング詐欺と[安全なリンク](atp-safe-links.md)、[安全な添付ファイル](atp-safe-attachments.md)、[フィッシング防止対策](anti-phishing-protection.md)などの機能をマルウェアから組織を保護するのに役立ちます。保護すると、電子メール メッセージ、および Office ドキュメント内のリンク (Url) がチェックされます。不審なまたは悪意のある URL が識別されると場合、は] をクリックすると、URL を開くをブロック可能性があります。サイトに直接ではなく、代わりに警告ページが表示可能性があります。 
  
[警告のページへの最近の更新](atp-safe-links-warning-pages.md#updates)と、表示される[警告のページの例](atp-safe-links-warning-pages.md#examples)を参照するには、この資料を参照してください。
  
## <a name="examples-of-warning-pages"></a>警告ページの例

### <a name="atp-is-scanning-the-link"></a>分析ツールでは、リンクをスキャンします。

![分析ツールでは、リンクをスキャンします。](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

ATP の安全なリンクによってスキャンされる URL です。しばらくリンクをもう一度実行する必要があります。

### <a name="a-url-is-in-a-suspicious-email-message"></a>不審な電子メール メッセージの URL は、します。

![不審な電子メール メッセージでこの URL は、します。](media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

URL は、疑わしいと考えられるその他の電子メール メッセージに類似したように見える電子メール メッセージでは。サイトに進む前に電子メール メッセージをもう一度チェックすることをお勧めします。

### <a name="a-url-is-in-a-message-identified-as-a-phishing-attempt"></a>フィッシング詐欺として識別されたメッセージの URL は、します。

![この URL は、フィッシング詐欺として識別されたメッセージには](media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

URL は、フィッシング攻撃として識別された電子メール メッセージには。その結果、電子メール メッセージ内のすべての Url がブロックされます。サイトを続行しないでことをお勧めします。

### <a name="a-site-has-been-identified-as-malicious"></a>悪意のあるサイトが発見されました

![悪意あるコードとしてこのサイトが発見されました](media/058883c8-23f0-4672-9c1c-66b084796177.png)

URL は、悪意あるコードとして認定されているサイトを指しています。  <br/> サイトを続行しないでことをお勧めします。

### <a name="a-site-is-blocked"></a>サイトがブロックされています。

![このサイトがブロックされています。](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

組織の URL がブロックされます。URL をブロックする理由は、いくつか考えられます。組織の Office 365 の管理者に問い合わせることをお勧めします。

### <a name="an-error-has-occurred"></a>エラーが発生しました

![エラーが発生しました](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

何らかのエラーが発生し、URL を開くことができません。

   
## <a name="recent-updates-to-warning-pages"></a>警告のページへの最新の更新プログラム

いくつかの警告ページは、Office 365 の ATP の最近更新されました。、更新されたページが表示されていない場合は、すぐにします。更新プログラムには、新しい配色パターン、詳細については、特定の警告と推奨事項があっても、サイトを続行することなどがあります。

### <a name="url-scan-in-progress"></a>URL スキャンの進行状況

元の警告] ページ:

![URL スキャンの進行状況についての元の警告] ページ](media/04368763-763f-43d6-94a4-a48291d36893.png)

更新の警告] ページ:

![分析ツールでは、リンクをスキャンします。](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="malicious-site-warning"></a>悪意のあるサイトの警告

元の警告] ページ:

![悪意のあるサイトについての元の警告] ページ](media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

更新の警告] ページ:

![悪意あるコードとしてこのサイトが発見されました](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="blocked-url-warning"></a>警告の URL をブロック

元の警告] ページ:

![ブロックされた URL の元の警告] ページ](media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

更新の警告] ページ:

![このサイトがブロックされています。](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="error-occurred-warning-page"></a>「エラーが発生しました」の警告ページ

元の警告] ページ:

![元「エラーが発生しました」の警告ページ](media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)

更新の警告] ページ:

![エラーが発生しました](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)
  
   
## <a name="related-topics"></a>関連項目

[Office により、フィッシング詐欺から保護する方法](https://support.office.com/article/be0de46a-29cd-4c59-aaaf-136cf177d593)
  
[Office 365 の ATP の安全なリンク](atp-safe-links.md)
  
[Office 365 ATP の安全な添付ファイル](atp-safe-attachments.md)
  
[Office 365 のスパム対策とマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)
  

