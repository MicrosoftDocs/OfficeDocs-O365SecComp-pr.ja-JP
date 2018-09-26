---
title: Office 365 でサードパーティのデータをアーカイブする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理者は、Office 365 の組織内のメールボックスに、ソーシャル メディアのプラットフォーム、インスタント メッセージング ・ プラットフォーム、およびドキュメントのコラボレーション プラットフォームからサード ・ パーティ製のデータをインポートできます。Facebook、Twitter やデータ ソースから Office 365 のデータをアーカイブできます。サード ・ パーティ製のデータを appply Office 365 のコンプライアンス機能 (法的保存要件、コンテンツの検索、保存ポリシーなど) ができます。
ms.openlocfilehash: 5e8fe94e0c3e8b39aec479f4755a263438513d35
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038110"
---
# <a name="archiving-third-party-data-in-office-365"></a>Office 365 でサードパーティのデータをアーカイブする

Office 365 では、管理者がインポートし、インスタント メッセージングのプラットフォーム、およびドキュメントのコラボレーション プラットフォームでは、Office 365 の組織内のメールボックスに、ソーシャル メディアのプラットフォームからのサード ・ パーティ製のデータをアーカイブできます。Office 365 にインポートすることができますサードパーティのデータ ソースの例を以下に示します。 
  
- **ソーシャル**・ Twitter、Facebook、Yammer、LinkedIn 
    
- **インスタント メッセージング**の yahoo メッセンジャー、GoogleTalk、および Cisco の Jabber 
    
- **ドキュメントの共同作業**のボックスとドロップ ボックス 
    
- **業種**の Salesforce Chatter) などの顧客関係管理、トムソンガゼル Reuters および Bloomberg) などの金融サービス 
    
- **SMS/テキスト メッセージ**の BlackBerry 
    
サード ・ パーティ製のデータがインポートされると、Office 365 のコンプライアンス機能を割り当てることができます-証拠保全、コンテンツの検索、埋め込み先のアーカイブ、監査、および Office 365 のリテンション ・ ポリシーなど、このデータにします。たとえば、証拠保全にメールボックスが格納されると、サード パーティのデータは保持されます。コンテンツの検索を使用して、サード パーティのデータを検索できます。アーカイブを適用することや、Microsoft のデータの場合と同様に、サード ・ パーティ製データ保存のポリシーします。つまり、Office 365 のサード ・ パーティ製データのアーカイブを支援して政府や規制ポリシーに準拠したままです。
  
ここでは、サード ・ パーティ製データを Office 365 にインポートするために必要なプロセスと手順の概要を説明です。

