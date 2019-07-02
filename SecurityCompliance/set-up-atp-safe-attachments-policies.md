---
title: Office 365 の ATP の安全な添付ファイルのポリシーを設定する
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 安全な添付ファイルのポリシーを定義して、電子メール内の悪意のあるファイルから組織を保護します。
ms.openlocfilehash: 532a4b6ab2d26506f10adb621a29718a32d52ff6
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652700"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Office 365 の ATP の安全な添付ファイルのポリシーを設定する

> [!IMPORTANT]
> この記事は、 [Office 365 Advanced Threat Protection](office-365-atp.md)を使用しているビジネスのお客様を対象としています。 Outlook での安全な添付ファイルに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

ユーザーは、ドキュメント、プレゼンテーション、スプレッドシートなどの添付ファイルを日常的に送信、受信、共有します。 電子メールメッセージを見るだけで、添付ファイルが安全か悪意かを知ることは常に容易ではありません。 最後に必要なのは、組織にとって wreaking 危害を受ける、悪意のある添付ファイルです。 さいわい、 [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) は役立ちます。 組織が安全でない電子メールの添付ファイルによる攻撃から保護されるようにするために、 [ATP の安全な添付ファイル](atp-safe-attachments.md)ポリシーを設定できます。 
  
## <a name="what-to-do"></a>行うこと 
  
1. 前提条件を確認する
    
2. ATP の安全な添付ファイルポリシーを設定する
    
3. ATP の安全な添付ファイルポリシーのオプションについて
    
## <a name="step-1-review-the-prerequisites"></a>手順 1: 前提条件を確認する

- 組織に[Office 365 Advanced Threat Protection](office-365-atp.md)があることを確認します。
    
