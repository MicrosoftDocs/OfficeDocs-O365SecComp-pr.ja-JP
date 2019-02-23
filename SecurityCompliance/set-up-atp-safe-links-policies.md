---
title: Office 365 の ATP の安全なリンクポリシーを設定する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection: M365-security-compliance
description: 安全なリンクポリシーを設定して、Word、Excel、PowerPoint、および Visio ファイル内の悪意のあるリンクや、電子メールメッセージだけで組織を保護します。
ms.openlocfilehash: db7da9d6ce2d2f2503585c0cde89f2b2626e2afa
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220167"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Office 365 の ATP の安全なリンクポリシーを設定する

> [!IMPORTANT]
> この記事は、ビジネスのお客様を対象としています。Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

[atp の安全なリンク](atp-safe-links.md)は、 [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) の機能で、フィッシングやその他の攻撃で使用されている悪意のあるリンクから組織を保護するのに役立ちます。[Office 365 セキュリティ&amp;コンプライアンスセンターに必要なアクセス許可](permissions-in-the-security-and-compliance-center.md)がある場合は、ユーザーが web アドレス (url) をクリックしたときに組織が保護されるようにするために、ATP の安全なリンクポリシーを設定することができます。ATP の安全なリンクポリシーを構成して、Office ドキュメント内の電子メールと url の url をスキャンできます。
  
