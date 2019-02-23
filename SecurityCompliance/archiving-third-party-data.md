---
title: Office 365 でサードパーティのデータをアーカイブする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理者は、ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートできます。これにより、Office 365 の Facebook、Twitter、データソースからデータをアーカイブできます。その後、Office 365 のコンプライアンス機能 (法的情報保持、コンテンツ検索、アイテム保持ポリシーなど) をサードパーティのデータに appply 使用できます。
ms.openlocfilehash: 37811fdbee52cf956c6371deea53a242c2a3c550
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218498"
---
# <a name="archiving-third-party-data-in-office-365"></a>Office 365 でサードパーティのデータをアーカイブする

office 365 を使用すると、管理者はソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから office 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。Office 365 にインポートできるサードパーティのデータソースの例を次に示します。 
  
- **ソーシャル**Twitter、Facebook、Yammer、および LinkedIn 
    
- **インスタントメッセージング**-Yahoo メッセンジャー、GoogleTalk、および Cisco jabber 
    
- **ドキュメントのコラボレーション**-ボックスとドロップボックス 
    
- **垂直産業**-顧客関係管理 (Salesforce チャターなど) や財務 (Thomson Reuters、Bloomberg など) 
    
- **SMS/text messaging** -BlackBerry 
    
サードパーティのデータをインポートした後は、このデータに、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、および Office 365 アイテム保持ポリシーなどの office 365 コンプライアンス機能を適用できます。たとえば、メールボックスが訴訟ホールドの対象となっている場合、サードパーティのデータは保持されます。コンテンツ検索を使用して、サードパーティのデータを検索できます。また、Microsoft データの場合と同じように、アーカイブポリシーおよびアイテム保持ポリシーをサードパーティデータに適用することができます。簡単に言えば、Office 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。
  
このプロセスの概要と、Office 365 にサードパーティのデータをインポートするために必要な手順を示します。

