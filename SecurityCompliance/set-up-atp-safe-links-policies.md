---
title: Office 365 の ATP の安全なリンクのポリシーを設定します
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: Word、Excel、PowerPoint、および Visio のファイルおよび電子メール メッセージ内の悪意のあるリンクから組織を保護するために、安全なリンクのポリシーを設定します。
ms.openlocfilehash: 9110fce9a6eb53832707de6235b79100e10c9b8a
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454334"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Office 365 の ATP の安全なリンクのポリシーを設定します

[ATP の安全なリンク](atp-safe-links.md)、 [Office 365 の高度な脅威保護](office-365-atp.md)(ATP) の機能は、フィッシングやその他の攻撃で使用される、悪意のあるリンクから組織を保護するために役立ちます。必要がある場合[Office 365 のセキュリティに割り当てられたアクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)ATP の安全なリンク ポリシーをセットアップするには、web アドレス (Url) をクリックすることを確認のために、組織を保護します。メール内の Url、および Office ドキュメント内の Url をスキャンするのには、ATP の安全なリンク ポリシーを構成できます。
  
[ATP の安全なリンクに新しい機能が随時追加](atp-safe-links.md#new-features-are-continually-being-added-to-atp-safe-links)されます。新機能が追加されるは、既存の分析ツールの安全なリンク ポリシーを調整する必要があります。

## <a name="what-to-do"></a>行うこと 
  
1. [前提条件を確認](#review-the-prerequisites)します。
    
2. [レビューしすべてのユーザーに適用される分析ツールの安全なリンクの既定のポリシーを編集](#define-an-atp-safe-links-policy-that-applies-to-everyone)します。たとえば、 [ATP の安全なリンクのカスタム ブロックされた Url リストを設定](set-up-a-custom-blocked-urls-list-wtih-atp.md)できます。
    
3. [特定の電子メールの受信者ポリシーを追加または編集](#add-a-policy-for-specific-email-recipients)を含む[ATP の安全なリンクのカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)します。
    
4. [ATP の安全なリンク ポリシーのオプションについて理解します。](#learn-about-atp-safe-links-policy-options)(ここでは)、最近の変更の設定を含む
    
## <a name="step-1-review-the-prerequisites"></a>手順 1: 前提条件を確認します。

- 組織が[Office 365 の高度な脅威保護](office-365-atp.md)を持っていることを確認します。
    
- ATP のポリシーを編集または定義するために必要な権限があることを確認します。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。
    
- [ATP の安全なリンク ポリシーのオプションについて理解します。](#learn-about-atp-safe-links-policy-options)(この記事で)。 

- [現代の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用する Office のクライアントが構成されていることを確認します。
    
- 最大 30 分間のすべての Office 365 のデータ センターに展開するのには、新規または更新されたポリシーを使用できます。
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>手順 2: 定義 (または確認) すべてのユーザーに適用される分析ツールの安全なリンク ポリシー

脅威保護の高度な Office 365 の企業である場合は、組織内の全員に適用される既定の ATP の安全なリンク ポリシーするがあります。 
  
1. [https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。 
    
2. **脅威の管理**の下で、左側のナビゲーションでは、選択**ポリシー \> ** **安全なリンク**です。
    
3. **組織全体に適用されるポリシー** ] セクションで **[既定**] を選択しの**編集**([編集] ボタンのような鉛筆) します。 
    
    ![安全なリンクの保護のため、既定のポリシーを編集するのにはの編集] をクリックします。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. **次の Url をブロックする**] セクションでは、訪問から、組織内のユーザーを禁止する 1 つまたは複数の Url を指定します。( [ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください)。
    
5. **電子メール以外のコンテンツに適用される設定**をオンまたはオフ) に使用するオプションです。(お勧めのすべてのオプションを選択します。 
    
6. [ **保存**] を選択します。
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>手順 3: 追加 (または編集) 特定の電子メールの受信者に適用される ATP の安全なリンク ポリシー

ATP の安全なリンクのポリシーのすべてのユーザーを確認した後は、電子メールの受信者の特定のグループの追加のポリシーを定義することを検討します。これにより、既定のポリシーに対する例外を指定することができます。 
  
1. [https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。 
    
2. **脅威の管理**の下で、左側のナビゲーションでは、**ポリシー**を選択します。
    
3. **安全なリンク**を選択します。
    
4. **特定の受信者に適用されるポリシー** ] セクションで [**新規**] をクリックして ([新規] ボタンのようなプラス記号 ( **+**))。<br/>![特定の電子メールの受信者の安全なリンク ポリシーを追加するのには新規を選択します。](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. ポリシーの名前、説明、設定を指定します。<br/>**の使用例:** ない直接クリックでと呼ばれる順番にクリックして特定の web サイト分析ツールの安全なリンクの保護なしに、組織内の特定のグループにユーザーを許可しないポリシーを設定するに可能性がありますを指定する次の設定を推奨します。 
    
  - [**名**] ボックスで、型を直接クリックします。
    
  - [**説明**] ボックスで、人々 のように、しませんから、ATP の安全なリンクの確認を行わず、web サイトにアクセス] をクリックして特定のグループの説明を入力します。
    
  - [**アクションを選択**] セクション**を**クリックします。
    
  - **使用の安全な添付ファイル**を選択します。
    
  - このオプションが利用可能な場合は、**組織内で送信されるメッセージに適用の安全なリンク**を選択します。
    
  - **元の URL を使用] をクリックするユーザーを許可しない**を選択します。
    
  - (省略可能です)**次の Url の書き換えは**、組織の安全であると見なされる 1 つまたは複数の Url を指定します。( [ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください)
    
  - [**適用先**] セクションでは、**受信者のメンバーである**を選択し、ポリシーに追加するグループを選択し、します。**追加**を選択し、[ **ok]** をクリックします。
    
6. [ **保存**] を選択します。
    
## <a name="step-5-learn-about-atp-safe-links-policy-options"></a>ATP の安全なリンク ポリシーのオプションについて、手順 5。

設定する、ATP の安全なリンク ポリシーを編集するか、利用可能ないくつかのオプションが表示されます。参考までにこれらのオプションとは、次の表は各 1 つとその影響について説明します。 

定義または編集するポリシーの 2 つのメイン種類があります: すべてのユーザーに適用される既定のポリシーおよび特定の受信者に対して定義されているポリシーを追加します。ものについては、次の表に、**このポリシーの**列で区別されます。
  
|**このポリシーの**|**このオプション**|**機能**|
|:-----|:-----|:-----|
|既定値 (定義されると、既定のポリシーが適用されます、組織内の全員に)  <br/> |**次の Url をブロックします。** <br/> |自動的にブロックされている Url のカスタム リストを所有する組織を有効にします。ユーザーは、この一覧に URL をクリックするときは、URL がブロックされている理由を説明する[警告] ページ](atp-safe-links-warning-pages.md)に移動します。<br/> 最大 3 つのワイルドカードのアスタリスクを新たに追加されたサポートの詳細については[ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください (\*)。  <br/> |
|既定値  <br/> |**Office 365 ProPlus、オフィスの iOS および Android** <br/> |このオプションを選択すると、ATP の安全なリンクはドキュメントの Url に保護が適用される文書を開く Office 365 用リソース (Word、Excel、および PowerPoint では、Windows または Mac OS) の Office、iOS または Android デバイス、ウィンドウ、および Office オンライン (Word で Visio 2016オンライン、PowerPoint のオンライン、オンラインの Excel で、OneNote オンライン) は、Office 365 にサインインしたユーザーを提供します。 <br/><br/>**Windows で Office 2016**のみが表示された場合、機能の更新に達していない、Office 365 環境まだ (および準備中)。それまでは、Word 2016、2016 の Excel、PowerPoint 2016 または Windows で実行されている Visio 2016 ATP の安全なリンクの保護が適用されます。           |
|既定値  <br/> |**ユーザーは、ATP の安全なリンクをクリックしたときに記録しません。** <br/> |このオプションを選択すると、Word、Excel、PowerPoint、および Visio のドキュメント内の Url が格納されていないために、データをクリックします。  <br/> |
|既定値  <br/> |**ユーザーが元の URL への ATP の安全なリンクをクリックしてできないように** <br/> |このオプションを選択すると、ユーザーは、悪意があると決定される URL に過去の[警告] ページ](atp-safe-links-warning-pages.md)の続行できません。  <br/> |
|特定の電子メールの受信者用に作成されたポリシー  <br/> |**Off** <br/> |電子メール メッセージ内の Url をスキャンしません。  <br/> 使用すると、特定の受信者グループに電子メール メッセージで Url をスキャンしないルールなど、例外の規則を定義できます。  <br/> |
|特定の電子メールの受信者用に作成されたポリシー  <br/> |**上** <br/> |ユーザーが電子メール メッセージで Url をクリックすると、ATP の安全なリンクの保護を使用してルート ユーザーに Url をリライトします。  <br/> ブロックまたは悪意のある Url の一覧をクリックすると URL をチェックします。  <br/> |
|特定の電子メールの受信者用に作成されたポリシー  <br/> |**安全な添付ファイルを使用して、ダウンロード可能なコンテンツをスキャンするには** <br/> |このオプションを選択すると、ダウンロード可能なコンテンツをポイントする Url がスキャンされます。  <br/> |
|特定の電子メールの受信者用に作成されたポリシー  <br/> |**安全なリンクを組織内で送信されたメッセージに適用します。** <br/> | このオプションが使用可能であり、選択した場合、ATP の安全なリンクの保護は、電子メール アカウントを提供する、組織内のユーザー間で送信されるメッセージは、Office 365 でホストされる電子メールに適用されます。  <br/> |
|特定の電子メールの受信者用に作成されたポリシー  <br/> |**ユーザーのクリックを追跡しません。** <br/> |このオプションを選択すると、外部の送信者からの電子メール内の Url が格納されていないために、データをクリックします。URL は、組織内で送信された電子メール メッセージ内のリンクの追跡] をクリックします。 は現在サポートされていません。  <br/> |
|特定の電子メールの受信者用に作成されたポリシー  <br/> |**ユーザーが元の URL を使用] をクリックしてできないようにします。** <br/> |このオプションを選択すると、ユーザーは、悪意があると決定される URL に過去の[警告] ページ](atp-safe-links-warning-pages.md)の続行できません。  <br/> |
|特定の電子メールの受信者用に作成されたポリシー  <br/> |**次の Url の書き換えを行う** <br/> |Url のままです。電子メールの受信者、組織内の特定のグループのスキャンの必要がない安全な Url のカスタム一覧を保持します。 詳細については、アスタリスクのワイルドカードをサポートするために最新の変更を含む[ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください (\*)。<br/> |
   
## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Office 365 で ATP の安全なリンク](atp-safe-links.md)
  
[ATP の安全な添付ファイルを Office 365 で](atp-safe-attachments.md)
  
[ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。](set-up-a-custom-blocked-urls-list-wtih-atp.md)
  
[ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定します。](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
  
[脅威の高度な保護のためのレポートを表示します。](view-reports-for-atp.md)

[Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)
  

