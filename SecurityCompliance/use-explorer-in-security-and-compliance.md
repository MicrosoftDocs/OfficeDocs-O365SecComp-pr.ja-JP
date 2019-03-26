---
title: セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターのエクスプローラー (脅威エクスプローラーとも呼ばれます) について説明します。
ms.openlocfilehash: 202898873bb9611c747aed335d295c749c7cd0fa
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30732260"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する

組織に[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)があり、必要なアクセス許可を持っている場合は、脅威エクスプローラーを使用して脅威を特定して分析することができます。 たとえば、配信された悪意のある電子メールを特定して削除したり、Office 365 セキュリティ機能によって検出されたマルウェアを確認したりすることができます。 脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティ運用チームがセキュリティ&amp;コンプライアンスセンターで脅威を調査して対応するのに役立つ、ほぼリアルタイムの強力なツールです。
  
![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
エクスプローラーを使用するには、 &amp;セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します。

> [!IMPORTANT]
> office 365 脅威インテリジェンスは office 365 Advanced threat protection プラン2に加えて、追加の脅威保護機能と共に提供されるようになりました。 詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。
      
## <a name="explorer-overview"></a>エクスプローラーの概要

組織に[Office 365 の脅威の調査と応答機能](office-365-ti.md)(ATP Plan 2 に含まれています) があり、必要なアクセス許可がある場合は、脅威エクスプローラー (エクスプローラーとも呼ばれます) を使用して脅威を識別して分析することができます。 (セキュリティ&amp;コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します)。

![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

この記事では、エクスプローラーで実行できるいくつかの操作について説明します (多くの可能性があります)。

- [電子メールで検出されたマルウェアの種類](#see-malware-detected-in-email-by-technology)、および脅威保護テクノロジ (マルウェア対策保護、ATP の安全な添付ファイルなど) について説明します。

- [フィッシングリンク (url) に関するデータ](#view-data-about-phishing-urls-and-click-verdict)、およびクリック verdicts がどのようなものか (警告が発生しても、ブロック、許可、またはアクセスした url) を表示します。

- 迷惑[メール (迷惑メールではない) として報告された電子メールメッセージを確認](#review-email-messages-reported-by-users)し、傾向 (通常はフィッシングとして報告されるメッセージ数の大きいなど) を特定します。 

## <a name="see-malware-detected-in-email-by-technology"></a>テクノロジによる電子メールで検出されたマルウェアを参照

電子メールで検出されたマルウェアと Office 365 のテクノロジについて確認する必要があるとします。 これを行うには、エクスプローラーの [ [Email > マルウェア](threat-explorer-views.md#email--malware)] ビューを使用します。

1. Office 365[https://protection.office.com](https://protection.office.com)セキュリティ & コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。
2. [**表示**] メニューで、[**電子メール** > **マルウェア**] を選択します。<br/>![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. [**送信者**] をクリックし、[**基本** > **検出テクノロジ**] を選択します。<br/>これで、検出テクノロジがレポートのフィルターとして使用できるようになります。<br/>![マルウェア検出テクノロジ](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. オプションを選択し、[更新] ボタンをクリックしてそのフィルターを適用します。<br/>![選択されている検出テクノロジ](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

レポートが更新され、選択した [テクノロジ] オプションを使用して、電子メールで検出された結果のマルウェアが表示されます。 ここから、さらに分析を行うことができます。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>フィッシング url に関するデータを表示し、[verdict] をクリックします。

許可された url の一覧を含む電子メール内の url を使用して、許可され、ブロックされ、上書きされたフィッシングを表示する場合を考えてみます。 これを行うには、エクスプローラーの [ [Email > フィッシング](threat-explorer-views.md#email--phish)] ビューを使用します。

1. Office 365[https://protection.office.com](https://protection.office.com)セキュリティ & コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。
2. [**表示**] メニューの [**電子メール** > **フィッシング**] をクリックします。<br/>![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailPhishMenu.png)<br/>
3. [**送信者**] をクリックし、[ **url** > ] を選択して、**[verdict] をクリック**します。
4. 1つ以上のオプション ([**ブロック**されてブロックされた**ブロック**] など) を選択し、[**更新**] ボタンをクリックしてそのフィルターを適用します。<br/>![url および [verdicts] をクリックします。](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

レポートが更新され、電子メールの配信状態と共に、検出された (または警告に関係していても表示されている) 電子メールで検出されたフィッシング url が表示されます ここから、さらに分析を行うことができます。 たとえば、グラフの下に、組織の電子メールでブロックされた上位の url が表示されます。 

![ブロックされたエクスプローラーの url](media/ExplorerPhishClickVerdictURLs.png) 

URL を選択して、詳細情報を表示します。

## <a name="review-email-messages-reported-by-users"></a>ユーザーが報告した電子メールメッセージを確認する

組織内のユーザーが、 [outlook 用のレポートメッセージアドインと web 上の outlook](enable-the-report-message-add-in.md)を使用して、迷惑メールではなく迷惑メールとして報告した電子メールメッセージを表示したいとします。 これを行うには、> のエクスプローラーの[ユーザーレポート](threat-explorer-views.md#email--user-reported)ビューを使用します。

1. Office 365[https://protection.office.com](https://protection.office.com)セキュリティ & コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。
2. [**表示**] メニューで、[**電子メール** > **ユーザー-レポート**] を選択します。<br/>![エクスプローラーの [表示] メニュー](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. [**送信者**] をクリックし、[**基本** > **レポートの種類**] を選択します。
4. オプション (**フィッシング**など) を選択し、[**更新**] ボタンをクリックします。 <br/>![ユーザーによって報告されるフィッシング](media/EmailUserReportedReportType.png)<br/> 

レポートが更新され、組織内のユーザーがフィッシングとして報告した電子メールメッセージに関するデータが表示されます。 この情報を使用して、さらに分析を行い、必要に応じて、 [ATP のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)を調整することができます。

## <a name="theres-more"></a>他にもまだあります！

この記事で説明されている3つのシナリオに加えて、多くのレポートシナリオをエクスプローラーで利用できます。 その他の例を次に示します。

- [配信された悪意のあるメールの検索と調査](investigate-malicious-email-that-was-delivered.md)

- [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する](malicious-files-detected-in-spo-odb-or-teams.md)

- [脅威エクスプローラーのビューの概要を取得する](threat-explorer-views.md)

## <a name="how-to-get-explorer"></a>エクスプローラーを取得する方法

Explorer は[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)に含まれています。 

エクスプローラーを表示して使用するには、セキュリティ管理者やセキュリティリーダーに付与されている権限など、適切なアクセス許可を持っている必要があります。 

- セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。
    - 組織の管理
    - セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)
    - セキュリティリーダ

- exchange online の場合は、exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [exchange online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。
    - 組織の管理
    - 表示限定の組織管理
    - "View-Only Recipients/表示専用受信者" 役割
    - コンプライアンス管理

詳細については、以下のリソースを参照してください。

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online の機能アクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="related-topics"></a>関連項目

- [自動化された調査と応答 (AIR)](automated-investigation-response-office.md)

- [脅威エクスプローラーのビュー](threat-explorer-views.md)

- [Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)
