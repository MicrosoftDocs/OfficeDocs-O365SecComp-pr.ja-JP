---
title: 組織用に監督ポリシーを構成する
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 監督レビューポリシーを設定して、レビューのために従業員のコミュニケーションをキャプチャします。
ms.openlocfilehash: ce032a96131fdfb6f226dd25dfbb8e2de41c9931
ms.sourcegitcommit: a79eb9907759d4cd849c3f948695a9ff890b19bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30866393"
---
# <a name="configure-supervision-policies-for-your-organization"></a>組織用に監督ポリシーを構成する

監督ポリシーを使用して、内部または外部のレビューアーによる検査のために従業員の通信をキャプチャします。 監督ポリシーが組織内の通信を監視するのに役立つ方法の詳細については、「 [Office 365 の監督ポリシー](supervision-policies.md)」を参照してください。

> [!NOTE]
> 監督ポリシーによって監視されるユーザーは、Microsoft 365 E5 コンプライアンスライセンス、Advanced コンプライアンスアドオンを備えた office 365 Enterprise E3 ライセンス、または office 365 Enterprise E5 サブスクリプションに含まれている必要があります。
既存の Enterprise e5 プランを所有しておらず、監督を試みる場合は、 [Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。
  
Office 365 組織の監督をセットアップして使用するには、次の手順を実行します。
  
- **手順 1 (オプション)** - [監督のグループをセットアップする](configure-supervision-policies.md#exampledist)

    監督の使用を開始する前に、誰が通信をレビューし、それらのレビューを実行するかを決定します。 監督がどのように機能するかを確認するために、少数のユーザーのみを使用して作業を開始する場合は、現時点ではグループの設定を省略できます。

- **手順 2 (必須)** - [組織内で監督を利用できるようにする](configure-supervision-policies.md#MakeAvailable)

    ポリシーをセットアップできるように、自分を監督レビュー役割グループに追加します。 この役割が割り当てられているすべてのユーザーは、Security & コンプライアンスセンターの**データガバナンス**の下にある [**監督**] ページにアクセスできます。 確認する電子メールが exchange online でホストされている場合、各レビュー担当者も[exchange online へのリモート PowerShell アクセス権](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)を持っている必要があります。

- **手順 3 (省略可能)** - [カスタムの機密情報の種類またはユーザー設定のキーワードディクショナリ/辞書を構成する](configure-supervision-policies.md#sensitiveinfo)

    監督ポリシーにカスタムの機密情報の種類またはカスタムキーワード辞書を使用する必要がある場合は、監督のウィザードを開始する前に、それを作成する必要があります。

- **手順 4 (必須)** - [監督ポリシーをセットアップする](configure-supervision-policies.md#setupsuper)

    「Security & コンプライアンスセンターで監督ポリシーを作成します。 これらのポリシーは、組織内で検討する必要のある通信を定義し、レビューを実行するユーザーを指定します。 コミュニケーションには、電子メールと Microsoft Teams の通信、およびサードパーティ製のプラットフォーム通信 (Facebook、Twitter など) が含まれます。

- **手順 5-(省略可能)**[新しい監督ポリシーをテストする](configure-supervision-policies.md#TestPolicy)

    監督ポリシーをテストして、必要に応じて機能していることを確認してください。これは、コンプライアンス戦略が標準を満たしていることを確認するための重要な部分です。

- **手順 6-(省略可能)**[Office 365 監督ダッシュボードまたは web 上の outlook (以前の outlook web App) を使用しないで、監視された通信を確認するには、outlook を構成](configure-supervision-policies.md#UseOutlook)します。

    outlook を構成して、レビューアーが outlook クライアント内の監督機能にアクセスできるようにして、各アイテムを評価および分類できるようにすることができます。

<a name="exampledist"> </a>

## <a name="step-1---set-up-groups-for-supervision-optional"></a>手順 1-監督のグループをセットアップする (オプション)

 監督ポリシーを作成すると、誰が通信をレビューし、それらのレビューを実行するかを決定できます。 このポリシーでは、電子メールアドレスを使用して個人またはユーザーのグループを識別します。 セットアップを簡単にするために、コミュニケーションをレビューするユーザーのためのグループを作成できます。 グループを使用している場合、たとえば、2つの異なるグループ間の通信を監視する場合、または、監視しないグループを指定する場合は、いくつかの必要な場合があります。

次の表を使用して、監督ポリシー用に組織内のグループを構成する方法について説明します。

| **ポリシーメンバー** | **サポートされるグループ** | **サポートされないグループ** |
|:-----|:-----|:-----|
|ユーザーの監視 | 配布グループ <br> Office 365 グループ | 動的配布グループ |
| Reviewers | メールが有効なセキュリティ グループ  | 配布グループ <br> 動的配布グループ |
  
大規模なエンタープライズ組織での管理対象ユーザーを管理するには、非常に大きなグループにまたがるすべてのユーザーを監視する必要がある場合があります。 PowerShell を使用して、割り当てられたグループのグローバル監督ポリシーの配布グループを構成できます。 これは、1つのポリシーで数千のユーザーを監視し、新しい従業員が組織に参加したときに監督ポリシーを更新するのに役立ちます。

1. 次のプロパティを使用して、グローバル監督ポリシー用の専用の[配布グループ](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)を作成します。 この配布グループが他の目的または他の Office 365 サービスで使用されていないことを確認してください。

    - **MemberDepartRestriction = Closed**。 これにより、ユーザーは配布グループから自分自身を削除することができなくなります。
    - **memberjoinrestriction = Closed**。 これにより、ユーザーは自分を配布グループに追加できなくなります。
    - **ModerationEnabled = True**。 これにより、このグループに送信されるすべてのメッセージを承認する必要があり、監督ポリシー構成の外部との通信にグループが使用されていないことが保証されます。

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. 組織内の監督ポリシーに追加されたユーザーを追跡するために使用する、未使用の[Exchange カスタム属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)を選択します。

3. 次の PowerShell スクリプトを定期的なスケジュールで実行して、ユーザーを監督ポリシーに追加します。

    ```
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

グループのセットアップの詳細については、以下を参照してください。
- [配布グループを作成および管理する](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [メールが有効なセキュリティ グループの管理](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Office 365 グループの概要](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

<a name="MakeAvailable"> </a>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>手順 2-組織で監督を利用できるようにする (必須)

セキュリティ & コンプライアンスセンターで、**監督**をメニューオプションとして利用できるようにするには、監督レビュー管理者の役割が割り当てられている必要があります。
  
これを行うには、自分を監督レビュー役割グループのメンバーとして追加するか、新しい役割グループを作成することができます。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>監督レビュー役割グループにメンバーを追加する

1. Office 365 [https://protection.office.com](https://protection.office.com)組織の管理者アカウントの資格情報を使用してサインインします。

2. セキュリティ & コンプライアンスセンターで、[**アクセス許可**] に移動します。

3. [**監督レビュー** ] 役割グループを選択し、[編集] アイコンをクリックします。

4. [**メンバー** ] セクションで、組織の監督を管理するユーザーを追加します。

### <a name="create-a-new-role-group"></a>新しい役割グループを作成する

1. Office 365 [https://protection.office.com](https://protection.office.com)組織の管理者アカウントの資格情報を使用してサインインします。

2. セキュリティ & コンプライアンスセンターで、[**アクセス許可**] に移動し、[**+** 追加] () をクリックします。

3. [**役割**] セクションで、[追加**+**] () をクリックし、[**監督レビュー管理者**] まで下にスクロールします。 この役割を役割グループに追加します。

4. [**メンバー** ] セクションで、組織の監督を管理するユーザーを追加します。

役割グループとアクセス許可の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>レビューアーのリモート PowerShell アクセスを有効にする (電子メールが Exchange Online でホストされている場合)

1. 「 [Exchange Online PowerShell へのアクセスを有効または無効](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)にする」のガイダンスに従ってください。

<a name="sensitiveinfo"> </a>
  
## <a name="step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>手順 3-カスタムの機密情報の種類とカスタムのキーワードディクショナリを作成する (オプション)

監督ポリシーウィザードで既存のカスタムの機密情報の種類またはカスタムキーワードディクショナリから選択するには、最初に、必要に応じてこれらの項目を作成する必要があります。

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>ユーザー設定のキーワード辞書/辞書を作成する (オプション)

テキストエディター (メモ帳など) を使用して、監督ポリシーで監視するキーワード用語を含む新しいファイルを作成します。 各用語が別々の行にあることを確認し、 **Unicode/utf-16 (リトルエンディアン)** 形式でファイルを保存します。

### <a name="create-custom-sensitive-information-types"></a>カスタムの機密情報の種類を作成する

1. 新しい機密情報の種類を作成し、Office 365 セキュリティ & コンプライアンスセンターでユーザー辞書を追加します。 [**分類** \> **機密情報の種類**] に移動し、**新しい機密情報の種類ウィザード**の手順に従います。 ここでは、次の操作を行います。

    - 機密情報の種類の名前と説明を定義する
    - 近接、信頼度、およびプライマリパターン要素を定義する
    - ユーザー辞書を一致要素の要件としてインポートする
    - 選択内容を確認し、機密情報の種類を作成する

    詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」および「[キーワードディクショナリを作成](create-a-keyword-dictionary.md)する」を参照してください。

    ユーザー辞書または辞書を作成した後で、 [get-dlpkeyworddictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)コマンドレットを使用して構成済みのキーワードを表示するか、 [get-dlpkeyworddictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)コマンドレットを使用して用語を追加または削除することができます。

<a name="setupsuper"> </a>

## <a name="step-4---set-up-a-supervision-policy-required"></a>手順 4-監督ポリシーを設定する (必須)
  
1. Office 365 [https://protection.office.com](https://protection.office.com)組織の管理者アカウントの資格情報を使用してサインインします。

2. セキュリティ & コンプライアンスセンターで、[**監督**] を選択します。
  
3. [**作成**] を選択し、ウィザードの指示に従って、ポリシーの次のページを設定します。 ウィザードを使用すると、次のことを行うことができます。

    - ポリシーに名前と説明を指定します。
    - 監督するユーザーまたはグループを選択します。これには、除外するユーザーまたはグループを選択することも含まれます。
    - 監督ポリシー条件を定義します。
    - 機密情報の種類を含めるかどうかを選択します。 ここでは、既定およびカスタムの機密情報の種類を選択できます。
    - レビューする通信の割合を定義します。
    - ポリシーのレビュー担当者を選択します。 レビュー担当者は、個々のユーザーまたは[メールが有効なセキュリティグループに](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)することができます。
    - ポリシーの選択を確認し、ポリシーを作成します。

<a name="TestPolicy"> </a>

## <a name="step-5---test-your-supervision-policy-optional"></a>手順 5-監督ポリシーをテストする (オプション)

監督ポリシーを作成したら、定義した条件がポリシーによって適切に適用されているかどうかをテストすることをお勧めします。 監督ポリシーに機密情報の種類が含まれている場合は、[データ損失防止 (DLP) ポリシーをテスト](create-test-tune-dlp-policy.md)することもできます。 監督ポリシーをテストするには、次の手順を実行します。

1. テストするポリシーで定義された、監視対象のユーザーとしてログインした電子メールクライアントまたは Microsoft Teams を開きます。
2. 監督ポリシーで定義した条件を満たすメールまたは Microsoft Teams のチャットを送信します。 これには、キーワード、添付ファイルのサイズ、ドメインなどを指定できます。ポリシーに構成された条件設定が制限を超えているか、厳しすぎるかを確認してください。

    > [!Note]
    > 定義されたポリシーの対象となるメールは、ほぼリアルタイムで処理され、ポリシーの構成後すぐにテストできます。 Microsoft Teams でのチャットは、ポリシー内で完全に処理されるまでに最大24時間かかる場合があります。 

3. 監督ポリシーに指定されたレビュー担当者として Office 365 テナントにログインします。 [*カスタムポリシー* > **** の**監視** > ] に移動して、ポリシーのレポートを表示します。

<a name="UseOutlook"> </a>

## <a name="step-6---configure-outlook-for-reviewers-optional"></a>手順 6-レビュー担当者用に Outlook を構成する (オプション)

Office 365 で監督ダッシュボードを使用しないで outlook を使用して通信を確認するには、outlook クライアントを構成する必要があります。

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>手順 1: 監督メールボックスのアドレスをコピーする

outlook デスクトップまたは web 用の outlook のレビューを構成するには、監督ポリシーのセットアップの一部として作成された監督メールボックスのアドレスが必要です。
  
> [!NOTE]
> 他のユーザーがポリシーを作成した場合は、そのポリシーからこのアドレスを取得してアドインをインストールする必要があります。

 **監督メールボックスのアドレスを検索するには**
  
1. Office 365 組織の管理者アカウントの資格情報を使用して、 [ &amp;セキュリティコンプライアンスセンター](https://protection.office.com)にサインインします。

2. [**監督**] に移動します。

3. 確認する通信を収集する監督ポリシーをクリックします。

4. [ポリシーの詳細] ポップアップの [**監督メールボックス**] で、アドレスをコピーします。<br/>![強調表示されている監督ポリシーの詳細ポップアップの [監督メールボックス] セクション](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a>手順 2: Outlook アクセス用に監督メールボックスを構成する

次に、レビューアーは、Outlook を監督メールボックスに接続できるように、Exchange Online の PowerShell コマンドをいくつか実行する必要があります。
  
1. Exchange Online PowerShell に接続します。 [タスクの実行方法](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. 次のコマンドを実行し*ます。ここで、SupervisoryReview {GUID} @domain*は上記の手順1でコピーしたアドレスで、 *User*は、手順3で監督メールボックスに接続するレビュー担当者の名前になります。

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. 少なくとも1時間待ってから、手順3に進みます。

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>手順 3: 監督メールボックスに接続するための Outlook プロファイルを作成する

最後の手順では、監督者は、監督メールボックスに接続するための Outlook プロファイルを作成する必要があります。

> [!NOTE]
> 新しい Outlook プロファイルを作成するには、Windows のコントロールパネルの [メール] 設定を使用します。 これらの設定にアクセスするために必要なパスは、使用している windows オペレーティングシステム (windows 7、windows 8、または windows 10)、およびインストールされている Outlook のバージョンによって異なる場合があります。
  
1. [コントロールパネル] を開き、ウィンドウ上部の [**検索**] ボックスに「 **Mail**」と入力します。<br/>(コントロールパネルへのアクセス方法がわからない場合はどうすればよいですか? [[コントロールパネルの場所] を](https://support.microsoft.com/help/13764/windows-where-is-control-panel)参照)
  
2. **メール**アプリを開きます。

3. [**メールの設定-Outlook**] で、[**プロファイルの表示**] をクリックします。<br/>![[プロファイルの表示] ボタンが強調表示されている [メールの設定-Outlook] ダイアログボックス](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. [**メール**] で、[**追加**] をクリックします。 次に、[**新しいプロファイル**] で、監督メールボックスの名前 (「**監督**」など) を入力します。<br/>![[プロファイル名] ボックスに "監督" という名前が表示されている [新しいプロファイル] ダイアログ](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. [ **Outlook を Office 365 に接続**する] で、[**別のアカウントに接続する**] をクリックします。<br/>![[別のアカウントへの接続] リンクが強調表示されている [Outlook から Office への接続 365] メッセージ](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. [**自動アカウントセットアップ**] で、[**手動セットアップ] または [サーバーの種類の追加**] を選択し、[**次へ**] をクリックします。

7. [**アカウントの種類を選択して**ください] で、[ **Office 365**] を選択します。 その後、[**電子メールアドレス**] ボックスに、先ほどコピーした監督メールボックスのアドレスを入力します。<br/>![Outlook の [アカウントの種類の追加] ページで、[メールアドレス] ボックスが強調表示されています。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. メッセージが表示されたら、Office 365 資格情報を入力します。

9. 成功した場合、Outlook のフォルダー一覧ビューに、 ** \<監督ポリシー名\> **フォルダーが表示されます。

## <a name="powershell-reference"></a>PowerShell リファレンス

必要に応じて、次の PowerShell コマンドレットを使用して、監督ポリシーを作成および管理できます。

- [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)