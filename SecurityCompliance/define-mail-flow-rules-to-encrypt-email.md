---
title: Office 365 で電子メール メッセージを暗号化するためにメール フローの規則を定義します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: Office 365 グローバル管理者は、メールに Office 365 メッセージの暗号化 (ホーム) を有効にするのには、フロー ルールを作成できます。送信電子メール メッセージを暗号化し、内部のメッセージから、または組織から送信される、暗号化されたメッセージへの返信を暗号化を解除できます。
ms.openlocfilehash: e9c6874ce304d1af9da093c02cbc954c54dae8cc
ms.sourcegitcommit: c05076501dfe118e575998ecfc08ad69d13c8abc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "25853092"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>Office 365 で電子メール メッセージを暗号化するためにメール フローの規則を定義します。

Office 365 グローバル管理者は、メール フロー ルール、送受信する電子メールのメッセージを保護するために、トランスポート ルールとも呼ばれますを作成します。送信電子メール メッセージを暗号化および暗号化されたメッセージを組織内から、または組織から送信される、暗号化されたメッセージへの返信から暗号化を削除するルールを設定することができます。これらのルールを作成するのには、Exchange 管理センター (EAC) または Exchange のオンラインの Windows PowerShell コマンドレットを使用できます。 だけでなく全体の暗号化の規則を有効にするか、エンド ・ ユーザーの個々 のメッセージの暗号化オプションを無効にすることもできます。
  
最近に移行する AD RMS から Azure 情報の保護、新しい環境で作業を続けられるようにするのには、既存のメール フロー ルールを確認する必要があります。さらに、新しい Office 365 メッセージの暗号化 (ホーム) 機能を使用するを通じて利用 Azure 情報保護する場合は、既存のメール フロー ルールを更新する必要があります。それ以外の場合、ユーザーは引き続き、シームレスな新しいホームの経験ではなく HTML 添付ファイルの以前の形式を使用する暗号化されたメールを受信します。ホームをまだ設定していない場合は、情報の[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能を設定](set-up-new-message-encryption-capabilities.md)を参照してください。 
  
メール フロー ルール、およびメール フローによる作業時間の規則を構成するコンポーネントについては、 [Exchange Online でメールの流れのルール (トランスポート ルール)](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)を参照してください。Azure の情報保護とメール フロー ルールの動作に関する詳細については、 [Azure の情報保護のラベルのメール フロー ルールを構成する Exchange のオンライン](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)を参照してください。
  
## <a name="hybrid-exchange-environments-do-this-first"></a>ハイブリッド Exchange 環境: この最初の操作を行います
オンプレミス Exchange Online でメールをルーティングする場合は、ホームを使用して、暗号化されたメールを送信できます。これを行うには、メール フローをフロー、電子メール サーバーから Office 365 に構成する必要があります。Office 365 を通過するメールを構成した後は、この資料を使用してホームのメール フロー ルールを作成できます。

手順については、 [Office 365 と、独自のメール ・ サーバ間でメールをルーティングするコネクタのセットアップ](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)を参照してください。具体的には、手順に"第 2 部: メールをメール サーバーから Office 365 へのフローを構成する」です。

## <a name="create-a-mail-flow-rule-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>新しいホーム機能を持つ電子メール メッセージを暗号化するためにメール フロー ルールを作成します。

EAC を使用して新しいホーム機能でメッセージの暗号化をトリガーするためのメール フロー ルールを定義することができます。
  
### <a name="to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities-by-using-the-eac"></a>EAC を使用して新しいホーム機能を持つ電子メール メッセージを暗号化するための規則を作成するには

1. Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。
    
2. **管理者**のタイルを選択します。 
    
3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。
    
4. EAC で**メールの流れ**に移動\>**ルール** \> ![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)(**新規**) \> **新しい規則を作成**します。詳細については、EAC を使用して、 [Exchange のオンラインでの Exchange 管理センター](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)を参照してください。
    
5. [**名前**] には、DrToniRamos@hotmail.com の暗号化メールのルールの名前を入力します。
    
