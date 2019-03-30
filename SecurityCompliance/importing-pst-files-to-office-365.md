---
title: Overview of importing your organization PST files to Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: '管理者向け: Security & コンプライアンスセンターのインポートサービスを使用して、Exchange Online のユーザーメールボックスに電子メールデータ (PST ファイル) を一括インポートする方法について説明します。 このトピックでは、faq を示し、PST インポート処理のしくみについて説明します。'
ms.openlocfilehash: 3a7dba3db608eb45347609acef396faf73da483f
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000240"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Overview of importing your organization PST files to Office 365

> [!NOTE]
> この記事は、管理者を対象としています。 PST ファイルを自分のメールボックスにインポートしようとしていますか? 「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。

Security & コンプライアンスセンターのインポートサービスを使用して、Office 365 組織の Exchange Online メールボックスに PST ファイルをすばやく一括インポートすることができます。 PST ファイルを Office 365 にインポートするには、次の2つの方法があります。
   
- **ネットワークアップロード**![クラウドの](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png)アップロード-PST ファイルをネットワーク経由で Microsoft クラウド内の一時的な Azure ストレージの場所にアップロードします。 次に、office 365 インポートサービスを使用して、office 365 組織のメールボックスに PST データをインポートします。 

- **ドライブの送付**![ハードディスク](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) -PST ファイルを BitLocker で暗号化されたハードドライブにコピーし、ドライブを Microsoft に物理的に送付します。 microsoft がハードドライブを受け取ると、データセンターの担当者は、microsoft クラウド内の一時的な Azure ストレージの場所にデータをアップロードします。 次に、office 365 インポートサービスを使用して、office 365 組織のメールボックスにデータをインポートします。

## <a name="step-by-step-instructions"></a>ステップごとの手順
  
組織の PST ファイルを Office 365 に一括インポートする詳細な手順については、以下のいずれかのトピックを参照してください。 
   
