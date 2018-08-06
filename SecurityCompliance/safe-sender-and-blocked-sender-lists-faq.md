---
title: Exchange Online の差出人セーフ リストと受信拒否リスト
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
description: Exchange Online または Exchange Online Protection (EOP) の管理者は、サービスを通過する電子メール メッセージがスパムとしてマークされないようにできます。そのための方法の 1 つに、組織内のユーザーの中で、信頼できる差出人とブロックする差出人のリストを作成する、というものがあります。
ms.openlocfilehash: fcb43f990750782788dc6f459dd5c7d296146a38
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028084"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Exchange Online の差出人セーフ リストと受信拒否リスト

Exchange Online または Exchange Online Protection (EOP) の管理者は、サービスを通過する電子メール メッセージがスパムとしてマークされないようにできます。そのための方法の 1 つに、組織内のユーザーの中で、信頼できる差出人とブロックする差出人のリストを作成する、というものがあります。 
  
 *管理者としてこのリストで作業を行う方法のヒントと手順の更新されたバージョンについては、「* [EOP と Office 365 でメールが迷惑メールとして検出されないようにする](https://go.microsoft.com/fwlink/p/?LinkID=534224)」を参照してください。 
  
管理者でないユーザーが、信頼できる差出人のリストを使用して Outlook で迷惑メールを管理するだけの場合は、「[迷惑メール フィルターの概要](https://go.microsoft.com/fwlink/?LinkId=817222)」の手順をご確認ください。 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Exchange Online での信頼できる差出人とブロックする差出人の制限について

Exchange Online での信頼できる差出人とブロックする差出人の制限は、Active Directory の制限や Outlook の制限と異なります。以下にその例を示します。
  
- 差出人セーフ リストの制限: 1,024
    
- ブロックする差出人の制限: 500
    
注:
  
KB 2590466 (「Outlook Web App for Exchange Server 2010 で「迷惑メールの検証エラー」を受信する」) で説明するエラーが発生することがあります。この問題を解決するには、「自分の連絡先からのメールを信頼する」チェック ボックスをオフにします。あるいは、既定の連絡先フォルダーに含まれている電子メール アドレスの数を、Exchange Online の制限である 1,024 以下に減らします。この制限は 「MaxSafeSenders」属性で設定されています。この属性と Set-Mailbox コマンドレットの詳細については、次のトピックを参照してください。
  
[Set-Mailbox](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/Set-Mailbox?view=exchange-ps)
  
## <a name="see-also"></a>See also

[Sender filtering in Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

