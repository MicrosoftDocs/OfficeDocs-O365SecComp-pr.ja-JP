---
title: Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/6/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Office 365 メッセージの暗号化では、組織内のユーザーと外部のユーザーとの間で暗号化された電子メールメッセージの送受信を行うことができます。電子メールメッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
ms.openlocfilehash: eae2b6ca4756fc90837c2bfac4b5eae20001d37a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220287"
---
# <a name="office-365-message-encryption"></a>Office 365 Message Encryption

Office 365 メッセージの暗号化では、組織内のユーザーと外部のユーザーとの間で暗号化された電子メールメッセージの送受信を行うことができます。Office 365 メッセージの暗号化は、Outlook.com、yahoo!、Gmail、その他の電子メールサービスで機能します。電子メールメッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
  
この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。次の表を使用して、必要な情報をすばやく見つけることができます。
  
|||
|:-----|:-----|
|この記事を読む  <br/> |使用する方法  <br/> |
|[Office 365 で保護されたメッセージについて](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |暗号化されたメッセージのしくみと、ユーザーが使用できるオプションについての詳細を知りたいエンドユーザー。  <br/> |
|[保護されたメッセージを開くにはどうすればよいですか?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |受信した保護されたメッセージの読み取りを希望するエンドユーザー。この記事には、複数のバージョンの Outlook および異なるメールアカウントからのメッセージの読み取りに関する情報が含まれています。これには、gmail や yahoo! のアカウントなど、Office 365 の外部にあるものも含まれます。  <br/> |
|[Outlook で暗号化されたメッセージの送信、表示、および返信を行う](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |Outlook からの暗号化されたメッセージの送信、表示、または返信を必要とするエンドユーザー。Office 365 組織のメンバーでない場合でも、Outlook で送信された暗号化されたメッセージの通知を受信することになります。この記事を使用して、Office 365 から送信された暗号化されたメッセージを表示および返信する方法について説明します。  <br/> |
|[デジタル署名または暗号化されたメッセージを送信する](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |Outlook for Mac を使用して、暗号化されたメッセージの送信、表示、または返信を希望するエンドユーザー。この記事では、S/MIME など、OME 以外の暗号化方式を使用する方法についても説明します。  <br/> |
|[Android デバイスで暗号化されたメッセージを表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |Android デバイスで Office 365 メッセージの暗号化を使用して暗号化されたメッセージを受信したエンドユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された応答を送信することができます。この記事では、その方法について説明します。  <br/> |
|[iPhone または iPad で暗号化されたメッセージを表示する](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |Office 365 メッセージの暗号化によって暗号化されたメッセージを iPhone または iPad で受信したエンドユーザーは、自由 OME ビューアアプリを使用してメッセージを表示し、暗号化された応答を送信することができます。この記事では、その方法について説明します。  <br/> |
|Office 365 Message Encryption (OME) (この記事)  <br/> |Office 365 または Exchange Online Protection 管理者が、その他のリソースについての情報を入手できます。  <br/> |
|[OME のバージョンを比較する](ome-version-comparison.md)  <br/> |従来の office 365 メッセージの暗号化と新しい OME 機能の相違点と、それらがどのように連携するかについて理解する必要がある office 365 または Exchange Online Protection 管理者。  <br/> |
|[Office 365 Message Encryption に関する FAQ](ome-faq.md) <br/> |ライセンスや、新しい機能と従来の OME の比較など、よく寄せられる質問に対する回答を必要とする Office 365 または Exchange Online Protection 管理者。  <br/> |
|[新しい Office 365 Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md) <br/> |office 365 または Exchange Online Protection 管理者 office 365 組織に新しい office 365 メッセージの暗号化機能をセットアップする方法について学ぶことができます。  <br/> |
|[Office 365 でメールを暗号化するためにメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md) <br/> |office 365 または Exchange Online Protection 管理者が既に office 365 メッセージの暗号化を設定しており、組織から送信された電子メールメッセージを自動的に暗号化するメールフロールールを定義する準備ができました。  <br/> |
|[Office 365 Message Encryption を管理する](manage-office-365-message-encryption.md) <br/> |office 365 または Exchange Online Protection 管理者が既に office 365 メッセージの暗号化を設定していて、OME のオプションの設定を構成したい。  <br/> |
|[組織のブランドを暗号化されたメッセージに追加する](add-your-organization-brand-to-encrypted-messages.md) <br/> |会社のブランドを適用して、組織の office 365 メッセージ暗号化の電子メールメッセージと OME ポータルの内容の外観をカスタマイズする office 365 または Exchange Online Protection 管理者。  <br/> |
|[Office 365 メッセージ暗号化の電子メールの取り消し](revoke-ome-encrypted-mail.md) <br/> |office 365 または Exchange Online Protection 管理者が office 365 メッセージの暗号化を使用して暗号化された電子メールを取り消すことを希望している。  <br/> |
|[メッセージポリシーおよびコンプライアンスサービスの説明](https://technet.microsoft.com/en-us/library/5c43c8eb-f8f7-4b5a-a743-b1dab7dc2fc8#bkmk_O365_MessageEncryption)における Office 365 メッセージの暗号化 <br/> |office 365 から入手できる、サポートされている sku を含む、office 365 メッセージの暗号化機能の詳細な説明を参照してください。  <br/> |
|[Office 365 Message Encryption の旧来の情報](legacy-information-for-message-encryption.md) <br/> |office 365 または Exchange Online Protection 管理者が既に office 365 メッセージの暗号化を設定しており、新機能のリリース前に OME がどのように動作しているかについての情報を必要としています。新しい機能なしで OME を使用して新しい展開をセットアップすることはできませんが、Microsoft は既存の展開を引き続きサポートしています。  <br/> |
||

この記事の残りの部分は、新しい OME 機能に適用されます。
  
## <a name="how-office-365-message-encryption-works"></a>Office 365 メッセージの暗号化のしくみ

Office 365 Message Encryption は、Microsoft azure Rights Management (azure RMS) に基づいて構築されているオンラインサービスで、azure Information Protection の一部です。Office 365 管理者は、メールフロールールを定義して、暗号化の条件を決定できます。たとえば、特定の受信者に宛てたすべてのメッセージの暗号化を必要とするルールがあります。
  
他のユーザーが暗号化メールフロールールに一致する電子メールメッセージを Exchange Online で送信すると、メッセージは送信される前に暗号化されます。Outlook クライアントを使用してメールを読むすべての Office 365 エンドユーザーは、送信者と同じ組織にいない場合でも、暗号化されていて、権利で保護されたメールのネイティブなファーストクラスの読み取りエクスペリエンスを受信します。サポートされている outlook クライアントには、outlook デスクトップ、outlook Mac、iOS および Android 上の outlook mobile、および web 上の outlook (旧称 outlook web App) があります。
  
暗号化されたメッセージ、または Outlook.com、Gmail、yahoo のアカウントに送信された権限で保護されたメールを受信する受信者は、Microsoft アカウントまたは gmail または yahoo の資格情報を使用して、OME ポータルへの認証を簡単に行うことができます。
  
暗号化された、または権限で保護されたメールを Outlook 以外のクライアントで閲覧するエンドユーザーも、OME ポータルを使用して、受信した暗号化された、または権利で保護されたメッセージを表示します。
  
Office 365 メッセージの暗号化を使用して暗号化できるメッセージと添付ファイルのサイズ制限を拡大しました。制限の詳細については、「 [Exchange Online の制限](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)」を参照してください。
  
## <a name="defining-rules-for-office-365-message-encryption"></a>Office 365 Message Encryption のルールの定義

Office 365 の新しい機能を有効にする方法の1つは、exchange online および exchange online Protection 管理者がメールフロールールを定義することです。これらのルールは、電子メールメッセージを暗号化する必要がある条件を決定します。ルールに対して暗号化アクションが設定されている場合、ルールの条件に一致するメッセージは、送信される前に暗号化されます。
  
メールフロールールは柔軟性に富んでおり、条件を組み合わせて1つのルール内の特定のセキュリティ要件を満たすことができます。たとえば、指定したキーワードを含むすべてのメッセージを暗号化するルールを作成し、外部の受信者に送信することができます。Office 365 Message Encryption の新機能は、暗号化された電子メールの受信者からの返信も暗号化します。
  
メールフロールールを作成して新しい OME 機能を活用する方法の詳細については、「 [Define rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>暗号化された電子メール メッセージの送信、表示、および返信

Office 365 のメッセージ暗号化では、ユーザーは outlook および web 上の outlook から暗号化された電子メールを送信できます。また、管理者は、Office 365 でメールフロールールを設定して、キーワード一致またはその他の条件に基づいてメールを自動的に暗号化することができます。
  
Office 365 組織の暗号化されたメッセージの受信者は、outlook for PC、outlook for Mac、outlook on the web、outlook for iOS、outlook for Android などの任意のバージョンの outlook でこれらのメッセージをシームレスに読み取ることができます。他の電子メールクライアントで暗号化されたメッセージを受信するユーザーは、OME ポータルでメッセージを表示できます。
  
暗号化されたメッセージを送信および表示する方法の詳細については、次の記事を参照してください。
  
- [保護されたメッセージを開くにはどうすればよいですか?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)

- [Outlook で暗号化されたメッセージの送信、表示、および返信を行う](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)

## <a name="get-started-with-the-new-ome-capabilities"></a>新しい OME 機能の使用を開始する

組織内で新しい OME 機能の使用を開始する準備ができている場合は、「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。
