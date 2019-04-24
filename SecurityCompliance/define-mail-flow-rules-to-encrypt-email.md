---
title: Office 365 でメール メッセージを暗号化するためにメール フロー ルールを定義する
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 メッセージの暗号化を使用してメッセージを暗号化および復号化するメールフロールール (トランスポートルール) を作成する方法について説明します。
ms.openlocfilehash: 1f5b0ff9be5994f036d2367d0b15744c24f2bbe0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257705"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>Office 365 でメール メッセージを暗号化するためにメール フロー ルールを定義する

Office 365 全体管理者は、メールフロールール (トランスポートルールとも呼ばれます) を作成して、送受信する電子メールメッセージを保護することができます。 送信電子メールメッセージを暗号化したり、組織内から送信される暗号化されたメッセージから暗号化を削除したり、組織から送信された暗号化メッセージへの返信を削除したりするためのルールを設定できます。 これらのルールを作成するには、exchange 管理センター (EAC) または exchange Online PowerShell を使用できます。 全体的な暗号化ルールに加えて、エンド ユーザー用に個別のメッセージの暗号化オプションの有効化/無効化を選択することもできます。

||
|:-----|
|この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。 この記事は、管理者および it 担当者を対象としています。 暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。 |
||

AD RMS から Azure Information Protection に最近移行した場合は、既存のメールフロールールを確認して、新しい環境で引き続き動作するようにする必要があります。 さらに、Azure Information Protection を使用して利用できる新しい Office 365 Message Encryption (OME) 機能を利用する場合は、既存のメールフロールールを更新する必要があります。 そうしないと、ユーザーは、新しいシームレスな OME の操作ではなく、前の HTML 添付ファイル形式を使用する暗号化メールを引き続き受信できます。 まだ OME をセットアップしていない場合は、「 [Office の新しい365メッセージ暗号化機能を設定](set-up-new-message-encryption-capabilities.md)する」を参照してください。

