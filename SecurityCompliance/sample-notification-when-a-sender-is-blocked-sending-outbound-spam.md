---
title: 送信者が送信スパムの送信をブロックされる場合の通知例
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 送信スパムを送信しようとしたために送信者がサービスからブロックされる場合、「送信スパム ポリシーを構成する」で指定したドメイン管理者は、次のような通知の電子メールを受信します。
ms.openlocfilehash: 04d8bde8e9cadd3525191a5bee7d368229e85056
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30691808"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>送信者が送信スパムの送信をブロックされる場合の通知例

送信スパムを送信しようとしたために送信者がサービスからブロックされる場合、「[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)」で指定したドメイン管理者は、次のような通知の電子メールを受信します。 
  
 **送信者アドレス:** spamalerts@microsoft.com 
  
 **件名:** 送信スパムの通知 - \<  *account name*  \> の送信メールの送信がブロックされました 
  
 **本文:** これは、Exchange Online Protection スパム分析システムからの自動応答です。 
  
あなたの組織を発信元とする、スパムとしてマークされた大量の電子メールまたはその他の疑わしい動作が検出されたたため、連絡しました。以下の電子メール アカウントは、電子メールの送信が禁止されています (電子メールの受信は可能です)。
  
\< *アカウント名*  \> 
  
この電子メール アカウントが侵害されている可能性があります。次の手順を実行してください。
  
1. 以下のことを実行して、この問題をご自分で解決します。
    
  - アカウントのパスワードを変更する。
    
  - アカウントがどのように侵害されたかを確認する。
    
  - この脆弱性が再び悪用されないようにするための予防策を講じる。
    
  - 送信メールのキューから、問題のあるメッセージがすべて消去されていることを確認する。
    
2. 通常の連絡手段を使用して Microsoft サポートにお問い合わせください。
    
3. メールの送信がブロックされているユーザーがいること、また問題が処理されたことを説明します。
    
4. エージェントは、提供された情報でサポート チケットを作成し、当該の電子メール アドレスまたはドメインのブロックが解除されるようにそのチケットをエスカレートします。
    
5. アドレスのブロックが解除され、保留中の他の問題がなくなると、連絡があり、ブロック解除に関する通知を受け取ります。
    
迷惑メールを制御することにご協力いただき、ありがとうございました。
  
Exchange Online Protection
  
\*\*注意: この電子メールは監視されていないアドレスから送信されているため、このメールには返信しないでください\*\*
  
> [!TIP]
> 「 [Help and support for EOP](eop/help-and-support-for-eop.md)」に記載されているオプションを使用してサポートに連絡することもできます。 
  

