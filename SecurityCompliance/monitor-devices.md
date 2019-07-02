---
title: Microsoft 365 セキュリティセンターのデバイスの監視とレポート
description: 組織において、デバイスのセキュリティを確保し、最新の状態を維持し、潜在的な脅威を特定する方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、デバイス
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 44fd28a0ba2ec72d999c89d183d85ccb496903ec
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852871"
---
# <a name="device-monitoring-and-reporting-in-microsoft-365-security-center"></a>Microsoft 365 セキュリティセンターのデバイスの監視とレポート

モバイルデバイスのセキュリティを確保し、最新の状態に保つことができます。また、潜在的な脅威については、Microsoft 365 セキュリティセンターを使用してください。

## <a name="view-device-alerts"></a>デバイスの通知を表示する

Microsoft Defender ATP (E5 ライセンス付き) から、デバイスに対する違反アクティビティやその他の脅威に関する最新の通知を入手できます。 Microsoft 365 セキュリティセンターは、優先ワークフローを使用して、これらのアラートを高レベルで効果的に監視します。

### <a name="monitor-high-impact-alerts"></a>影響度の高いアラートを監視する

Microsoft Defender ATP の各アラートには、対応する重要度 (高、中、低、または情報) があります。これは、無人のままでネットワークに影響を与える可能性があることを示します。  

**デバイスアラートの重要度**カードを使用して、より深刻で、即時応答を必要とする可能性があるアラートに特に注目します。 このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。