[手順 1: サード パーティのデータのパートナーを見つける](#step-1-find-a-third-party-data-partner)

[手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する](#step-3-configure-user-mailboxes-for-third-party-data)

[手順 4: パートナーに情報を提供する](#step-4-provide-your-partner-with-information)

[手順 5: サード ・ パーティ製データ コネクタを Azure Active Directory に登録します。](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>動作するサードパーティ製のデータがプロセスをインポートする方法 >

以下の図および説明は、サードパーティのデータのインポート プロセスが実行される方法を示しています。
  
![サードパーティのデータのインポート プロセスが実行される方法](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. お客様は、サードパーティのデータ ソースから項目を抽出し、それらのアイテムを Office 365 にインポートするコネクタを構成するのには最適なパートナーと連携します。
    
2. パートナー コネクタは、(スケジュールまたはで構成された単位で)、サードパーティ製の API を使用してサードパーティのデータ ソースに接続し、データ ソースから項目を抽出します。パートナーのコネクタは、アイテムの内容を電子メールのメッセージ形式に変換します。メッセージ形式のスキーマの詳細については、[詳細について](#more-information)はを参照してください。 
    
3. パートナーのコネクタは、既知のエンドポイントを使用して Exchange Web サービス (EWS) を使用して、Office 365 で Azure のサービスに接続します。
    
4. アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。
    
    **Office 365 ユーザー アカウントに対応するユーザー ID を持っているアイテム**の場合はパートナーのコネクタは、Office 365 では、アイテムの ID がフォルダーにコピー、**削除**ユーザーの特定のユーザーにサード パーティのデータ ソース内の項目のユーザー ID をマップできます a.回復可能なアイテム] フォルダー。削除フォルダー内のアイテムにアクセスできません。ただし、削除フォルダー内のアイテムを検索するのには、Office 365 の電子的証拠開示のツールを使用できます。
    
    b. の**項目が、Office 365 のユーザー アカウントに対応するユーザー ID を必要はありません**- パートナーのコネクタは、特定のユーザーが Office 365 では、アイテムの ID は、サード ・ パーティ製データ メールボックスの**受信トレイ**フォルダーにコピーするアイテムのユーザー ID をマップできない場合。受信トレイにアイテムをインポートすることができますまたは他の組織とパートナーのコネクタの構成で実行する調整が必要なかどうかを参照してくださいの表示および、これらの項目を管理するサード ・ パーティ製のメールボックスにサインインします。
 
## <a name="step-1-find-a-third-party-data-partner"></a>手順 1: サード パーティのデータのパートナーを見つける

Office 365 のサード ・ パーティ製データのアーカイブの重要なコンポーネントは検索と、サード ・ パーティ製のデータ ソースからデータをキャプチャし、Office 365 にインポートすることで専門とするマイクロソフトのパートナーと連携します。データがインポートされると、そのアーカイブし、とともに保持、組織が Exchange からの電子メールやドキュメントを SharePoint とビジネスの OneDrive など、他の Microsoft のデータの。パートナー (BlackBerry、Facebook、Google +、トムソンガゼル Reuters、Twitter、および YouTube) などの組織のサード ・ パーティ製のデータ ソースからデータを抽出し、そのデータを Office 365 の API としての Exchange メールボックスにアイテムをインポートするコネクタを作成します。メッセージを電子メールで送信します。 
  
次の各項では、マイクロソフトのパートナー- とをサポートしているサード ・ パーティ製のデータ ソース: Office 365 のサード ・ パーティ製のデータをアーカイブするためのプログラムに参加していること。

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

[Actiance](https://www.actiance.com)には、以下のサードパーティのデータ ソースがサポートされています。 
  
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

    
- CellTrust
    
- チャットのインポート

    
- チャットのリアルタイム ロギングとポリシー

    
- チャター

    
- Cisco IM&amp;プレゼンス サーバー (v9.0.1、v9.1、v9.1.1 SU1、v10、v10.5.1 SU1)
    
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

    
- アイス/YellowJacket
    
- IM のインポート

    
- IM のリアルタイム ロギングとポリシー

    
- Indii Messenger

    
- Instant Bloomberg

    
- IRC
    
- Jive

    
- Jive 6 Real Time Logging (v6、v7)

    
- Jive のインポート
    
- JXTA
    
- LinkedIn
    
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
    
- WinMX
    
- Winny
    
- Yahoo

    
- Yammer
    
- YouTube
    
  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com)には、以下のサードパーティのデータ ソースがサポートされています。 
  
- Facebook
    
- Flickr

    
- Instagram

    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com)には、以下のサードパーティのデータ ソースがサポートされています。 
  
- AOL with Pivot クライアント 
    
- BlackBerry 呼び出しログ (v5、v10、v12)
    
- BlackBerry メッセンジャー (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg チャット

    
- Bloomberg メール

    
- Box

    
- CipherCloud for Salesforce Chatter
    
- Cisco IM&amp;プレゼンス サーバー (v10、v10.5.1 SU1、v11.0、v11.5 SU2)

- Cisco Webex チーム

- Citrix ワークスペース&amp;ShareFile

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

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)は、以下のサードパーティのデータ ソースをサポートしています。 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="verba"></a>Verba

[Verba](https://www.verba.com)には、以下のサードパーティのデータ ソースがサポートされています。 
  
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

    
- Cisco UCCX/UCCE ビデオ
    
- Cisco UCCX/UCCE 音声
    
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

作成し、Office 365 にデータをインポートするためのサード ・ パーティ製データ メールボックスを構成するための手順を次に示します。前に説明すると、パートナーのコネクタは、Office 365 のユーザー アカウントにアイテムのユーザー ID をマップできない場合、このメールボックスにアイテムがインポートされます。
  
 **Office 365 の管理ページでこれらのタスクを完了します。**
  
1. Office 365 に新しいユーザー アカウントを作成し、Exchange オンライン計画 2 ライセンスを割り当てること[Office 365 のユーザーの追加](https://go.microsoft.com/fwlink/p/?LinkId=692098)を参照してください。証拠保全のメールボックスを配置するか、無制限のストレージ クォータを持つアーカイブ先のメールボックスを有効にするのには計画の 2 ライセンスが必要です。
    
2. サード ・ パーティ製データ メールボックスのユーザー アカウントを Office 365 の [ **Exchange 管理者**の管理者の役割に追加します。[Office 365 の管理者の役割の割り当て](https://go.microsoft.com/fwlink/p/?LinkId=532393)を参照してください。
    
    > [!TIP]
    > このユーザー アカウントの資格情報を控えておきます。手順 4 で説明するように、この情報をパートナーに提供する必要があります。 
  
 **Exchange 管理センターでこれらのタスクを完了します。**
  
1. アドレス帳と、組織内の他のアドレス一覧からサード ・ パーティ製データ メールボックスを非表示にします。[ユーザーのメールボックスの管理](https://go.microsoft.com/fwlink/p/?LinkId=616058)を参照してください。また、次の PowerShell コマンドを実行することができます。
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. **FullAccess**アクセス許可、メールボックスを割り当てるサード ・ パーティ製データ管理者またはコンプライアンス担当役員は、Outlook デスクトップ クライアントでサード ・ パーティ製データ メールボックスを開くことができますように[受信者のアクセス権の管理](https://go.microsoft.com/fwlink/p/?LinkId=692104)を参照してください。
    
3. サード ・ パーティ製データ メールボックスの次コンプライアンスに関連する Office 365 機能を有効にするには。
    
    - アーカイブ先のメールボックスを有効にします。参照してください[Office 365 のセキュリティのアーカイブ メールボックスを有効にする&amp;コンプライアンス センター](enable-archive-mailboxes.md)し、 [Office 365 で無制限のアーカイブを有効に](enable-unlimited-archiving.md)します。これは、テンプレートを使用するサード ・ パーティ製のデータ項目をアーカイブ メールボックスに移動するアーカイブ ポリシーを設定することによってプライマリ メールボックスの空き記憶領域です。無制限のストレージを持つサード ・ パーティ製データの提供このされます。
    
    - 証拠保全のサード ・ パーティ製データ メールボックスを配置します。Office 365 のセキュリティでは、Office 365 の保持ポリシーを適用することも&amp;コンプライアンス センターです。保留中のこのメールボックスを配置すること、(永久にまたは指定した期間) に、サード ・ パーティ製のデータ アイテムを保持し、メールボックスからパージされないようにします。次のトピックを参照してください。
    
      - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [アイテム保持ポリシーの概要](retention-policies.md)
    
       
    
    - 所有者、デリゲート、および管理者メールボックスへのアクセス、サード ・ パーティ製のデータはログ出力のメールボックスの監査を有効にします。[メールボックスを Office 365 で監査を有効にする](enable-mailbox-auditing.md)を参照してください。これは、オプションを選択するサード ・ パーティ製データ メールボックスにアクセスできる任意のユーザーによって実行されるすべてのアクティビティを監査することができます。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する

次の手順では、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。Exchange 管理センターを使用するか、対応する Windows PowerShell コマンドレットを使用して、これらのタスクを完了します。
  
1. 各ユーザーのアーカイブ メールボックスを有効にします。参照してください[Office 365 のセキュリティのアーカイブ メールボックスを有効にする&amp;コンプライアンス センター](enable-archive-mailboxes.md)し、 [Office 365 で無制限のアーカイブを有効に](enable-unlimited-archiving.md)します。
    
2. 証拠保全でユーザーのメールボックスを配置するか、Office 365 保持ポリシーを適用次のトピックを参照してください。 
    
    - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [アイテム保持ポリシーの概要](retention-policies.md)
    
    前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。

## <a name="step-4-provide-your-partner-with-information"></a>手順 4: パートナーに情報を提供する

最後の手順は、パートナーが Office 365 の組織に接続するコネクタを構成し、ユーザーのメールボックスおよびサード パーティのデータのメールボックスにデータをインポートできるように、パートナーに以下の情報を提供することです。 
  
- Office 365 では、Azure のサービスへの接続に使用されるエンドポイント。

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 資格情報 (Office 365 のユーザー ID とパスワード) 手順 2 で作成したサード ・ パーティ製データ メールボックス内の標識です。パートナーのコネクタにアクセスし、サード ・ パーティ製データ メールボックスにユーザーのメールボックスにアイテムをインポートするため、これらの資格情報が必要です。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>手順 5: サード ・ パーティ製データ コネクタを Azure Active Directory に登録します。

認証を使用して新しい Exchange オンライン データをインポートするのには、Office 365 の組織に接続しようとするサード ・ パーティ製データ コネクタを認証するために開始 2018 年 9 月 30日 Office 365 で Azure サービスが開始されます。この変更の理由は、Azure のサービスに接続する前に説明したエンドポイントを使用する whitelisting サードパーティ製のコネクタを基盤とする現在の方法よりも高いセキュリティを提供する最新の認証をします。

新しい近代的な認証方法を使用して Office 365 に接続するためのサード ・ パーティ製データ コネクタを有効にするには、組織の Office 365 の管理者する必要があります Azure Active Directory の信頼されたサービス アプリケーションとして、コネクタを登録するのには同意するものです。これは、は、Azure Active Directory 内の組織のデータにアクセスするためのコネクタを許可するアクセス許可の要求を受け入れることによって行われます。この依頼を承諾した後は、サード ・ パーティ製データ コネクタが Azure Active directory のエンタープライズ ・ アプリケーションとして追加され、サービス主体として表されます。承認プロセスの詳細は、[テナント管理者の承認](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)を参照してください。

アクセスし、コネクタを登録するのには依頼を承諾する手順を以下に示します。

1. [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動し、Office 365 のグローバル管理者の資格情報を使用してサインインします。<br/><br/>次のダイアログ ボックスが表示されます。コネクタに割り当てられるアクセス許可を確認するのには、カレットを開くことができます。<br/><br/>![アクセス許可の要求] ダイアログが表示されます。](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. **受け付ける**] をクリックします。

依頼を承諾すると、 [Azure ポータル](https://portal.azure.com)が表示されます。**Azure Active Directory**をクリックして、組織のアプリケーションの一覧を表示するのには > **エンタープライズ ・ アプリケーション**です。**エンタープライズ ・ アプリケーション**のブレードでは、Office 365 のサード ・ パーティ製データ コネクタが表示されます。

> [!IMPORTANT]
> 後 2018 年 9 月 30日サード ・ パーティ製が不要になったにデータをインポート、組織内のメールボックス Azure Active Directory でサード ・ パーティ製データ コネクタを登録していない場合。ノートの既存のサード ・ パーティ製データ コネクタ (2018 年 9 月 30日前に作成されたもの) は、手順 5 の手順に従って、Azure Active Directory にも登録してください。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>サード ・ パーティ製データ コネクタの同意を取り消す

Azure Active Directory のサード ・ パーティ製データ コネクタを登録するのにはアクセス許可の要求に同意の上、組織後、組織は、いつでもその承諾を取り消すことができます。ただし、コネクタの同意を取り消すと、サードパーティのデータ ソースからデータが不要になった Office 365 にインポートします。

サード ・ パーティ製データ コネクタの同意を取り消すにはすることができますからアプリケーションを削除 (対応するサービス ・ プリンシパルを削除する) を Azure Active Directory の**エンタープライズ ・ アプリケーション**のブレードを使用して、Azure のポータルでは、または、[を使用して、削除 MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) Office 365 の PowerShell にします。Azure Active Directory PowerShell の[削除 AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)コマンドレットを使用することもできます。
  
## <a name="more-information"></a>詳細情報

- 前に説明すると、アイテムからサードパーティ製のデータ ソースは、電子メール メッセージとして Exchange のメールボックスにインポートされます。パートナーのコネクタでは、Office 365 の API に必要なスキーマを使用してアイテムをインポートします。次の表は、電子メール メッセージとして Exchange メールボックスにインポートした後、サード ・ パーティ製のデータ ソースからのアイテムのメッセージのプロパティを説明します。メッセージ プロパティは必須だかどうかも示します。必須プロパティを設定する必要があります。アイテムには、必須プロパティが不足しているが場合、は、Office 365 にインポートされません。インポート プロセスでは、項目がインポートされなかった理由と、どのプロパティが不足しているを説明するエラー メッセージを返します。
    
    |**メッセージのプロパティ**|**必須ですか。**|**説明**|**値の例**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |はい  <br/> |最初に作成またはサードパーティのデータ ソースのアイテムを送信したユーザー。パートナーのコネクタはすべての参加者 (FROM および TO フィールド内のユーザー) のソースの項目 (たとえば、Twitter のハンドル) から Office 365 のユーザー アカウントにユーザー ID をマップしようとします。メッセージのコピーは、すべての参加者のメールボックスにインポートされます。アイテムから参加者をマップするには Office 365 のユーザー アカウントに、Office 365 のサード ・ パーティ製アーカイブ メールボックスにアイテムがインポートされます。<br/> <br/> アイテムの送信者として識別される参加者は、アクティブなメールボックスにインポートされているアイテムを Office 365 の組織で必要があります。送信者には、アクティブなメールボックスが割り当てられていない、次のエラーが返されます。<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |はい  <br/> |アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。  <br/> | `bob@contoso.com` <br/> |
    |**SUBJECT** <br/> |いいえ  <br/> |ソース アイテムの件名。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**日付** <br/> |はい  <br/> |アイテムが最初に作成されたか、または顧客データ ソースに投稿された日付 (たとえば、Twitter のメッセージがツイートされた日付)。  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |いいえ  <br/> |メッセージまたは投稿の内容です。一部のデータ ソースでは、このプロパティの内容が **[主題**] プロパティの内容と同じで可能性があります。インポート プロセス中にパートナーのコネクタからコンテンツのソースにできるだけ忠実に維持するために試みます。可能であればファイル、グラフィック、または他のコンテンツ ソース アイテムの本文からは、このプロパティに含まれます。それ以外の場合、**添付ファイル**のプロパティの元の項目のコンテンツが含まれます。このプロパティの内容は、パートナーのコネクタで、ソース ・ プラットフォームの機能に依存します。<br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |いいえ  <br/> |Twitter やインスタント メッセージ会話でのツイート) などのデータ ソース内の項目の添付ファイルやイメージなどがあります、パートナーは、 **BODY**プロパティに添付ファイルを含めるには最初の試行を接続します。可能ではない場合に追加される、* * 添付 * * プロパティです。添付ファイルの他の例には、Facebook、コンテンツ ソースは、メッセージまたは投稿への応答からのメタデータの中になが含まれます。<br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |はい  <br/> | これは、複数値プロパティが作成され、パートナーのコネクタによって作成されます。このプロパティの形式は、 `IPM.NOTE.Source.Event`。(このプロパティで始まる必要があります`IPM.NOTE`はこの形式はのような`IPM.NOTE.X`メッセージ クラス)。このプロパティには、次の情報が含まれています。<br/><br/>`Source`-サード ・ パーティ製のデータ ソースを指定します。たとえば、Twitter、Facebook、または BlackBerry にします。  <br/> <br/>  `Event`-の項目を生成するサードパーティのデータ ソースで実行されたアクティビティの種類を指定します。たとえば、つぶやき Twitter または Facebook の投稿にします。イベントは、データ ソースに固有です。<br/> <br/>  このプロパティの目的の 1 つは、アイテムが作成されたか、イベントの種類に基づいて、データ ソースに基づく特定のアイテムをフィルターするのには。たとえば、電子的証拠開示検索の [特定のユーザーによってアップロードされたすべての tweets を検索する検索クエリを作成します。<br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- アイテムは、Office 365 のメールボックスに正常にインポートは、HTTP 応答の一部として呼び出し元に一意の識別子が返されます。この識別子などと呼ばれる`x-IngestionCorrelationID`: 項目のエンド ・ ツー ・ エンドの追跡のためのパートナーがそれ以降のトラブルシューティングの際に使用できます。パートナーがこの情報をキャプチャし、それに応じてそれをログに記録をお勧めしますが、最後にします。この識別子を示す HTTP 応答の例を以下に示します。

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- Office 365 のセキュリティ コンテンツの検索ツールを使用することができます&amp;コンプライアンス センターをサード ・ パーティ製のデータ ソースから Office 365 のメールボックスにインポートされたアイテムを検索します。具体的には、これらのインポートされたアイテムを検索するには、コンテンツ検索のキーワード] ボックスで次のメッセージ プロパティと値のペアを使用できます。. 
    
  - **`kind:externaldata`**-すべてのサード ・ パーティ製データ型を検索するのには、このプロパティと値のペアを使用します。たとえば、インポートされたアイテムの Subject プロパティで"contoso"という単語が含まれているサード パーティのデータ ソースからインポートされたアイテムを検索するにはクエリを使用するキーワード`kind:externaldata AND subject:contoso`。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**-サード ・ パーティ製のデータを指定する型の検索のみにこのプロパティと値のペアを使用します。たとえば、のみ [件名] プロパティには、"contoso"という単語を含む Facebook のデータを検索するにはクエリを使用するキーワード`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。 

  サード ・ パーティ製のデータ型に使用する値の完全な一覧については、`itemclass`プロパティでは、 [Office 365 にインポートされたサード ・ パーティ製のデータを検索するコンテンツの検索の使用](use-content-search-to-search-third-party-data-that-was-imported.md)を参照してください。
    
   コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。
    
  - [Office 365 でのコンテンツの検索](content-search.md)
    
  - [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
 
