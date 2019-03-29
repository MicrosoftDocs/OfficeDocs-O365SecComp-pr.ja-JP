---
title: セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/28/2019
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
ms.openlocfilehash: e6177970edc67c8b9e1c0ae6144f4c37f116012f
ms.sourcegitcommit: 787a0fef671e5dc6f5e805b580321b2edbfad8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30989612"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する

組織に[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md) (ATP) があり、必要なアクセス許可がある場合は、脅威エクスプローラー (エクスプローラーとも呼ばれます) を使用して脅威を識別して分析できます。 (エクスプローラーを使用するには、 &amp;セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します)。

![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

エクスプローラーは、セキュリティ運用チームがセキュリティ&amp;コンプライアンスセンターで脅威を調査して対応するのに役立つ、強力でほぼリアルタイムのツールです。 実行できる操作の一部を次に示します。
- [Office 365 のセキュリティ機能によって検出されたマルウェアを参照してください。](#see-malware-detected-in-email-by-technology)
- [フィッシング url に関するデータを表示し、[verdict] をクリックします。](#view-data-about-phishing-urls-and-click-verdict)
- [エクスプローラーのビューから自動化された調査と応答プロセスを開始する](#start-automated-investigation-and-response)
- ...その[他](#more-ways-to-use-explorer)

## <a name="see-malware-detected-in-email-by-technology"></a>テクノロジによる電子メールで検出されたマルウェアを参照

電子メールで検出されたマルウェアと Office 365 のテクノロジについて確認する必要があるとします。 これを行うには、エクスプローラーの [ [Email > マルウェア](threat-explorer-views.md#email--malware)] ビューを使用します。

1. セキュリティ &[https://protection.office.com](https://protection.office.com)コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。
2. [**表示**] メニューで、[**電子メール** > **マルウェア**] を選択します。<br/>![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. [**送信者**] をクリックし、[**基本** > **検出テクノロジ**] を選択します。<br/>これで、検出テクノロジがレポートのフィルターとして使用できるようになります。<br/>![マルウェア検出テクノロジ](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. オプションを選択し、[更新] ボタンをクリックしてそのフィルターを適用します。<br/>![選択されている検出テクノロジ](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

レポートが更新され、選択した [テクノロジ] オプションを使用して、電子メールで検出された結果のマルウェアが表示されます。 ここから、さらに分析を行うことができます。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>フィッシング url に関するデータを表示し、[verdict] をクリックします。

許可された url の一覧を含む電子メール内の url を使用して、許可され、ブロックされ、上書きされたフィッシングを表示する場合を考えてみます。 これを行うには、エクスプローラーの [ [Email > フィッシング](threat-explorer-views.md#email--phish)] ビューを使用します。

1. セキュリティ &[https://protection.office.com](https://protection.office.com)コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。
2. [**表示**] メニューの [**電子メール** > **フィッシング**] をクリックします。<br/>![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailPhishMenu.png)<br/>
3. [**送信者**] をクリックし、[ **url** > ] を選択して、**[verdict] をクリック**します。
4. 1つ以上のオプション ([**ブロック**されてブロックされた**ブロック**] など) を選択し、[**更新**] ボタンをクリックしてそのフィルターを適用します。<br/>![url および [verdicts] をクリックします。](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

レポートが更新され、電子メールの配信状態と共に、検出された (または警告に関係していても表示されている) 電子メールで検出されたフィッシング url が表示されます ここから、さらに分析を行うことができます。 たとえば、グラフの下に、組織の電子メールでブロックされた上位の url が表示されます。 

![ブロックされたエクスプローラーの url](media/ExplorerPhishClickVerdictURLs.png) 

URL を選択して、詳細情報を表示します。

## <a name="review-email-messages-reported-by-users"></a>ユーザーが報告した電子メールメッセージを確認する

組織内のユーザーが、 [outlook 用のレポートメッセージアドインと web 上の outlook](enable-the-report-message-add-in.md)を使用して、迷惑メールではなく迷惑メールとして報告した電子メールメッセージを表示したいとします。 これを行うには、> のエクスプローラーの[ユーザーレポート](threat-explorer-views.md#email--user-reported)ビューを使用します。

1. セキュリティ &[https://protection.office.com](https://protection.office.com)コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。
2. [**表示**] メニューで、[**電子メール** > **ユーザー-レポート**] を選択します。<br/>![エクスプローラーの [表示] メニュー](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. [**送信者**] をクリックし、[**基本** > **レポートの種類**] を選択します。
4. オプション (**フィッシング**など) を選択し、[**更新**] ボタンをクリックします。 <br/>![ユーザーによって報告されるフィッシング](media/EmailUserReportedReportType.png)<br/> 

レポートが更新され、組織内のユーザーがフィッシングとして報告した電子メールメッセージに関するデータが表示されます。 この情報を使用して、さらに分析を行い、必要に応じて、 [ATP のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)を調整することができます。

## <a name="start-automated-investigation-and-response"></a>自動調査と応答の開始

(新)ATP プラン2に追加された[自動調査と応答](automated-investigation-response-office.md)を使用すると、セキュリティ運用チームに多くの時間と労力をかけることができます。これにより、サイバー攻撃の調査と軽減が可能になります。 セキュリティプレイブックをトリガーできる通知を構成するだけでなく、エクスプローラーのビューから自動化された調査および応答プロセスを開始できます。 

詳細については、「[例: セキュリティ管理者が脅威エクスプローラーから調査を開始する](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)」を参照してください。

## <a name="more-ways-to-use-explorer"></a>エクスプローラーのその他の使用方法

この記事で説明されているシナリオに加えて、エクスプローラーで利用できるレポートオプションが他にも多数あります。 
- [配信された悪意のあるメールの検索と調査](investigate-malicious-email-that-was-delivered.md)
- [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する](malicious-files-detected-in-spo-odb-or-teams.md)
- [脅威エクスプローラーのビューの概要を取得する](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

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

役割とアクセス許可の詳細については、以下のリソースを参照してください。

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online の機能アクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
