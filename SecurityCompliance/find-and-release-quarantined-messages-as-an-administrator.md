---
title: 管理者として検疫済みメッセージを検索して解放する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: このトピックでは、Exchange Online and Exchange Online Protection (EOP) の管理者が、Exchange 管理センター (EAC) の検疫済みメッセージに入っているメッセージの検索、解放、報告を行う方法について説明します。
ms.openlocfilehash: 9bf821885ad8d4ec89aa3c349a6c072f78f6c57a
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699352"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>管理者として検疫済みメッセージを検索して解放する

このトピックでは、Exchange Online and Exchange Online Protection (EOP) の管理者が、Exchange 管理センター (EAC) の検疫済みメッセージに入っているメッセージの検索、解放、報告を行う方法について説明します。 Office 365 は、スパムとして識別されたか、メールフロールール (トランスポートルールとも呼ばれる) と一致したために、メッセージを検疫するように指示します。 
  
Use the Security &amp; Compliance Center instead of the EAC to complete any of these tasks as well as view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
検疫済みメッセージは EAC の **[検疫]** ページに一覧表示されます。既定では、メッセージは **[受信]** フィールドの降順で並べ替えられます。 **[送信者]**、 **[件名]**、および **[有効期限]** の値もメッセージごとに表示されます。フィールドは、ヘッダーをクリックして並べ替えることができます。見出しをもう一度クリックすると、逆の順序で並べ替えられます。 **[検疫]** ページには最大で 500 個のメッセージを表示できます。 
  
すべての検疫メッセージの一覧を表示するか、フィルタ条件を指定して特定のメッセージを検索することができます (500 以上のメッセージがある場合はフィルタリングによって結果セットを削減することが可能)。検疫されたメッセージを検索して特定したら、メッセージに関する詳細を表示できます。次のようにすることもできます。
  
- 1 人以上の受信者にメッセージを解放し、オプションとして、メッセージを偽陽性のメッセージ (迷惑メールではないメール) として Microsoft スパム分析チームに報告します。Microsoft スパム分析チームは、メッセージを評価し分析します。分析結果によっては、このメッセージが許可されるようにサービス全体のスパム コンテンツ フィルター ルールが調整されることがあります。
    
- メッセージを解放し、その送信者からの将来のメッセージをすべて許可します。
    
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「検疫」エントリを参照してください。 
    
- **[検疫]** ページでは、一度に複数のメッセージを解放または報告することができません。代わりに、このタスクを実行するリモート Windows PowerShell スクリプトを作成することができます。メッセージを検索する場合は [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) コマンドレットを使用し、それらを解放する場合は [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) コマンドレットを使用します。 
    
- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。
    
> [!TIP]
> 問題がある場合は、 Exchange のフォーラムで質問してください。 > 一般法人向け Office 365 の管理者の場合は、サポートに問い合わせることができます。 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>高度な検索を使用して検疫済みメッセージをフィルター処理して特定する
<a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a>

Exchange 管理センター (EAC) では、高度な検索を使用してさまざまな条件に基づいて検疫済みアイテムをフィルター処理することができます。これらの条件は、個別に使用することも、組み合わせて使用することもできます。検索によって、すべてのフィルター条件を満たすメッセージのリストが返されます。
  
1. EAC で、 **[保護]** \> **[検疫]** と移動し、 **[高度な検索]** をクリックします。
    
2. **[高度な検索]** ウィンドウで、次の条件の任意の組み合わせを選択します。各条件を有効にするには、関連するチェック ボックスをオンにします。ワイルドカードはサポートされていません。 
    
1. **[メッセージ ID]** このパラメーターは、特定のメッセージにターゲットを絞った検索を実行するために使用できます。たとえば、組織のユーザーが特定のメッセージを送信したか、組織のユーザーに向けて特定のメッセージを送信したものの、宛先に届かない場合は、メッセージの追跡機能を使用してメッセージを検索できます。詳細については、「 [メッセージの追跡を実行し、結果を表示する](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx)」をご覧ください。メッセージがルールと一致したりスパムとして識別されたために検疫に送信されたことが判明した場合は、メッセージ ID を指定して検疫内でそのメッセージを簡単に見つけることができます。完全なメッセージ ID 文字列を含める必要があります。メッセージ ID には、山かっこ (\<\>) が含まれる場合もあります。 
    
2. **[送信者のメール アドレス]** メッセージを送信した人物のメール アドレスを指定します。 
    
3. **[受信者のメール アドレス]** メッセージの意図した受信者の電子メール アドレスを指定します。 
    
4. **[件名]** メッセージの件名行のテキストを指定します。 
    
5. **[受信日時]** メッセージが検疫に到着したのが過去 24 時間以内 ( **[今日]**) か、過去 48 時間以内 ( **[過去 2 日間]**) か、過去 1 週間以内 ( **[過去 7 日間]**) かを選択したり、メッセージが検疫に到着した期間を指定することもできます。 
    