6. **[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。 
    
    1. **[次の場合、このルールを適用する]** で、**[受信者]** を選択します。
    
    2. 連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。 
    
        既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。
    
        新しい名前を入力、[**名前**] ボックスで電子メール アドレスを入力し、 **[名前の確認**を\> **OK**です。
    
7. さらに条件を追加するのには**他のオプション**を選択**条件の追加**] を選択し、一覧から選択します。 
    
    たとえば、組織外の受信者がいる場合にのみルールを適用するに**条件を追加**] を選択し、[**受信者が外部および内部** \> **組織外** \> **OK**です。
    
8. ホームの新機能で、**次の操作**をからを使用して暗号化を有効にするには、**メッセージ セキュリティの変更**] を選択し、 **Office 365 メッセージ暗号化を適用し権利保護**します。RMS テンプレートを一覧から選択、**保存**を選択し、[ **ok]** します。
    
    テンプレートの一覧には、すべての既定のテンプレートが含まれていて、オプションと同様に作成したカスタム テンプレートを Office 365 で使用します。リストが空の場合は、設定することが Office 365 のメッセージの暗号化を新しい機能を備えた[Azure の情報保護の上位に構築され、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)の説明に従ってを確認します。既定のテンプレートの詳細については、[構成して Azure の情報保護のためのテンプレートを管理する](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)を参照してください。[**転送不可**] オプションの詳細については、[電子メールの転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を参照してください。**のみ暗号化**オプションの詳細については、[電子メールの暗号化のみ] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を参照してください。
    
    別のアクションを指定する場合は、**アクションを追加する**選択できます。 
    
### <a name="to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities-by-using-the-eac"></a>EAC を使用してホームの新機能を使用する既存のメール フロー ルールを更新するには

1. Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。
    
2. **管理者**のタイルを選択します。 
    
3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。
    
4. **メール フロー**には、EAC で\>**の規則**。
    
5. メール フロー ルールの一覧で、新しいホーム機能を使用し、選択を変更するルールを選択します![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)(**編集**) します。
    
6. ホームの新機能で、**次の操作**をからを使用して暗号化を有効にするには、**メッセージのセキュリティの変更**を選択し、**適用 Office 365 のメッセージの暗号化および権利の保護**します。RMS テンプレートを一覧から選択、**保存**を選択し、[ **ok]** します。
    
    テンプレートの一覧には、すべての既定のテンプレートが含まれていて、オプションと同様に作成したカスタム テンプレートを Office 365 で使用します。リストが空の場合は、設定することが Office 365 のメッセージの暗号化を新しい機能を備えた[Azure の情報保護の上位に構築され、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)の説明に従ってを確認します。既定のテンプレートの詳細については、[構成して Azure の情報保護のためのテンプレートを管理する](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)を参照してください。[**転送不可**] オプションの詳細については、[電子メールの転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を参照してください。**のみ暗号化**オプションの詳細については、[電子メールの暗号化のみ] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を参照してください。
    
    別のアクションを指定する場合は、**アクションを追加する**選択できます。 
    
7. **次の操作**] ボックスの一覧から、**メッセージ セキュリティの変更**] に割り当てられているすべてのアクションを削除します\>**ホームの以前のバージョンを適用**します。
    
8. [ **保存**] を選びます。
    
## <a name="creating-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Office 365 のメッセージの暗号化のルールを作成する新しい機能がないです。

