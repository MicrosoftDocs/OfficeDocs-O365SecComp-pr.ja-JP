---
title: Office 365 メッセージの暗号化バージョンの比較
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: さまざまなバージョンの Office 365 メッセージ暗号化と共に提供される機能の相違点と、2つの操作がどのように連携するかについて説明します。
ms.openlocfilehash: 47632d7e960e2dee2b068baaf46b98716fc8d4d0
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341438"
---
# <a name="compare-versions-of-ome"></a>OME のバージョンを比較する

この記事では、従来の Office 365 メッセージの暗号化を新しい OME 機能と比較します。新機能は、OME と Information Rights Management (IRM) の両方の合併およびより新しいバージョンです。また、2つのを Office 365 組織に共存させる方法についても説明します。

||
|:-----|
|この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。この記事は、管理者および it 担当者を対象としています。暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。 |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>機能と機能の並行比較

|                                   |以前の機能       |                   |新機能              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**機能**                     | **従来の OME**    | **IRM**           | **OME の新機能** |
|*暗号化されたメールを送信する*        |Exchange メールフロールールを使用する|エンドユーザーが outlook デスクトップまたは outlook on the Web から開始しました。または Exchange メールフロールールを介して|エンドユーザーが outlook デスクトップ、outlook for Mac、または outlook on the Web から開始しました。Exchange メールフロールール (トランスポートルールとも呼ばれます) および Office 365 データ損失防止 (DLP) を使用します。|
|*Rights management テンプレート*       |   N/A      |オプションとカスタムテンプレートを転送しない|転送不可オプション、暗号化のみオプション、およびカスタムテンプレート|
|*受信者の種類*                   |内部および外部の受信者|内部受信者のみ         |内部および外部の受信者|
|*内部の受信者のための環境*|受信者が HTML メッセージを受信し、web ブラウザーまたはモバイルアプリでそれをダウンロードして開く|Outlook クライアントでのネイティブインライン環境|Office 365 受信者のネイティブインライン環境。他のすべての受信者は OME ポータルからメッセージを読み取ることができます (ダウンロードまたはアプリは必要ありません)。|
|*外部の受信者のための環境*|受信者が HTML メッセージを受信し、web ブラウザーまたはモバイルアプリでそれをダウンロードして開く|N/A|Office 365 受信者のネイティブインライン環境。他のすべての受信者は OME ポータルからメッセージを読み取ることができます (ダウンロードまたはアプリは必要ありません)。|
|*添付ファイルのアクセス許可*           |添付ファイルに制限はありません。|添付ファイルが保護されている|添付ファイルは、[転送不可] オプションおよびカスタムテンプレートに対して保護されています。管理者は、[暗号化のみ] オプションの添付ファイルを保護するかどうかを選択できます。|
|*独自のキー (byok) のサポートを利用する*|なし                |なし               |byok サポート          |
||

## <a name="advantages-of-using-the-new-ome-capabilities-over-legacy-ome"></a>従来の OME で新しい OME 機能を使用する利点

新機能には、次のような利点があります。

- 暗号化のみ (セキュリティで保護されたコラボレーションを可能にする)、転送不可、カスタム制限などを使用できます。
- 送信者は、新しい機能で暗号化されたメールを outlook デスクトップ、outlook for Mac、web クライアントの outlook から手動で送信できます。
- Office 365 の受信者は、サポートされている Outlook クライアントでインライン表示を使用することができます。または、管理者が Office 365 の受信者をブランド化された環境で表示するように選択することもできます。
- Gmail、Yahoo、Microsoft accounts などの Office 365 の外部のアカウントは、OME ポータルと連携しています。これにより、これらの受信者にとってより良いユーザー環境が提供されます。その他のすべての id は、1回限りのパスコードを使用して暗号化されたメッセージにアクセスします。
- 管理者はブランド化をカスタマイズし、複数のブランド設定テンプレートを作成できます。
- 管理者は、新しい機能で暗号化されたメールを取り消すことができます。
- 新しい機能は、セキュリティ&amp;コンプライアンスセンターを通じて詳細な利用状況レポートを提供します。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>従来の OME と、同じテナント内の新機能の共存

従来の OME と新機能の両方を同じテナントで使用できます。管理者として、メールフロールールの作成時に使用する OME のバージョンを選択することによって、これを行います。

- 以前のバージョンの OME を指定するには、Exchange メールフロールールのアクション "OME の前のバージョンを適用" を使用します。
- 新しい機能を指定するには、Exchange メールフロールールのアクション "Office 365 メッセージの暗号化と権利の保護を適用する" を使用します。

ユーザーは、新しい機能を使用して暗号化されたメールを、outlook デスクトップ、outlook for Mac、web クライアントの outlook から手動で送信することもできます。

## <a name="migrating-from-legacy-ome-to-the-new-capabilities"></a>従来の OME から新しい機能への移行

両方のバージョンの OME を共存させることができますが、ルールのアクション "OME の前のバージョンを適用" を使用して新しい機能を使用する古いメールフロールールを編集することを強くお勧めします。メールフロールールのアクション "apply Office 365 Message Encryption" を指定するおよび権利保護]。手順については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

## <a name="getting-started-with-ome"></a>OME の概要

通常、新しい OME 機能は Office 365 組織に対して自動的に有効になります。組織内で新しい OME 機能の使用を開始する準備ができている場合は、「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。

Azure Information Protection を有効にしている場合、OME のレガシバージョンは Office 365 組織に対して自動的に有効になります。以前は、Azure Information Protection が有効になっていない場合でも、従来の OME は動作していました。このような場合は、これで終了です。

従来の OME の使用を開始するには、Azure Information Protection を有効にしている場合は、"以前のバージョンの OME を適用" というルールのアクションを使用するメールフロールールを構成するだけで済みます。手順については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。