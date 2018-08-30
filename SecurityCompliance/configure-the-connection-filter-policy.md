---
title: 接続フィルター ポリシーを構成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
description: 信頼できる人から送信された電子メールがブロックされていないことを確認するには、信頼できる IP アドレスの安全な送信者リストとも呼ばれ、許可リストを作成するのには、接続フィルター ポリシーを使用することができます。受信拒否リストを作成することもできます。
ms.openlocfilehash: cb9b73ff61b477f1c7ea0bb8da4039bebce83d1b
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003266"
---
# <a name="configure-the-connection-filter-policy"></a>接続フィルター ポリシーを構成する
 
ほとんどの人は友人やビジネス パートナーを信頼しています。信頼する人からの電子メールが迷惑メール フォルダーに入っていたり、スパム フィルターによって完全にブロックされたりすると、もどかしさを感じます。そのようなメールがブロックされないようにするには、接続フィルター ポリシーを利用して許可リスト (「差出人セーフ リスト」ともいう) を作成し、信頼する IP アドレスを登録することができます。また、受信拒否リストを作成して既知のスパム メール送信者の IP アドレスを登録し、そのような送信者からの電子メール メッセージを受信しないようにすることもできます。
  
 組織全体に適用されるスパム設定の詳細については、「 [EOP と Office 365 でメールが迷惑メールとして検出されないようにする](https://go.microsoft.com/fwlink/p/?LinkId=534224)」または「[Office 365 のスパム フィルターでスパムや迷惑メールをブロックして、検出漏れ問題を防止する](https://go.microsoft.com/fwlink/p/?LinkId=534225)」を参照してください。これらは、管理者レベルの制御権限を持っている場合にスパムの誤検知や検出漏れを防ぐ上で役立ちます。
  
次のビデオでは、接続フィルター ポリシーの構成手順を示します。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

- 予想所要時間 : 15 分
    
- このプロシージャまたはプロシージャを実行する前にアクセス許可を割り当てる必要があります。必要なアクセス許可については、 [Exchange のオンラインでの機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)トピックの「スパム対策」エントリを参照してください。 
    
- 許可またはブロックする送信者の IP アドレスを取得するには、メッセージのインターネット ヘッダーを確認するという方法があります。「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」で説明されているように、CIP ヘッダーを調べます。メール クライアントでメッセージ ヘッダーを表示する方法については、「[メッセージ ヘッダー アナライザー](https://go.microsoft.com/fwlink/p/?LinkId=306583)」をご覧ください。 
    
- IP ブロック一覧の IP アドレスから送信された電子メール メッセージは拒否され、スパムとしてマークされず、追加のフィルター処理は行われません。
    
- リモート PowerShell を使用しても、次の接続フィルターの手順を実行できます。設定と、接続フィルター ポリシーの設定を編集するのには[一連の HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx)を確認するのには、 [Get HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx)コマンドレットを使用します。Exchange のオンライン保護への接続に Windows PowerShell を使用する方法については、 [Exchange のオンライン保護 PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)を参照してください。Exchange Online に接続する Windows PowerShell を使用する方法については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)を参照してください。
    
- このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>EAC を使用して既定の接続フィルター ポリシーを編集する
<a name="sectionSection1"> </a>

IP 許可リストまたは IP 禁止リストを作成するには、Exchange 管理センター (EAC) で接続フィルター ポリシーを編集します。接続フィルター ポリシーの設定は、受信メッセージのみに適用されます。
  
1. Exchange 管理センター (EAC) で、 **[保護]** \> **[接続フィルター]** に移動し、既定のポリシーをダブルクリックします。
    
2. **[接続フィルター]** メニュー項目をクリックし、IP 許可一覧、IP 禁止一覧、あるいはその両方のうち、必要な一覧を作成します。 
    
    この一覧を作成するには、![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックします。後続のダイアログ ボックスでは、IP アドレスまたはアドレス範囲を指定して **[OK]** をクリックします。さらにアドレスを追加するには、このプロセスを繰り返します。(IP アドレスは、追加後に編集または削除できます。)
    
    > [!NOTE]
    >  両方の一覧に IP アドレスを追加した場合、その IP アドレスから送信される電子メールは許可されます。 >  IPV4 の IP アドレスは nnn.nnn.nnn.nnn (nnn は 0 から 255 までの数値) の形式で指定する必要があります。クラスレス ドメイン間ルーティング (CIDR) の範囲を nnn.nnn.nnn.nnn/rr (rr は 24 から 32 までの数値) の形式で指定することもできます。24 から 32 以外の範囲を指定するには、「 [IP 許可一覧を構成する場合のその他の留意点](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)」を参照してください。 >  最大 1273 のエントリを指定できます。各エントリは、単一の IP アドレス、または IP アドレスの CIDR 範囲 (/24 から /32 まで) にすることができます。 >  TLS 暗号化メッセージを送信している場合は、IPv6 のアドレスとアドレス範囲はサポートされません。 
  
3. オプションとして、 **[セーフ リストを有効にする]** チェック ボックスを選択していくつかの既知の送信者からの電子メールをブロックしないようにできます。そのために、Microsoft は、信頼できる送信者のサード パーティ ソースにサブスクライブしています。このセーフ リストを使用すれば、信頼できる送信者に誤ってスパムのマークを付けないようにできます。このオプションを選択すると、誤検知 (スパムとして分類される正常なメール) の受信数が減少するため、選択することをお勧めします。 
    
4. **[保存]** をクリックします。既定のポリシー設定の概要が右側のウィンドウに表示されます。
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>IP 許可一覧を構成する場合のその他の留意点
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

IP 許可一覧を構成する場合に考慮するまたは認識すべきその他の留意点を以下に示します。
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>推奨範囲外の CIDR 範囲の指定

/1 ～ /23 の CIDR IP アドレス範囲を指定するには、Spam Confidence Level (SCL) を **[スパム フィルターをバイパスする]** に設定した、この IP アドレス範囲に対して動作するトランスポート ルールを作成する必要があります (この IP アドレス範囲から受信されたすべてのメッセージが "非スパム" に設定され、サービスによるフィルタリングがこれ以上行われないことを意味します)。ただし、これらの IP アドレスのいずれかが Microsoft 独自のブロック リストのいずれか、または、サード・パーティ・ブロック・リストのいずれかに含まれている場合は、これらのメッセージもブロックされます。そのため、/32 ～ /24 の IP アドレス範囲の使用を強くお勧めします。 
  
トランスポート ルールを作成するには、以下の手順を実行します。
  
1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。
    
3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。
    
4. **[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。
    
5. **[IP アドレスを指定する]** で、IP アドレス範囲を指定して、 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[ok]** をクリックします。
    
6. **[実行する処理]** ボックスで、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[スパム対策フィルターをバイパスする]** を選択してから、 **[ok]** をクリックします。
    
7. これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。ルールを施行する前に一定期間ルールをテストすることをお勧めします。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) にこれらの選択肢に関する詳細が記載されています。 
    
8. **[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。 
    
ルールを作成して適用したら、指定した IP アドレス範囲に対してスパム フィルター処理が省略されます。
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>特定のドメインに関する IP 許可一覧例外の範囲指定

一般に、安全だと思われるドメインの IP アドレス (または IP アドレス範囲) をすべて IP 許可一覧に追加することをお勧めします。ただし、IP 許可一覧のエントリをすべてのドメインに適用しない場合は、特定のドメインを除外するトランスポート ルールを作成することができます。 
  
たとえば、ContosoA.com、ContosoB.com、および ContosoC.com という 3 つのドメインがあり、IP アドレス (簡単にするために、1.2.3.4 を使用する) を追加して、ContosoB.com ドメインのフィルター処理だけを省略することにしましょう。すべてのドメインの Spam Confidence Level (SCL) を -1 に設定する (非スパムに分類されることを意味する) 1.2.3.4 用の IP 許可一覧を作成します。その後、ContosoB.com 以外のすべてのドメインについて SCL を 0 に設定するトランスポート ルールを作成できます。これにより、ルールの適用外のドメインに指定されている ContosoB.com を除く IP アドレスに対応するすべてのドメインについてメッセージが再スキャンされます。ContosoB.com の SCL はフィルター処理をスキップする -1 のままであるのに対して、ContosoA.com と ContosoC.com の SCL はコンテンツ フィルターによって再スキャンされる 0 です。
  
これを実現するには、以下の手順を実行します。
  
1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。
    
3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。
    
4. **[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。
    
5. **[IP アドレスを指定する]** ボックスで、IP 許可一覧に入力した IP アドレスまたは IP アドレス範囲を指定して、 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[ok]** をクリックします。
    
6. **[実行する処理]** で、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[0]** を選択してから、 **[ok]** をクリックします。
    
7. **[例外の追加]** をクリックして、 **[ただし次の場合を除く]** で、 **[差出人]** を選択し、 **[ドメイン名]** を選択します。 
    
8. **[ドメインの指定]** ボックスで、 **contoso.com** のように、スパム フィルター処理を省略するドメインを入力します。 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックして、そのドメインを語句の一覧に移動します。その他のドメインを例外として追加する場合はこの手順を繰り返し、完了したら、 **[ok]** をクリックします。 
    
9. これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。ルールを施行する前に一定期間ルールをテストすることをお勧めします。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) にこれらの選択肢に関する詳細が記載されています。 
    
10. **[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。 
    
ルールを作成して適用すると、指定した IP アドレスまたは IP アドレス範囲に対するスパム フィルター処理が入力したドメイン例外の場合にのみ省略されます。
  
## <a name="new-to-office-365"></a>Office 365 を初めて使用する場合
<a name="sectionSection3"> </a>

||
|:-----|
|![LinkedIn Learning の小さいアイコン](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。 |
   
## <a name="for-more-information"></a>詳細情報
<a name="sectionSection4"> </a>

[Exchange Online の差出人セーフ リストと受信拒否リスト](safe-sender-and-blocked-sender-lists-faq.md)
  
[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)
  
[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)
  
[メッセージがスパムとしてマークされないようにする方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

