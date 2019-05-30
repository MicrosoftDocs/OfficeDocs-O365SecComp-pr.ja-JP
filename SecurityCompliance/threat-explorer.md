---
title: 脅威エクスプローラー (およびリアルタイム検出)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターのエクスプローラー (およびリアルタイム検出) について説明します。
ms.openlocfilehash: 030f866c5e86daa3dc543bddae7152e19f377d3b
ms.sourcegitcommit: 6c0fcb82178a4ac26375545f328389a6852a81be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "34490533"
---
# <a name="threat-explorer-and-real-time-detections"></a>脅威エクスプローラー (およびリアルタイム検出)

組織で[office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP) を使用していて、[必要なアクセス許可](#required-licenses-and-permissions)がある場合は、 **Explorer**または**リアルタイムの検出**(以前の*リアルタイムのレポート*) を使用します。 [新機能](#new-features-in-real-time-detections))。 セキュリティ & コンプライアンスセンターで、[脅威の**管理**] に移動してから、[**エクスプローラー** ] または [**リアルタイムの検出**] を選択します。 

|ATP プラン2を使用すると、次のように表示されることになります。  |ATP プラン1では、次のように表示されることがあります。  |
|---------|---------|
|![脅威エクスプローラー](media/threatmgmt-explorer.png)      |![リアルタイムの検出](media/threatmgmt-realtimedetections.png)         |

エクスプローラー (リアルタイム検出) では、強力なレポートが用意されており、セキュリティ運用チームが脅威を調査して効果的かつ効率的に応答でき、次の図のようになります。 

![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

このレポートでは、次のことができます。
- [Office 365 のセキュリティ機能によって検出されたマルウェアを参照](#see-malware-detected-in-email-by-technology)
- [フィッシング Url に関するデータを表示し、[verdict] をクリックします。](#view-data-about-phishing-urls-and-click-verdict)
- [エクスプローラーのビューから自動化された調査と応答プロセスを開始](#start-automated-investigation-and-response)する(ATP プラン2のみ)
- ...[悪意のある電子メールの調査など](#more-ways-to-use-explorer-or-real-time-detections)

## <a name="new-features-in-real-time-detections"></a>リアルタイム検出の新機能

Office 365 ATP Plan 1 ユーザーの場合、*リアルタイムの検出*レポートは、以前は*リアルタイムレポート*と呼ばれていました。 名前の変更に加えて、いくつかの新機能と拡張機能がロールアウトされています。

- フィッシングビューには、 [ATP の安全なリンク](atp-safe-links.md)によって検出された url に関する詳細が表示されます。 新しい詳細と機能は次のとおりです。
  - 電子メールメッセージ内の Url
  - URL 情報に基づくフィルター処理
  - データグラフに表示される URL 情報
  - メッセージ内のクリックに関するクリック時間データ

- URL が変更されるたびに、[verdict] をクリックすると、警告が表示されます。 URL クリック verdicts は、URL の評価が分析に変更されたとき、または ATP の安全なリンクによって保護されているユーザーが[atp の安全なリンクの警告](atp-safe-links-warning-pages.md)を上書きしたときに変更できます。  
 
これらの機能拡張によって、組織のセキュリティ管理者は以前よりも詳細な情報を表示できるようになります。 セキュリティ管理者は、URL ドメイン、不在 Url、[verdicts] などの情報を参照し、Office 365 ATP ポリシーを適切に調整することができます。

> [!NOTE]
> これらの機能はプレビュー段階にありますが、URL データは限られた日数のみ利用可能になります。 

## <a name="see-malware-detected-in-email-by-technology"></a>テクノロジによる電子メールで検出されたマルウェアを参照

Office 365 テクノロジを使用して、電子メールで検出されたマルウェアを確認する必要があるとします。 これを行うには、エクスプローラーの [ [Email _GT_ マルウェア](threat-explorer-views.md#email--malware)] ビュー (またはリアルタイムの検出) を使用します。

1. セキュリティ & コンプライアンス[https://protection.office.com](https://protection.office.com)センター () で、[**脅威管理** > **エクスプローラー** (または**リアルタイムの検出**)] を選択します。 (この例ではエクスプローラーを使用しています)。

2. [**表示**] メニューで、[**電子メール** > **マルウェア**] を選択します。<br/>![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailMalwareMenu.png)<br/>

3. [**送信者**] をクリックし、[**基本** > **検出テクノロジ**] を選択します。<br/>これで、検出テクノロジがレポートのフィルターとして使用できるようになります。<br/>![マルウェア検出テクノロジ](media/ExplorerEmailMalwareDetectionTech.png)<br/> 

4. オプションを選択し、[**更新**] ボタンをクリックしてそのフィルターを適用します。<br/>![選択されている検出テクノロジ](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

レポートが更新され、選択した [テクノロジ] オプションを使用して、電子メールで検出された結果のマルウェアが表示されます。 ここから、さらに分析を行うことができます。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>フィッシング Url に関するデータを表示し、[verdict] をクリックします。

許可された Url の一覧を含む、電子メール内の Url によるフィッシングの試行、禁止、および上書きを確認するとします。 クリックされた Url を識別するには、 [ATP の安全なリンク](atp-safe-links.md)を構成する必要があります。 [クリック時の保護とログ記録のための、 [atp の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を設定していることを確認してください] verdicts の [安全なリンク] をクリックします。 

メッセージ内のフィッシング Url を確認し、フィッシングメッセージで Url をクリックするには、Explorer の [[電子メール _GT_ フィッシング](threat-explorer-views.md#email--phish)ビュー (またはリアルタイムの検出) を使用します。

1. セキュリティ & コンプライアンス[https://protection.office.com](https://protection.office.com)センター () で、[**脅威管理** > **エクスプローラー** (または**リアルタイムの検出**)] を選択します。 (この例ではエクスプローラーを使用しています)。

2. [**表示**] メニューの [**電子メール** > **フィッシング**] をクリックします。<br/>![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailPhishMenu.png)<br/>

3. [**送信者**] をクリックし、[ **url** > ] を選択して、**[verdict] をクリック**します。

4. 1つまたは複数のオプション ([**ブロック**されて**ブロック**する] など) を選択し、[**更新**] ボタンをクリックして、そのフィルターを適用するオプションと同じ行にあるものをクリックします。 (ブラウザーウィンドウを更新しないでください)。<br/>![Url および [verdicts] をクリックします。](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

    レポートが更新され、[URL] タブにレポートの下に2つの異なる URL テーブルが表示されます。

   1. **トップ url**は、フィルター処理されたメッセージに含まれる url と、各 url の電子メール配信アクション数を示します。 [フィッシング email] ビューには、通常、正当な Url が含まれています。 攻撃者は、適切な Url と正しくない Url をメッセージに混在させて配信を試みることができますが、ユーザーがクリックすると、悪意のあるリンクがより興味深いものになります。 Url の表は、電子メールの合計数によって並べ替えられます (注: この列はビューを簡略化するために表示されていません)。

   2. **トップクリック**は、クリックされた url をラップした安全なリンクです。 [合計] をクリックします (この列はビューを簡略化するためにも表示されません)。 列別の合計カウント [セーフリンク] は、クリックされた各 URL の [verdict count] を示します。 フィッシングの電子メール表示では、多くの場合、疑わしいまたは悪意のある Url ですが、フィッシングメッセージ内にあるクリーンな Url を含めることができます。 ラップされていないリンクの URL クリックは表示されません。
   
   2つの Url 表は、配信アクションと場所によって、フィッシングメールの上位の Url を示しています。また、ブロックされた (または警告によってアクセスされた) URL クリックが表示されるので、ユーザーが無効にしたり、ユーザーによって操作された潜在的なリンクを知ることができます。 ここから、さらに分析を行うことができます。 たとえば、グラフの下に、組織の環境でブロックされたメールの上位の Url が表示されます。
   
   ![ブロックされたエクスプローラーの Url](media/ExplorerPhishClickVerdictURLs.png)
   
   URL を選択して、詳細情報を表示します。 [URL] ポップアップダイアログでは、メールのフィルタリングが削除されて、環境内の URL の公開が完全に表示されることに注意してください。 これにより、懸念されているものに対してエクスプローラーでメールをフィルター処理し、潜在的な脅威である特定の Url を見つけ、url フィルターを追加することなく、環境内の URL の公開について理解を深めることができます。エクスプローラービュー自体。

## <a name="review-email-messages-reported-by-users"></a>ユーザーが報告した電子メールメッセージを確認する

組織内のユーザーが、 [outlook 用のレポートメッセージアドインと web 上の outlook](enable-the-report-message-add-in.md)を使用して、迷惑メールではなく迷惑メールとして報告した電子メールメッセージを表示したいとします。 これを行うには、[電子メール > のユーザーレポート](threat-explorer-views.md#email--user-reported)ビュー (またはリアルタイムの検出) を使用します。

1. セキュリティ & コンプライアンス[https://protection.office.com](https://protection.office.com)センター () で、[**脅威管理** > **エクスプローラー** (または**リアルタイムの検出**)] を選択します。 (この例ではエクスプローラーを使用しています)。

2. [**表示**] メニューで、[**電子メール** > **ユーザー-レポート**] を選択します。<br/>![エクスプローラーの [表示] メニュー](media/ExplorerViewMenuEmailUserReported.png)<br/>

3. [**送信者**] をクリックし、[**基本** > **レポートの種類**] を選択します。

4. オプション (**フィッシング**など) を選択し、[**更新**] ボタンをクリックします。 <br/>![ユーザーによって報告されるフィッシング](media/EmailUserReportedReportType.png)<br/> 

レポートが更新され、組織内のユーザーがフィッシングとして報告した電子メールメッセージに関するデータが表示されます。 この情報を使用して、さらに分析を行い、必要に応じて、 [ATP のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)を調整することができます。

## <a name="start-automated-investigation-and-response"></a>自動調査と応答の開始

> [!NOTE]
> 自動化された調査および応答機能は、 **office 365 ATP Plan 2**および**office 365 E5**で利用できます。

(新)自動化された[調査と応答](automated-investigation-response-office.md)によって、セキュリティ運用チームの時間と労力を節約し、サイバー攻撃を調査および軽減することができます。 セキュリティプレイブックをトリガーできる通知を構成するだけでなく、エクスプローラーのビューから自動化された調査および応答プロセスを開始できます。 

詳細については、「[例: セキュリティ管理者がエクスプローラーから調査を開始する](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)」を参照してください。

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>エクスプローラーを使用するその他の方法 (またはリアルタイムの検出)

この記事で説明されているシナリオに加えて、エクスプローラー (またはリアルタイムの検出) で利用できるレポートオプションが他にも多数あります。 
- [配信された悪意のあるメールの検索と調査](investigate-malicious-email-that-was-delivered.md)
- [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する](malicious-files-detected-in-spo-odb-or-teams.md)
- [脅威エクスプローラーのビューの概要 (およびリアルタイムの検出) を取得する](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

エクスプローラーまたはリアルタイムの検出を取得するには、 [Office 365 ATP](office-365-atp.md)が必要です。
- Explorer は Office 365 ATP Plan 2 に含まれています。 
- リアルタイム検出レポートは、Office 365 ATP Plan 1 に含まれています。

エクスプローラーまたはリアルタイム検出を表示して使用するには、セキュリティ管理者やセキュリティリーダーに付与されている権限など、適切なアクセス許可を持っている必要があります。 

- セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。
    - 組織の管理
    - セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)
    - セキュリティリーダ

- Exchange Online の場合は、Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [Exchange online Powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。
    - 組織の管理
    - 表示限定の組織管理
    - "View-Only Recipients/表示専用受信者" 役割
    - コンプライアンス管理

役割とアクセス許可の詳細については、以下のリソースを参照してください。

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online の機能アクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
