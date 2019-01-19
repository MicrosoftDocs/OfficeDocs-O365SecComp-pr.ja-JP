---
title: レポート メッセージ アドインを有効にする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Outlook と Outlook は、個々 のユーザーまたは組織全体のメッセージのレポート アドインを有効にする方法を説明します。
ms.openlocfilehash: 013145813e8feb3e7389f6248ee26195c1df3d08
ms.sourcegitcommit: 1169a5759b9c2336fbc89d4651daf29e556f62fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "28727871"
---
# <a name="enable-the-report-message-add-in"></a>レポート メッセージ アドインを有効にする

## <a name="overview"></a>概要

レポート メッセージを追加で、Outlook と Outlook web 上で簡単に報告する misclassified メールは、安全なまたは悪意のあるかどうかマイクロソフトおよびその関連会社の分析のためにユーザーを使用できます。マイクロソフトでは、電子メール保護テクノロジの有効性を向上させるためにこれらの送信を使用します。さらに、 [Office 365 の高度な脅威保護](office-365-atp.md)または[Office 365 の脅威インテリジェンス](office-365-ti.md)組織を使用している場合、レポート メッセージを追加では、についての情報を確認および更新に使用できる、組織のセキュリティ チームセキュリティ ポリシーです。 

たとえば、ユーザーがフィッシング メッセージの多くを報告するいるとします。この情報には、[ダッシュ ボードのセキュリティ](security-dashboard.md)およびその他のレポート内のサーフェスが。組織のセキュリティ チームは、フィッシング詐欺対策のポリシーを更新する必要がありますを示す値として、この情報を使用できます。または、ユーザーには、多くのメッセージのレポート アドインを使用して、迷惑メールと迷惑メールとしてフラグ付けされたメッセージが報告される場合、組織のセキュリティ チームが[迷惑メール対策ポリシー](configure-the-anti-spam-policies.md)を調整する必要があります。 

レポート メッセージを追加では、Office 365 サブスクリプションと次の製品で動作します。
 - Outlook on the web
 - Outlook 2013 SP1
 - Outlook 2016
 - Outlook 2016 for Mac
 - Outlook を Office 365 用リソースに含まれています。

> [!NOTE]
> レポート メッセージ用のアドインの Outlook と web 上で Outlook は[Outlook 迷惑メール フィルター](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)と同じ迷惑メール、迷惑メールまたはフィッシング詐欺メールを開封するのには使用できますが、両方。レポート メッセージ用のアドインの Outlook と Outlook web Outlook 迷惑メール フィルターがユーザーのメールボックスに電子メール メッセージを整理するに対して、misclassified の電子メールについてマイクロソフトに通知します。 
  
