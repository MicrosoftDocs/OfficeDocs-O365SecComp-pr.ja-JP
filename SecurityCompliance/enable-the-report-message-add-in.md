---
title: レポート メッセージ アドインを有効にする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/05/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 個々のユーザーまたは組織全体で、outlook および outlook on the web 用のレポートメッセージアドインを有効にする方法について説明します。
ms.openlocfilehash: f2bb79c4c613fdb804d19226fb359124387a678f
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693386"
---
# <a name="enable-the-report-message-add-in"></a>レポート メッセージ アドインを有効にする

> [!NOTE]
> outlook および outlook on the web 用のレポートメッセージアドインは、 [outlook 迷惑メールフィルター](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)とまったく同じではありませんが、両方を使用して、電子メールを迷惑メール、迷惑メールではないメールとしてマークしたり、フィッシングを試行したりすることができます。 違いは、outlook 用のレポートメッセージアドインと web 上の outlook は、分類された電子メールの誤通知を Microsoft に通知するのに対して、outlook の迷惑メールフィルターを使用してユーザーのメールボックス内の電子メールメッセージを整理しています。 

## <a name="overview"></a>概要

outlook 用のレポートメッセージアドインと web 上の outlook を使用すると、ユーザーは、安全であるか悪意のある電子メールであっても、分析のために Microsoft と関連会社に対して、誤った分類されたメールを簡単に報告できます。 Microsoft では、これらの送信を使用して、電子メール保護テクノロジの有効性を向上させています。 さらに、組織で[Office 365 Advanced Threat Protection プラン 1](office-365-atp.md)または[Plan 2](office-365-ti.md)を使用している場合は、レポートメッセージアドインにより、組織のセキュリティチームに対して、セキュリティポリシーの確認と更新に使用できる有用な情報が提供されます。 

たとえば、ユーザーが大量のメッセージをフィッシングとして報告しているとします。 この情報は、[セキュリティダッシュボード](security-dashboard.md)やその他のレポートに表示されます。 組織のセキュリティチームは、この情報を、フィッシング対策ポリシーの更新が必要になる可能性があることを示すものとして使用できます。 または、レポートメッセージアドインを使用して迷惑メールではないというフラグが付いたメッセージを多数報告している場合は、組織のセキュリティチームが[スパム対策ポリシー](configure-the-anti-spam-policies.md)を調整する必要があります。 

レポートメッセージアドインは、Office 365 サブスクリプションと、次の製品で機能します。
 - Outlook on the web
 - Outlook 2013 SP1
 - Outlook 2016
 - Outlook 2016 for Mac
 - Office 365 ProPlus に含まれている Outlook

既存の web ブラウザーでは、レポートメッセージアドインが動作するように十分である必要があります。ただし、アドインが使用できない、または正常に動作しないことが判明した場合は、別のブラウザーを試してみてください。
  