- 必要なアクセス許可を持っていることを確認してください。 ATP ポリシーを定義 (または編集) するには、適切な役割が割り当てられている必要があります。 次の表では、いくつかの例について説明します。 <br>

    |役割  |参照先/割り当て方法  |
    |---------|---------|
    |Office 365 グローバル管理者 |Office 365 の購入へのサインアップをする場合、既定ではグローバル管理者になります。詳細については、「[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。         |
    |セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online 組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照してください) |
    
    役割とアクセス許可の詳細については、「[Office 365 セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

- [ATP の安全な添付ファイルポリシーのオプションについて](#step-3-learn-about-atp-safe-attachments-policy-options)(この記事の内容)。 モニターまたは置換オプションなどの一部のオプションでは、添付ファイルがスキャンされている間、電子メールの多少の遅延が生じることがあります。 メッセージの遅延を回避するには、[動的配信とプレビュー](dynamic-delivery-and-previewing.md)を使用することを検討してください。
    
- 新規または更新されたポリシーがすべての Office 365 データセンターに蔓延するのに最大30分かかります。
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>手順 2: ATP の安全な添付ファイルポリシーを設定 (または編集) する
  
1. [https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。 
    
2. Office 365 &amp;セキュリティ/コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下にある [**ポリシー** \>の**安全な添付ファイル**] を選択します。
    
3. **[SharePoint、OneDrive、Microsoft Teams に対して ATP を有効**にする] が表示されている場合は、このオプションを選択することをお勧めします。 これにより、office [365 Advanced Threat Protection For SharePoint、OneDrive、Microsoft Teams](atp-for-spo-odb-and-teams.md) for office 365 環境が有効になります。 
    
4. [**新規**] を選択します (新しいボタンは**+** プラス記号 () に似ています)。ポリシーの作成を開始します。
    
5. ポリシーの名前、説明、および設定を指定します。<br/><br/>**例:** すべてのユーザーのメッセージを直ちに配信する "遅延なし" というポリシーを設定し、スキャン後に添付ファイルを再び添付するには、次の設定を指定できます。 
    
      - [**名前**] ボックスに、「遅延」と入力します。
    
      - [**説明**] ボックスに、次のような説明を入力します。スキャン後にメッセージを直ちに送信して、添付ファイルを再度添付します。
    
      - [応答] セクションで、[**動的配信**] オプションを選択します。 ([動的配信と、ATP の安全な添付ファイルを使用したプレビューの詳細について説明](dynamic-delivery-and-previewing.md)します)。
    
      - [**添付ファイルのリダイレクト**] セクションで、[リダイレクトを有効にする] オプションを選択し、悪意のある添付ファイルを調査する Office 365 グローバル管理者、セキュリティ管理者、またはセキュリティアナリストの電子メールアドレスを入力します。 
    
      - [**適用先**] セクションで、[**受信者ドメイン**] を選択して、ドメインを選択します。 [**追加**] を選択し、[ **OK]** を選択します。
    
6. **[保存]** を選択します。
    
組織に複数の ATP の安全な添付ファイルポリシーをセットアップすることを検討してください。 これらのポリシーは、[ **ATP Safe Attachments** ] ページに表示されている順序で適用されます。 ポリシーを定義または編集した後、ポリシーが Microsoft データセンター全体で有効になるまで、少なくとも30分待ってください。 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>手順 3: ATP の安全な添付ファイルポリシーのオプションについて学習する

ATP の安全な添付ファイルのポリシーを設定するときは、Monitor、Block、Replace、動的配信など、さまざまなオプションから選択します。 これらのオプションの機能について疑問がある場合は、次の表で各オプションとその影響について要約しています。
  
|**オプション**|**Effect**|**次の場合に使用します。**|
|:-----|:-----|:-----|
|**オフ** <br/> |マルウェアの添付ファイルをスキャンしない  <br/> メッセージ配信を遅延しない  <br/> |既知の適切な添付ファイルのみを送信する内部送信者、スキャナー、fax、またはスマートホストのスキャンを無効にします。  <br/> 内部メールのルーティングで不必要な遅延が発生しないようにする  <br/> **このオプションは、ほとんどのユーザーには推奨されていません。このオプションを使用すると、内部の送信者の小さなグループに対して、ATP の安全な添付ファイルのスキャンをオフにすることができます。**           |
|**モニター** <br/> |添付ファイル付きのメッセージを配信し、検出されたマルウェアの発生を追跡します。  <br/> |検出されたマルウェアが組織内で通過する場所を確認する  <br/> |
|**Block** <br/> |検出されたマルウェア添付ファイルのメッセージを処理できないようにする  <br/> 検出されたマルウェアを持つメッセージを[Office 365 で検疫](manage-quarantined-messages-and-files.md)に送信します。これにより、セキュリティ管理者またはアナリストは、これらのメッセージを確認および解放 (または削除) できます。  <br/> 今後のメッセージと添付ファイルを自動的にブロックする  <br/> |同じマルウェアの添付ファイルを使用して、組織を繰り返しの攻撃から保護する  <br/> |
|**Replace** <br/> |検出されたマルウェアの添付ファイルを削除する  <br/> 添付ファイルが削除されたことを受信者に通知します  <br/> 検出されたマルウェアを持つメッセージを[Office 365 で検疫](manage-quarantined-messages-and-files.md)に送信します。これにより、セキュリティ管理者またはアナリストは、これらのメッセージを確認および解放 (または削除) できます。  <br/> |検出されたマルウェアが原因で添付ファイルが削除された受信者に表示を昇格させる  <br/> |
|**動的配信** <br/> |メッセージを即時配信  <br/> スキャンが完了するまで添付ファイルをプレースホルダーファイルに置き換え、マルウェアが検出されない場合は添付ファイルを再び添付します。  <br/> スキャン時に、ほとんどの Pdf および Office ファイルの添付ファイルのプレビュー機能が含まれます。  <br/> 検出されたマルウェアを含むメッセージを、セキュリティ管理者またはアナリストが確認および解放 (または削除) できる検疫に送信します。  <br/> [ATP の安全な添付ファイルを使用した動的配信とプレビューについて](dynamic-delivery-and-previewing.md) <br/> |悪意のあるファイルから受信者を保護するときにメッセージの遅延を回避する  <br/> 受信者がスキャンの実行中にセーフモードで添付ファイルをプレビューできるようにする  <br/> |
|**リダイレクトを有効にする** <br/> |[モニター、ブロック、または置換] オプションを選択したときに適用されます。  <br/> セキュリティ管理者またはアナリストが調査できる指定された電子メールアドレスに添付ファイルを送信します。  <br/> |セキュリティ管理者とアナリストが疑わしい添付ファイルを調査できるようにする  <br/> |
   
## <a name="next-steps"></a>次のステップ

ATP の安全な添付ファイルのポリシーを設定すると、レポートを表示することによって、ATP が組織でどのように機能しているかを確認できます。 詳細については、以下のリソースを参照してください。
- [Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)
- [セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する](use-explorer-in-security-and-compliance.md)

ATP に関する新機能を常に活用してください。 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)にアクセスし、 [ATP に追加](office-365-atp.md#new-features-in-office-365-atp)されている新機能について説明します。
 