---
title: Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。Microsoft 電子情報開示ツールを使用して、非アクティブなメールボックスを検索できるようになります。
ms.openlocfilehash: 5113bd0dffe98a7af1c65af234caaefffff95184
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692596"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する

削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。Microsoft 電子情報開示ツールを使用して、非アクティブなメールボックスを検索できるようになります。
  
> [!NOTE]
> exchange online (Office 365 および exchange online スタンドアロンプラン) に新しいインプレースホールドを作成する期限を延期しました。 But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Office 365 Security &amp; Compliance Center. After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported. And, you'll still be able to place mailboxes on Litigation Hold. 
  
You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Office 365 Security &amp; Compliance Center, or the eDiscovery Center in SharePoint Online. 
  
> [!NOTE]
> Exchange Online では、削除済みメールボックス (回復可能) は、メールボックスが削除されていても、特定の保存期間内であれば回復することができます。Exchange Online の削除済みメールボックス (回復可能) の保存期間は 30 日です。つまり、削除してから 30 日以内なら、メールボックスは復元できます (または、非アクティブなメールボックスにできます)。30 日が経過すると、削除済みメールボックスには完全削除のマークが付けられ、回復または非アクティブにすることができなくなります。 
  
## <a name="before-you-begin"></a>はじめに

- 削除済みメールボックス (回復可能) にインプレース ホールドを設定するには、Windows PowerShell で **New-MailboxSearch** コマンドレットを使う必要があります。Exchange 管理センター (EAC) または SharePoint Online の電子情報開示センターを使用することはできません。 
    
- Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
    
- 組織内の削除済みメールボックス (回復可能) の識別情報を取得するには、次のコマンドを実行します。 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックスの概要](inactive-mailboxes-in-office-365.md)」を参照してください。
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>削除済みメールボックス (回復可能) にインプレース ホールドを適用し、非アクティブなメールボックスにする

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

削除済みメールボックス (回復可能) を非アクティブなメールボックスにしてから、いろいろな方法でメールボックスを管理することができます。詳細については、以下を参照してください。
  
- [非アクティブなメールボックスの保持期間を変更する](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)
    
- [非アクティブなメールボックスを復元する](restore-an-inactive-mailbox.md)
    
- [非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)(保留リストを削除する)
