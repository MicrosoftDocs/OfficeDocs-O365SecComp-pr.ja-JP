---
title: Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Office 365 Message Encryption を使用すると、組織は組織内外のユーザーとの間で暗号化されたメール メッセージを送受信できます。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
ms.openlocfilehash: f6f6f59225d267d08ba20e1fdea219dc5d890ed5
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852861"
---
# <a name="office-365-message-encryption"></a>Office 365 Message Encryption

電子メールは、財務データ、法的契約、社外秘の製品情報、売上レポートや売上見込み、患者の医療情報、顧客や従業員の情報などの機密性の高い情報を交換するためによく使われています。その結果、メールボックスが機密性の高い大量の情報のリポジトリとして使用され、組織にとって情報漏洩が深刻な脅威となる可能性があります。

Office 365 Message Encryption を使用すると、組織は組織内外のユーザーとの間で暗号化されたメール メッセージを送受信できます。 Office 365 Message Encryption は、Outlook.com、Yahoo!、Gmail、およびその他のメール サービスで機能します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
  
この記事の以降の部分では、新しい OME 機能について説明します。
  
## <a name="how-office-365-message-encryption-works"></a>Office 365 Message Encryption の仕組み

Office 365 Message Encryption は、Azure Information Protection の一部である Microsoft Azure Rights Management (Azure RMS) 上に構築されたオンライン サービスです。 このサービスには、メールをセキュリティで保護するための暗号化、ID、および認証ポリシーが含まれています。 メッセージを暗号化するには、アクセス許可管理のテンプレートである[転送不可オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)および[暗号化のみ](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)オプションを使用します。

ユーザーはこれらのオプションを使用して、メール メッセージやさまざまな Office 365 の添付ファイルを暗号化できます。 サポートされているすべての添付ファイルの種類の一覧については、「[IRM ポリシーの対象となるメッセージ添付ファイルの種類](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)」を参照してください。

管理者は、この保護を適用するメール フロー ルールを定義することもできます。 たとえば、特定の受信者宛てのすべてのメッセージや件名行に特定の言葉が含まれるメッセージの暗号化を要求したり、受信者はメッセージのコンテンツのコピーや印刷の禁止を規定したりするルールを作成できます。

以前のバージョンの OME とは異なり、これらの新機能では、組織の内部または Office 365 の外部の受信者にメールを送信しているかどうかに関わらず、送信者には統一された操作環境が提供されます。 さらに、Outlook 2016 または Outlook on the web での Office 365 アカウントに送信された保護されているメール メッセージを受信する受信者は、メッセージを表示するための追加の操作を実行する必要がありません。 シームレスに動作します。 また、他のメール クライアントやメール サービス プロバイダーを使用している受信者の操作性も向上しました。 詳細については、「[Office 365 の保護されたメッセージについて](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)」および「[保護されたメッセージを開く方法を教えてください](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)」を参照してください。

以前のバージョンの OME と新しい OME の間での機能の違いの詳細一覧は、「[OME のバージョンを比較する](ome-version-comparison.md)」をご覧ください。

暗号化メール フロー ルールに一致するメール メッセージを誰かが送信すると、メッセージは送信される前に暗号化されます。 たとえ受信者が送信者と同じ組織に存在していない場合でも、暗号化され権限で保護されたメールでネイティブの、ファーストクラスの読み取り操作が Outlook クライアントを使用してメールを読むすべての Office 365 エンドユーザーに提供されます。 サポートされている Outlook クライアントには、Outlook デスクトップ、Outlook Mac、iOS および Android の Outlook Mobile、Outlook on the web (旧称: Outlook Web App) が含まれます。
  
Outlook.com、Gmail、および Yahoo アカウントに送られた暗号化され権限で保護されたメッセージを受信する暗号化されたメッセージの受信者には、Microsoft アカウント、Gmail、または Yahoo の資格情報を使用してすばやく認証を行える OME ポータルにユーザーをリダイレクトするラッパー メールが送信されます。
  
暗号化され権限で保護されたメールを Outlook 以外のクライアントで閲覧するエンド ユーザーの場合も、受信した暗号化され権限で保護されたメッセージを表示するのに OME ポータルを使用します。

また、GCC High 内部の送信者が GCC High 外部の受信者 (商用版 Office 365 ユーザー、Outlook.com ユーザー、および Gmail などの他のメール プロバイダーのユーザーなど) 宛てに保護されたメールを送信した場合、メッセージの閲覧と返信が行える OME ポータルにリダイレクトするラッパー メッセージが受信者に送信されます。 上記以外の場合で、送信者と受信者の両方が GCC High の内部にいる場合は、たとえ受信者が送信者と同じ組織に存在していない場合でも、Outlook クライアントを使用してメールを読む受信者には暗号化され権限で保護されたメールでネイティブの、ファーストクラスの読み取り操作が提供されます。 GCC High での操作方法の違いの詳細については、「[OME のバージョンを比較する](ome-version-comparison.md)」を参照してください。
  