6. **[有効期限]** メッセージが検疫から削除されるのが今後 24 時間以内 ( **[今日]**) か、今後 48 時間以内 ( **[今後 2 日間]**) か、今後 1 週間以内 ( **[今後 7 日間]**) かを選択したり、メッセージが検疫から削除される期間を指定することもできます。
    
    > [!IMPORTANT]
    > 既定では、スパム検疫メッセージは15日間検疫に保持され、メールフロールールと一致した検疫メッセージは7日間検疫に保持されます。 この期間が経過したら、Office 365 はメッセージを削除し、メッセージは取得不能になります。 メールフロールールと一致した検疫済みメッセージの保持期間は構成できません。 ただし、スパム検疫メッセージの保持期間は、コンテンツ フィルター ポリシーの **[次の期間スパムを保持する (日)]** の設定によって短縮できます。 詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。 
  
7. **種類****スパム**として識別された検疫済みメッセージを検索するかどうか、またはメールフロールール (**トランスポートルール**) に一致したメッセージを検索するかどうかを指定できます。
    
3. 高度な検索の実行を開始するには、 **[OK]** をクリックします。 
    
    > [!NOTE]
    > 検索条件をクリアして、検疫内のすべてのメッセージを表示するには、 **[高度な検索]** ウィンドウ内のすべてのチェック ボックスをオフにして、 **[OK]** をクリックします。 
  
メッセージの検索後、指定した基準に一致する結果がユーザー インターフェイスに表示されます。EAC には、最大で 500 個のメッセージを表示できます。 
  
## <a name="view-details-about-a-specific-quarantined-message"></a>特定の検疫済みメッセージの詳細を表示する
<a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a>

**[検疫]** ページで検疫済みメッセージを特定した後、その詳細を表示することができます。 
  