新しいホーム機能を提供する、Office 365 の組織にまだ移動していない場合、は、組織のメッセージを暗号化するためにメール フローの規則を定義するのにはこれらのタスクを使用します。ホームの新機能、組織の適切なことがすぐに移動するための計画を作成することをお勧めします。手順については、[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。
  
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-the-eac"></a>EAC を使用して新しいホーム機能のない電子メール メッセージを暗号化するための規則を作成するには

1. Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。
    
2. **管理者**のタイルを選択します。 
    
3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。
    
4. EAC で**メールの流れ**に移動\>**ルール** \> **+** (**新規**) \> **新しい規則を作成**します。詳細については、EAC を使用して、 [Exchange のオンラインでの Exchange 管理センター](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)を参照してください。
    
5. [**名前**] には、DrToniRamos@hotmail.com の暗号化メールのルールの名前を入力します。
    
6. **[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。 
    
1. **[次の場合、このルールを適用する]** で、**[受信者]** を選択します。
    
2. 連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。 
    
    既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。
    
    新しい名前を入力、[**名前**] ボックスで電子メール アドレスを入力し、 **[名前の確認**を\> **OK**です。
    
7. さらに条件を追加するに**他のオプション**を選択し、[**条件の追加**] を選択し、リストから選択します。 
    
    たとえば、組織外の受信者がいる場合にのみルールを適用するに**条件を追加**] を選択し、[**受信者が外部および内部** \> **組織外** \> **OK**です。
    
8. なし機能を使用して、新しいホーム、**次の操作**で暗号化を有効にするのには **、メッセージ セキュリティの変更**] を選択\>**ホームの以前のバージョンを適用**し、**保存**を選択します。
    
    エラーが発生する場合は、使用許諾契約が IRM 機能が有効になってし、まだ組織のホームを設定していません。ホームをここで設定したい場合は、新しいホーム機能を使用するを設定する必要があります。については、[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。Microsoft は、新しい機能がないホームの新規の展開の設定をサポートしていません。
    
    別のアクションを指定する場合は、**アクションを追加する**選択できます。 
    
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a>Exchange オンラインの Windows PowerShell を使用して新しいホーム機能のない電子メール メッセージを暗号化するための規則を作成するには

1. オンラインの Exchange へのリモート PowerShell セッションを作成するのには、ローカル コンピューター上の Windows PowerShell を使用します。詳細については、 [Exchange オンライン PowerShell への接続](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)を参照してください。
    
2. **新規 TransportRule**コマンドレットを使用してルールを定義し、 **ApplyOME**属性を**true**に設定します。
    
    たとえば、DrToniRamos@hotmail.com にアドレス指定されたすべての電子メール メッセージを暗号化する必要があることを必要とする次のように入力します。
    
     ```
     New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
     ```

    この例では次のようになっています。
    
  - 新しいルールの名前は、「Dr Toni タモの暗号化ルール」です。
    
  - **-送信**パラメーターでは、電子メール メッセージ内の受信者を検索する条件を指定します。など、電子メール アドレス、名、識別名 (DN)、受信者を一意に識別する任意の値を使用することができます。この例では、受信者が電子メール アドレス"DrToniRamos@hotmail.com"によって識別されます。 
    
  - **-SentToScope**パラメーターは、受信者の場所を検索する条件を指定します。この例では、受信者のメールボックスは hotmail し、"NotInOrganization"の値が使用されるので、Office 365 の組織の一部ではありません。 
    
    このコマンドレットを使用してメール フローの規則を設定することができます、条件の詳細については、[新規 TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)を参照してください。
    
### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>新しいホーム機能なしで暗号化電子メールの返信の暗号化を解除します。

電子メール ユーザーは、暗号化されたメッセージを送信、ときにそれらのメッセージの受信者が暗号化された応答で応答できます。メールの返信を組織のメール ユーザーを表示するための暗号化のポータルにサインインする必要はありませんので暗号化を自動的に削除するフロー ルールを作成できます。EAC または Windows PowerShell コマンドレットを使用すると、これらの規則を定義します。ホームの新機能を使用されていない場合は、あなたの組織または組織内から送信されたメッセージへの返信のメッセージから送信されたいずれかのメッセージのみ解読できます。組織の外部から発信されたメッセージを暗号化の暗号化を解除することはできません。
  
#### <a name="to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-the-eac"></a>EAC を使用して新しいホーム機能なしで暗号化電子メールの返信を暗号化を削除するルールを作成するには
<a name="DecryptruleEACNoNewOME"> </a>

1. Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)の管理者権限が与えられている、職場、学校のアカウントを使用してください。
    
2. **管理者**のタイルを選択します。 
    
3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。
    
4. EAC で**メールの流れ**に移動\>**ルール** \> **+** (**新規**) \> **新しい規則を作成**します。詳細については、EAC を使用して、 [Exchange のオンラインでの Exchange 管理センター](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx)を参照してください。
    
5. [**名前**] には、受信メールから削除暗号化など、ルールの名前を入力します。
    
6. **場合は、このルールを適用する**には、**受信者は**、メッセージから暗号化を削除する必要がある条件を選択して\> **、組織の内部**。
    
7. **次の操作**をには、**メッセージ セキュリティの変更**] を選択\>**ホームの以前のバージョンを削除**します。
    
8. [ **保存**] をクリックします。
    
#### <a name="to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a>Exchange オンラインの Windows PowerShell を使用して新しいホーム機能なしで暗号化電子メールの返信を暗号化を解除する規則を作成するには
<a name="DecryptrulePShellNoNewOME"> </a>

1. オンラインの Exchange へのリモート PowerShell セッションを作成するのには、ローカル コンピューター上の Windows PowerShell を使用します。詳細については、 [Exchange オンライン PowerShell への接続](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)を参照してください。
    
2. **新規 TransportRule**コマンドレットを使用してルールを定義し、 **RemoveOME**属性を**true**に設定します。
    
    たとえば、Office 365 の組織内の受信者に送信されるすべてのメールから暗号化を削除するのには次のように入力します。
    
     ```
     New-TransportRule - Name "Remove encryption from incoming mail"     -SentToScope "InOrganization" -RemoveOME $true
     ```

    この例では次のようになっています。
    
  - 新しいルールの名前は、「受信メールから暗号化を削除する」です。
    
  - **-SentToScope**パラメーターは、受信者の場所を検索する条件を指定します。この例では、あることを示す"InOrganization"の値を使用します。 
    
  - 受信者のメールボックス、メール ユーザー、グループ、または組織内のパブリック フォルダーのメールが有効なのですか
    
  - 受信者のメール アドレスが、権限のあるドメインまたは内部の中継ドメインとして構成されている承認済みドメインに属していて、かつ メッセージが認証済み接続経由で送信または受信された。
    
    このコマンドレットを使用してメール フローの規則を設定することができます、条件の詳細については、[新規 TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)を参照してください。
    
## <a name="related-topics"></a>関連項目

[Office 365 での暗号化](encryption.md)
  
[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能を設定します](set-up-new-message-encryption-capabilities.md)
  
[暗号化メッセージへのブランドの追加](add-your-organization-brand-to-encrypted-messages.md)
  
[Exchange Online のメール フロー ルール (トランスポート ルール)](https://go.microsoft.com/fwlink/p/?LinkId=506707)
  
[Exchange Online Protection のメール フロー ルール (トランスポート ルール)](https://go.microsoft.com/fwlink/p/?LinkId=506708)
  

