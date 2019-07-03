---
title: Office 365 でインスタント Bloomberg データをアーカイブするためのコネクタを設定する (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、インスタント Bloomberg チャットツールから Office 365 にデータをインポートするためのネイティブコネクタをセットアップできます。 これにより、Office 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、およびアイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 0b69ddaa21196bd0e149eba672fec104eabe2e5e
ms.sourcegitcommit: ab16ddf4c050a995471a058150767a0778be0b88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35431608"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data-in-office-365-preview"></a>Office 365 でインスタント Bloomberg データをアーカイブするためのコネクタを設定する (プレビュー)

Office 365 のインスタント Bloomberg データをアーカイブするためのコネクタ機能はプレビュー段階です。

Office 365 のセキュリティ & コンプライアンスセンターのネイティブコネクタを使用して、[インスタント Bloomberg](https://www.bloomberg.com/professional/product/collaboration/)コラボレーションツールから金融サービスチャットデータをインポートおよびアーカイブします。 コネクタをセットアップして構成した後は、組織の Bloomberg secure FTP サイト (SFTP) に毎日接続して、チャットメッセージの内容を電子メールメッセージの形式に変換した後、それらのアイテムを Office 365 のメールボックスにインポートします。

ユーザーのメールボックスにインスタント Bloomberg データが格納された後、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能をインスタント Bloomberg データに適用することができます。 たとえば、コンテンツ検索を使用してインスタント Bloomberg チャットメッセージを検索したり、インスタント Bloomberg データを含むメールボックスを高度な電子情報開示ケースの保管担当者に関連付けることができます。 Office 365 でインスタント Bloomberg コネクタを使用してデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-instant-bloomberg-data"></a>インスタント Bloomberg データのアーカイブの概要

次の概要では、コネクタを使用して Office 365 でインスタント Bloomberg チャットデータをアーカイブするプロセスについて説明します。 

![インスタント Bloomberg のインポートとアーカイブのプロセス](media/InstantBloombergDataArchiving.png)

1. 組織は Bloomberg を使用して、Bloomberg SFTP サイトをセットアップします。 Bloomberg を使用して、チャットメッセージを Bloomberg SFTP サイトにコピーするためのインスタント Bloomberg を構成することもできます。

2. 24時間ごとに、インスタント Bloomberg からのチャットメッセージが Bloomberg SFTP サイトにコピーされます。
    
3. セキュリティ & コンプライアンスセンターで作成したインスタント Bloomberg コネクタは、毎日 Bloomberg SFTP サイトに接続して、過去24時間のチャットメッセージを Microsoft クラウド内のセキュアな Azure ストレージ領域に転送します。 また、コネクタはチャットのメッセージの内容を電子メールメッセージの形式に変換します。
    
4. コネクタは、チャットメッセージアイテムを特定のユーザーのメールボックスまたは代替メールボックスにインポートします。 コネクタは、 *CorporateEmailAddress*プロパティの値を使用して実行されます。 すべてのチャットメッセージには、このプロパティが含まれており、チャットメッセージのすべての参加者の電子メールアドレスが設定されます。 アイテムが特定のユーザーメールボックスにインポートされるか、または代替メールボックスにインポートされるかは、次の条件に基づいて決まります。
    
    a. **Office 365 ユーザーアカウントに対応する CorporateEmailAddress プロパティの値を持つアイテム**。コネクタが*CorporateEmailAddress*プロパティの電子メールアドレスを office 365 の特定のユーザーアカウントに関連付けることができる場合は、アイテムは、ユーザーの Office 365 メールボックスの受信トレイフォルダーにコピーされます。
    
    b. **Office 365 ユーザーアカウントに対応していない CorporateEmailAddress プロパティの値を持つアイテム**。コネクタが*CorporateEmailAddress*プロパティの電子メールアドレスを office の特定のユーザーアカウントに関連付けることができない場合365、アイテムは Office 365 の別の "キャッチオール" メールボックスの受信トレイフォルダーにコピーされます。

## <a name="before-you-begin"></a>始める前に

インスタント Bloomberg データをアーカイブするために必要な実装手順の多くは、Office 365 の外部にあり、セキュリティ & コンプライアンスセンターでコネクタを作成する前に完了する必要があります。

- [Blooomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)にサブスクライブします。 これは、Bloomberg Anywhere にログインして、設定および構成する必要がある Bloomberg SFTP サイトにアクセスできるようにするために必要です。

- Bloomberg SFTP (Secure file transfer protocol) サイトをセットアップします。 Bloomberg を使用して SFTP サイトを設定した後は、インスタント Bloomberg のデータが毎日 SFTP サイトにアップロードされます。 手順2で作成したコネクタがこの SFTP サイトに接続し、チャットデータを Office 365 メールボックスに転送します。 SFTP は、転送プロセス中に Office 365 メールボックスに送信されるインスタント Bloomberg チャットデータを暗号化することもできます。

    Bloomberg SFTP ( *BB*とも呼ばれます) の詳細については、以下を参照してください。

    - 「 [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/)」の「SFTP Connectivity 標準」ドキュメントを参照してください。
    
    - [Bloomberg カスタマーサポート](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)に問い合わせてください。

    Bloomberg を使用して SFTP サイトを設定した後、Bloomberg は Bloomberg 実装の電子メールメッセージに応答した後に情報を提供します。 次の情報のコピーを保存します。 これを使用して、手順3でコネクタを設定します。

    - 企業の ID であり、Bloomberg SFTP サイトにログインするために使用される、企業のコードです。

    - Bloomberg SFTP サイトのパスワード

    - Bloomberg SFTP サイトの URL (たとえば、sftp.bloomberg.com)

    - Bloomberg SFTP サイトのポート番号

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 手順3でインスタント Bloomberg コネクタを正常に作成するには、この手順を完了する必要があります。

- 手順3でインスタント Bloomberg コネクタを作成したユーザー (および手順1で公開キーと IP アドレスをダウンロードするユーザー) に、Exchange Online のメールボックスのインポートのエクスポート役割を割り当てる必要があります。 これは、セキュリティ & コンプライアンスセンターの [**サードパーティのデータをアーカイブ**する] ページにアクセスするために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>手順 1: SSH と PGP の公開キーを取得する

最初の手順として、Secure Shell (SSH) およびかなり良好なプライバシー (PGP) のための公開キーのコピーを取得します。 手順2でこれらのキーを使用して、Bloomberg SFTP サイトを構成して、コネクタ (手順3で作成したもの) が SFTP サイトに接続し、インスタント Bloomberg のチャットデータを Office 365 メールボックスに転送できるようにします。 また、この手順では IP アドレスも取得します。これは、Bloomberg SFTP サイトを構成するときに使用します。

1. に移動<https://protection.office.com>して、[**データ\>ガバナンスのインポート**] をクリックし、[**サードパーティのデータをアーカイブ**する] をクリックします。

2. [**サードパーティのデータをアーカイブ**する] ページで、[**コネクタの追加**] をクリックし、[**インスタント Bloomberg**] をクリックします。

3. [**サービス利用規約**] ページで、[**同意**する] をクリックします。

4. 各公開キーファイルのコピーをローカルコンピューターに保存するには、手順1の**BLOOMBERG SFTP サイトの資格情報の追加**] をクリックし、「 **SSH キーをダウンロード**する」および「 **PGP キー**をダウンロードする」をクリックします。 これらのファイルには、手順2で Bloomberg SFTP サイトを構成するために使用される次の項目が含まれています。

   - SSH 公開キー–このキーは Secure Shell (SSH) を構成するために使用され、コネクタが Bloomberg SFTP サイトに接続する際にセキュリティで保護されたリモートログインを有効にします。

   - PGP 公開キー–このキーは、Bloomberg SFTP サイトから Office 365 に転送されるデータの暗号化を構成するために使用されます。

   - IP アドレス– Bloomberg SFTP サイトは、この IP アドレスからの接続要求のみを受け入れるように構成されます。これは、手順3で作成したインスタント Bloomberg コネクタによって使用されます。 

5. ウィザードを閉じるには、[**キャンセル**] をクリックします。 このウィザードに戻り、手順3でコネクタを作成します。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>手順 2: Bloomberg SFTP サイトを構成する

次の手順では、SSH と PGP の公開キーと、手順1で取得した IP アドレスを使用して、Bloomberg SFTP サイトの SSH 認証と PGP 暗号化を構成します。 これにより、手順3で作成したインスタント Bloomberg コネクタが Bloomberg SFTP サイトに接続し、インスタント Bloomberg データを Office 365 に転送できるようになります。 この設定についてのサポートが必要な場合は、 [Bloomberg カスタマーサポート](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)に問い合わせてください。

1. 組織のアカウントを使用して、Bloomberg CCNS コントロールパネルにログインします。

2. CCNS に移動し、[**公開キー** ] タブをクリックします。

3. SSH 認証を有効にするには、[**追加**] をクリックします。

4. [**公開キーの追加**] ウィンドウで、[**キーの種類**] ドロップダウンリストをクリックし、[**ログイン**] をクリックします。

5. 手順1でダウンロードした SSH 公開キー全体 (二重引用符を除く) をコピーして、このフィールドに貼り付け、[ **Submit** ] をクリックしてキーを保存します。
 
    たとえば、次のような SSH 公開キーをコピーします。

    `
    ssh-rsa
    AAAAB3NzaC1yc2EAAAABIwAAAQEA1dxAyc0JzCmc5NzgyzRYhnj3FGHK5Kd9T2cwZNkmL/9nFhQupQor081rmuw9gACAmeot7y+V/fmijo/q4rxDe3Auu3hfLl1NpWlIssQJHzycms8zimtdQcXbMKwDQOnRthpEocF5ySs76KE72vaYQJTvclAamWWq0D75SUmXDFFr7afvEy57F7KgMD1ecg6lH7q8seSKbiiWxX1Ul0kL15fzpUyhjDP41owb1XC/dF7fJwAmCO1+HZfDLEp62q4tnApLpdd92KoR41LZTryO5dICKhk+S+JxPLkksxL0wm5YevOr2n4ScuRdsBV8mWKZ1Xw+cOss9O6L7cCcEiB3Ow==
    `

6. PGP 暗号化を有効にするには、[**公開キー** ] タブで [**追加**] をもう一度クリックし、[**キーの種類**] ドロップダウンリストをクリックして、今度は [**暗号化**] をクリックします。

7. 手順1でダウンロードした PGP 公開キー全体 (二重引用符を除く) をコピーして、このフィールドに貼り付け、[ **Submit** ] をクリックしてキーを保存します。 

    たとえば、次の PGP 公開キーをコピーします。

    `
    -----BEGIN PGP PUBLIC KEY BLOCK-----
    Version: BCPG C# v1.7.4137.9688
    nmQENBFz+6UQBCACKC4ilYoVOP5b/F0CO+oQYbag79Ov4NZxM4EKW51lUAvKNExRM\nc1C/gwXm8bghht8GEODckXXqx8qSSXUEeA/ROweXNtD1u1kn7PgYEFUeD/qE739m\nm5lxXF9Vod26AtKQ9Y1EvYoQEltwztAaXg8K8LQzB+tzN079d1cxM5tbiRQLttAh\nOt5amLXuINt8+dWyNas3DfgIBUmwfkwCbUO0ElrIhvvO3A85K97SX9Q6Py0SkfkK\nQpnULuhdjSm+7k7qlVMf0s8e/9jUXYKbMFkxlOoMq052vV0l0VQNSeuKoC+m6+LT\nEPab89AMt6S4Ujum9wTUy1eWNx9vV0y/w8N7ABEBAAG0JDM5MjM4ZTg3LWI1YWIt\nNGVmNi1hNTU5LWFmNTRjNmIwN2I0MokBHAQQAQIABgUCXP7pRAAKCRAJQdjaG//S\nCy70B/wKrR2CcqtZx56yrGJFfVy3niEt16VEA3xJM3D9nX0gmgo85Nh5gkiY3ahH\nnNEmgW5vlCM1gcgFeoZWe8A80G4QoabslSUzLbq9HsHOOAQApsfhrhXpylrAVa4n\nI53XUOxWdOTa4xsOob8hSRADqJbwHPOsoAr2A87TvZ9LSi2Mii5omeTq416CLnoS\nPBAEhelZm+ruy5JhzA1yXvWYFH08wNqSHO3bskdES2yW5SyQmYlcoEztWE0Q0Z+G\nZT3kOa/W2MbcZovFCQIfqhwVfXtIzx5uYUmxgk5cFKUJJMlO0AZK/HwM22xuuIWe\ndMa6OMo/n8tvEBxrLQMdVPlz+hZ6
    =AwmP
    -----END PGP PUBLIC KEY BLOCK-----
    `
8. CCNS コントロールパネルのメインウィンドウに戻り、[ **ip アドレスをここに追加**する] の下に、[**アドレスの追加] フィールド**に、手順1でダウンロードしたキー .txt ファイルに含まれている次の ip アドレスを入力します。

   `
   40.124.28.216
   `

## <a name="step-3-create-an-instant-bloomberg-connector"></a>手順 3: インスタント Bloomberg コネクタを作成する

最後の手順では、セキュリティ & コンプライアンスセンターでインスタント Bloomberg コネクタを作成します。 コネクタは、提供された情報を使用して、Bloomberg SFTP サイトに接続し、Office 365 の対応するユーザーメールボックスにチャットメッセージを転送します。 

1. に移動<https://protection.office.com>して、[**データ\>ガバナンスのインポート**] をクリックし、[**サードパーティのデータをアーカイブ**する] をクリックします。

2. [**サードパーティのデータをアーカイブ**する] ページで、[**コネクタの追加**] をクリックし、[**インスタント Bloomberg**] をクリックします。

3. [**サービス利用規約**] ページで、[**同意**する] をクリックします。

4. [ **BLOOMBERG SFTP サイトの資格情報の追加**] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[**次へ**] をクリックします。

    - [**確定コード**] –組織の ID を Bloomberg SFTP サイトのユーザー名として使用します。

    - **パスワード**– Bloomberg SFTP サイトのパスワード

    - [ **SFTP url** ] – Bloomberg SFTP サイトの url (たとえば、sftp.bloomberg.com)。

    - **Sftp ポート**– Bloomberg SFTP サイトのポート番号。 コネクタはこれを使用して、SFTP サイトに接続します。

5. [**代替メールボックス**] ページで、組織内のユーザーメールボックスに関連付けられていないインスタント Bloomberg からのチャットメッセージを格納するために使用されるメールボックスの電子メールアドレスを入力します。

   > [!NOTE]
   > インスタント Bloomberg のすべての会話のすべてのチャットメッセージには、 *CorporateEmailAddress*という名前のプロパティが含まれています。このプロパティには、チャットの参加者の組織の電子メールアドレスが含まれています。 インポート処理中に、コネクタは、 *CorporateEmailAddress*プロパティのものと一致する電子メールアドレスを持つ Office 365 のユーザーメールボックスにチャットメッセージをインポートしようとします。 *CorporateEmailAddress*プロパティのものと同じアドレスを持つ Office 365 メールボックスがない場合、コネクタはこのページで指定した代替メールボックスにチャットメッセージをインポートします。 現時点では、代替メールボックスにアーカイブされたインスタント Bloomberg チャットメッセージは、Office 365 の監督ポリシーでは監視されません。

6. [**次へ**] をクリックして設定を確認し、[**準備**] をクリックしてコネクタを作成します。

7. [**サードパーティのデータをアーカイブ**する] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。
