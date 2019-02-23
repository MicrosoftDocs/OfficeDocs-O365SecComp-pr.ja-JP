---
title: Office 365 Cloud App Security の新機能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 01/25/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 2018 for Office 365 Cloud App Security でリリースされた機能を参照してください。
ms.openlocfilehash: 986fb64eedf8184e7835d1fec41845fde13b294b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214347"
---
# <a name="office-365-cloud-app-security-updates-during-2018"></a>2018の Office 365 Cloud App Security updates

## <a name="office-365-cloud-app-security-release-138"></a>Office 365 Cloud App Security release 138

*2018年12月23日リリース*

** [Microsoft Cloud App Security release 138](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-138)のフォロー**:

- **Windows での Docker を使用したログの自動アップロード**Cloud App Security では、windows で Docker を使用して windows 10 ([クリエーターの更新プログラム](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)と新しいバージョン) および windows Server ([バージョン 1709](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1709)以降) の自動ログアップロードがサポートされるようになりました。詳細については、[この記事](https://docs.microsoft.com/cloud-app-security/discovery-docker-windows)を参照し、Docker を構成してください。  

- **Microsoft Flow の統合**Cloud App Security が[Microsoft Flow](https://docs.microsoft.com/flow/getting-started)と統合され、カスタムの通知の自動化とオーケストレーションのプレイブックが提供されるようになりました。詳細については、[この記事](https://docs.microsoft.com/cloud-app-security/flow-integration)を参照して Microsoft Flow 統合を構成してください。 

## <a name="office-365-cloud-app-security-release-137"></a>Office 365 Cloud App Security release 137

*2018年12月8日リリース*

** [Microsoft Cloud App Security release 137](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-137)のフォロー**:

- **Dynamics のサポートが追加されました**Cloud App Security には、Office 365 監査ログでサポートされている Microsoft Dynamics アクティビティのサポートが含まれるようになりました。 

- **head: 新しい用語**わかりやすくするために、アプリのアクセス許可機能の名前が変更されました。これは、OAuth apps と呼ばれています。 

## <a name="office-365-cloud-app-security-release-136"></a>Office 365 Cloud App Security release 136

*2018年11月25日リリース*

** [Microsoft Cloud App Security release 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)のフォロー**:

- **クラウド検出の更新**カスタムログパーサーが拡張され、さらに複雑な web トラフィックログの形式をサポートするようになりました。これらの拡張機能の一部として、ユーザーは、headerless CSV ログファイル用のカスタムヘッダーを入力できるようになりました。また、キー値ファイル、処理 Syslog ファイル形式などに特別な区切り記号を使用することもできます。

- **新しい異常検出ポリシー: 疑わしい受信トレイ操作ルール**このポリシーは、ユーザーの受信トレイでメッセージまたはフォルダーを削除または移動する不審なルールが設定されている場合に、環境をプロファイルし、アラートをトリガーします。これは、ユーザーのアカウントが侵害され、メッセージが意図的に非表示になっており、組織内でスパムまたはマルウェアを配信するためにメールボックスが使用されていることを示している可能性があります。

- **アプリのアクセス許可ポリシーのグループのサポート**Cloud App Security では、アプリを承認したユーザーのグループメンバーシップに基づいて、アプリのアクセス許可ポリシーをより細かく定義できるようになりました。たとえば、管理者は、アクセス許可を承認したユーザーが administrators グループのメンバーである場合にのみ、よくあるアプリを取り消すようにポリシーを設定することができます。

## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a>Office 365 Cloud App Security は133、134、および135をリリースします。

*2018年10月にリリース*

** [Microsoft Cloud App Security release 133、134、および 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)を次に**示します。

- **新しい異常検出ポリシー**は段階的にロールアウトされています。
    
    - ユーザーまたは IP アドレスが承認されていないアプリを使用して、組織から情報を exfiltrate しようとしたときに発生するアクティビティを実行している場合は、承認を取り消した**アプリポリシーに対する新しいデータ exfiltration フィルター**処理が自動的に有効になります。
    
    - [新しい**複数削除 VM アクティビティ**] ポリシーは、環境をプロファイルし、ユーザーが組織内のベースラインを基準にして1つのセッションで複数の vm を削除したときに通知をトリガーします。

- **i フィルターでのクラウド検出のサポート**cloud App Security cloud Discovery 機能は、i フィルター syslog パーサーのサポートを強化しました。

## <a name="office-365-cloud-app-security-release-131"></a>Office 365 Cloud App Security release 131

*2018年9月16日リリース*

** [Microsoft Cloud App Security release 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)のフォロー**:

- **リスクの高い OAuth アプリケーションに対するアクセス許可を自動的に取り消す**Office で oauth アプリのアプリのアクセス許可を取り消すことにより、ユーザーがアクセスできる oauth アプリを制御できるようになりました。アプリのアクセス許可ポリシーを作成するときに、アプリのアクセス許可を取り消すようにポリシーを設定できるようになりました。

- **クラウド検出の追加の組み込みパーサーがサポートされている**クラウド検出は、forcepoint Web Security cloud ログ形式をサポートするようになりました。
  
## <a name="office-365-cloud-app-security-release-130"></a>Office 365 Cloud App Security release 130

*2018年9月5日リリース*

** [Microsoft Cloud App Security release 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)のフォロー**:

- **新しいメニューバー**microsoft 365 製品間でより一貫性のある管理者を提供し、microsoft のセキュリティソリューション間でより簡単にピボットできるようにするために、Cloud App security ポータルのメニューバーは画面の左側に移動しました。この一貫したナビゲーション環境によって、Microsoft セキュリティポータル間での移行時に自分を理解することができます。<br/>![Office Cloud App Security のメニューバー](media/OCAS-MenuBar.png)<br/>

- **影響 OAuth アプリのスコア**組織で OAuth アプリが検出された場合に、悪意のあるように見えることを知らせるために、Cloud app Security team のフィードバックを送信できるようになりました。この新しい機能により、セキュリティコミュニティの一部として、OAuth アプリのリスクスコアと分析を強化できます。詳細については、「 [Manage OAuth apps](manage-app-permissions-in-ocas.md)」を参照してください。

- **新しいクラウド検出パーサー**クラウド検出パーサーは、iboss の Secure Cloud Gateway と Sophos xg をサポートするようになりました。

## <a name="office-365-cloud-app-security-release-128"></a>Office 365 Cloud App Security release 128

*2018年8月5日リリース* 
  
** [Microsoft Cloud App Security release 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)のフォロー**: 
  
- **複数のアプリにまたがる OAuth アプリ**OAuth アプリの場合、1つのアクションで複数のアプリを禁止または承認できるようになりました。たとえば、組織内のユーザーによってアクセス許可が付与されているすべてのアプリを確認するには、禁止するすべてのアプリを選択し、[アプリの禁止] をクリックして、付与されたすべての同意を取り消し、ユーザーがそれらのアプリに対するアクセス許可を付与できなくなります。詳細については、「 [Office 365 Cloud App Security を使用して OAuth アプリを管理](manage-app-permissions-in-ocas.md)する」を参照してください。 
    
- **新しい提案されたクエリ: GDPR ready cloud apps**GDPR ready の検出されたアプリを特定できるようにするための新しい推奨クエリが用意されています。すでにご存じのとおり、GDPR は、セキュリティ管理者にとって最近の優先度になっています。このクエリを使用すると、GDPR ready のアプリを簡単に特定し、脅威を軽減することができます。アプリのリスクを評価します。新しいクエリを使用するには、**クラウド探索**ダッシュボードの [検出された**アプリ**] タブで、[**クエリ** > **GDPR-ready Cloud apps**] を選択します。<br/>![GDPR ready cloud apps クエリ](media/OCAS-FindGDPRQueries.png)<br/>
    
## <a name="office-365-cloud-app-security-release-126"></a>Office 365 Cloud App Security release 126

*2018年7月7日リリース* 
  
** [Microsoft Cloud App Security release 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)のフォロー**: 
  
- **不審なアクティビティの自動修復**異常検出ポリシーによってトリガーされた疑わしいセッションの自動修復アクションを設定できるようになりました。この拡張機能により、違反が発生したときに即座に通知が行われ、中断ユーザーなどのガバナンスアクションが自動的に適用されます。詳細については、「 [Office 365 Cloud App Security」の「異常検出ポリシー](anomaly-detection-policies-in-ocas.md)」を参照してください。
    
- **リスクの高い OAuth アプリの自動検出**環境に接続された oauth アプリの既存の調査に加えて、Office 365 Cloud app Security では、oauth アプリが特定の条件を満たしていることを通知する自動化された通知を設定することができます。たとえば、高レベルのアクセス許可レベルを必要とし、50を超えるユーザーによって承認されたアプリがある場合は、自動的に通知を受け取ることができます。詳細については、「 [Office 365 Cloud App Security を使用して OAuth アプリを管理する](manage-app-permissions-in-ocas.md)」を参照してください。
    
- **Managed Security Service プロバイダ management (MSSP) のサポート**office 365 cloud app security では、mssps に対してより優れた管理機能が提供されるようになり、office 365 Cloud app security で現在使用可能な任意の役割を持つ管理者として外部パートナーを構成できます。さらに、複数のテナントへのアクセス権を持つ管理者は、テナント間を簡単にピボットできるようになりました。 
    
## <a name="office-365-cloud-app-security-release-124"></a>Office 365 Cloud App Security release 124

*2018年6月10日リリース* 
  
** [Microsoft Cloud App Security release 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)のフォロー**: 
  
- **スコープ付き展開**エンタープライズ組織は、グループメンバーシップに基づいて、監視および保護するユーザーを細かく決定できます。この機能により、保護されたアプリケーションに対してアクティビティが表示されないユーザーを選択できます。スコープ監視は、コンプライアンスおよびライセンスに特に役立ちます。一部のコンプライアンス規制では、地域規制により特定の国からのユーザーの監視を控える必要があります。さらに、Office 365 Cloud App Security ライセンスの制限内にとどまるユーザーの数を監視することはできません。 
    
- **新しい電子メールサーバー**Office 365 用の電子メールサーバーの Cloud App Security が変更され、異なる IP アドレス範囲を使用しています。通知を取得できるようにするには、新しい IP アドレスをスパム対策ホワイトリストに追加します。通知をカスタマイズする組織の場合、Cloud App Security では、サードパーティの電子メールサービスである mailchimp を使用して、これを有効にすることができます。メールサーバーの IP アドレスの一覧、および mailchimp で作業を有効にする手順については、「[ネットワーク要件 (microsoft cloud app security)](https://docs.microsoft.com/cloud-app-security/network-requirements) 」と「[メール設定 (microsoft cloud app security)](https://docs.microsoft.com/cloud-app-security/mail-settings)」を参照してください。
    
## <a name="office-365-cloud-app-security-release-121"></a>Office 365 Cloud App Security release 121

*リリース2018年5月6日* 
  
** [Microsoft Cloud App Security release 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)のフォロー**: 
  
- **異常検出ポリシーの改善**。Office 365 Cloud App Security の異常検出ポリシーは、段階的にロールアウトされる2種類の脅威検出を含むように改善されました。 
    
  - **ランサムウェアのアクティビティ。** ランサムウェア検出機能は異常検出によって拡張されており、高度なランサムウェア攻撃に対する包括的なサポートを提供しています。 
    
  - **終了したユーザーアクティビティ。** 中断されたユーザーアクティビティでは、組織のアプリケーションからプロビジョニングが解除されている場合でも、特定の企業リソースにアクセスできる可能性がある、終了したユーザーのアカウントを監視できます。 
    
    [異常な検出ポリシー](anomaly-detection-policies-in-ocas.md)を表示するには、Office 365 Cloud App Security ポータルで、[**ポリシー**の**制御** \> ] を選択します。
    
## <a name="office-365-cloud-app-security-release-120"></a>Office 365 Cloud App Security release 120

*2018年4月22日リリース* 
  
** [Microsoft Cloud App Security release 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)のフォロー**: 
  
- **ユーザーアクティビティとしての内部アプリケーション**。office 365 および azure Active Directory (azure ad) の場合、office 365 および azure ad アプリケーション (内部と外部の両方) によって実行されたユーザーアカウントアクティビティとして、内部アプリケーションを検出する機能を徐々に展開しています。これにより、アプリケーションが予期しないアクティビティを実行した場合に警告するポリシーを作成できます。 
    
- **OAuth アプリリストのエクスポートのその他のフィールド**。OAuth アプリリストを csv にエクスポートする場合は、コンプライアンスおよび調査プロセスを支援するために publisher、アクセス許可レベル、コミュニティ使用法などの追加のフィールドが含まれています。 
    
## <a name="office-365-cloud-app-security-release-119"></a>Office 365 Cloud App Security release 119

*2018年4月1日リリース* 
  
** [Microsoft Cloud App Security release 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)のフォロー**: 
  
- **クラウド検出の強化**。クラウド探索は、上位ユーザーおよび IP アドレスについて詳細な情報を提供します。これにより、Office 365 およびその他のアプリの利用状況の詳細を表示することが容易になります。詳細については、「 [Office 365 Cloud app Security でアプリ検出に関する調査結果を確認](review-app-discovery-findings-in-ocas.md)する」を参照してください。
    
    ![クラウド検出ダッシュボードが更新されました](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Office 365 Cloud App Security release 118

*2018年3月18日リリース* 
  
** [Microsoft Cloud App Security release 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)のフォロー**: 
  
- **Barracuda サポート**。クラウド検出は、Barracuda f series ファイアウォールと Barracuda f シリーズファイアウォール web ログストリーミングをサポートするようになりました。 
    
## <a name="office-365-cloud-app-security-release-117"></a>Office 365 Cloud App Security release 117

*2018年3月6日リリース* 
  
** [Microsoft Cloud App Security release 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)のフォロー**: 
  
- **i フィルタサポート**。クラウド検出は、i フィルターをサポートするようになりました。 
    
## <a name="office-365-cloud-app-security-release-116"></a>Office 365 Cloud App Security release 116

*2018年2月18日リリース* 
  
** [Microsoft Cloud App Security release 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)のフォロー**: 
  
- **異常検出ポリシーの拡張**。Office 365 の異常検出ポリシー Office Cloud App Security は、不可能な移動、疑わしい IP アドレスからのアクティビティ、ログイン試行の失敗など、新しいシナリオベースの検出によって強化されました。新しいポリシーが自動的に有効になり、クラウド環境全体ですぐに使用できる脅威の検出が提供されます。さらに、新しいポリシーにより、Office 365 Cloud App Security detection engine から多くのデータが公開されます。これにより、調査プロセスの時間を短縮し、継続的な脅威を含めることができます。詳細については、「Microsoft Cloud App Security」を参照してください。この記事では、[迅速な行動分析と異常検出](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)について説明します。
    
- **チェックポイント形式のログ解析サポート**。クラウド検出ログパーサーは、XML、および kpc という2つの追加のチェックポイント形式をサポートするようになりました。 
    
## <a name="office-365-cloud-app-security-release-114"></a>Office 365 Cloud App Security release 114

*2018年1月21日リリース* 
  
** [Microsoft Cloud App Security release 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)のフォロー**: 
  
- **サービスの状態**。[**システムステータス**の**ヘルプ** \>にアクセスすることで、現在の Office 365 Cloud App Security サービスの状態を確認できるようになりました。 
    
    ![[ヘルプ\>システムの状態] をクリックして、システムの正常性の状態を表示します。](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **アクティビティログのカスタムクエリ**。バージョン114以降では、アクティビティログでカスタムクエリを作成して保存する機能が段階的にロールアウトされています。カスタムクエリを使用すると、詳細な調査のために再利用できるフィルタテンプレートを作成できます。さらに、アクティビティおよび検出されたアプリをフィルター処理するためのすぐに使用できる調査テンプレートを提供するために、推奨されるクエリが追加されています。推奨されるクエリには、偽装アクティビティ、管理者アクティビティ、リスクに準拠していないクラウドストレージアプリ、脆弱な暗号化を使用したエンタープライズアプリ、セキュリティリスクなどのリスクを識別するためのカスタムフィルターが含まれています。提案されたクエリを開始点として使用し、必要に応じて変更して、新しいクエリとして保存します。 
    
## <a name="office-365-cloud-app-security-release-113"></a>Office 365 Cloud App Security release 113

*2018年1月8日リリース* 
  
** [Microsoft Cloud App Security release 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)のフォロー**: 
  
- **汎用形式のログパーサーサポート**。クラウド検出ログパーサーは、leef、cef、および W3C という一般的な形式をサポートするようになりました。 

## <a name="related-topics"></a>関連項目

[Office 365 Cloud App Security の新機能](new-in-office-365-cas.md)

[「2017 updates for Office 365 Cloud App Security」を参照してください。](new-in-office-365-cas-2017.md)
    
[Office 365 Cloud App Security 展開後の利用に関する作業](utilization-activities-for-ocas.md)