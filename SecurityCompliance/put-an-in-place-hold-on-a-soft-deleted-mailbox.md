---
title: Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。Microsoft 電子情報開示ツールを使用して、非アクティブなメールボックスを検索できるようになります。
ms.openlocfilehash: 226929764fe39b99f526301029d4a41e2fa486cc
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027614"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する

削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。Microsoft 電子情報開示ツールを使用して、非アクティブなメールボックスを検索できるようになります。
  
> [!NOTE]
> 新規作成の場所に保持している Exchange オンラインで Office 365 および Exchange オンラインのスタンドアロン プラン)、2017 年 7 月 1 日の期限を延期してしました。今年または来年の早期ことはできません新しいを作成する場所に保持している Exchange オンライン。インプレース保持しているを使用する代わりに、使用できます[電子的証拠開示のサポート案件](https://go.microsoft.com/fwlink/?linkid=780738)または[アイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=827811)で Office 365 のセキュリティ&amp;コンプライアンス センターです。私たちを非コミッションに新しい場所に保持している後、まだことができます既存の埋め込み先を保持しているを変更して、新規作成を保持する、インプレースでは、Exchange Server 2013 と Exchange ハイブリッド展開はサポートされます。証拠保全上のメールボックスを配置することができます。 
  
人が、組織のままにされ、対応するユーザー アカウントとメールボックスが削除された場合があります。その後、保持する必要のあるメールボックスに情報がわかっています。できることは何ですか。削除済みメールボックスの保存期間の期限が切れていない場合は (ソフト削除されたメールボックスと呼ばれます)、削除済みメールボックスの配置、埋め込みを保持し、非アクティブなメールボックスを使用すればできます。*非アクティブなメールボックス*は、彼または彼女が組織を離れた後に、以前の社員の電子メールを保持するために使用されます。埋め込み保持の期間は、アクティブでないとなったときソフト削除されたメールボックスに配置されますの非アクティブなメールボックスの内容は保持されます。Exchange オンライン、Office 365 のセキュリティでのコンテンツの検索で、インプレース電子証拠開示を使用してメールボックスを検索するには、メールボックスを無効になりましたが後、&amp;コンプライアンス部門、または SharePoint Online では、電子的証拠開示中心です。 
  
> [!NOTE]
> Exchange Online では、削除済みメールボックス (回復可能) は、メールボックスが削除されていても、特定の保存期間内であれば回復することができます。Exchange Online の削除済みメールボックス (回復可能) の保存期間は 30 日です。つまり、削除してから 30 日以内なら、メールボックスは復元できます (または、非アクティブなメールボックスにできます)。30 日が経過すると、削除済みメールボックスには完全削除のマークが付けられ、回復または非アクティブにすることができなくなります。 
  
## <a name="before-you-begin"></a>はじめに
<a name="sectionSection0"> </a>

- 削除済みメールボックス (回復可能) にインプレース ホールドを設定するには、Windows PowerShell で **New-MailboxSearch** コマンドレットを使う必要があります。Exchange 管理センター (EAC) または SharePoint Online の電子情報開示センターを使用することはできません。 
    
- Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
    
- 組織内の削除済みメールボックス (回復可能) の識別情報を取得するには、次のコマンドを実行します。 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 非アクティブなメールボックスの詳細については、「[Exchange Online の非アクティブなメールボックス](http://technet.microsoft.com/library/2f2948c5-1c5a-4643-865c-b36e4ac1414b.aspx)」を参照してください。
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>削除済みメールボックス (回復可能) にインプレース ホールドを適用し、非アクティブなメールボックスにする
<a name="sectionSection1"> </a>

**New-MailboxSearch** コマンドレットを使用して、削除済みメールボックス (回復可能) を非アクティブなメールボックスにします。詳細については、「 [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)」を参照してください。
  
1. 削除済みメールボックス (回復可能) のプロパティを含む変数を作成します。 
    
  ```
  $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
  ```

    > [!IMPORTANT]
    > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGuid** プロパティの値を使用して削除済みメールボックス (回復可能) を識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと削除済みメールボックス (回復可能) でプライマリ SMTP アドレスが等しい可能性があります。 
  
2. インプレース ホールドを作成し、削除済みメールボックス (回復可能) に適用します。この例では、保存期間が指定されていません。この場合、アイテムは無制限に、または非アクティブなメールボックスからホールドが解除されるまで保存されます。
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
  
  ```

    インプレース ホールドを作成するときに、保存期間を指定することもできます。この例では、非アクティブなメールボックスのアイテムを約 7 年間保持します。
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
  ```

3. しばらくしてから、次のコマンドのいずれかを実行して削除済みメールボックス (回復可能) が、非アクティブなメールボックスになっていることを確認します。
    
  ```
  Get-Mailbox -InactiveMailboxOnly
  ```

    または
    
  ```
  Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
  ```

## <a name="more-information"></a>詳細情報
<a name="sectionSection2"> </a>

削除済みメールボックス (回復可能) を非アクティブなメールボックスにしてから、いろいろな方法でメールボックスを管理することができます。詳細については、以下を参照してください。
  
- [Exchange Online の非アクティブなメールボックスの保持期間を変更する](http://technet.microsoft.com/library/96eb634e-af2f-454e-8014-b698396811c4.aspx)
    
- [Exchange Online の非アクティブなメールボックスを回復する](http://technet.microsoft.com/library/283838b4-66ba-4c34-b221-e1a3875e1d29.aspx)
    
- [Exchange Online の非アクティブなメールボックスを復元する](http://technet.microsoft.com/library/1fb02feb-49e5-4485-aec5-9f1537b772b6.aspx)
    
- [Exchange Online の非アクティブなメールボックスからホールドを削除する](http://technet.microsoft.com/library/930a98c3-cd81-4aaa-8e22-19714cb2b731.aspx)
    