![デバイス通知の重要度カード](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>通知のソースを理解する

Microsoft Defender ATP は、さまざまなセキュリティセンサーおよびインテリジェンスソースからのデータを利用して、アラートを生成します。 たとえば、web サービス API によって提供される独自のカスタム脅威インテリジェンスに加えて、Windows Defender ウイルス対策およびサードパーティのマルウェア対策の検出情報を使用することができます。

**デバイスアラート検出**ソースカードは、通知のソース別の配布を示しています。 このカードは、特定のソース (特にカスタムソース) に関連するアクティビティを追跡するのに役立ちます。 また、これを使用して、悪意のあるアクティビティやコンポーネントを自動的にブロックするように構成されていないセンサーからのアラートに焦点を当てることもできます。

![デバイスアラート検出ソースカード](./media/security-docs/device-alert-detection-sources.png)

このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>アラートを発生させる脅威の種類を理解する

Microsoft Defender ATP は、各アラートを、アタックチェーンまたは脅威コンポーネントの特定の段階を表すカテゴリに分類します。 たとえば、検出された脅威アクティビティは、ネットワーク上の他のデバイスに接続しようとしたときに、攻撃者が初期 foothold を取得した後に発生した可能性があることを示すために、"左右の移動" に分類されます。 検出された場合、脅威コンポーネントは、「マルウェア」、または特に「ランサムウェア」、「資格情報の盗用」、またはその他の悪意のあるソフトウェアまたは望ましくないソフトウェアとして分類されます。

**デバイスの脅威カテゴリ**カードには、これらのカテゴリへのアラートの配布が表示されます。 この情報を使用して、資格情報の盗難などの脅威のアクティビティを識別できます。たとえば、ソーシャルエンジニアリングの試行と比較して、より重大な影響を与える可能性があります。 これを使用して、ランサムウェアなどの潜在的な破壊的脅威を監視することもできます。

![デバイスの脅威カテゴリカード](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>アクティブなアラートを監視する

**デバイス通知ステータス**カードは、解決されておらず、注意が必要なアラートの数を示しています。 このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。

![デバイスアラートステータスカード](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>解決されたアラートの分類を監視する

Microsoft Defender ATP 通知を解決するとき、セキュリティ担当者は通知を次のように確認するかどうかを指定できます。

* 実際の違反アクティビティまたは脅威コンポーネントを識別する真の通知
* 通常のアクティビティを誤って検出した false アラート

**デバイス通知分類**カードは、解決済みのアラートが true または誤通知として分類されているかどうかを示します。 このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。

注: 状況によっては、特定の通知に対して分類情報を使用できない場合があります。

![デバイスアラート分類カード](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>解決されたアラートの決定を監視する

解決時にアラートが true であるか false であるかを分類するだけでなく、セキュリティ担当者は、通知の検証中に検出された通常または悪意のあるアクティビティの種類を示す判断を行うことができます。

**デバイス通知判別**カードは、各アラートに対して提供される決定を示します。具体的には次のようになります。

* **APT** –高度な永続的脅威。検出されたアクティビティまたは脅威コンポーネントが、影響を受けるネットワークで foothold を取得するように設計された高度な違反の一部であることを示します。  
* **マルウェア**–悪意のあるファイルまたはコード
* **セキュリティ担当者**–セキュリティスタッフによって実行される通常のアクティビティ
* **セキュリティテスト**–実際の脅威をシミュレートし、セキュリティセンサーをトリガーし、通知を生成するように設計されたアクティビティまたはコンポーネントです。
* **不要なソフトウェア**–悪意のあるアプリやその他のソフトウェア。それ以外の場合は、ポリシーや使用規約に違反する
* **** その他: 指定された種類の下にない他の決定

このカードから、Microsoft Defender セキュリティセンターの詳細情報を表示することができます。

![デバイスのアラート判別カード](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>危険にさらされているデバイスを理解する

**デバイス保護**は、デバイスのリスクレベルを示しています。 リスクレベルは、デバイス上のアラートの種類や重要度などの要因に基づいています。

![デバイス保護カード](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Intune で管理されているデバイスの状態を監視および報告する

次のレポートには、Intune に登録されたデバイスからのデータが含まれています。 未登録のデバイスからのデータは含まれません。 これらのカードを表示できるのは、全体管理者のみです。

Intune 登録デバイスデータには次のものが含まれます。

* デバイスのポリシー準拠
* アクティブなマルウェアがあるデバイス
* デバイス上のマルウェアの種類
* デバイスのマルウェア
* マルウェアが検出されるデバイス
* マルウェアが検出されるユーザー

### <a name="monitor-device-compliance"></a>デバイスコンプライアンスを監視する

**デバイスのコンプライアンス**Intune に登録されているデバイスの数が、構成ポリシーに準拠していることを示します。

![デバイスコンプライアンスカード](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>マルウェアが検出されるデバイスを検出する

**デバイスマルウェアの検出**は、保留中のアクション (再起動、完全なスキャン、または手動のユーザー操作) によって完全に解決されていないマルウェアを含む Intune 登録済みデバイスの数を示します。また、修復アクションが正常に完了していない場合もあります。

![デバイスマルウェア検出カード](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>検出されたマルウェアの種類を理解する

**デバイス上のマルウェアの種類**は、Intune に登録されたデバイスで検出されたさまざまな種類のマルウェアを示しています。 Microsoft 365 セキュリティセンターでは、それぞれの種類を調べることができます。

![デバイスカードのマルウェアの種類](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>デバイスで検出された特定のマルウェアについて理解する

**デバイス上のマルウェア**は、デバイスで検出された特定のマルウェアの一覧を提供します。

![デバイスカードのマルウェア](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>最もマルウェアがあるデバイスを理解する

**マルウェアが検出**されたデバイスには、マルウェアの検出数が最も多いデバイスが表示されます。 Microsoft 365 セキュリティセンターでは、マルウェアがアクティブであるかどうか、デバイスを使用しているかどうか、および Intune での管理状態を調査できます。

![マルウェア検出カードがあるデバイス](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>最も多くのマルウェアがあるデバイスをどのユーザーが所有しているかを理解する

**マルウェアが検出**されたユーザーには、マルウェアが検出されたデバイスを持つユーザーが表示されます。 Microsoft 365 セキュリティセンターでは、各ユーザーに割り当てられているデバイスの数と、各デバイスおよびマルウェアの種類に関する詳細情報を表示できます。

![マルウェア検出カードを使用するユーザー](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a>ASR ルールの展開と検出を監視および管理する

[Attack Surface Reduction (ASR) ルール](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)は、一般的に悪用される行為やアプリを阻止するのに役立ちます。マルウェアに感染したコンピューターに感染します。 これらのルールは、実行可能ファイルをいつどのように実行するかを制御します。 たとえば、JavaScript または VBScript がダウンロードされた実行可能ファイルを起動したり、Office マクロからの Win32 API 呼び出しをブロックしたり、USB ドライブから実行するブロックプロセスを禁止したりすることができます。

![アタック表面減少カード](./media/security-docs/attack-surface-reduction-rules.png)

「 **Attack surface reduction rules** card」では、デバイス全体にわたるルールの展開の概要を説明します。

カードの上部のバーには、次の展開モードになっているデバイスの合計数が表示されます。

* **ブロックモード**–検出されたアクティビティをブロックするように少なくとも1つのルールを持つデバイス
* **監査モード**–検出されたアクティビティをブロックするようにルールが設定されていないデバイスが検出されたアクティビティを監査するために少なくとも1つのルールを設定している  
* **オフ**–すべての ASR ルールがオフになっているデバイス

このカードの下の部分には、デバイス全体の設定がルール別に表示されます。 各棒は、検出をブロックまたは監査するように設定されているデバイスの数、または規則が完全にオフになっていることを示します。

### <a name="view-asr-detections"></a>ASR 検出を表示する

ネットワーク内の ASR ルールの検出に関する詳細情報を表示するには、[ **Attack surface reduction ルール**カード] の [**検出の表示**] を選択します。 [詳細レポート] ページの [**検出**] タブが開きます。

![[検出] タブ](./media/security-docs/detections-tab.png)

ページ上部のグラフには、ブロックまたは監査された時間帯の検出の検出が表示されます。 下部の表には、最新の検出が表示されます。 次の表の情報を使用して、検出の性質を理解してください。

* **検出さ**れたファイル–通常はスクリプトまたはドキュメントで、発生の疑いがある攻撃の内容を引き起こしたファイル。
* **ルール**: ルールが検出するように設計されたアタックアクティビティを記述する名前。 既存の ASR ルールについての情報を読む
* **ソースアプリ**–攻撃の疑いのある活動をトリガーするコンテンツを読み込んだ、または実行したアプリケーション。 これは、web ブラウザー、Office アプリケーション、PowerShell のようなシステムツールなどの正当なアプリケーションである可能性があります。
* **Publisher** –ソースアプリをリリースしたベンダー

### <a name="review-device-asr-rule-settings"></a>デバイス ASR ルールの設定を確認する

[ **Attack surface reduction ルール**レポート] ページで、[**構成**] タブに移動して個々のデバイスのルールの設定を確認します。 デバイスを選択して、各ルールがブロックモード、監査モード、または完全にオフになっているかどうかに関する詳細情報を取得します。

![[構成] タブ](./media/security-docs/configuration-tab.png)

Microsoft Intune は、ASR ルールの管理機能を提供します。 設定を更新する場合は、タブの [デバイスの**構成**] の [**開始**] を選択して、Intune でデバイス管理を開きます。

### <a name="exclude-files-from-asr-rules"></a>ASR ルールからファイルを除外する

Microsoft 365 セキュリティセンターでは、攻撃対象から[除外する可能性のあるファイル](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive)の名前を検出します。 ファイルを除外することで、誤検知を減らすことができます。ブロックモードでは、攻撃対象領域の削減ルールをより確実に展開することができます。

除外は Microsoft Intune で管理されますが、Microsoft 365 セキュリティセンターには、ファイルを理解するのに役立つ分析ツールが用意されています。 除外するファイルの収集を開始するには、[ **Attack surface reduction ルール**レポート] ページの [**除外の追加**] タブに移動します。

>[!NOTE]  
>このツールでは、すべての攻撃対象領域の削減ルールによって検出が分析されますが、[一部のルールのみが除外をサポート](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules)します。

![[除外の追加] タブ](./media/security-docs/add-exclusions-tab.png)

攻撃対象領域の削減ルールによって検出されたすべてのファイル名の一覧を示します。 ファイルを選択して、それらを除外した場合の影響を確認できます。

* 検出回数を減らす
* 検出を報告するデバイス数の削減

選択したファイルの完全パスを除外するには、[除外する**パスを取得**する] を選択します。

**Windows ローカルセキュリティ機関サブシステム (lsass.exe) から**の ASR ルールブロックの資格情報のログは、ソースアプリ**lsass.exe**(通常のシステムファイル) を検出されたファイルとしてキャプチャします。 そのため、生成された除外パスの一覧には、このファイルが含まれます。 **Lsass.exe**ではなく、このルールをトリガーしたファイルを除外するには、検出されたファイルの代わりにソースアプリへのパスを使用します。

ソースアプリを見つけるには、この特定のルールに対して次の[高度な検索クエリ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)を実行します (ルール ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 によって識別されます)。

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>ファイルの除外を確認する
ASR からファイルを除外する前に、ファイルを検査して、悪意がないかどうかを確認することをお勧めします。

ファイルを確認するには、Microsoft Defender セキュリティセンターの [[ファイル情報] ページ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files)を使用します。 このページには、流行の情報と、VirusTotal のウイルス検出率が表示されます。 ページを使用して、詳細な分析のためにファイルを送信することもできます。

Microsoft Defender セキュリティセンターで検出されたファイルを特定するには、次の高度な検索クエリを使用して、すべての ASR 検出を検索します。

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

結果で**SHA1**または**InitiatingProcessSHA1**を使用して、Microsoft Defender セキュリティセンターのユニバーサル検索バーを使用してファイルを検索します。
