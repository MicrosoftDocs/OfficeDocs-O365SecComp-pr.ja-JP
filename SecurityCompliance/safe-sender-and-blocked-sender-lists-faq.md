---
title: Exchange Online の差出人セーフ リストと受信拒否リスト
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Exchange Online または Exchange Online Protection (EOP) の管理者は、サービスを通過する電子メール メッセージがスパムとしてマークされないようにできます。そのための方法の 1 つに、組織内のユーザーの中で、信頼できる差出人とブロックする差出人のリストを作成する、というものがあります。
ms.openlocfilehash: 390b414c44da6b30193bcb6b9db0b8162aafffb7
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275657"
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
  
[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)で説明されているエラーが発生することがあります。この問題を解決するには、[連絡先からの電子メールを信頼する] チェックボックスをオフにします。または、"MaxSafeSenders" 属性に設定されている Exchange Online で、既定の連絡先フォルダーに含まれる電子メールアドレスの量を減らして、最大許容制限である1024に設定します。この属性とメールボックスの設定コマンドレットの詳細については、次のトピックを参照してください。
  
[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a>See also

[Sender filtering in Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