[新機能は ATP に継続的に追加](office-365-atp.md#new-features-in-office-365-atp)されています。新機能が追加されたときに、既存の ATP の安全なリンクポリシーを調整する必要がある場合があります。

## <a name="what-to-do"></a>行うこと 
  
1. [前提条件を確認](#review-the-prerequisites)します。
    
2. [すべてのユーザーに適用される既定の ATP の安全なリンクポリシーを確認して編集](#define-an-atp-safe-links-policy-that-applies-to-everyone)します。たとえば、 [ATP の安全なリンクに対し](set-up-a-custom-blocked-urls-list-wtih-atp.md)て、カスタムのブロックされた url リストを設定できます。
    
3. [特定の電子メール受信者のポリシーを追加または編集](#add-a-policy-for-specific-email-recipients)します。これには、 [ATP の安全なリンクのためのカスタムの "リライト not リライト" url リストの設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)が含まれます。
    
4. [ATP の安全なリンクポリシーのオプションについて説明](#learn-about-atp-safe-links-policy-options)します。(この記事では、最近の変更の設定を含む)。
    
## <a name="step-1-review-the-prerequisites"></a>手順 1: 前提条件を確認する

- 組織に[Office 365 Advanced Threat Protection](office-365-atp.md)があることを確認します。
    
- 必要なアクセス許可を持っていることを確認してください。ATP ポリシーを定義 (または編集) するには、適切な役割が割り当てられている必要があります。次の表では、いくつかの例について説明します。 <br>

    |役割  |場所/割り当て方法  |
    |---------|---------|
    |Office 365 グローバル管理者 |Office 365 の購入にサインアップするユーザーは、既定ではグローバル管理者です。(詳細については、「 [Office 365 管理者の役割につい](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください)。         |
    |セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online 組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  powershell コマンドレット (「 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) |

    役割とアクセス許可の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

- office クライアントが[先進認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用するように構成されていることを確認します (これは、office ドキュメントの ATP の安全なリンク保護に対して行われます)。
    
- [ATP の安全なリンクポリシーのオプションについて説明](#learn-about-atp-safe-links-policy-options)します。(この記事の内容)。 

- 新規または更新されたポリシーがすべての Office 365 データセンターに蔓延するのに最大30分かかります。
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>手順 2: すべてのユーザーに適用される ATP の安全なリンクポリシーを定義 (または確認) します。

[Office 365 Advanced Threat Protection](office-365-atp.md)を使用している場合は、組織内のすべてのユーザーに適用される既定の ATP 安全なリンクポリシーがあります。必ず確認してください。必要に応じて、既定のポリシーを編集します。
  
1. に[https://protection.office.com](https://protection.office.com)移動して、職場または学校のアカウントでサインインします。 
    
2. 左側のナビゲーションで、[**脅威の管理**] の下にある [ ** \>ポリシー** **セーフリンク**] を選択します。
    
3. [**組織全体に適用されるポリシー** ] セクションで、[**既定**] を選択し、[**編集**] を選択します (このボタンは鉛筆に似ています)。<br/>![[編集] をクリックして、安全なリンクの保護のための既定のポリシーを編集します。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. [**次の url をブロック**する] セクションで、組織内のユーザーが閲覧できないようにする1つ以上の url を指定します。(「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-wtih-atp.md)」を参照してください)。
    
5. [**電子メール以外のコンテンツに適用する設定**] セクションで、使用するオプションを選択 (またはクリア) します。(すべてのオプションを選択することをお勧めします)。 
    
6. [**保存**] を選択します。
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>手順 3: 特定の電子メール受信者に適用される ATP の安全なリンクポリシーを追加 (または編集) します。

すべてのユーザーに適用される既定の ATP の安全なリンクポリシーを確認 (または編集) した後、次の手順として、特定の受信者に適用する追加のポリシーを定義します。たとえば、追加のポリシーを定義することによって、既定のポリシーに対する例外を指定できます。 
  
1. に[https://protection.office.com](https://protection.office.com)移動して、職場または学校のアカウントでサインインします。 
    
2. 左側のナビゲーションで、[**脅威の管理**] の下にある [**ポリシー**] を選択します。
    
3. [**安全なリンク**] を選択します。
    
4. [**特定の受信者に適用されるポリシー** ] セクションで、[**新規**] を選択します**+**(新しいボタンは、プラス記号 () に似ています)。<br/>![[新規] を選択して、特定の電子メール受信者の安全なリンクポリシーを追加します。](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. ポリシーの名前、説明、設定を指定します。<br/>**例:**"直接クリックしない" というポリシーを設定するには、組織内の特定のグループのユーザーが、ATP の安全なリンク保護を行わずに特定の web サイトをクリックすることを許可しないようにします。次の推奨設定を指定することができます。 
    
  - [**名前**] ボックスに「直接クリックしない」と入力します。
    
  - [**説明**] ボックスに、次のような説明を入力します。特定のグループのユーザーが、ATP の安全なリンク確認を行わずに web サイトをクリックするのを防ぐことができます。
    
  - **[アクションの選択**] セクションで、[**オン**] を選択します。
    
  - [**安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする**] を選択します。
    
  - このオプションが使用可能な場合は、[**組織内で送信されたメッセージに対して安全なリンクを適用する**] を選択します。
    
  - [**ユーザーが元の URL に**移動できないようにする] を選択します。
    
  - (オプション)[**次の url を書き換えない**] セクションで、組織に対して安全と見なされる1つ以上の url を指定します。(「 [ATP Safe Links を使用して、ユーザー設定の "書き込み不可" url リストを設定する](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)」を参照してください)
    
  - [**適用先**] セクションで、[**受信者が次のメンバー**である] を選択し、ポリシーに含めるグループを選択します。[**追加**] を選択し、[ **OK]** を選択します。
    
6. [**保存**] を選択します。
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>手順 4: ATP の安全なリンクポリシーのオプションについて学習する

ATP の安全なリンクポリシーを設定または編集すると、いくつかのオプションが表示されます。これらのオプションがどのようなものかがわからない場合は、次の表で各オプションとその影響について説明します。次の2種類の ATP 安全なリンクポリシーを定義または編集することに注意してください。
- すべてのユーザーに適用される[既定のポリシー](#default-policy-options) 
- [特定の受信者に対して定義](#policies-that-apply-to-specific-email-recipients)されているその他のポリシー 

### <a name="default-policy-options"></a>既定のポリシーオプション

既定のポリシーオプションは、組織内のすべてのユーザーに適用されます。

|このオプション  |機能  |
|---------|---------|
| **次の url をブロックする** <br/>    | 自動でブロックされる url のカスタムリストを組織で使用できるようにします。ユーザーがこのリストの url をクリックすると、url がブロックされる理由を説明する[警告ページ](atp-safe-links-warning-pages.md)が表示されます。<br/> 詳細については、「ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする」を参照してください。      |
| **office 365 ProPlus、iOS 版 office および Android** <br/>    | このオプションが選択されている場合、office 365 ProPlus (word、Excel、および PowerPoint on Windows または Mac OS) で開いているドキュメント内の url、iOS 上の office ドキュメント、または Android デバイス、Visio 2016 on windows、および Office Online (wordユーザーが Office 365 にサインインしている場合は、オンライン、PowerPoint online、Excel online、および OneNote online)。 <br/><br/>**Windows で office 2016**のみが表示されている場合は、機能更新プログラムがまだ office 365 環境に達していません (および近日中に公開されています)。それまでは、ATP の安全なリンク保護は Word 2016、Excel 2016、PowerPoint 2016、または Windows で実行されている Visio 2016 に適用されます。            |
| **ユーザーが ATP の安全なリンクをクリックしたときに追跡しない** <br/>  | このオプションが選択されている場合は、Word、Excel、PowerPoint、および Visio のドキュメントで、[データの url] をクリックしても保存されません。  <br/> |
|**ユーザーが元の URL に対して ATP の安全なリンクをクリックできないようにします。** <br/> |このオプションが選択されている場合、ユーザーは、悪意があると判断された URL に[警告ページ](atp-safe-links-warning-pages.md)をスキップすることはできません。  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>特定の電子メールの受信者に適用されるポリシー

|このオプション  |機能  |
|---------|---------|
|**Off** <br/> |電子メールメッセージ内の url はスキャンされません。  <br/> 特定の受信者グループの電子メールメッセージ内の url をスキャンしないルールなどの例外ルールを定義できます。  <br/> |
|**オン** <br/> |ユーザーが電子メールメッセージ内の url をクリックしたときに、ユーザーが ATP の安全なリンク保護を介してユーザーをルーティングするように url を書き換えます。  <br/> 禁止または悪意のある url の一覧に対してクリックしたときに URL をチェックします。  <br/> |
|**安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする** <br/> |このオプションを選択すると、ダウンロード可能なコンテンツをポイントする url がスキャンされます。  <br/> |
|**組織内で送信されるメッセージに安全なリンクを適用する** <br/> | このオプションを選択して選択すると、電子メールアカウントが Office 365 でホストされている場合に、組織内のユーザー間で送信される電子メールメッセージに対して ATP の安全なリンク保護が適用されます。  <br/> |
|**ユーザーのクリックを追跡しない** <br/> |このオプションが選択されている場合は、[外部送信者からの電子メール] の [データ] をクリックします。URL [組織内で送信された電子メールメッセージ内のリンクの追跡] [現在サポートされていません]。  <br/> |
|**ユーザーが元の URL にクリックできないようにする** <br/> |このオプションが選択されている場合、ユーザーは、悪意があると判断された URL に[警告ページ](atp-safe-links-warning-pages.md)をスキップすることはできません。  <br/> |
|**次の url を書き換えないでください。** <br/> |url をそのまま残します。組織内の特定の電子メール受信者グループに対して、スキャンを必要としない安全な url のカスタムリストを保持します。 追加の詳細については、「 [ATP Safe Links を使用してカスタムの url リストを設定する](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)」を参照してください\*。これには、ワイルドカードのアスタリスク () のサポートに関する最新の変更が含まれています。<br/> |
   
## <a name="next-steps"></a>次の手順

atp の安全なリンクポリシーを設定すると、レポートを表示することにより、atp が自分の組織でどのように動作しているかを確認できます。詳細については、以下のリソースを参照してください。

- [Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)

- [セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する](use-explorer-in-security-and-compliance.md)

ATP に関する新機能を常に活用してください。[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)にアクセスし、 [ATP に追加](office-365-atp.md#new-features-in-office-365-atp)されている新機能について説明します。