個人ユーザーの場合は、[レポートメッセージアドインを自分自身に対して有効に](#get-the-report-message-add-in-for-yourself)することができます。 
  
Office 365 の全体管理者または exchange Online 管理者であり、exchange が OAuth 認証を使用するように構成されている場合は、[組織に対してレポートメッセージアドインを有効](#get-and-enable-the-report-message-add-in-for-your-organization)にすることができます。 これで、レポートメッセージアドインが[一元展開](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)によって利用可能になりました。
    
## <a name="get-the-report-message-add-in-for-yourself"></a>自分用のレポートメッセージアドインを取得する

1. [Microsoft appsource](https://appsource.microsoft.com/marketplace/apps)で、[レポートメッセージアドイン](https://appsource.microsoft.com/product/office/wa104381180)を検索します。
    
2. [**今すぐ取得**] を選択します。<br/>![レポートメッセージ-今すぐ取得](media/ReportMessageGETITNOW.png)<br/> 
    
3. 使用条件とプライバシーポリシーを確認します。 [ **Continue**] を選びます。 
    
4. 職場または学校アカウントを使用して Office 365 にサインインします (一般法人向け)。または Microsoft アカウント (個人使用)。
    
アドインがインストールされて有効になると、次のアイコンが表示されます。 

- Outlook のアイコンは、次のように表示されます。 <br/> ![Outlook のレポートメッセージアドインアイコン](media/OutlookReportMessageIcon.png)<br/>
- web 上の outlook (旧称 outlook web App) では、アイコンは次のようになります。<br/>![Outlook on the web レポートメッセージアドインアイコン](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> 次の手順として、[レポートメッセージアドインの使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)方法について説明します。
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>組織のレポートメッセージアドインを取得して有効にする

> [!IMPORTANT]
> このタスクを完了するには、Office 365 の全体管理者または Exchange Online 管理者である必要があります。 また、詳細については、OAuth 認証を使用するように exchange を構成する必要があります。詳細については、「 [exchange の要件 (アドインの一元展開)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)」を参照してください。 

1. Microsoft 365 管理センターの [[サービス & アドイン] ページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に移動します。<br/>![新しい Microsoft 365 管理センターの [サービスとアドイン] ページ](media/ServicesAddInsPageNewM365AdminCenter.png)<br/> 
    
2. [ **+ アドインの展開**] を選択します。<br/>![[アドインの展開] を選択する](media/ServicesAddIns-ChooseDeployAddIn.png)<br/> 
    
3. [**新しいアドイン**] 画面で情報を確認し、[**次へ**] を選択します。<br/>![新しいアドインの詳細](media/NewAddInScreen1.png)<br/>
    
4. [ **Office ストアからアドインを追加**する] を選択し、[**次へ**] を選択します。<br/>![新しいアドインを追加する](media/NewAddInScreen2.png)<br/> 
    
5. **レポートメッセージ**を検索し、結果の一覧で、[**レポートメッセージアドイン**] の横にある [**追加**] を選択します。<br/>![レポートメッセージを検索し、[追加] を選択します。](media/NewAddInScreen3.png)<br/>
    
6. [**レポートメッセージ**] 画面で情報を確認し、[**次へ**] を選択します。<br/>![レポートメッセージの詳細](media/ReportMessageAdd-InNewScreen4.png)<br/>

7. Outlook のユーザーの既定の設定を指定し、[**次へ**] をクリックします。<br/>![Outlook の既定のレポートメッセージ設定](media/ReportMessageOptionsScreen5.png)<br/>

8. レポートメッセージアドインを取得するユーザーを指定し、[**保存**] を選択します。 <br/>![レポートメッセージアドインを取得するユーザー](media/ReportMessageOptionsScreen6.png)<br/>

> [!TIP]
> [ユーザーによって報告された電子メールメッセージのコピーを取得するルールを設定することを](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)お勧めします。

アドインのセットアップ時に選択した内容に応じて (上記の手順 7-8)、組織内のユーザーが[レポートメッセージアドイン](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を使用できるようになります。 組織内のユーザーには、次のアイコンが表示されます。 

- Outlook のアイコンは、次のように表示されます。 <br/> ![Outlook のレポートメッセージアドインアイコン](media/OutlookReportMessageIcon.png)<br/>
- web 上の Outlook では、アイコンは次のようになります。<br/>![Outlook on the Web レポートメッセージアドインアイコン](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> レポートメッセージアドインについてユーザーに通知する場合は、[レポートメッセージアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)するためのリンクを含めます。

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>ユーザーによって報告された電子メールメッセージのコピーを取得するルールを設定する

> [!IMPORTANT]
> このタスクを実行するには、Exchange Online の管理者である必要があります。
  
組織内のユーザーによって報告された電子メールメッセージのコピーを取得するルールを設定できます。 この操作は、組織でレポートメッセージアドインをダウンロードして有効にした後に行います。
  
1. Exchange 管理センターで、[**メールフロー** \> **ルール**] を選択します。 
    
2. [ **+** \> **新しいルールを作成する**] を選択します。 
    
3. [**名前**] ボックスに、「送信」などの名前を入力します。
    
4. [**このルールを適用する条件**] ボックスの一覧で、[**受信者のアドレス**を選択してください...] を選択します。 
    
5. [**単語または語句の指定**] 画面`junk@office365.microsoft.com`で`phish@office365.microsoft.com`、とを追加し、[ **OK]** を選択します。<br/>![ルールの迷惑メールアドレスとフィッシングメールアドレスを指定する](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)<br/>
  
6. [**実行する処理...** ] の一覧で、[**メッセージの Bcc**] を選択します。 
    
7. ユーザーが Microsoft に報告する各電子メールメッセージのコピーを受信する必要のある全体管理者、セキュリティ管理者、およびセキュリティ閲覧者を追加し、[ **OK]** を選択します。<br/>![グローバルまたはセキュリティ管理者を追加して、報告された各メッセージのコピーを受信する](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)<br/>
  
8. [**このルールを次の重大度レベルで監査**する] を選択し、[**中**] を選択します。 
    
9. [**このルールのモードの選択**] で、[**強制**] を選択します。<br/>![レポートされた各メッセージのコピーを取得するルールを設定する](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)<br/>
  
10. **[保存]** を選択します。 
    
このルールが設定されている場合、組織内のユーザーがレポートメッセージアドインを使用して電子メールメッセージを報告するたびに、全体管理者、セキュリティ管理者、セキュリティリーダがそのメッセージのコピーを受け取ります。 この情報を使用すると、 [Office 365 の ATP の安全なリンク](atp-safe-links.md)ポリシー、または[スパム対策](anti-spam-protection.md)の設定などのポリシーを設定または調整することができます。 

## <a name="learn-how-to-use-the-report-message-add-in"></a>レポートメッセージアドインの使用方法について説明します。

「[レポートメッセージアドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)」を参照してください。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>レポートメッセージアドインの設定を確認または編集する

[[サービス & アドイン] ページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)で、レポートメッセージアドインの既定の設定を確認および編集できます。 

> [!IMPORTANT]
> このタスクを完了するには、Office 365 の全体管理者または Exchange Online 管理者である必要があります。
    
1. Microsoft 365 管理センターの [[サービス & アドイン] ページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に移動します。<br/>![新しい Microsoft 365 管理センターの [サービスとアドイン] ページ](media/ServicesAddInsPageNewM365AdminCenter.png)<br/>

2. レポートメッセージアドインを検索して選択します。<br/>![レポートメッセージアドインを検索して選択する](media/FindReportMessageAddIn.png)<br/> 
    
3. [レポートメッセージ] 画面で、組織に合わせて設定を確認して編集します。<br/>![レポートメッセージアドインの設定](media/EditReportMessageAddIn.png)<br/> 

## <a name="related-topics"></a>関連項目

[レポートメッセージアドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[セキュリティ&amp; /コンプライアンスセンターで電子メールのセキュリティレポートを表示する](view-email-security-reports.md)

[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)

[セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する](use-explorer-in-security-and-compliance.md)
  

