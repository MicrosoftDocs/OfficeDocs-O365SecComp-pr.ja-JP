---
title: はい
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
description: Office 365 メッセージの暗号化では、組織内のユーザーと外部のユーザーとの間で暗号化された電子メールメッセージの送受信を行うことができます。 電子メールメッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
ms.openlocfilehash: 06c43bcb3364b83114e2d7b1a2ef0273858cffb0
ms.sourcegitcommit: 895f67531f2b4afe46c7487ca5b44555ca791bae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836811"
---
# <a name="office-365-message-encryption"></a>はい

Office 365 メッセージの暗号化では、組織内のユーザーと外部のユーザーとの間で暗号化された電子メールメッセージの送受信を行うことができます。 Office 365 メッセージの暗号化は、Outlook.com、yahoo!、Gmail、その他の電子メールサービスで機能します。 電子メールメッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
  
この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。 次の表を使用して、必要な情報をすばやく見つけることができます。
  
|||
|:-----|:-----|
|この記事を読む  <br/> |使用する方法  <br/> |
|[Office 365 で保護されたメッセージについて](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |暗号化されたメッセージのしくみと、ユーザーが使用できるオプションについての詳細を知りたいエンドユーザー。  <br/> |
|[保護されたメッセージを開くにはどうすればよいですか?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |受信した保護されたメッセージの読み取りを希望するエンドユーザー。 この記事では、複数のバージョンの Outlook および異なる電子メールアカウント (gmail、yahoo! などの Office 365 の外部にあるものも含む) からのメッセージの読み取りに関する情報を記載しています。 科目.  <br/> |
|[Outlook で暗号化されたメッセージの送信、表示、および返信を行う](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |Outlook からの暗号化されたメッセージの送信、表示、または返信を必要とするエンドユーザー。 Office 365 組織のメンバーでない場合でも、Outlook で送信された暗号化されたメッセージの通知を受信することになります。 この記事を使用して、Office 365 から送信された暗号化されたメッセージを表示および返信する方法について説明します。  <br/> |
|[デジタル署名または暗号化されたメッセージを送信する](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |Outlook for Mac を使用して、暗号化されたメッセージの送信、表示、または返信を希望するエンドユーザー。 この記事では、S/MIME など、OME 以外の暗号化方式を使用する方法についても説明します。  <br/> |
|[Android デバイスで暗号化されたメッセージを表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |Android デバイスで Office 365 メッセージの暗号化を使用して暗号化されたメッセージを受信したエンドユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された応答を送信することができます。 この記事では、その方法について説明します。  <br/> |
|[iPhone または iPad で暗号化されたメッセージを表示する](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |Office 365 メッセージの暗号化によって暗号化されたメッセージを iPhone または iPad で受信したエンドユーザーは、自由 OME ビューアアプリを使用してメッセージを表示し、暗号化された応答を送信することができます。 この記事では、その方法について説明します。  <br/> |
|Office 365 Message Encryption (OME) (この記事)  <br/> |Office 365 または Exchange Online Protection 管理者が、その他のリソースについての情報を入手できます。  <br/> |
|[OME のバージョンを比較する](ome-version-comparison.md)  <br/> |従来の office 365 メッセージの暗号化と新しい OME 機能の相違点と、それらがどのように連携するかについて理解する必要がある office 365 または Exchange Online Protection 管理者。  <br/> |
|[Office 365 Message Encryption に関する FAQ](ome-faq.md) <br/> |ライセンスや、新しい機能と従来の OME の比較など、よく寄せられる質問に対する回答を必要とする Office 365 または Exchange Online Protection 管理者。  <br/> |
|[新しい Office 365 Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md) <br/> |office 365 または Exchange Online Protection 管理者 office 365 組織に新しい office 365 メッセージの暗号化機能をセットアップする方法について学ぶことができます。  <br/> |
|[Office 365 でメールを暗号化するためにメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md) <br/> |office 365 または Exchange Online Protection 管理者が既に office 365 メッセージの暗号化を設定しており、組織から送信された電子メールメッセージを自動的に暗号化するメールフロールールを定義する準備ができました。  <br/> |
|[Office 365 Message Encryption を管理する](manage-office-365-message-encryption.md) <br/> |office 365 または Exchange Online Protection 管理者が既に office 365 メッセージの暗号化を設定していて、OME のオプションの設定を構成したい。  <br/> |
|[組織のブランドを暗号化されたメッセージに追加する](add-your-organization-brand-to-encrypted-messages.md) <br/> |会社のブランドを適用して、組織の office 365 メッセージ暗号化の電子メールメッセージと OME ポータルの内容の外観をカスタマイズする office 365 または Exchange Online Protection 管理者。  <br/> |
|[Office 365 メッセージ暗号化の電子メールの取り消し](revoke-ome-encrypted-mail.md) <br/> |office 365 または Exchange Online Protection 管理者が office 365 メッセージの暗号化を使用して暗号化された電子メールを取り消すことを希望している。  <br/> |
|[メッセージポリシーおよびコンプライアンスサービスの説明](https://technet.microsoft.com/en-us/library/5c43c8eb-f8f7-4b5a-a743-b1dab7dc2fc8#bkmk_O365_MessageEncryption)における Office 365 メッセージの暗号化 <br/> |office 365 から入手できる、サポートされている sku を含む、office 365 メッセージの暗号化機能の詳細な説明を参照してください。  <br/> |
|[Office 365 Message Encryption の旧来の情報](legacy-information-for-message-encryption.md) <br/> |office 365 または Exchange Online Protection 管理者が既に office 365 メッセージの暗号化を設定しており、新機能のリリース前に OME がどのように動作しているかについての情報を必要としています。 新しい機能なしで OME を使用して新しい展開をセットアップすることはできませんが、Microsoft は既存の展開を引き続きサポートしています。 <br/> |
||

この記事の残りの部分は、新しい OME 機能に適用されます。
  
## <a name="how-office-365-message-encryption-works"></a>Office 365 メッセージの暗号化のしくみ

Office 365 Message Encryption は、Microsoft azure Rights Management (azure RMS) に基づいて構築されているオンラインサービスで、azure Information Protection の一部です。 これには、電子メールのセキュリティ保護に役立つ暗号化、id、および承認のポリシーが含まれます。 [rights management テンプレート]、[[転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)、および [[暗号化のみ] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を使用してメッセージを暗号化できます。

ユーザーは、これらのオプションを使用して、電子メールメッセージとさまざまな Office 365 添付ファイルを暗号化できます。 サポートされている添付ファイルの種類の完全な一覧については、「[電子メールメッセージの irm の概要」の「メッセージに添付されているファイルの種類」](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)を参照してください。

管理者は、この保護を適用するメールフロールールを定義することもできます。 たとえば、特定の受信者に宛てられたすべてのメッセージ、または件名行に特定の単語が含まれるすべてのメッセージの暗号化を要求するルールを作成できます。また、受信者がメッセージの内容をコピーまたは印刷できないように指定することもできます。

以前のバージョンの OME とは異なり、新機能により、組織内または Office 365 の外部の受信者にメールを送信しているかどうかにかかわらず、統合された送信者の環境が提供されます。 また、outlook 2016 または web 上の outlook で Office 365 アカウントに送信される保護された電子メールメッセージを受信する受信者は、メッセージを表示するために追加のアクションを実行する必要はありません。 シームレスに動作します。 他の電子メールクライアントや電子メールサービスプロバイダーを使用する受信者にも、改善された操作性があります。 詳細については、「 [Office 365 で保護されたメッセージについ](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)て」および「[保護されたメッセージを開く方法](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)」を参照してください。

以前のバージョンの OME と新しい OME 機能との違いの詳細な一覧については、「 [OME のバージョンを比較](ome-version-comparison.md)する」を参照してください。

他のユーザーが暗号化メールフロールールに一致する電子メールメッセージを送信すると、メッセージは送信される前に暗号化されます。 Outlook クライアントを使用してメールを読むすべての Office 365 エンドユーザーは、送信者と同じ組織にいない場合でも、暗号化されていて、権利で保護されたメールのネイティブなファーストクラスの読み取りエクスペリエンスを受信します。 サポートされている outlook クライアントには、outlook デスクトップ、outlook Mac、iOS および Android 上の outlook mobile、および web 上の outlook (旧称 outlook web App) があります。
  
暗号化されたメッセージ、または Outlook.com、gmail、および Yahoo のアカウントに送信された権限で保護されたメールを受信する受信者は、OME ポータルにメールを送信するラッパーメールを受信します。これにより、Microsoft アカウント、gmail、またはその両方を使用して簡単に認証できるようになります。Yahoo の資格情報。
  
暗号化された、または権限で保護されたメールを Outlook 以外のクライアントで閲覧するエンドユーザーも、OME ポータルを使用して、受信した暗号化された、または権利で保護されたメッセージを表示します。

さらに、保護されたメールの送信者が gcc high で、かつ受信者が、市販の Office 365 ユーザー、Outlook.com ユーザー、および Gmail などの他の電子メールプロバイダーのユーザーを含む gcc の外部にいる場合は、受信者はにリダイレクトするラッパーメールを受信します。受信者がメッセージを読んで返信できる OME ポータル。 送信者と受信者の両方が GCC の高環境にある場合は、Outlook クライアントを使用してメールを読む受信者は、同じ組織内にいない場合でも、暗号化されていて、権利で保護されたメールに対して、ネイティブなファーストクラスの読み取りエクスペリエンスを提供します。送信者として。
  
OME を使用して暗号化できるメッセージと添付ファイルのサイズ制限が拡張されました。 制限の詳細については、「 [Exchange Online の制限](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)」を参照してください。
  
## <a name="defining-rules-for-office-365-message-encryption"></a>Office 365 Message Encryption のルールの定義

Office 365 の新しい機能を有効にする方法の1つは、exchange online および exchange online Protection 管理者がメールフロールールを定義することです。 これらのルールは、電子メールメッセージを暗号化する必要がある条件を決定します。 ルールに対して暗号化アクションが設定されている場合、ルールの条件に一致するメッセージは、送信される前に暗号化されます。
  
メールフロールールは柔軟性に富んでおり、条件を組み合わせて1つのルール内の特定のセキュリティ要件を満たすことができます。 たとえば、指定したキーワードを含むすべてのメッセージを暗号化するルールを作成し、外部の受信者に送信することができます。 Office 365 Message Encryption の新機能は、暗号化された電子メールの受信者からの返信も暗号化します。
  
メールフロールールを作成して新しい OME 機能を活用する方法の詳細については、「 [Define rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>暗号化された電子メール メッセージの送信、表示、および返信

Office 365 のメッセージ暗号化では、ユーザーは outlook および web 上の outlook から暗号化された電子メールを送信できます。 また、管理者は、Office 365 でメールフロールールを設定して、キーワード一致またはその他の条件に基づいてメールを自動的に暗号化することができます。
  
Office 365 組織の暗号化されたメッセージの受信者は、outlook for PC、outlook for Mac、outlook on the web、outlook for iOS、outlook for Android などの任意のバージョンの outlook でこれらのメッセージをシームレスに読み取ることができます。 他の電子メールクライアントで暗号化されたメッセージを受信するユーザーは、OME ポータルでメッセージを表示できます。
  
暗号化されたメッセージを送信および表示する方法の詳細については、次の記事を参照してください。
  
- [保護されたメッセージを開くにはどうすればよいですか?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)

- [Outlook で暗号化されたメッセージの送信、表示、および返信を行う](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)

## <a name="get-started-with-the-new-ome-capabilities"></a>新しい OME 機能の使用を開始する

組織内で新しい OME 機能の使用を開始する準備ができている場合は、「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。