OME を使用して暗号化できるメッセージと添付ファイルのサイズの上限を増やしました。 制限の詳細については、「[Exchange Online の制限
](https://technet.microsoft.com/ja-JP/library/exchange-online-limits.aspx)」を参照してください。

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Office 365 Advanced Message Encryption が OME 上で動作する仕組み

Office 365 Advanced Message Encryption を使用すると、複数のブランド テンプレートを作成することができます。これにより、受信者のメールの制御を細かく調整し、さまざまな組織構造をサポートするためのカスタム ブランド エクスペリエンスを作成できます。

Office 365 の Advanced Message Encryption を使用すると、暗号化されたメールへの外部の受信者のアクセスに関してより柔軟な制御が要求されるコンプライアンス義務を遵守することができます。 Office 365 の Advanced Message Encryption では、管理者は機密情報の種類 (PII、財務 ID、保険 ID など) またはキーワードを検出する自動ポリシーを使用して外部共有される機密メールを制御することができ、暗号化されたメールへのアクセスの有効期限を保護された Web ポータルを通して設定することで保護を強化できます。 また、管理者はメールへのアクセス権限をいつでも無効にできるため、Office 365 Web ポータル経由での暗号化されたメールへの外部からのアクセスをさらに制御できます。

メッセージの失効と有効期限は、ユーザーが Office 365 組織外の受信者に送信するメールに対してのみ機能します。 また、受信者は Web ポータル経由でメールにアクセスする必要があります。 受信者がメールを受信するのにポータルを使用するよう、ラッパーを適用するカスタム ブランド テンプレートを設定します。 次に、メール フロー ルールでブランド テンプレートを適用します。 Advanced Message Encryption の詳細については、「[Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)」を参照してください。

## <a name="defining-rules-for-office-365-message-encryption"></a>Office 365 Message Encryption のルールの定義

Office 365 Message Encryption の新機能を有効にする方法の 1 つとして、Exchange Online および Exchange Online Protection の管理者がメール フロー ルールを定義することができます。 これらのルールにより、メール メッセージの暗号化が求められる条件が規定されます。 暗号化アクションをルールで設定すると、そのルールの条件を満たすすべてのメッセージが送信前に暗号化されます。
  
メール フロー ルールは柔軟であるため条件を組み合わせることができ、1 つのルールで特定のセキュリティ要件を満たすことができます。 たとえば、指定したキーワードを含み、外部の受信者に宛てられたすべてのメッセージを暗号化するルールを作成できます。 Office 365 Message Encryption の新しい機能では、暗号化されたメールの受信者からの返信も暗号化します。
  
メール フロー ルールを作成して新しい OME 機能を活用する方法の詳細については、「[Office 365 でメール メッセージを暗号化するためにルールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。
  
## <a name="get-started-with-the-new-ome-capabilities"></a>新しい OME 機能の使用を開始する

組織内で OME 新機能を使用する準備ができた場合は、「[新しい Office 365 Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md)」をご覧ください。

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>暗号化されたメール メッセージの送信、表示、および返信

Office 365 Message Encryption では、Outlook と Outlook on the web から暗号化されたメールを送信できます。 また、管理者は、キーワードの一致やその他の条件に基づいて自動的にメールを暗号化するように、Office 365 でメール フロー ルールを設定できます。
  
暗号化されたメッセージの受信者が Office 365 組織内にいる場合、受信者はすべてのバージョンの Outlook (Outlook for PC、Outlook for Mac、Outlook on the web、iOS 版 Outlook、Android 版 Outlook など) でこれらのメッセージをシームレスに読むことができます。 他のメール クライアントで暗号化されたメッセージを受信するユーザーは、OME ポータルでメッセージを表示できます。
  
暗号化されたメッセージを送信および表示する方法について詳しくは、次の記事を参照してください。
  
|||
|:-----|:-----|
|関連記事  <br/> |記事の対象となるユーザーの種類  <br/> |
|[Office 365 の保護されたメッセージについて](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |暗号化されたメッセージの仕組みや利用できるオプションについて詳しく知りたいエンド ユーザー。  <br/> |
|[保護されたメッセージを開く方法を教えてください](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |自分宛てに送信された保護されたメッセージを読みたいエンド ユーザー。 この記事では、複数のバージョンの Outlook および Gmail や Yahoo! などの Office 365 以外の他のメール アカウントからメッセージを読む方法について説明します 。  <br/> |
|[Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |暗号化されたメッセージの送信、表示、返信を Outlook で行うエンド ユーザー。 ユーザーが Office 365 組織のメンバーではない場合でも、ユーザーは、ユーザー宛てに送信された暗号化されたメッセージに関する通知を Outlook で受け取ります。 Office 365 から送信された暗号化メッセージを表示して返信する方法については、こちらの記事を参照してください。  <br/> |
|[デジタル署名または暗号化されたメッセージを送信する](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |暗号化されたメッセージの送信、表示、または返信を Outlook for Mac で行うエンド ユーザー。 この記事では、OME 以外の暗号化方法 (S/MIME など) の使用についても説明します。  <br/> |
|[暗号化されたメッセージを Android デバイスで表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |Office 365 Message Encryption で暗号化されたメッセージを Android デバイスで受信したエンド ユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された返信を送信できます。 この記事では、その方法について説明します。  <br/> |
|[iPhone または iPad で暗号化されたメッセージを表示する](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |Office 365 Message Encryption で暗号化されたメッセージを iPhone または iPad で受信したエンド ユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された返信を送信できます。 この記事では、その方法について説明します。  <br/> |
||