- [ネットワークアップロードを使用して Office 365 に PST ファイルをインポートする](use-network-upload-to-import-pst-files.md)
- [ドライブ送付を使用して PST ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>PST ファイルのインポートのしくみ

以下に、完全な PST インポートプロセスの図と説明を示します。 この図はプライマリワークフローを示しており、ネットワークアップロード方法とドライブ送付方法の相違点を強調しています。
  
![PST インポートプロセスのワークフロー](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **pst インポートツールとキーをプライベート Azure ストレージの場所にダウンロード**する-最初の手順として、pst ファイルのアップロードまたはハードドライブへのコピーに使用するツールとアクセスキーをダウンロードします。 これらは、セキュリティ & コンプライアンスセンターの [**インポート**] ページから取得します。 このキーを使用すると、機密およびセキュリティで保護された Azure ストレージの場所に PST ファイルをアップロードするために必要なアクセス許可が付与されたユーザー (または、ドライブを配送する場合は Microsoft データセンターのスタッフ) が提供されます。 このアクセスキーは組織に固有のものであり、Microsoft クラウドにアップロードされた後に PST ファイルへの権限のないアクセスを防止するのに役立てることができます。 Office 365 に PST ファイルをインポートする場合は、組織で別の Azure サブスクリプションを使用する必要はありません。 
    
2. **pst ファイルのアップロードまたはコピー** -次の手順は、pst ファイルをインポートするためにネットワークアップロードまたはドライブ配送を使用しているかどうかによって異なります。 どちらの場合も、前の手順で取得したツールとセキュリティ保護されたストレージキーを使用します。
    
    - **ネットワークアップロード**(手順1でダウンロードした) azcopy ツールを使用して、PST ファイルをアップロードし、Microsoft クラウド内の Azure ストレージの場所に保存します。 PST ファイルをアップロードする Azure ストレージの場所は、Office 365 組織が配置されているのと同じ地域の Microsoft データセンターに存在することに注意してください。 
    
      これらをアップロードするには、Office 365 にインポートする PST ファイルが、組織内のファイル共有またはファイルサーバーに配置されている必要があります。
    
    - **ドライブの送付**ユーザーの PST ファイルをハードドライブにコピーするには、手順1でダウンロードした waimportexport .exe ツールを使用します。 このツールは、BitLocker を使用してハードドライブを暗号化し、次に pst をハードドライブにコピーします。 ネットワークアップロードと同様に、ハードドライブにコピーする PST ファイルは、組織内のファイル共有またはファイルサーバーに配置する必要があります。
    
3. **pst インポートのマッピングファイルを作成**する-pst ファイルが Azure の保存場所にアップロードされた後、またはハードドライブにコピーされた後、次の手順では、pst ファイルをインポートするユーザーメールボックスを指定するコンマ区切り値 (CSV) ファイルを作成します。nd PST ファイルは、ユーザーのプライマリメールボックスまたは自分のアーカイブメールボックスにインポートできます。 Office 365 インポートサービスは、この情報を使用して PST ファイルをインポートします。 
    
4. **pst インポートジョブを作成**する-次の手順では、セキュリティ & コンプライアンスセンターの [**インポート**] ページで pst インポートジョブを作成し、前の手順で作成した pst インポートマッピングファイルを送信します。 ネットワークアップロードの場合 (pst ファイルが Azure にアップロードされているため)、Office 365 は pst ファイルのデータを分析し、pst インポートマッピングファイルで指定されているメールボックスに実際にインポートするデータを制御するフィルターを設定する機会を提供します。 
    
    ドライブの配送に関しては、プロセスのこの時点でいくつかの追加が行われます。
    
    - ハードドライブを microsoft データセンターに物理的に輸送します (インポートジョブの作成時に microsoft データセンターの送付先住所が表示されます)。
    
    - Microsoft がハードドライブを受け取ると、データセンター担当者は、組織のためにハードドライブ上の pst ファイルを Azure ストレージの場所にアップロードします。 前述したように、PST ファイルは、Office 365 組織が配置されているのと同じ地域の Microsoft データセンターに存在する Azure ストレージの場所にアップロードされます。
    
      > [!NOTE]
      > ハードドライブ上の PST ファイルは、Microsoft がハードドライブを受け取った後、7 ~ 10 営業日以内に Azure にアップロードされます。 
  
      ネットワークアップロードプロセスと同様に、Office 365 は pst ファイルのデータを分析し、pst インポートマッピングファイルで指定されたメールボックスに実際にインポートするデータを制御するフィルターを設定する機会を提供します。
    
    - Microsoft は、hdd をお送りします。 
    
5. **メールボックスにインポートする pst データのフィルター処理**-インポートジョブが作成された後 (およびドライブ出荷ジョブからの pst ファイルが Azure ストレージの場所にアップロードされた後)、Office 365 は pst ファイルのデータ (安全かつ安全) を分析します。アイテムの保存期間、および PST ファイルに含まれるさまざまなメッセージの種類を識別する。 分析が完了し、データをインポートする準備ができたら、PST ファイルに含まれるすべてのデータをインポートするか、インポートするデータを制御するフィルターを設定してインポートしたデータをトリミングすることができます。 
    
6. **pst インポートジョブを開始**する-インポートジョブが開始されると、Office 365 は pst インポートマッピングファイル内の情報を使用して、pst ファイルをユーザーのメールボックスにインポートします。 インポートジョブに関する状態情報 (インポートされる各 PST ファイルに関する情報を含む) は、セキュリティ & コンプライアンスセンターの [**インポート**] ページに表示されます。 インポートジョブが完了すると、ジョブの状態が [**完了**] に設定されます。
  
## <a name="why-import-email-data-to-office-365"></a>メールデータを Office 365 にインポートする理由

- PST ファイルのユーザーメールボックスへのインポートは、組織の電子メールを Office 365 に移行する1つの方法です。
    
- [インテリジェントインポート](filter-data-when-importing-pst-files.md)機能を使用すると、移動先のメールボックスに実際にインポートされる PST ファイル内のアイテムをフィルター処理できます。 これにより、インポートするデータを制御するフィルターを設定することによって、インポートされたデータをトリミングできます。 
    
- メールデータを Office 365 にインポートすると、組織のコンプライアンスニーズに対応できます。
    
  - [アーカイブメールボックス](enable-archive-mailboxes.md)と[無制限のアーカイブ](unlimited-archiving.md)を有効にして、ユーザーに追加のメールボックス記憶領域を付与します。 
    
  - メールボックスを[訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=841243)の対象にして、コンテンツを保持します。 
    
  - [コンテンツ検索ツール](content-search.md)を使用して、メールボックスのコンテンツを検索します。 
    
  - [電子情報開示ケース](ediscovery-cases.md)を使用して組織の法的調査を行う 
    
  - セキュリティ & コンプライアンスセンターの[アイテム保持ポリシー](retention-policies.md)を使用して、メールボックスのコンテンツを保持する期間を制御し、保存期間の期限が切れた後にコンテンツを削除します。 
    
- Office 365 にデータをインポートすると、データの損失を防ぐことができます。 Office 365 にインポートされた電子メールデータは、Exchange Online の高可用性機能を継承します。
    
- Office 365 の電子メールデータは、クラウドに格納されているため、すべてのデバイスのユーザーが利用できます。
    
## <a name="importing-sharepoint-data-to-office-365"></a>Office 365 に SharePoint データをインポートする

また、Office 365 組織の SharePoint サイトや OneDrive アカウントにファイルやドキュメントをインポートすることもできます。 詳細については、以下の記事を参照してください。

- [SharePoint Online に移行する](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [SharePoint 移行ツールの概要](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [PowerShell を使用して SharePoint Onine に移行する](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [Azure データボックスを使用してファイル共有コンテンツを SharePoint Online に移行する](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>Office 365 への PST ファイルのインポートに関してよく寄せられる質問
  
office 365 インポートサービスを使用して PST ファイルを office 365 メールボックスに一括インポートする方法についてよく寄せられる質問を以下に示します。 
  
- [ネットワークアップロードを使用して PST ファイルをインポートする](#using-network-upload-to-import-pst-files)
  
- [ドライブ配送を使用して PST ファイルをインポートする](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>ネットワークアップロードを使用して PST ファイルをインポートする

 **Office 365 インポートサービスでインポートジョブを作成するには、どのようなアクセス許可が必要ですか。**
  
PST ファイルを Office 365 メールボックスにインポートするには、Exchange Online でメールボックスのインポートのエクスポートの役割を割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 詳細については、「 [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」セクションを参照してください。
  
さらに、Security & コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。
  
- Exchange Online では、メール受信者の役割が割り当てられている必要があります。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    または
    
- Office 365 組織の全体管理者である必要があります。
    
> [!TIP]
> Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。 PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。 
  
 **ネットワークアップロードを使用できる場所**
  
Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
これは、PST ファイルが Azure ストレージ領域から削除された後に、Microsoft 365 管理センターでインポートジョブが完了したファイルの一覧に表示されなくなったことも意味します。 [ **Office にデータをインポート**します] ページにインポートジョブが表示されている可能性がありますが、古いインポートジョブの詳細を表示すると、PST ファイルの一覧は空の場合があります。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. ただし、ANSI PST ファイル形式を使用するファイル (2 バイト文字セット (DBCS) を使用する言語など) は、Office 365 にインポートすることもできます。 ANSI pst ファイルのインポートの詳細については、「[ネットワークアップロードを使用して pst ファイルを Office 365 にインポートする](https://go.microsoft.com/fwlink/p/?LinkId=823074)」の手順4を参照してください。
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **PST ファイルを azure ストレージ領域にアップロードした後、削除される前に azure で保持されている期間はどのくらいか。**
  
network upload メソッドを使用して PST ファイルをインポートする場合は、 **ingestiondata**という名前の Azure blob コンテナーにアップロードします。 セキュリティ & コンプライアンスセンターの [**インポート**] ページで進行中のインポートジョブがない場合、Azure の**ingestiondata**コンテナーにあるすべての PST ファイルは、最新のインポートジョブがセキュリティ & で作成されてから30日後に削除されます。コンプライアンスセンター また、「Security & コンプライアンスセンター (ネットワークアップロード手順の手順5」を参照) で新しいインポートジョブを作成し、30日以内に PST ファイルを Azure にアップロードしなければならないことも意味します。 
  
これは、PST ファイルが Azure ストレージ領域から削除された後に、Security & コンプライアンスセンターでインポートジョブが完了したファイルの一覧に表示されなくなったことも意味します。 インポートジョブは、セキュリティ & コンプライアンスセンターの [**インポート**] ページに表示されたままの場合がありますが、古いインポートジョブの詳細を表示すると、PST ファイルの一覧は空になる可能性があります。 
  
 **PST ファイルをメールボックスにインポートするのにどのくらいの時間がかかりますか?**
  
It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. pst ファイルが Azure ストレージ領域にコピーされると、1日あたり 24 GB 以上の速度で pst ファイルが Office 365 メールボックスにインポートされます。 このレートがニーズに合わない場合は、電子メールデータを Office 365 に移行する他の方法を検討してください。 詳細については、「[複数のメール アカウントを Office 365 に移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)」を参照してください。
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. 同様に、複数の PST ファイルが同じメールボックスにインポートされると、それらのファイルは同時にインポートされます。
  
 **Is there a message size limit when importing PST files?**
  
はい。 PST ファイルに 150 MB を超えるメールボックスアイテムが含まれている場合、インポート処理中にそのアイテムはスキップされます。
  
 **は、メッセージが送受信された日時、受信者のリスト、および PST ファイルが Office 365 メールボックスにインポートされるときに保持されるメッセージのプロパティです。**
  
はい。 インポート処理中は、元のメッセージのメタデータは変更されません。
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use network upload to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available. 
  
 **Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **ネットワークアップロードを使用して、Exchange Online のパブリックフォルダーに PST ファイルをインポートできますか。**
  
いいえ。 PST ファイルをパブリックフォルダーにインポートすることはできません。
  
### <a name="using-drive-shipping-to-import-pst-files"></a>ドライブ配送を使用して PST ファイルをインポートする

 **Office 365 インポートサービスでインポートジョブを作成するには、どのようなアクセス許可が必要ですか。**
  
PST ファイルを Office 365 メールボックスにインポートするには、メールボックスのインポートのエクスポート役割が割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 詳細については、「 [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」セクションを参照してください。
  
さらに、Security & コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。
  
- Exchange Online では、メール受信者の役割が割り当てられている必要があります。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    または
    
- Office 365 組織の全体管理者である必要があります。
    
> [!TIP]
> Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。 PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。 
  
 **ドライブ出荷の利用可能な場所**
  
現時点では、ドライブの配送は米国、カナダ、ブラジル、英国、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国共和国、オーストラリアで利用可能です。 Drive shipping will be available in more regions soon.
  
 **What commercial licensing agreements support drive shipping?**
  
Office 365 に PST ファイルをインポートするためのドライブの送付は、Microsoft Enterprise アグリーメント (EA) を通じて利用できます。 ドライブの送付は、Microsoft 製品およびサービス契約 (mpsa) 経由では利用できません。
  
 **PST ファイルを Office 365 にインポートするためにドライブ出荷を使用する場合の価格設定について**
  
The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. パートナーの検索の詳細について[は、「Office 365 パートナーまたは販売店を検索](https://go.microsoft.com/fwlink/p/?LinkId=785197)する」を参照してください。
  
 **What kind of hard drives are supported for drive shipping?**
  
Office 365 インポートサービスでの使用には、2.5 インチのソリッドステートドライブ (ssd) または2.5 または3.5 インチの SATA II/III 内部ハードドライブのみがサポートされています。 You can use hard drives up to 10 TB. インポートジョブの場合、ハードドライブ上の最初のデータボリュームのみが処理されます。 The data volume must be formatted with NTFS. データをハードドライブにコピーする場合は、2.5 インチ ssd または2.5 または3.5 インチ sata ii/iii コネクタを使用して直接接続できます。また、外部の2.5 インチ ssd または2.5 または3.5 インチの sata ii/iii USB アダプターを使用して外部に接続することもできます。
  
> [!IMPORTANT]
> 組み込みの USB アダプターが付属している外部ハードドライブは、Office 365 インポートサービスではサポートされていません。 Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
 **How many hard drives can I ship for a single import job?**
  
You can ship a maximum of 10 hard drives for a single import job.
  
 **After I ship my hard drive, how long does it take to get to the Microsoft data center?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **Microsoft データセンターにハードドライブが到着した後、PST ファイルを Azure にアップロードするのにどのくらいの時間がかかりますか?**
  
microsoft データセンターでハードドライブを受信した後は、7 ~ 10 営業日かかります。 PST ファイルは、組織の Microsoft Azure ストレージ領域にアップロードされます。 PST ファイルは、という名前`ingestiondata`の Azure blob コンテナーにアップロードされます。 
  
 **PST ファイルをメールボックスにインポートするのにどのくらいの時間がかかりますか?**
  
pst ファイルが Azure ストレージ領域にアップロードされると、Office 365 は pst ファイルのデータ (安全かつ安全な方法) を分析して、アイテムの保存期間と pst ファイルに含まれるさまざまなメッセージの種類を特定します。 この分析が完了すると、PST ファイルのすべてのデータをインポートするか、インポートするデータを制御するフィルターを設定するかを選択できます。 インポートジョブを開始すると、1日に 24 GB 以上の速度で PST ファイルが Office 365 メールボックスにインポートされます。 このレートがニーズに合わない場合は、Office 365 に電子メールデータをインポートするためのその他の方法を検討することができます。 詳細については、「[複数のメール アカウントを Office 365 に移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)」を参照してください。
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. 同様に、複数の PST ファイルが同じメールボックスにインポートされると、それらのファイルは同時にインポートされます。
  
 **Microsoft は、PST ファイルを azure にアップロードした後、削除される前に azure に保存されている期間はどのくらいか。**
  
組織の Azure ストレージの場所 (名前付き`ingestiondata`blob コンテナー内) にあるすべての PST ファイルは、最新のインポートジョブが & コンプライアンスセンターの [**インポート**] ページで作成されてから30日後に削除されます。 
  
これは、PST ファイルが Azure ストレージ領域から削除された後に、Security & コンプライアンスセンターでインポートジョブが完了したファイルの一覧に表示されなくなったことも意味します。 インポートジョブは、セキュリティ & コンプライアンスセンターの [**インポート**] ページに表示されたままの場合がありますが、古いインポートジョブの詳細を表示すると、PST ファイルの一覧は空になる可能性があります。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. ただし、ANSI PST ファイル形式を使用するファイル (2 バイト文字セット (DBCS) を使用する言語など) は、Office 365 にインポートすることもできます。 ANSI pst ファイルのインポートの詳細については、「Use drive 送料」の手順3「[組織の pst ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)」を参照してください。
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Is there a message size limit when importing PST files?**
  
はい。 PST ファイルに 150 MB を超えるメールボックスアイテムが含まれている場合、インポート処理中にそのアイテムはスキップされます。
  
 **は、メッセージが送受信された日時、受信者のリスト、および PST ファイルが Office 365 メールボックスにインポートされるときに保持されるメッセージのプロパティです。**
  
はい。 インポート処理中に元のメッセージのメタデータが変更されない
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available.
  
 **Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available.
  
 **ドライブの配送を使用して、Exchange Online のパブリックフォルダーに PST ファイルをインポートできますか。**
  
いいえ。 PST ファイルをパブリックフォルダーにインポートすることはできません。
  
 **Can Microsoft wipe my hard drive before they ship it back to me?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Microsoft は、自分のハードドライブを自分に出荷する代わりに、shred することはできますか?**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **返品出荷に対してサポートされている媒体使用サービスについて**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **返品送料のコストはどの程度ですか。**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **FedEx custom 送料などのカスタムの宅配便サービスを使用して、Microsoft にハードドライブを送付できますか。**
  
はい。
  
 **If I have to ship my hard drive to another country, is there anything I need to do?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
