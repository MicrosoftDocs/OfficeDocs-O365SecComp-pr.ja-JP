---
title: 電子情報開示のために Bcc および展開された配布グループの受信者を保持する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: インプレースホールド、訴訟ホールド、および Office 365 のアイテム保持ポリシーを使用すると、メールボックスのコンテンツを保持して規制コンプライアンスおよび電子情報開示の要件を満たすことができます。
ms.openlocfilehash: 21f6d4520f41710e89e0a7ce1fc491aa03ea44b0
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693236"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>電子情報開示のために Bcc および展開された配布グループの受信者を保持する
  
In-Place Hold, Litigation Hold, and [Office 365 retention policies](http://go.microsoft.com/fwlink/?LinkID=827811) (created in the Office 365 Security &amp; Compliance Center) allow you to preserve mailbox content to meet regulatory compliance and eDiscovery requirements. Information about recipients directly addressed in the To and Cc fields of a message is included in all messages by default, but your organization may require the ability to search for and reproduce details about all recipients of a message. This includes: 
  
- **メッセージの [BCC] フィールドを使用して指定された受信者:** BCC の受信者は、送信者のメールボックス内のメッセージには格納されますが、受信者に配信されたメッセージのヘッダーには含まれません。 
    
- **展開された配布グループの受信者:** メッセージの [宛先]、[CC]、[BCC] のいずれかに指定された配布グループのメンバーであるためにメッセージを受信した受信者。 
    
Exchange Online and Exchange Server 2013 (Cumulative Update 7 and later versions) retain information about Bcc and expanded distribution group recipients. You can search for this information by using an In-Place eDiscovery search in the Exchange admin center (EAC) or a Content Search in the Security &amp; Compliance Center. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>BCC 受信者および展開された配布グループの受信者を保持する方法
<a name="sectionSection0"> </a>

前述のように、BCC に指定された受信者に関する情報は、送信者のメールボックス内のメッセージに格納されます。この情報にはインデックスが付けられ、電子情報開示検索とホールドが使用できるようになります。 
  
展開された配布グループの受信者に関する情報は、メールボックスをインプレース保持または訴訟ホールドの対象にした後にメッセージと共に格納されます。Office 365 では、この情報は Office 365 保持ポリシーがメールボックスに適用されるときにも格納されます。配布グループのメンバーシップは、メッセージが送信された時点で決まります。メッセージを送信した後でグループのメンバーに変更が加えられても、メッセージと共に格納された展開された受信者のリストは影響を受けません。 
  
|**格納される情報の対象...**|**格納場所...**|**既定で格納されるかどうか...**|**アクセスできる対象者…**|
|:-----|:-----|:-----|:-----|
|宛先と CC の受信者  <br/> |送信者および受信者のメールボックスのメッセージ プロパティ  <br/> |○  <br/> |送信者、受信者、コンプライアンス責任者  <br/> |
|BCC の受信者  <br/> |送信者のメールボックスのメッセージ プロパティ  <br/> |はい  <br/> |送信者およびコンプライアンス責任者  <br/> |
|展開された配布グループの受信者  <br/> |送信者のメールボックスのメッセージ プロパティ  <br/> |いいえ。展開された配布グループの受信者の情報は、メールボックスがインプレースホールドまたは訴訟ホールドの対象にされた後、あるいは Office 365 アイテム保持ポリシーに割り当てられた後に格納されます。  <br/> |コンプライアンス責任者  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>BCC 受信者および展開された配布グループの受信者に送信されたメッセージの検索
<a name="sectionSection1"> </a>

ある受信者へ送信されたメッセージを検索するとき、電子情報開示の検索結果には、その受信者がメンバーである配布グループに送信されたメッセージが含まれるようになります。電子情報開示の検索によって BCC の受信者および展開された配布グループの受信者に送信されたメッセージが返されるシナリオを、以下の表に示します。
  
シナリオ 1: John は US-Sales 配布グループのメンバーです。Bob が John にメッセージを直接送信した場合、または配布グループを介して間接的に送信した場合の電子情報開示の検索結果を、以下の表に示します。
  
|**Bob のメールボックスで検索するメッセージの送信先**|**メッセージの送信時に指定した宛先**|**結果にメッセージが含まれるかどうか**|
|:-----|:-----|:-----|
|宛先:John  <br/> |[宛先] に John  <br/> |はい  <br/> |
|宛先:John  <br/> |[宛先] に US-Sales  <br/> |はい  <br/> |
|宛先:US-Sales  <br/> |[宛先] に US-Sales  <br/> |はい  <br/> |
|CC:John  <br/> |[CC] に John  <br/> |はい  <br/> |
|CC:John  <br/> |[CC] に US-Sales  <br/> |はい  <br/> |
|CC:US-Sales  <br/> |[CC] に US-Sales  <br/> |はい  <br/> |
   
シナリオ 2: Bob は電子メールを John (宛先/CC) および Jack (BCC で直接に、または配布グループを介して間接に) に送信します。以下の表に、電子情報開示の検索結果を示します。
  
|**検索する対象**|**検索するメッセージの送信先**|**結果にメッセージが含まれるかどうか**|**注**|
|:-----|:-----|:-----|:-----|
|Bob のメールボックス  <br/> |宛先/CC:John  <br/> |はい  <br/> |Jack が BCC で送信されたことが示されます  <br/> |
|Bob のメールボックス  <br/> |BCC:Jack  <br/> |はい  <br/> |Jack が BCC で送信されたことが示されます  <br/> |
|Bob のメールボックス  <br/> |BCC:Jack (配布グループ経由)  <br/> |はい  <br/> |BCC で送信された配布グループ (メッセージの送信時に展開される) のメンバーのリストが、電子情報開示の検索プレビュー、エクスポート、およびログに表示されます。  <br/> |
|John のメールボックス  <br/> |宛先/CC:John  <br/> |はい  <br/> |BCC 受信者に関する標識はありません。  <br/> |
|John のメールボックス  <br/> |BCC:Jack (直接または配布グループ経由)  <br/> |X  <br/> |受信者に配信されるメッセージに BCC の情報は格納されません。送信者のメールボックスを検索する必要があります。  <br/> |
|Jack のメールボックス  <br/> |宛先/CC:John (直接または配布グループ経由)  <br/> |はい  <br/> |宛先/CC の情報は、すべての受信者に配信されるメッセージに含まれます。  <br/> |
|Jack のメールボックス  <br/> |BCC:Jack (直接または配布グループ経由)  <br/> |X  <br/> |受信者に配信されるメッセージに BCC の情報は格納されません。送信者のメールボックスを検索する必要があります。  <br/> |
   
## <a name="frequently-asked-questions"></a>よく寄せられる質問
<a name="sectionSection2"> </a>

 **Q. BCC 受信者の情報はいつ、どこに格納されますか?**
  
A. 既定では、BCC 受信者の情報は送信者のメールボックスの元のメッセージに保持されます。BCC 受信者が配布グループである場合には、配布グループのメンバーシップは、送信者のメールボックスがホールドの対象になった場合、または Office 365 アイテム保持ポリシーに割り当てられた場合にのみ展開されます。
  
 **Q. 展開された配布グループの受信者のリストはいつ、どこに格納されますか?**
  
A. グループのメンバーシップは、メッセージが送信された時点で展開されます。展開された配布グループのメンバーシップのリストは、送信者のメールボックスの元のメッセージに格納されます。送信者のメールボックスは、インプレース ホールドまたは訴訟ホールドの対象であるか、Office 365 アイテム保持ポリシーに割り当てられている必要があります。
  
 **Q. 宛先/CC の受信者は、BCC の受信者がだれかを確認できますか?**
  
A. いいえ。この情報は、メッセージ ヘッダーには含まれず、宛先/CC の受信者には表示されません。送信者は、自分のメールボックスに格納された元のメッセージに含まれる [BCC] フィールドを確認できます。コンプライアンス責任者は、送信者のメールボックスを検索する際に、この情報を確認することができます。
  
 **Q. 展開された配布グループの受信者を常に保持するにはどうしたらよいですか?**
  
A. 展開された配布グループのメンバーを常にメッセージと一緒に保持するには、[すべてのメールボックスを保持に設定する](http://technet.microsoft.com/library/4c141604-3210-44cc-b98e-f3e0f15613b8.aspx) を行うか、組織全体の Office 365 アイテム保持ポリシーを作成してください。 
  
 **Q. どのタイプのグループがサポートされますか?**
  
A. 配布グループ、メールが有効なセキュリティ グループ、および動的配布グループがサポートされます。 
  
 **Q. 展開されてメッセージに格納される配布グループの受信者数に制限はありますか?**
  
A. 最大 10,000 人まで配布グループのメンバーを保持できます。
  
 **Q. 入れ子になった配布グループはサポートされますか?**
  
A. 25 レベルまで入れ子になった配布グループが展開されます。
  
 **Q. BCC および展開された配布グループの受信者の情報はどこで表示できますか?**
  
A. BCC および展開された配布グループの受信者の情報は、電子情報開示検索を実行したコンプライアンス責任者に表示されます。BCC および展開された配布グループの受信者は、探索メールボックスにコピーされた検索結果、または PST ファイルにエクスポートされた検索結果に含まれます。あるいは、検索結果に含まれる電子情報開示ログにも含まれます。BCC 受信者情報は、検索結果のプレビューでも確認できます。
  
 **Q. 組織のグローバル アドレス一覧 (GAL) から配布グループのメンバーが非表示になった場合、どうなりますか?**
  
A.影響はありません。受信者が GAL から非表示になった場合でも、展開された配布グループの受信者の一覧に含まれます。
  