1. **[検疫]** ページで特定のメッセージを選択すると、そのメッセージのプロパティの概要が画面右側の詳細ウィンドウに表示されます。 
    
    **[メッセージの状態]** の値は次のいずれかです。 
    
  - **種類**メッセージが**スパム**として識別されたかどうか、またはメールフロールール (**トランスポートルール**) に一致したかどうかを示します。
    
  - **[有効期限]** メッセージが検疫から削除される日付。 
    
    **[メッセージの詳細]** の値は次のいずれかです。 
    
  - **[送信者]** メッセージの送信者の電子メール アドレス。 
    
  - **[件名]** メッセージの件名のテキスト。 
    
  - **[受信日時]** 検疫でメッセージが受信された日付。 
    
  - **[サイズ]** キロバイト (KB) 単位のメッセージのサイズ。メッセージ サイズが 999 KB より大きい場合はメガバイト (MB) 単位。 
    
  - **[メッセージ ヘッダーの表示]** このリンクをクリックすると **[メッセージ ヘッダー]** ダイアログ ボックスが開かれ、メッセージ ヘッダー テキストが表示可能されます。メッセージ ヘッダー テキストをクリップボードにコピーして [メッセージ ヘッダー アナライザー](https://testconnectivity.microsoft.com/?tabid=mha)に貼り付けることもできます。メッセージ ヘッダー アナライザー ツールに貼り付ければ、 **[ヘッダーの分析]** をクリックしてヘッダーに関する情報を取得できます。 
    
    > [!TIP]
    > サービスによって挿入される特定のスパム対策メッセージ ヘッダー フィールドの詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。 
  
  - **[メール メッセージのプレビュー]** このリンクをクリックして、メッセージのテキストを確認します。 
    
2. 検疫済みメッセージをダブルクリックすると、 **[検疫済みメッセージ]** ウィンドウが開き、次の情報が表示されます。 
    
  - **[解放されました]** メッセージが解放されたすべてのメール アドレス (存在する場合) の一覧。 
    
  - **まだ解放されていません** メッセージが解放されていないすべての電子メール アドレス (存在する場合) の一覧。メッセージを解放するには、 **[解放する]** リンクをクリックします。メッセージの解放に関する詳細については、次のセクションを参照してください。 
    
  - **[メッセージ ID]** メッセージのヘッダーに表示されるインターネット メッセージ ID (クライアント ID とも呼ばれる)。 
    
    **[閉じる]** をクリックしてメインの検疫ウィンドウに戻ります。 
    
## <a name="release-messages-from-quarantine"></a>メッセージの検疫からの解放
<a name="sectionSection3"> </a>

受信者宛てのメッセージを解放する場合のオプションは、次のとおりです。
  
- [検疫済みメッセージを解放し、この送信者からの将来のメッセージを許可する](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [検疫済みメッセージを誤検知として報告せずに特定の受信者に解放する](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [1 つ以上の検疫済みメッセージをすべての受信者に解放する](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [Release one or more quarantined messages to all recipients and report false positives](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>検疫済みメッセージを解放し、この送信者からの将来のメッセージを許可する
<a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a>

1. EAC で、 **[保護]** \> **[検疫]** に移動します。
    
2. メッセージをクリックして選択し、次のスクリーン ショットに示される **[メッセージの解放]** アイコンをクリックします。 
  
![[メッセージの解放] アイコンが強調表示され、解放オプションが示されている検疫ページを表示しています](media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
**[選択したメッセージを解放し、送信者を許可します]** をドロップダウン リストからクリックします。 
    
3. **[メッセージを解放し、送信者を許可する]** ダイアログ ボックスが開きます。 オプションで、メッセージを Microsoft に報告することを選択し、その後、 **[解放して許可する]** をクリックすることもできます。 メッセージは、アドレス指定されるすべての受信者に解放され、この送信者からの将来のメッセージはすべて許可されます。 ただし、このメッセージがメールフロールールまたはブロックされる送信者によって検疫された場合、今後のメッセージの送信者は引き続きブロックされます。 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>検疫済みメッセージを誤検知として報告せずに特定の受信者に解放する
<a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a>

1. EAC で、 **[保護]** \> **[検疫]** に移動します。
    
2. メッセージを選択し、 **[メッセージの解放]** アイコンをクリックして、ドロップダウン リストから **[特定の受信者にメッセージを解放します]** をクリックします 
    
3. **[メッセージの解放]** ダイアログ ボックスで、次のオプションのいずれかを選択します。 
    
  - **すべての受信者にメッセージを解放する** このオプションを選択する場合、同じ受信者に 2 回以上メッセージを解放することはできないので注意してください。受信者が既にメッセージを受け取っていた場合、メッセージがその受信者にもう一度解放されることはありません。 
    
  - **特定の受信者にメッセージを解放する** メッセージを解放できる受信者を選択します。メッセージは各受信者に 1 回しか解放できないため、解放先とすることができるユーザーのみがこの一覧に表示されます。複数選択がサポートされています。受信者を選択し、 **[追加]** をクリックします。
    
4. **[解放]** をクリックします。 
    
**[最新の情報に更新]**![[最新の情報に更新] アイコン](media/ITPro-EAC-RefreshIcon.gif) アイコンをクリックしてデータを更新してから、メッセージをダブルクリックすると、それが目的の受信者に解放されていることが示されます。 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>1 つ以上の検疫済みメッセージをすべての受信者に解放する
<a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a>

1. EAC で、 **[保護]** \> **[検疫]** に移動します。
    
2. メッセージをクリックして選択するか、SHIFT キーを使用して複数のメッセージを選択します。 **[メッセージの解放]** アイコンをクリックします。 
    
3. **[選択したメッセージをすべての受信者に解放します]** をドロップダウン リストからクリックします。 
    
4. 警告ダイアログ ボックスが開きます。警告を読み、次に進む場合は **[はい]** を選択します。このオプションを選択する場合、同じ受信者に 2 回以上メッセージを解放することはできないので注意してください。受信者が既にメッセージを受け取っていた場合、メッセージがその受信者にもう一度解放されることはありません。 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>すべての受信者に 1 つ以上の検疫済みメッセージを解放し、誤検知として報告する
<a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a>

1. EAC で、 **[保護]** \> **[検疫]** に移動します。
    
2. メッセージをクリックして選択するか、SHIFT キーを使用して複数のメッセージを選択します。 **[メッセージの解放]** アイコンをクリックします。 
    
3. **[選択したメッセージを解放し、誤検知として報告します]** をドロップダウン リストからクリックします。 
    
4. 警告ダイアログ ボックスが開きます。警告を読み、次に進む場合は **[はい]** を選択します。このオプションを選択する場合、同じ受信者に 2 回以上メッセージを解放することはできないので注意してください。受信者が既にメッセージを受け取っていた場合、メッセージがその受信者にもう一度解放されることはありません。 
    
     このオプションを選択する場合、そのメッセージをまだ受信していないすべての受信者にメッセージが解放されます。スパム検疫済みメッセージの場合は、メッセージの評価と分析を行う Microsoft スパム分析チームに報告されます。分析結果によっては、このメッセージが許可されるようにサービス全体のスパム コンテンツ フィルター ルールが調整されることがあります。 
    
> [!TIP]
> 「[メッセージがスパムとしてマークされないようにする方法](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)」の手順に従って、メッセージがスパムとしてマークされないようにします。 
  
**[最新の情報に更新]**![[最新の情報に更新] アイコン](media/ITPro-EAC-RefreshIcon.gif) アイコンをクリックしてデータを更新してから、メッセージをダブルクリックすると、それが目的の受信者に解放されていることが示されます。 
  
## <a name="for-more-information"></a>関連情報
<a name="sectionSection4"> </a>

[検疫に関する FAQ](quarantine-faq.md)
  

