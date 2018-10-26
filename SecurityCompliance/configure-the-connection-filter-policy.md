---
title: 接続フィルター ポリシーを構成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
description: 信頼できる人から送信された電子メールがブロックされていないことを確認するには、信頼できる IP アドレスの安全な送信者リストとも呼ばれ、許可リストを作成するのには、接続フィルター ポリシーを使用することができます。受信拒否リストを作成することもできます。
ms.openlocfilehash: 2f8ec3d01de4358d7394c68d0efae9222db08282
ms.sourcegitcommit: a07b91723bae9ecee2cb092bfbc5b208b30b11a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "25793562"
---
# <a name="configure-the-connection-filter-policy"></a>接続フィルター ポリシーを構成する
 
ほとんどの人は友人やビジネス パートナーを信頼しています。信頼する人からの電子メールが迷惑メール フォルダーに入っていたり、スパム フィルターによって完全にブロックされたりすると、もどかしさを感じます。そのようなメールがブロックされないようにするには、接続フィルター ポリシーを利用して許可リスト (「差出人セーフ リスト」ともいう) を作成し、信頼する IP アドレスを登録することができます。また、受信拒否リストを作成して既知のスパム メール送信者の IP アドレスを登録し、そのような送信者からの電子メール メッセージを受信しないようにすることもできます。
  
 組織全体に適用されるスパム設定の詳細については、「 [EOP と Office 365 でメールが迷惑メールとして検出されないようにする](https://go.microsoft.com/fwlink/p/?LinkId=534224)」または「[Office 365 のスパム フィルターでスパムや迷惑メールをブロックして、検出漏れ問題を防止する](https://go.microsoft.com/fwlink/p/?LinkId=534225)」を参照してください。これらは、管理者レベルの制御権限を持っている場合にスパムの誤検知や検出漏れを防ぐ上で役立ちます。
  
次のビデオでは、接続フィルター ポリシーの構成手順を示します。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

- 完了までの推定時間: 15 分
    
- このプロシージャまたはプロシージャを実行する前にアクセス許可を割り当てる必要があります。必要なアクセス許可については、 [Exchange のオンラインでの機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)トピックの「スパム対策」エントリを参照してください。 
    
- 許可またはブロックを行うメッセージの送信者の IP アドレスを取得するには、メッセージのインターネット ヘッダーを確認できます。[スパム メッセージのヘッダー](anti-spam-message-headers.md)に記載されているように CIP ヘッダーを確認します。さまざまな電子メール クライアントでメッセージ ヘッダーを表示する方法の詳細については、[メッセージ ヘッダーの分析](https://go.microsoft.com/fwlink/p/?LinkId=306583)を参照してください。 
    
- IP ブロック一覧の IP アドレスから送信された電子メール メッセージは拒否され、スパムとしてマークされず、追加のフィルター処理は行われません。
    
- リモート PowerShell を使用しても、次の接続フィルターの手順を実行できます。設定と、接続フィルター ポリシーの設定を編集するのには[一連の HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx)を確認するのには、 [Get HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx)コマンドレットを使用します。Exchange のオンライン保護への接続に Windows PowerShell を使用する方法については、 [Exchange のオンライン保護 PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)を参照してください。Exchange Online に接続する Windows PowerShell を使用する方法については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)を参照してください。
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>EAC を使用して既定の接続フィルター ポリシーを編集する
<a name="sectionSection1"> </a>

IP 許可リストまたは IP 禁止リストを作成するには、Exchange 管理センター (EAC) で接続フィルター ポリシーを編集します。接続フィルター ポリシーの設定は、受信メッセージのみに適用されます。
  
1. Exchange 管理センター (EAC) で、 **[保護]** \> **[接続フィルター]** に移動し、既定のポリシーをダブルクリックします。
    
2. **[接続フィルター]** メニュー項目をクリックし、IP 許可一覧、IP 禁止一覧、あるいはその両方のうち、必要な一覧を作成します。 
    
    この一覧を作成するには、![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックします。後続のダイアログ ボックスでは、IP アドレスまたはアドレス範囲を指定して **[OK]** をクリックします。さらにアドレスを追加するには、このプロセスを繰り返します。(IP アドレスは、追加後に編集または削除できます。)
    
    > [!NOTE]
    >  両方の一覧に IP アドレスを追加すると、その IP アドレスから送信された電子メールは許可されます。 

    Nnn には、0 から 255 までの数値形式 nnn.nnn.nnn.nnn の IPV4 の IP アドレスを指定します。Rr が 24 から 32 までの数字を形式 nnn.nnn.nnn.nnn/rr でクラスレス ドメイン間ルーティング (CIDR) の範囲を指定することもできます。24 ~ 32 の範囲外の範囲を指定するには、 [IP 許可を構成するときの追加の考慮事項の一覧](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)を参照してください。 

    1273 のエントリ、エントリが 1 つの IP アドレスまたは、CIDR の IP アドレス範囲/24 から/32 のいずれかを最大を指定できます。> TLS で暗号化されたメッセージを送信する場合、IPv6 アドレスおよびアドレス範囲はサポートされません。 
  
3. しないようにするのには、[**セーフ リストを有効にする**] チェック ボックスを選択して必要に応じて、特定の既知の送信者からのメールがありません。どう。マイクロソフトでは、差出人セーフ リストのサード パーティのソースをサブスクライブします。このセーフ リストを使用して、これらの信頼された送信者はいない誤ってスパムとしてマークされたことを意味します。誤検知 (スパムとして分類されている適切なメール) の数を削減する必要がありますので、このオプションを選択することをお勧めします。 表示されます。 
    
4. **[保存]** をクリックします。既定のポリシー設定の概要が右側のウィンドウに表示されます。
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>IP 許可一覧を構成する場合のその他の留意点
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

IP 許可一覧を構成する場合に考慮するまたは認識すべきその他の留意点を以下に示します。
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>推奨範囲外の CIDR 範囲の指定

CIDR IP のアドレス/1 から/23 の範囲を指定するには、**スパムのフィルタ リングを使用しない**(つまり、この IP アドレス範囲から受信したすべてのメッセージがスパム信頼レベル (SCL) を設定している IP アドレスの範囲で動作するメールの流れのルールを作成する必要があります。「スパム」に設定) し、サービスが追加のフィルター処理は実行されません)。ただしに表示されるこれらの IP アドレスの一覧が表示マイクロソフトの独自のブロックのいずれか、または、サード パーティのブロックのいずれかの一覧が表示、これらのメッセージはブロックされます。したがって強くお勧め/24 から 32 に IP アドレスの範囲を使用することです。 
  
このメール フロー ルールを作成するには、次の手順を実行します。
  
1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。
    
3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。
    
4. **[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。
    
5. **IP アドレスを指定**する IP アドレスの範囲を指定、[**追加**] をクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)、し、[ **ok**] をクリックします。
    
6. **[実行する処理]** ボックスで、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[スパム対策フィルターをバイパスする]** を選択してから、 **[ok]** をクリックします。
    
7. 希望する場合は、監査規則、ルールをテスト、特定の期間中にルールをアクティブにするための選択および他の選択を行うことができます。それを実施する前に一定のルールをテストすることをお勧めします。[メール フローの手順のルールでは、Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)には、これらの選択の詳細については含まれています。 
    
8. ルールを保存**保存**をクリックします。ルールは、ルールの一覧に表示されます。 
    
作成して、ルールを適用すると、サービスは、スパムの IP アドレスの範囲を指定したフィルターをバイパスします。
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>特定のドメインに関する IP 許可一覧例外の範囲指定

一般に、安全だと思われるドメインの IP アドレス (または IP アドレス範囲) をすべて IP 許可一覧に追加することをお勧めします。ただし、IP 許可一覧のエントリをすべてのドメインに適用しない場合は、特定のドメインを除外するトランスポート ルールを作成することができます。 
  
たとえば、ContosoA.com、ContosoB.com、および ContosoC.com という 3 つのドメインがあり、IP アドレス (簡単にするために、1.2.3.4 を使用する) を追加して、ContosoB.com ドメインのフィルター処理だけを省略することにしましょう。すべてのドメインの Spam Confidence Level (SCL) を -1 に設定する (非スパムに分類されることを意味する) 1.2.3.4 用の IP 許可一覧を作成します。その後、ContosoB.com 以外のすべてのドメインについて SCL を 0 に設定するトランスポート ルールを作成できます。これにより、ルールの適用外のドメインに指定されている ContosoB.com を除く IP アドレスに対応するすべてのドメインについてメッセージが再スキャンされます。ContosoB.com の SCL はフィルター処理をスキップする -1 のままであるのに対して、ContosoA.com と ContosoC.com の SCL はコンテンツ フィルターによって再スキャンされる 0 です。
  
これを実現するには、以下の手順を実行します。
  
1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。
    
3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。
    
4. **[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。
    
5. IP アドレスまたは IP 許可一覧に入力した IP アドレスの範囲を指定、[ **IP アドレスを指定**] ボックスで、[**追加**] をクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)、し、[ **ok**] をクリックします。
    
6. **[実行する処理]** で、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[0]** を選択してから、 **[ok]** をクリックします。
    
7. **[例外の追加]** をクリックして、 **[ただし次の場合を除く]** で、 **[差出人]** を選択し、 **[ドメイン名]** を選択します。 
    
8. **ドメインの指定**] ボックスで、 **contosob.com**など、スパムのフィルタ リングをバイパスするドメインを入力します。[**追加**] をクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)語句のリストに移動します。例外として追加のドメインの追加が完了したら、[ **ok** ] をクリックする場合は、この手順を繰り返します。 
    
9. 希望する場合は、監査規則、ルールをテスト、特定の期間中にルールをアクティブにするための選択および他の選択を行うことができます。それを実施する前に一定のルールをテストすることをお勧めします。[メール フローの手順のルールでは、Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)には、これらの選択の詳細については含まれています。 
    
10. ルールを保存**保存**をクリックします。ルールは、ルールの一覧に表示されます。 
    
ルールを作成して適用すると、指定した IP アドレスまたは IP アドレス範囲に対するスパム フィルター処理が入力したドメイン例外の場合にのみ省略されます。
  
## <a name="new-to-office-365"></a>Office 365 を初めて使用する場合
<a name="sectionSection3"> </a>

||
|:-----|
|![LinkedIn Learning の小さいアイコン](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。 |
   
## <a name="for-more-information"></a>関連情報
<a name="sectionSection4"> </a>

[Exchange Online の差出人セーフ リストと受信拒否リスト](safe-sender-and-blocked-sender-lists-faq.md)
  
[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)
  
[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)
  
[メッセージがスパムとしてマークされないようにする方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

