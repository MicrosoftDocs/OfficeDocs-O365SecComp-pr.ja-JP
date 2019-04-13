---
title: Office 365 Message Encryption (OME) バージョンの比較
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: さまざまなバージョンの Office 365 Message Encryption で提供される機能の違いと、2つの処理がどのように連携するかについて説明します。
ms.openlocfilehash: bb13208e2b630c8a6217b78b48a4cd3bb4b0de79
ms.sourcegitcommit: 895f67531f2b4afe46c7487ca5b44555ca791bae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836841"
---
# <a name="compare-versions-of-ome"></a>OME のバージョンを比較する

この記事では、従来の Office 365 Message Encryption (OME) と新しい OME 機能を比較します。 新機能は、OME と Information Rights Management (IRM) の両方の合併およびより新しいバージョンです。 GCC High への展開に関する固有の特性についても概説します。 また、2つのを Office 365 組織に共存させる方法についても説明します。

||
|:-----|
|この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。 この記事は、管理者および it 担当者を対象としています。 暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。 |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>機能と機能の並行比較

|                                   |以前の機能       |                   |新機能              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**機能**                     | **従来の OME**    | **IRM**           | **OME の新機能** |
|*暗号化されたメールを送信する*        |Exchange メールフロールールを使用する|エンドユーザーが outlook デスクトップまたは outlook on the Web から開始しました。または Exchange メールフロールールを介して|エンドユーザーが outlook デスクトップ、outlook for Mac、または outlook on the Web から開始しました。Exchange メールフロールール (トランスポートルールとも呼ばれます) および Office 365 データ損失防止 (DLP) を使用します。|
|*Rights management テンプレート*       |   N/A      |オプションとカスタムテンプレートを転送しない|転送不可オプション、暗号化のみオプション、およびカスタムテンプレート|
|*受信者の種類*                   |内部および外部の受信者|内部受信者のみ         |内部および外部の受信者|
|*内部の受信者のための環境*|受信者が HTML メッセージを受信し、web ブラウザーまたはモバイルアプリでそれをダウンロードして開く|Outlook クライアントでのネイティブインライン環境|Office 365 受信者のネイティブインライン環境。 他のすべての受信者は OME ポータルからメッセージを読み取ることができます (ダウンロードまたはアプリは必要ありません)。|
|*外部の受信者のための環境*|受信者が HTML メッセージを受信し、web ブラウザーまたはモバイルアプリでそれをダウンロードして開く|N/A|Office 365 受信者のネイティブインライン環境。 他のすべての受信者は OME ポータルからメッセージを読み取ることができます (ダウンロードまたはアプリは必要ありません)。|
|*添付ファイルのアクセス許可*           |添付ファイルに制限はありません。|添付ファイルが保護されている|添付ファイルは、[転送不可] オプションおよびカスタムテンプレートに対して保護されています。 管理者は、[暗号化のみ] オプションの添付ファイルを保護するかどうかを選択できます。|
|*独自のキー (byok) のサポートを利用する*|なし                |なし               |byok サポート          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>従来の OME に比べた新しい OME 機能の利点

新機能には、次のような利点があります。

- 暗号化のみを使用する機能 (セキュリティで保護されたコラボレーションを有効にする)、転送不可、およびカスタム制限。
- 送信者は、新しい機能で暗号化されたメールを outlook デスクトップ、outlook for Mac、web クライアントの outlook から手動で送信できます。
- Office 365 の受信者は、サポートされている Outlook クライアントでインライン表示を使用することができます。 または、管理者が Office 365 の受信者をブランド化された環境で表示するように選択することもできます。
- Gmail、Yahoo、Microsoft accounts などの Office 365 の外部のアカウントは、OME ポータルと連携しています。これにより、これらの受信者にとってより良いユーザー環境が提供されます。 その他のすべての id は、1回限りのパスコードを使用して暗号化されたメッセージにアクセスします。
- 管理者はブランド化をカスタマイズし、複数のブランド設定テンプレートを作成できます。
- 管理者は、新しい機能で暗号化されたメールを取り消すことができます。
- 新しい機能は、セキュリティ&amp;コンプライアンスセンターを通じて詳細な利用状況レポートを提供します。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>GCC 高展開での Office 365 メッセージ暗号化の固有の特徴

GCC の高環境で Office 365 メッセージの暗号化を使用することを計画している場合は、受信者の利便性に関して独自の特徴があります。

### <a name="encrypted-email-from-gcc-high-to-gcc-high-recipients"></a>gcc high から gcc 高受信者への暗号化された電子メール

送信者は、outlook for PC および Mac および web 上の outlook でメールを手動で暗号化できます。また、Exchange メールフロールールを使用して電子メールを暗号化するポリシーを設定することもできます。

GCC の内部にいる受信者は、PC と Mac 用の outlook と、その他すべての Office 365 ユーザーと同様に web 上の outlook で、同じインライン読み取り操作を受け取ります。

### <a name="encrypted-email-from-gcc-high-to-non-gcc-high-recipients"></a>gcc high から非 gcc の高受信者への暗号化された電子メール

gcc の内部にある送信者は、暗号化された電子メールを gcc の境界外に送信できます。

市販の Office 365 ユーザー、Outlook.com ユーザー、およびその他の電子メールプロバイダー (Gmail、Yahoo など) を含む、GCC 以外のすべての受信者には、受信者が読み取り可能な OME ポータルに受信者をリダイレクトするラッパーメールを受信します。メッセージに返信します。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>従来の OME と、同じテナント内の新機能の共存

従来の OME と新機能の両方を同じテナントで使用できます。 管理者として、メールフロールールの作成時に使用する OME のバージョンを選択することによって、これを行います。

- 以前のバージョンの OME を指定するには、Exchange メールフロールールの動作を使用します。**以前のバージョンの OME を適用**します。
- 新しい機能を指定するには、Exchange メールフロールールのアクションを使用して、 **Office 365 メッセージの暗号化および権限保護を適用**します。

ユーザーは、outlook デスクトップ、outlook for Mac、および outlook on the web を使用して、新しい機能で暗号化されたメールを手動で送信できます。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>従来の OME から新機能への移行

両方のバージョンの OME を共存させることができますが、ルールのアクションを使用する古いメールフロールールを編集して、新しい機能を使用するには、**以前のバージョンの OME を適用**することを強くお勧めします。 メールフロールールのアクションを使用するようにこれらのルールを更新する**Office 365 メッセージの暗号化および権限保護を適用**します。 手順については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

## <a name="get-started-with-ome"></a>OME の使用を開始する

通常、新しい OME 機能は Office 365 組織に対して自動的に有効になります。 組織内の新しい OME 機能の詳細については、「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。

Azure Information Protection を有効にしている場合、OME のレガシバージョンは Office 365 組織に対して自動的に有効になります。 以前は、Azure Information Protection が有効になっていない場合でも、従来の OME は動作していました。 このような場合は、これで終了です。

従来の OME の使用を開始するには、Azure Information Protection を有効にしている場合は、ルールの動作を使用するメールフロールールを構成するだけで、**以前のバージョンの OME が適用**されます。 手順については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。