個々 のユーザーの場合、[自分のメッセージのレポート アドインを有効に](#get-the-report-message-add-in-for-yourself)することができます。 
  
Office 365 のグローバル管理者または Exchange Online 管理者は、OAuth 認証を使用する Exchange が構成されている場合は[、レポート メッセージ用のアドインの組織を有効に](#get-and-enable-the-report-message-add-in-for-your-organization)することができます。レポート メッセージ アドインが[一元的な展開](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)で利用できるようになりました。
    
## <a name="get-the-report-message-add-in-for-yourself"></a>自分用の追加のレポート メッセージを取得します。

1. [マイクロソフトの AppSource](https://appsource.microsoft.com/marketplace/apps)、検索[レポート メッセージを追加で](https://appsource.microsoft.com/product/office/wa104381180)します。
    
2. 選択**を取得ここでの IT**です。<br/>![メッセージを報告する-今すぐ](media/ReportMessageGETITNOW.png)<br/> 
    
3. 使用およびプライバシー ポリシーの条件を確認します。**続行**を選択します。 
    
4. 作業または学校アカウント (業務用) または Microsoft アカウント (個人向け) を使用して Office 365 にサインインします。
    
アドインがインストールされており後、は、次のアイコンが表示されます。 

- Outlook では、次のようなアイコンが表示されます。 <br/> ![Outlook のアイコンを追加でメッセージを報告します。](media/OutlookReportMessageIcon.png)<br/>
- Outlook Web App (または、web 上で Outlook) では、次のように、アイコンが表示されます。<br/>![Outlook web レポート メッセージの追加のアイコンを](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> については、次のステップとして[、レポート メッセージのアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)する方法です。
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>取得し、レポート メッセージ用のアドインの組織を有効にします。

> [!IMPORTANT]
> このタスクを完了するには、Office 365 のグローバル管理者またはオンラインの Exchange 管理者である必要があります。さらに、 [Exchange 要件 (アドインの展開を一元的な)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)を参照してください詳細については OAuth 認証を使用する Exchange を構成する必要があります。 

1. Microsoft 365 管理センターの[サービスの & のアドインのページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に移動します。<br/>![新しい 365 管理センターでのサービスとアドインのページ](media/ServicesAddInsPageNewM365AdminCenter.png)<br/> 
    
2. **アドインを配置 +** を選択します。<br/>![選択アドインを配置](media/ServicesAddIns-ChooseDeployAddIn.png)<br/> 
    
3. **新しいアドイン**] 画面で情報を確認してとし、[**次**] を選択します。<br/>![新しいアドインの詳細情報](media/NewAddInScreen1.png)<br/>
    
4. **Office ストアからアドインを追加する**にはを選択し、し、[**次**] を選択します。<br/>![新しいアドインを追加します。](media/NewAddInScreen2.png)<br/> 
    
5. **レポート メッセージ**、および**レポート メッセージのアドイン**の横に、結果の一覧でを検索する場合、**追加**を選択します。<br/>![レポート メッセージを検索し、[追加](media/NewAddInScreen3.png)<br/>
    
6. **レポート メッセージ**画面で、情報を確認し、[**次**] を選択します。<br/>![レポート メッセージの詳細](media/ReportMessageAdd-InNewScreen4.png)<br/>

7. Outlook のユーザーの既定の設定を指定し、し、[**次**] を選択します。<br/>![Outlook のメッセージの既定の設定を報告します。](media/ReportMessageOptionsScreen5.png)<br/>

8. メッセージのレポート アドインを取得するかを指定し、**保存**します。 <br/>![追加のレポート メッセージを取得します。](media/ReportMessageOptionsScreen6.png)<br/>

> [!TIP]
> [ユーザーから報告された電子メール メッセージのコピーを取得するルールの設定](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)を推奨します。

アドイン (手順 7-8 の上) を設定するときに選択した内容により、組織内のユーザー[レポート メッセージの追加に](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)使用できるがあります。組織内のユーザーは、次のアイコンで表示されます。 

- Outlook では、次のようなアイコンが表示されます。 <br/> ![Outlook 用アドインのメッセージのアイコンをレポート](media/OutlookReportMessageIcon.png)<br/>
- Outlook Web App (または、web 上で Outlook) では、次のように、アイコンが表示されます。<br/>![Outlook アドインの Web レポートのメッセージのアイコンを](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> メッセージのレポート アドインをユーザーに通知するときに[、レポート メッセージのアドインの使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)へのリンクが含まれます。

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>ルールの設定、ユーザーから報告された電子メール メッセージのコピーを取得するには

> [!IMPORTANT]
> このタスクを実行するのには、Exchange にアクセスする権限が必要です。
  
ルールを設定するには、組織内のユーザーによって報告された電子メール メッセージのコピーを取得します。ダウンロードし、組織のメッセージのレポート アドインを有効にした後に行います。
  
1. Exchange 管理センターで、**メール フロー**を選択します\>**ルール**です。 
    
2. 選択**+** \> **新しい規則を作成**します。 
    
3. **[名前**] ボックスで、提出書類などの名前を入力します。
    
4. **場合にこのルールを適用**] ボックスの一覧で、**受信者のアドレスが含まれています...** を選択します。 
    
5. **単語または語句を指定する**画面で、追加`junk@office365.microsoft.com`と`phish@office365.microsoft.com`、し、 **[ok]** を選択します。<br/>![ルールの迷惑メールおよびフィッシングの電子メール アドレスを指定します。](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)<br/>
  
6. **. 次の操作**の一覧の [ **、メッセージの [bcc] に...**。 
    
7. グローバル管理者、セキュリティ管理者は、またはセキュリティ リーダーいる人が、マイクロソフトに報告する各電子メール メッセージのコピーを受信する必要があり、[ **ok]** を追加します。<br/>![報告された各メッセージのコピーを受信するのにはグローバルまたはセキュリティ管理者を追加します。](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)<br/>
  
8. **監査の重大度レベルでは、この規則**を選択し、 **[中]** を選択します。 
    
9. [**この規則のモードの選択**を**強制する**を選択します。<br/>![報告された各メッセージのコピーを取得するルールを設定します。](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)<br/>
  
10. [ **保存**] を選びます。 
    
配置では、このルールが他の組織でアドインを使用して、レポート メッセージ、電子メール メッセージを報告するたびに、グローバル管理者、セキュリティ管理者、またはセキュリティ リーダーが表示されますがメッセージのコピー。この情報を使用して、セットアップまたは[Office 365 の ATP の安全なリンク](atp-safe-links.md)ポリシー、または[スパム対策](anti-spam-protection.md)の設定などのポリシーを調整することができます。 

## <a name="learn-how-to-use-the-report-message-add-in"></a>レポート メッセージを追加で使用する方法を学習します。

[レポート メッセージの追加の使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を参照してください。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>確認またはレポート メッセージを追加の設定を編集します。

確認し、レポート メッセージを追加で、 [& [アドイン サービス] ページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)の既定の設定を編集できます。 

> [!IMPORTANT]
> このタスクを完了するには、Office 365 のグローバル管理者またはオンラインの Exchange 管理者である必要があります。
    
1. Microsoft 365 管理センターの[サービスの & のアドインのページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に移動します。<br/>![新しい 365 管理センターでのサービスとアドインのページ](media/ServicesAddInsPageNewM365AdminCenter.png)<br/>

2. 検索し、レポート メッセージを追加で選択します。<br/>![検索し、レポート メッセージを追加で選択](media/FindReportMessageAddIn.png)<br/> 
    
3. レポート メッセージ画面で、確認し、組織の必要に応じて設定を編集します。<br/>![レポート メッセージのアドインの設定](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a>関連項目

[迷惑メール報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[セキュリティで電子メールのセキュリティ レポートを表示する&amp;コンプライアンス センター](view-email-security-reports.md)

[Office 365 の高度な脅威保護のためのレポートを表示します。](view-reports-for-atp.md)

[エクスプ ローラーを使用して、セキュリティで&amp;コンプライアンス センター](use-explorer-in-security-and-compliance.md)
  

