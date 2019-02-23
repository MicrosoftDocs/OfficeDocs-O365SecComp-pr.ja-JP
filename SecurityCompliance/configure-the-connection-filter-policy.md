---
title: 接続フィルター ポリシーを構成する
ms.author: tracyp
author: MSFTTracyP
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
ms.collection:
- M365-security-compliance
description: 信頼できるユーザーからの電子メールがブロックされないようにするには、接続フィルターポリシーを使用して、信頼する IP アドレスの許可リスト (安全な差出人のリストとも呼ばれます) を作成します。受信拒否リストを作成することもできます。
ms.openlocfilehash: d7c99f8fb6b9b05efb800804927ccb26f7dd9f40
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216907"
---
# <a name="configure-the-connection-filter-policy"></a>接続フィルター ポリシーを構成する
 
ほとんどの人は友人やビジネス パートナーを信頼しています。信頼する人からの電子メールが迷惑メール フォルダーに入っていたり、スパム フィルターによって完全にブロックされたりすると、もどかしさを感じます。そのようなメールがブロックされないようにするには、接続フィルター ポリシーを利用して許可リスト (「差出人セーフ リスト」ともいう) を作成し、信頼する IP アドレスを登録することができます。また、受信拒否リストを作成して既知のスパム メール送信者の IP アドレスを登録し、そのような送信者からの電子メール メッセージを受信しないようにすることもできます。
  
 組織全体に適用されるスパム設定の詳細については、「 [EOP と Office 365 でメールが迷惑メールとして検出されないようにする](https://go.microsoft.com/fwlink/p/?LinkId=534224)」または「[Office 365 のスパム フィルターでスパムや迷惑メールをブロックして、検出漏れ問題を防止する](https://go.microsoft.com/fwlink/p/?LinkId=534225)」を参照してください。これらは、管理者レベルの制御権限を持っている場合にスパムの誤検知や検出漏れを防ぐ上で役立ちます。
  
次のビデオでは、接続フィルター ポリシーの構成手順を示します。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

- 予想所要時間: 15 分
    
- この手順を実行する前に、アクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策」のエントリを参照してください。 
    
- 許可またはブロックするメッセージの送信者の IP アドレスを取得するには、メッセージのインターネットヘッダーを確認します。「[スパム対策メッセージヘッダー](anti-spam-message-headers.md)」で説明されているように、CIP ヘッダーを検索します。さまざまな電子メールクライアントでメッセージヘッダーを表示する方法については、「[メッセージヘッダーアナライザー](https://go.microsoft.com/fwlink/p/?LinkId=306583)」を参照してください。 
    
- IP ブロック一覧の IP アドレスから送信された電子メール メッセージは拒否され、スパムとしてマークされず、追加のフィルター処理は行われません。
    
- 次の接続フィルター手順は、リモート PowerShell を使用して実行することもできます。設定を確認するには、 [remove-hostedconnectionfilterpolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx)コマンドレットを使用し、接続フィルターポリシーの設定を編集するには[remove-hostedconnectionfilterpolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx)を使用します。Windows PowerShell を使用して exchange online protection に接続する方法については、「 [exchange online protection の PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)」を参照してください。Windows PowerShell を使用して exchange online に接続する方法については、「 [exchange online powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>EAC を使用して既定の接続フィルター ポリシーを編集する
<a name="sectionSection1"> </a>

IP 許可リストまたは IP 禁止リストを作成するには、Exchange 管理センター (EAC) で接続フィルター ポリシーを編集します。接続フィルター ポリシーの設定は、受信メッセージのみに適用されます。
  
1. Exchange 管理センター (EAC) で、 **[保護]** \> **[接続フィルター]** に移動し、既定のポリシーをダブルクリックします。
    
2. **[接続フィルター]** メニュー項目をクリックし、IP 許可一覧、IP 禁止一覧、あるいはその両方のうち、必要な一覧を作成します。 
    
    この一覧を作成するには、![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックします。後続のダイアログ ボックスでは、IP アドレスまたはアドレス範囲を指定して **[OK]** をクリックします。さらにアドレスを追加するには、このプロセスを繰り返します。(IP アドレスは、追加後に編集または削除できます。)
    
    > [!NOTE]
    >  両方のリストに ip アドレスを追加すると、その ip アドレスから送信された電子メールが許可されます。 

    形式を nnn. nnn にする場合は、IPV4 IP アドレスを指定します。 nnn には0から255の数値を指定します。また、rr が 24 ~ 32 の数字の形式の場合は、クラスレスドメイン間ルーティング (CIDR) 範囲を指定することもできます。24 ~ 32 の範囲外の範囲を指定するには、 [IP 許可一覧を構成するときの追加の考慮事項](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)を参照してください。 

    最大1273エントリを指定できます。これは、1つの ip アドレス、または、/24 から/32 の範囲の ip アドレスの CIDR 範囲のいずれかです。> TLS で暗号化されたメッセージを送信している場合、IPv6 アドレスとアドレス範囲はサポートされていません。 
  
3. 必要に応じて、[**セーフリストを有効**にする] チェックボックスをオンにして、特定の既知の送信者からの電子メールが失われないようにします。どう。Microsoft は、信頼できる送信者のサードパーティソースにサブスクライブします。このセーフリストを使用することは、これらの信頼できる差出人が誤ってスパムとしてマークされていることを意味します。受信する誤検知 (良好なメールに分類されているメール) の数を減らす必要があるため、このオプションを選択することをお勧めします。 
    
4. **[保存]** をクリックします。既定のポリシー設定の概要が右側のウィンドウに表示されます。
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>IP 許可一覧を構成する場合のその他の留意点
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

IP 許可一覧を構成する場合に考慮するまたは認識すべきその他の留意点を以下に示します。
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>推奨範囲外の CIDR 範囲の指定

/1 から/23 の CIDR ip アドレス範囲を指定するには、スパムの信頼レベル (SCL) を設定するメールフロールールを作成する必要があります。これは、スパムの**フィルター処理をバイパス**する (つまり、この ip アドレス範囲内で受信するすべてのメッセージが[迷惑メールではない] に設定し、サービスによって追加のフィルター処理は実行されません)。ただし、これらの IP アドレスのいずれかが Microsoft の独自のブロックリストまたはサードパーティのブロックリストのいずれかに表示される場合でも、これらのメッセージはブロックされます。そのため、/24 ~ 32 IP アドレス範囲を使用することを強くお勧めします。 
  
このメールフロールールを作成するには、次の手順を実行します。
  
1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。
    
3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。
    
4. **[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。
    
5. [ **ip アドレスの指定**] で、ip アドレスの範囲を**** ![指定し、](media/ITPro-EAC-AddIcon.gif)[追加] アイコンをクリックして、[ **ok]** をクリックします。
    
6. **[実行する処理]** ボックスで、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[スパム対策フィルターをバイパスする]** を選択してから、 **[ok]** をクリックします。
    
7. 必要に応じて、ルールを監査したり、ルールをテストしたり、特定の期間中にルールをアクティブ化したり、その他の選択を行ったりすることができます。ルールを適用する前に、期間に対してルールをテストすることをお勧めします。[Exchange Server のメールフロールールの手順には](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)、これらの選択についての詳細が含まれています。 
    
8. [**保存**] をクリックしてルールを保存します。ルールがルールの一覧に表示されます。 
    
ルールを作成して適用すると、サービスは指定した IP アドレス範囲のスパムフィルター処理をバイパスします。
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>特定のドメインに関する IP 許可一覧例外の範囲指定

一般に、安全だと思われるドメインの IP アドレス (または IP アドレス範囲) をすべて IP 許可一覧に追加することをお勧めします。ただし、IP 許可一覧のエントリをすべてのドメインに適用しない場合は、特定のドメインを除外するトランスポート ルールを作成することができます。 
  
たとえば、ContosoA.com、ContosoB.com、および ContosoC.com という 3 つのドメインがあり、IP アドレス (簡単にするために、1.2.3.4 を使用する) を追加して、ContosoB.com ドメインのフィルター処理だけを省略することにしましょう。すべてのドメインの Spam Confidence Level (SCL) を -1 に設定する (非スパムに分類されることを意味する) 1.2.3.4 用の IP 許可一覧を作成します。その後、ContosoB.com 以外のすべてのドメインについて SCL を 0 に設定するトランスポート ルールを作成できます。これにより、ルールの適用外のドメインに指定されている ContosoB.com を除く IP アドレスに対応するすべてのドメインについてメッセージが再スキャンされます。ContosoB.com の SCL はフィルター処理をスキップする -1 のままであるのに対して、ContosoA.com と ContosoC.com の SCL はコンテンツ フィルターによって再スキャンされる 0 です。
  
これを実現するには、以下の手順を実行します。
  
1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。
    
3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。
    
4. **[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。
    
5. [ip**アドレスの指定**] ボックスで、ip 許可一覧**** ![に入力した ip アドレスまたは ip アドレスの範囲を指定し](media/ITPro-EAC-AddIcon.gif)、[追加] アイコンをクリックし、[ **ok]** をクリックします。
    
6. **[実行する処理]** で、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[0]** を選択してから、 **[ok]** をクリックします。
    
7. **[例外の追加]** をクリックして、 **[ただし次の場合を除く]** で、 **[差出人]** を選択し、 **[ドメイン名]** を選択します。 
    
8. [**ドメインの指定**] ボックスに、スパムフィルタリングをバイパスするドメイン ( **contosob.com**など) を入力します。[追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックして、それを語句の一覧に移動します。 **** ![他のドメインを例外として追加する場合は、この手順を繰り返し、完了したら [ **ok** ] をクリックします。 
    
9. 必要に応じて、ルールを監査したり、ルールをテストしたり、特定の期間中にルールをアクティブ化したり、その他の選択を行ったりすることができます。ルールを適用する前に、期間に対してルールをテストすることをお勧めします。[Exchange Server のメールフロールールの手順には](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)、これらの選択についての詳細が含まれています。 
    
10. [**保存**] をクリックしてルールを保存します。ルールがルールの一覧に表示されます。 
    
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
  