[手順 1: サード パーティのデータのパートナーを見つける](#step-1-find-a-third-party-data-partner)

[手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する](#step-3-configure-user-mailboxes-for-third-party-data)

[手順 4: パートナーに情報を提供する](#step-4-provide-your-partner-with-information)

[手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>サードパーティのデータのインポートプロセスの works>

以下の図および説明は、サードパーティのデータのインポート プロセスが実行される方法を示しています。
  
![サードパーティのデータのインポート プロセスが実行される方法](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. お客様は、選択したパートナーと連携して、サードパーティのデータソースからアイテムを抽出し、それらのアイテムを Office 365 にインポートするコネクタを構成します。
    
2. パートナーコネクタは、サードパーティの API を使用してサードパーティのデータソースに接続し (スケジュールに従って、または構成されている場合)、データソースからアイテムを抽出します。パートナーコネクタは、アイテムのコンテンツを電子メールメッセージの形式に変換します。メッセージ形式スキーマの詳細については、「 [More information](#more-information) 」セクションを参照してください。 
    
3. パートナーコネクタは、既知のエンドポイントを介して Exchange Web サービス (EWS) を使用して、Office 365 の Azure サービスに接続します。
    
4. アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。
    
    a **office 365 ユーザーアカウントに対応するユーザー id を持つアイテム**パートナーコネクタがサードパーティデータソース内のアイテムのユーザー id を office 365 の特定のユーザー id にマップできる場合、そのアイテムはユーザーの削除フォルダーにコピーされます**** 。回復可能なアイテムフォルダー。ユーザーがパージフォルダー内のアイテムにアクセスできません。ただし、Office 365 電子情報開示ツールを使用して、[削除] フォルダー内のアイテムを検索できます。
    
    b. **office 365 ユーザーアカウントに対応するユーザー id を持たないアイテム**。パートナーコネクタがアイテムのユーザー id を office 365 の特定のユーザー id にマップできない場合、そのアイテムはサードパーティデータメールボックスの**受信トレイ**フォルダーにコピーされます。受信トレイにアイテムをインポートすると、組織内のユーザーがサードパーティのメールボックスにサインインしてこれらのアイテムを表示および管理できるようになります。また、パートナーコネクタ構成で調整が必要かどうかを確認します。
 
## <a name="step-1-find-a-third-party-data-partner"></a>手順 1: サード パーティのデータのパートナーを見つける

office 365 でサードパーティのデータをアーカイブするための主要なコンポーネントは、サードパーティのデータソースからデータを取得して office 365 にインポートすることに特化した Microsoft パートナーを検索して作業することです。インポートされたデータは、組織の他の Microsoft データ (Exchange からの電子メールや SharePoint および OneDrive for business からのメールなど) と共にアーカイブおよび保存することができます。パートナーは、組織のサードパーティのデータソース (BlackBerry、Facebook、Google +、Thomson Reuters、Twitter、YouTube など) からデータを抽出し、そのデータを、Exchange メールボックスにアイテムをインポートする Office 365 API に渡すコネクタを作成します。電子メールメッセージ。 
  
次のセクションでは、Office 365 でサードパーティのデータをアーカイブするためのプログラムに参加している Microsoft パートナーと、そのパートナーがサポートするサードパーティのデータソースを示します。

[17a-4 LLC](#17a-4-llc)
  
[Actiance](#actiance)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

17a-4 LLC は、次のサードパーティ データ ソースをサポートしています。
  
- BlackBerry
    
- Bloomberg データ ストリーム
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- 
MessageLabs データ ストリーム

    
- OpenText
    
- Oracle/ATG 'click-to-call' Live ヘルプ

    
- Pivot IMTRADER

    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- 
Skype for Business (Lync/OCS)
    
- 
Skype for Business Online (Lync Online)

    
- SQL データベース
    
- 
Squawker

    
- Thomson Reuters Eikon Messenger

  
### <a name="actiance"></a>Actiance

[Actiance](https://www.actiance.com)は、次のサードパーティデータソースをサポートしています。 
  
- AIM
    
- American Idol
    
- Apple Juice
    
- 
AOL with Pivot クライアント

    
- Ares
    
- Bazaarvoice
    
- Bearshare
    
- BitTorrent
    
- BlackBerry 呼び出しログ (v5、v10、v12)
    
- BlackBerry メッセンジャー (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg メール

    
- celltrust
    
- チャットのインポート

    
- チャットのリアルタイム ロギングとポリシー

    
- チャター

    
- Cisco IM &amp;プレゼンスサーバー (v 9.0.1、v 9.1、v 9.1.1 SU1、v10、v v10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)

    
- 共同作業のインポート

    
- 共同作業のリアルタイム ロギング

    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google+

    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)

    
- IBM Connections Chat Cloud

    
- IBM Connections Social Cloud

    
- IBM SameTime Advanced 8.5.2 IFR1

    
- IBM SameTime Communicate 9.0

    
- IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)

    
- IBM SameTime Complete 9.0

    
- IBM SameTime Conference 9.0

    
- IBM SameTime Meeting 8.5.2 IFR1

    
- ICE/YellowJacket
    
- IM のインポート

    
- IM のリアルタイム ロギングとポリシー

    
- Indii Messenger

    
- Instant Bloomberg

    
- IRC
    
- Jive

    
- Jive 6 Real Time Logging (v6、v7)

    
- Jive のインポート
    
- JXTA
    
- 履歴
    
- 
Microsoft Lync (2010、2013)

    
- MFTP
    
- Microsoft Lync 2013 Voice

    
- Microsoft SharePoint (2010、2013)

    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- NEONetwork
    
- Office 365 Lync Dedicated

    
- Office 365 Shared IM

    
- Pinterest
    
- Pivot
    
- QQ
    
- Skype for Business 2015

    
- SoftEther
    
- Symphony

    
- Thomson Reuters Eikon

    
- Thomson Reuters Messenger

    
- Tor
    
- TTT
    
- Twitter
    
- winmx
    
- Winny
    
- Yahoo

    
- Yammer
    
- YouTube
    
  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com)は、次のサードパーティデータソースをサポートしています。 
  
- Facebook
    
- Flickr

    
- Instagram

    
- 履歴
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com)は、次のサードパーティデータソースをサポートしています。 
  
- AOL with Pivot クライアント 
    
- BlackBerry 呼び出しログ (v5、v10、v12)
    
- BlackBerry メッセンジャー (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg チャット

    
- Bloomberg メール

    
- 検索ボックス
    
- CipherCloud for Salesforce Chatter
    
- Cisco IM &amp;プレゼンスサーバー (v10、v v10.5.1 SU1、v 11.0、v 11.5 SU2)

- Cisco Webex Teams

- Citrix ワーク&amp;スペースの編集ファイル

- CrowdCompass

- カスタムの区切り記号付きテキスト ファイル

    
- カスタムの XML ファイル

    
- Facebook (ページ)
    
- Factset

    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive

    
- Macgregor XIP


- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer

    
- Mobile Guard
    
- Pivot
    
- Salesforce Chatter

- Skype for Business Online
    
- Skype for Business、バージョン 2007 R2 ～ 2016 (オンプレミス)

    
- Slack Enterprise Grid
    
- Symphony

    
- Thomson Reuters Eikon

    
- Thomson Reuters Messenger

    
- Thomson Reuters Dealings 3000 / FX トレーディング

    
- Twitter
    
- UBS チャット

    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)は、次のサードパーティデータソースをサポートしています。 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="verba"></a>Verba

[verba](https://www.verba.com)は、次のサードパーティデータソースをサポートしています。 
  
- Avaya Aura ビデオ

    
- Avaya Aura 音声

    
- Avtec ラジオ

    
- Bosch/Telex ラジオ

    
- BroadSoft ビデオ

    
- BroadSoft 音声

    
- Centile 音声

    
- Cisco Jabber IM

    
- Cisco UC ビデオ

    
- Cisco UC 音声

    
- Cisco uccx/uccx ビデオ
    
- Cisco uccx/uccx 音声
    
- ESChat ラジオ
    
- Geoman Contact Expert
    
- IP Trade 音声

    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center for Lync (prairieFyre) 

    
- Oracle / Acme Packet Session Border Controller ビデオ  

    
- Oracle / Acme Packet Session Border Controller 音声

    
- Singtel モバイル ボイス

    
- SIPREC ビデオ
    
-  SIPREC 音声 
    
- Skype for Business / Lync IM

    
- Skype for Business / Lync ビデオ

    
- Skype for Business / Lync 音声

    
- Speakerbus 音声

    
- 標準的な SIP/H.323 ビデオ 

    
- 標準的な SIP/H.323 音声 

    
- Truphone 音声

    
- TwistedPair ラジオ

    
- Windows デスクトップ コンピューターの画面 

  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する

Office 365 にデータをインポートするためにサードパーティ製のデータメールボックスを作成して構成する手順を次に示します。前に説明したように、パートナーコネクタがアイテムのユーザー ID を Office 365 ユーザーアカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。
  
 **Office 365 管理センターでこれらのタスクを完了する**
  
1. Office 365 で新しいユーザーアカウントを作成し、Exchange Online プラン2のライセンスを割り当てます。「 [Office 365 にユーザーを追加する」を](https://go.microsoft.com/fwlink/p/?LinkId=692098)参照してください。プラン2ライセンスは、メールボックスを訴訟ホールドの対象にするため、または記憶域クォータが無制限のアーカイブメールボックスを有効にするために必要です。
    
2. Office 365 で、サードパーティのデータメールボックスのユーザーアカウントを**Exchange 管理**者の役割に追加します。「 [Office 365 で管理者ロールを割り当てる」を](https://go.microsoft.com/fwlink/p/?LinkId=532393)参照してください。
    
    > [!TIP]
    > このユーザー アカウントの資格情報を控えておきます。手順 4 で説明するように、この情報をパートナーに提供する必要があります。 
  
 **Exchange 管理センターでこれらのタスクを完了する**
  
1. 組織内のアドレス帳およびその他のアドレス一覧から、サードパーティのデータメールボックスを非表示にします。「[ユーザーメールボックスの管理](https://go.microsoft.com/fwlink/p/?LinkId=616058)」を参照してください。または、次の PowerShell コマンドを実行することもできます。
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. サードパーティのデータメールボックスに**fullaccess**のアクセス許可を割り当てて、管理者またはコンプライアンス責任者が Outlook デスクトップクライアントでサードパーティのデータメールボックスを開くことができるようにします。「[管理者のアクセス許可を管理する」を](https://go.microsoft.com/fwlink/p/?LinkId=692104)参照してください。
    
3. サードパーティのデータメールボックスに対して、次のコンプライアンス関連の Office 365 機能を有効にします。
    
    - アーカイブメールボックスを有効にします。「office [365 &amp;セキュリティコンプライアンスセンターでアーカイブメールボックスを有効](enable-archive-mailboxes.md)にする」および「 [office 365 で無制限のアーカイブを有効にする](enable-unlimited-archiving.md)」を参照してください。これにより、サードパーティのデータアイテムをアーカイブメールボックスに移動するアーカイブポリシーを設定することで、プライマリメールボックスの記憶域スペースを解放できるようになります。これにより、サードパーティのデータに対して無制限のストレージが提供されます。
    
    - サードパーティのデータメールボックスを訴訟ホールドの対象にします。office 365 セキュリティ&amp;コンプライアンスセンターで office 365 アイテム保持ポリシーを適用することもできます。このメールボックスを保留にすると、サードパーティのデータアイテム (無期限または指定した期間中) が保持され、それらがメールボックスから削除されるのを防ぐことができます。次のいずれかのトピックを参照してください。
    
      - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [アイテム保持ポリシーの概要](retention-policies.md)
    
       
    
    - サードパーティデータメールボックスへの所有者、代理人、および管理者のアクセスに対してメールボックス監査ログを有効にします。「 [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md)」を参照してください。これにより、サードパーティのデータメールボックスにアクセスできるすべてのユーザーによって実行されたすべてのアクティビティを監査できます。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する

次の手順では、サードパーティのデータをサポートするようにユーザーメールボックスを構成します。Exchange 管理センターまたは対応する Windows PowerShell コマンドレットを使用して、これらのタスクを完了します。
  
1. 各ユーザーのアーカイブメールボックスを有効にします。「office [365 &amp;セキュリティコンプライアンスセンターでアーカイブメールボックスを有効](enable-archive-mailboxes.md)にする」および「 [office 365 で無制限のアーカイブを有効にする](enable-unlimited-archiving.md)」を参照してください。
    
2. ユーザーメールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーを適用します。次のいずれかのトピックを参照してください。 
    
    - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [アイテム保持ポリシーの概要](retention-policies.md)
    
    前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。

## <a name="step-4-provide-your-partner-with-information"></a>手順 4: パートナーに情報を提供する

最後の手順は、パートナーが Office 365 の組織に接続するコネクタを構成し、ユーザーのメールボックスおよびサード パーティのデータのメールボックスにデータをインポートできるように、パートナーに以下の情報を提供することです。 
  
- Office 365 の Azure サービスに接続するために使用されるエンドポイント:

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 手順2で作成したサードパーティ製データメールボックスのサインイン資格情報 (Office 365 ユーザー ID とパスワード)。これらの資格情報は、パートナーコネクタがユーザーのメールボックスおよびサードパーティのデータメールボックスに対してアイテムにアクセスしてインポートできるようにするために必要です。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する

2018年9月30日以降、office 365 の Azure サービスは、Exchange Online での先進認証の使用を開始して、office 365 組織に接続してデータをインポートするサードパーティ製データコネクタを認証します。この変更によって、モダン認証は現在のメソッドよりも高いセキュリティを提供しています。これは、以前に説明したエンドポイントを使用して Azure サービスに接続するサードパーティコネクタに基づいていました。

新しいモダン認証方法を使用してサードパーティ製データコネクタを office 365 に接続できるようにするには、office 365 組織の管理者が、Azure Active Directory の信頼済みサービスアプリケーションとしてそのコネクタを登録するために同意する必要があります。これを行うには、アクセス許可要求を受け入れ、コネクタが Azure Active Directory 内の組織のデータにアクセスできるようにします。この要求を承諾すると、サードパーティのデータコネクタがエンタープライズアプリケーションとして Azure Active Directory に追加され、サービスプリンシパルとして表されます。同意プロセスの詳細については、「[テナント管理者の同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)」を参照してください。

コネクタを登録するための要求をアクセスして受け入れる手順を次に示します。

1. [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報を使用してサインインします。<br/><br/>次のダイアログボックスが表示されます。carets を展開して、コネクタに割り当てられているアクセス許可を確認できます。<br/><br/>![[アクセス許可の要求] ダイアログが表示されます。](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. [**承諾**] をクリックします。

要求を受け入れると、 [Azure portal](https://portal.azure.com)が表示されます。組織のアプリケーションの一覧を表示するには、[ **Azure Active Directory** > **エンタープライズアプリケーション**] をクリックします。Office 365 サードパーティデータコネクタは、**エンタープライズアプリケーション**ブレードに一覧表示されています。

> [!IMPORTANT]
> 2018年9月30日以降、サードパーティのデータコネクタを Azure Active Directory に登録しない場合、組織内のメールボックスにサードパーティのデータがインポートされなくなります。注: 既存のサードパーティのデータコネクタ (2018 年9月30日より前に作成されたもの) は、手順5の手順に従って Azure Active Directory に登録する必要もあります。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>サードパーティのデータコネクタの同意を取り消す

組織がアクセス許可要求に同意して、Azure Active Directory にサードパーティデータコネクタを登録すると、組織はいつでもその同意を取り消すことができます。ただし、コネクタの同意を取り消すと、サードパーティのデータソースからのデータは Office 365 にインポートされなくなります。

サードパーティのデータコネクタの同意を取り消すには、azure ポータルの [**エンタープライズアプリケーション**] ブレードまたはを使用[して、azure Active Directory からアプリケーション (対応するサービスプリンシパルを削除) を削除するか、または](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)Office 365 PowerShell で new-msolserviceprincipal を削除します。Azure Active Directory PowerShell で[AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)コマンドレットを使用することもできます。
  
## <a name="more-information"></a>詳細情報

- 前述したように、サードパーティのデータソースのアイテムは、電子メールメッセージとして Exchange メールボックスにインポートされます。パートナーコネクタは、Office 365 API によって必要とされるスキーマを使用してアイテムをインポートします。次の表は、電子メールメッセージとして Exchange メールボックスにインポートされた後の、サードパーティのデータソースからのアイテムのメッセージプロパティについて説明しています。この表は、message プロパティが必須であるかどうかも示しています。必須のプロパティを設定する必要があります。必須のプロパティが設定されていないアイテムは、Office 365 にインポートされません。インポートプロセスでは、アイテムがインポートされなかった理由と、不足しているプロパティがあることを示すエラーメッセージが返されます。
    
    |**メッセージのプロパティ**|**必須?**|**説明**|**値の例**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |はい  <br/> |最初にサードパーティのデータソースにアイテムを作成または送信したユーザー。パートナーコネクタは、ソースアイテム (Twitter ハンドルなど) から、すべての参加者 ([差出人] および [宛先] フィールド内のユーザー) の Office 365 ユーザーアカウントにユーザー ID をマップしようとします。メッセージのコピーは、すべての参加者のメールボックスにインポートされます。そのアイテムの参加者が office 365 ユーザーアカウントにマップできない場合、そのアイテムは office 365 のサードパーティのアーカイブメールボックスにインポートされます。<br/> <br/> アイテムの送信者として識別される参加者は、アイテムがインポートされる Office 365 組織にアクティブなメールボックスを持っている必要があります。送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |はい  <br/> |アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。  <br/> | `bob@contoso.com` <br/> |
    |**SUBJECT** <br/> |いいえ  <br/> |ソース アイテムの件名。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**状態** <br/> |はい  <br/> |アイテムが最初に作成されたか、または顧客データ ソースに投稿された日付 (たとえば、Twitter のメッセージがツイートされた日付)。  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |いいえ  <br/> |メッセージまたは投稿の内容。データソースによっては、このプロパティの内容が**SUBJECT**プロパティの内容と同じである場合があります。インポート処理中に、パートナーコネクタは、可能な限りコンテンツソースの完全な忠実性を維持しようとします。指定可能なファイル、グラフィックス、またはソースアイテムの本文のその他のコンテンツがこのプロパティに含まれている場合。それ以外の場合、ソースアイテムのコンテンツは**ATTACHMENT**プロパティに含まれます。このプロパティの内容は、パートナーコネクタとソースプラットフォームの機能によって異なります。<br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |いいえ  <br/> |データソース内のアイテム (Twitter のツイート、インスタントメッセージングの会話など) に添付ファイルがあり、画像が含まれている場合、パートナー接続は最初に**BODY**プロパティに添付ファイルを含めようとします。これができない場合は、* * ATTACHMENT * * プロパティに追加されます。添付ファイルのその他の例としては、Facebook のいいね、コンテンツソースのメタデータ、メッセージまたは投稿への応答などがあります。<br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |はい  <br/> | これは、パートナーコネクタによって作成および設定される複数値プロパティです。このプロパティの形式は`IPM.NOTE.Source.Event`です。(このプロパティはで`IPM.NOTE`始まる必要があります。この形式は、 `IPM.NOTE.X`メッセージクラスのものと似ています)。このプロパティには、次の情報が含まれます。<br/><br/>`Source`-サードパーティのデータソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。  <br/> <br/>  `Event`-アイテムを生成したサードパーティのデータソースで実行されたアクティビティの種類を示します。たとえば、Twitter のツイート、または Facebook の投稿。イベントは、データソースに固有のものです。<br/> <br/>  このプロパティの目的の1つは、アイテムが発生元であるデータソースに基づいて、またはイベントの種類に基づいて、特定のアイテムをフィルター処理することです。たとえば、電子情報開示検索では、検索クエリを作成して、特定のユーザーによって投稿されたすべてのツイートなど) を検索できます。<br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- アイテムが Office 365 のメールボックスに正常にインポートされると、一意識別子が HTTP 応答の一部として発信者に戻されます。この識別子`x-IngestionCorrelationID`は、アイテムのエンドツーエンドの追跡のためにパートナーによって、以降のトラブルシューティングのために使用されます。パートナーは、この情報を取得して、それを最終的にログに記録することをお勧めします。この識別子を示す HTTP 応答の例を次に示します。

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- office 365 セキュリティ&amp;コンプライアンスセンターのコンテンツ検索ツールを使用して、サードパーティのデータソースから office 365 のメールボックスにインポートされたアイテムを検索することができます。これらのインポートされたアイテムを検索するには、次のようなメッセージのプロパティと値のペアをキーワードボックスで使用します。. 
    
  - **`kind:externaldata`**-このプロパティと値のペアを使用して、すべてのサードパーティのデータ型を検索します。たとえば、サードパーティのデータソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、 `kind:externaldata AND subject:contoso`キーワードクエリを使用します。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**-このプロパティと値のペアを使用して、サードパーティのデータの指定した種類のみを検索します。たとえば、Subject プロパティに "contoso" という単語が含まれる Facebook データのみを検索するには、キーワードクエリ`itemclass:ipm.externaldata.Facebook* AND subject:contoso`を使用します。 

  `itemclass`プロパティのサードパーティデータ型に使用する値の完全な一覧については、「[コンテンツ検索を使用して、Office 365 にインポートされたサードパーティのデータを検索する](use-content-search-to-search-third-party-data-that-was-imported.md)」を参照してください。
    
   コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。
    
  - [Office 365 でのコンテンツ検索](content-search.md)
    
  - [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
 