メールフロールールを構成するコンポーネントと、メールフロールールのしくみについては、「 [Exchange Online のメールフロールール (トランスポートルール)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」を参照してください。 メールフロールールが azure information protection でどのように機能するかの詳細については、「 [azure information protection のラベルの Exchange Online メールフロールールの構成](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)」を参照してください。

> [!IMPORTANT]
> ハイブリッド exchange 環境では、オンプレミスのユーザーは、電子メールが Exchange Online を経由してルーティングされる場合にのみ、OME を使用して暗号化されたメールを送信できます。 ハイブリッド Exchange 環境で OME を構成するには、まず[ハイブリッド構成ウィザードを使用してハイブリッドを構成](https://docs.microsoft.com/Exchange/exchange-hybrid)し、次に、[電子メールサーバーから Office 365 にメールが流れるように構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)する必要があります。 Office 365 を通過するようにメールを構成したら、このガイダンスを使用して OME のメールフロールールを構成できます。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>メールフロールールを作成して、新しい OME 機能で電子メールメッセージを暗号化する

EAC を使用して、新しい OME 機能でメッセージの暗号化をトリガーするためのメールフロールールを定義できます。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能で電子メールメッセージを暗号化するためのルールを作成する

1. web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [**管理**] タイルを選択します。

3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。

4. EAC で、[**メールフロー** \> ] [**ルール**] に**** ![移動し、](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> [新しい新規作成] アイコンを選択して**新しいルールを作成**します。 EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。

5. [**名前**] にルールの名前 (DrToniRamos@hotmail.com のメールの暗号化など) を入力します。

6. **[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。

   1. **[次の場合、このルールを適用する]** で、**[受信者]** を選択します。

   2. 連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。

      - 既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。

      - 新しい名前を入力するには、[**名前の確認**] ボックスに電子メールアドレスを入力し、[**名前** \>の確認 **]** を選択します。

7. 他の条件を追加するには、[**その他のオプション**] を選択し、[**条件の追加**] を選択して、一覧から選択します。

   たとえば、受信者が組織の外部にいる場合にのみルールを適用するには、[**条件の追加**] を選択し、[**受信者が外部/内部** \>の**組織** \>外にある **]** を選択します。

8. 新しい OME 機能を使用して暗号化を有効にするには、**次の操作を行い**ます。次に、[**メッセージのセキュリティを変更**する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。 一覧から RMS テンプレートを選択し、[**保存**] を選択して、[ **OK]** を選択します。
  
  テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。 リストが空の場合は、「office の[新しいメッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」の説明に従って、office 365 メッセージの暗号化を新しい機能で設定していることを確認してください。 既定のテンプレートの詳細については、「 [Azure information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。 [**転送**しない] オプションの詳細については、「[メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。 [**暗号化のみ**] オプションの詳細については、「[電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。

  別のアクションを指定する場合は、[**アクションの追加**] を選択できます。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>EAC を使用して既存のメールフロールールを更新し、新しい OME 機能を使用する

1. web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [**管理**] タイルを選択します。

3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。

4. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

5. メールフロールールの一覧で、新しい OME 機能を使用するように変更するルールを選択し、[編集**** ![] [編集](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)] アイコンを選択します。

6. 新しい OME 機能を使用して暗号化を有効にするには、**次の操作を行い**ます。次に、[**メッセージのセキュリティを変更**する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。 一覧から RMS テンプレートを選択し、[**保存**] を選択して、[ **OK]** を選択します。

   テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。 リストが空の場合は、「 [Azure Information Protection の上に構築された新しい office 365 メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」に記載されているように、新しい機能を使用して office 365 メッセージの暗号化を設定していることを確認してください。 既定のテンプレートの詳細については、「 [Azure information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。 [**転送**しない] オプションの詳細については、「[メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。 [**暗号化のみ**] オプションの詳細については、「[電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。

   別のアクションを指定する場合は、[**アクションの追加**] を選択できます。

7. [**実行**する処理] で、**メッセージセキュリティ** \>を変更するために割り当てられているアクションを削除します。**以前のバージョンの OME を適用**します。

8. **[保存]** を選択します。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>新しい機能を使用せずに Office 365 メッセージ暗号化のメールフロールールを作成する

Office 365 組織を新しい OME 機能にまだ移行していない場合は、これらのタスクを使用して、組織のメッセージを暗号化するためのメールフロールールを定義します。 Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。 手順については、「 [Azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能を使用せずに電子メールメッセージを暗号化するためのメールフロールールを作成する

1. web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [**管理**] タイルを選択します。

3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。

4. EAC で、[**メールフロー** \> ] [**ルール**] に**** ![移動し、](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> [新しい新規作成] アイコンを選択して**新しいルールを作成**します。 EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。

5. [**名前**] にルールの名前 (DrToniRamos@hotmail.com のメールの暗号化など) を入力します。

6. **[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。

   1. **[次の場合、このルールを適用する]** で、**[受信者]** を選択します。

   2. 連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。

      - 既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。

      - 新しい名前を入力するには、[**名前の確認**] ボックスに電子メールアドレスを入力し、[**名前** \>の確認 **]** を選択します。

7. さらに条件を追加するには、[**その他のオプション**] を選択し、[**条件の追加**] を選択してリストから選択します。

   たとえば、受信者が組織の外部にいる場合にのみルールを適用するには、[**条件の追加**] を選択し、[**受信者が外部/内部** \>の**組織** \>外にある **]** を選択します。

8. 新しい OME 機能を使用せずに暗号化を有効にするには、**次の操作を行い**ます。 [**メッセージセキュリティ** \>を変更する] [**前のバージョンの OME を適用**する]、[**保存**] の順に選択します。

  IRM ライセンスが有効になっていないというエラーが表示された場合は、まだ組織の OME をセットアップしていません。 今すぐ OME を設定したい場合は、新しい OME 機能を使用するように設定する必要があります。 詳細については、「 [Azure information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。 Microsoft では、新しい機能なしで OME の新しい展開をセットアップすることはサポートされなくなりました。

  別のアクションを指定する場合は、[**アクションの追加**] を選択できます。

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Exchange Online の PowerShell を使用して、新しい OME 機能なしで電子メールメッセージを暗号化するためのメールフロールールを作成する

1. Exchange Online PowerShell への接続。 詳細については、「[Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

2. **new-transportrule**コマンドレットを使用してルールを作成し、 _ApplyOME_パラメーターをに`$true`設定します。

   この例では、DrToniRamos@hotmail.com に送信されるすべての電子メールメッセージが暗号化されている必要があります。

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   **注**:

   - 新しいルールの一意の名前は、"Dr toni ramos の暗号化ルール" です。

   - パラメーター_に_は、メッセージの受信者を指定します (名前、電子メールアドレス、識別名などで識別されます)。 この例では、受信者は電子メールアドレス "DrToniRamos@hotmail.com" によって識別されます。

   - / __ は、メッセージの受信者の場所を指定します。 この例では、受信者のメールボックスは hotmail にあり、Office 365 組織の一部ではないため`NotInOrganization` 、値が使用されます。

   構文およびパラメーターの詳細については、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)」を参照してください。

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>新しい OME 機能を使用せずに暗号化された電子メールの返信から暗号化を削除する

電子メール ユーザーが暗号化メッセージを送信した場合、これらのメッセージの受信者は、暗号化された返信で応答することができます。 メールフロールールを作成して、返信からの暗号化を自動的に削除することで、組織内の電子メールユーザーが暗号化ポータルにサインインして表示されないようにすることができます。 これらのルールは、EAC または Windows PowerShell コマンドレットを使用して定義できます。 新しい OME 機能をまだ使用していない場合は、組織内から送信されたメッセージまたは組織内から送信されたメッセージに返信されるメッセージの暗号化を解除することしかできません。 組織外からの暗号化されたメッセージを解読することはできません。

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能を使用せずに暗号化された電子メールの返信からの暗号化を削除するためのルールを作成する

1. web ブラウザーで、管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [**管理**] タイルを選択します。

3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。

4. EAC で、[**メールフロー** \> ] [**ルール**] に**** ![移動し、](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> [新しい新規作成] アイコンを選択して**新しいルールを作成**します。 EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。

5. [**名前**] にルールの名前を入力します。たとえば、[受信メールからの暗号化の削除] などです。

6. [**次の場合、このルールを適用**する] [**受信者が** \> **組織内**にある] など、メッセージから暗号化を削除する条件を選択します。

7. [**実行する処理**] で、[**メッセージのセキュリティ** \>を変更する] を選択します。**以前のバージョンの OME を削除**します。

8. [**保存**] を選択します。

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Exchange Online PowerShell を使用して、新しい OME 機能なしで暗号化された電子メールの返信から暗号化を削除するルールを作成する

1. Exchange Online PowerShell への接続。 詳細については、「[Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

2. **new-transportrule**コマンドレットを使用してルールを作成し、 _RemoveOME_パラメーターをに`$true`設定します。

   この例では、Office 365 組織内の受信者に送信されるすべてのメールから暗号化を削除します。

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   **注**:

   - 新しいルールの一意の名前は、"受信メールから暗号化を削除する" です。

   - / __ は、メッセージの受信者の場所を指定します。 この例では、値`InOrganization`の値を使用して、次のことを示します。

     - 受信者が組織内のメールボックス、メールユーザー、グループ、またはメールが有効なパブリックフォルダーである。

       or

     - 受信者の電子メールアドレスが、組織内の権限のあるドメインまたは内部の中継ドメインとして構成さ__ れている承認済みドメイン内にあり、認証された接続を介してメッセージが送信または受信された。

構文およびパラメーターの詳細については、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)」を参照してください。

## <a name="related-topics"></a>関連トピック

[Office 365 での暗号化](encryption.md)

[新しい Office 365 Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md)

[暗号化メッセージへのブランドの追加](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online のメール フロー ルール (トランスポート ルール)](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Exchange Online Protection のメール フロー ルール (トランスポート ルール)](https://go.microsoft.com/fwlink/p/?LinkId=506708)
