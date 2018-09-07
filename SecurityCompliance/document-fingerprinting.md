---
title: ドキュメント フィンガープリンティング
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 1e0c579c-26e0-462a-a1b0-d7506dfe05fa
description: 組織内のインフォメーション ワーカーは、さまざまな種類の典型的な 1 日の中に機密情報を処理します。文書 Fingerprinting では、組織全体で使用される標準のフォームを識別することによってこの情報を保護することが容易になります。このトピックでは、ドキュメントのフィンガー プリントと PowerShell を使用して作成する方法の概念について説明します。
ms.openlocfilehash: d73b769e7a014f2642a0fcd66cc6a500c68c46c3
ms.sourcegitcommit: 4be502d1fc6cbaef4c72d599758d51efe3a173c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "23867501"
---
# <a name="document-fingerprinting"></a>ドキュメント フィンガープリンティング

組織内のインフォメーション ワーカーは、さまざまな種類の典型的な 1 日の中に機密情報を処理します。セキュリティ&amp;コンプライアンス センター、文書の指紋と、簡単に組織全体で使用される標準のフォームを識別することによってこの情報を保護することです。このトピックでは、ドキュメントのフィンガー プリントと PowerShell を使用して作成する方法の概念について説明します。
  
## <a name="basic-scenario-for-document-fingerprinting"></a>ドキュメント フィンガープリンティングに関する基本的なシナリオ

ドキュメントの Fingerprinting は、標準のフォームを DLP ポリシーの規則で使用することができます、機密性の高い情報の種類に変換するデータ損失防止 (DLP) 機能です。たとえば、特許の空のテンプレートに基づくドキュメントのフィンガー プリントを作成でき、DLP ポリシーを検出して機密性の高いコンテンツを持つすべての送信特許テンプレートの入力ブロックを作成できます。必要に応じて、機密情報を送信する可能性があります、その送信者が、受信者がこれらの特許を受け取るための資格を確認する必要があります送信者に通知する[ポリシーのヒント](use-notifications-and-policy-tips.md)を設定できます。このプロセスは、組織で使用されている任意のテキスト ベースのフォームで動作します。アップロードできるフォームの他の例は次のとおりです。 
  
- 政府機関フォーム
    
- Health Insurance Portability and Accountability Act (HIPAA) 準拠フォーム
    
- 人事部門の従業員情報フォーム
    
- 組織用に特別に作成されたカスタム フォーム
    
理想的が存在する確立された業務の機密情報を送信する特定の形式を使用します。文書の指紋に変換され、対応するポリシーを設定するのには空のフォームをアップロードした後、DLP はその指紋が一致する送信メールのすべてのドキュメントを検出します。
  
## <a name="how-document-fingerprinting-works"></a>ドキュメント フィンガープリンティングのしくみ

ドキュメントは、実際の指紋を持っていないが、機能を説明する名前は、既に気付いたしました。人の指紋は、独自のパターンであるのと同じように、ドキュメントでは一意な単語のパターンがあります。ファイルをアップロードすると、DLP はドキュメントの一意な単語のパターンを識別、そのパターンに基づくドキュメントのフィンガー プリントを作成し、その文書の指紋を使用して、同じパターンが含まれているドキュメントと送信ドキュメントを検出するために。フォームをアップロードするためまたはテンプレートは、最も効果的な文書の指紋の種類を作成します。すべてのユーザーがフォームの入力単語の元の同じセットを使用して、文書に、自分の単語を追加限り、送信ドキュメントはパスワードで保護をされていないし、元のフォームからすべてのテキストが含まれています、DLP は、ドキュメントにドキュメントの指紋が一致したかどうかを確認できます。
  
次の例では、特許情報テンプレートに基づいてドキュメント フィンガープリントを作成した場合に何が行われるかを示しています。ただし、ドキュメント フィンガープリントは、任意のフォームに基づいて作成できます。
  
**特許情報テンプレートのドキュメント フィンガープリントと一致する特許情報ドキュメントの例**

![Document_Fingerprinting_diagram.png](media/Document_Fingerprinting_diagram.png)
  
特許のテンプレートには、「特許のタイトル、「空白のフィールドが含まれています「発明家、」し [説明] と各フィールドの説明: 単語パターンです。特許元のテンプレートをアップロードすることがサポートされているファイルの種類のいずれかで、テキスト形式でです。DLP の変換元のテキスト、および指紋を表す一意のハッシュ値を含むファイルの小さな Unicode xml ドキュメント指紋認証にこの単語のパターンは、Active Directory 内のデータのクラス分けとして保存されます。(セキュリティ上の手段として、元のドキュメント自体がサービスに格納されていない; ハッシュ値のみが格納されているとハッシュ値から元のドキュメントを再構築することはできません)特許の指紋、DLP ポリシーに関連付けることができる機密情報の種類になります。指紋を関連付けるには、DLP ポリシーを使用して後、DLP は特許の指紋が一致するドキュメントが含まれている送信された e メールを検出し、組織のポリシーに従って処理します。 

たとえば、正規従業員が特許を含む、送信メッセージの送信を禁止する DLP ポリシーを設定する可能性があります。DLP は特許を検出し、それらの電子メールをブロックする特許のフィンガー プリントを使用します。または、これを行うに必要な業務があるために、特許を他の組織に送ることができることは、法務部門をできるようにすることができます。特定の部門、DLP ポリシーで、これらの部門の例外を作成することで機密情報を送信することができます。 または業務の妥当性を持つポリシー ヒントをオーバーライドすることを許可できます。
  
### <a name="supported-file-types"></a>サポートされているファイルの種類

ドキュメントの Fingerprinting には、トランスポート ルールでサポートされている同じファイルの種類がサポートされています。サポートされているファイルの種類のリストは、[メール フロー ルールのコンテンツの検査のためのサポートされているファイルの種類](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)を参照してください。ファイルの種類の 1 つのクイック注: トランスポート ルールとドキュメントのフィンガー プリントのどちらもサポートしています .dotx ファイルの種類にすることが混乱を Word でテンプレート ファイルであるためです。Word およびその他の文書の指紋のトピックには、「テンプレート」を参照してください、とすると、テンプレート ファイルの種類ではない標準のフォームとして設定するドキュメントを参照します。
  
#### <a name="limitations-of-document-fingerprinting"></a>ドキュメント フィンガープリンティングの制限

ドキュメントの Fingerprinting は、次の場合に機密情報を認識できません。
  
- パスワードで保護されたファイル
    
- イメージのみが含まれているファイル
    
- ドキュメント フィンガープリントの作成に使用されたオリジナルのフォームのテキストがすべて含まれていないドキュメント
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>PowerShell を使用して、ドキュメントのフィンガー プリントに基づくクラス分けルール パッケージを作成するには

PowerShell を使用してセキュリティでのみドキュメントのフィンガー プリントを作成すること現在ことができます&amp;コンプライアンス センターです。接続するには、 [Office 365 のセキュリティとコンプライアンス センター PowerShell への接続](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)を参照してください。

DLP では、機密性の高いコンテンツを検出するためにクラス分け規則のパッケージを使用します。文書の指紋認証に基づくクラス分けルール パッケージを作成するには、**新規 DlpFingerprint**および**新しい DlpSensitiveInformationType**コマンドレットを使用します。同じでは、**新規 DlpFingerprint**および**新しい DlpSensitiveInformationType**または**セット DlpSensitiveInformationType**を常に実行するため、**新規 DlpFingerprint**の結果は、データの分類規則の外部に保存されていない、PowerShell セッションです。C:\My Documents\Contoso の従業員の Template.docx ファイルに基づく新しい文書の指紋を作成する例を次にします。PowerShell セッションを同時に**新規 DlpSensitiveInformationType**コマンドレットを使用できるように、変数として、新たな指紋を格納します。 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

ここで、C:\My Documents\Contoso Customer Information Form.docx ファイルのドキュメント フィンガープリントを使用する、"Contoso Employee Confidential" という名前の新しいデータ分類ルールを作成してみましょう。
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

DLP データのクラス分けのルール、すべてのパッケージを検索するのには、 **Get DlpSensitiveInformationType**コマンドレットを使用することができますようになりましたし、この例では、「Contoso ユーザーは社外秘」は、データのクラス分けルール パッケージ] の一覧の一部です。 
  
最後に、「Contoso ユーザーは社外秘」のデータのクラス分けルール パッケージをセキュリティで DLP ポリシーに追加する&amp;コンプライアンス センターです。次の使用例では、"ConfidentialPolicy"という名前の既存の DLP ポリシーに規則を追加します。

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

次の例に示すように、Exchange online では、トランスポート ルールで、データのクラス分けルール パッケージを使用できます。このコマンドを実行するのには最初に[オンラインの PowerShell を Exchange に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)する必要があります。ルール パッケージのセキュリティの同期の時間がかかることにも注意してください&amp;Exchange 管理センターへのコンプライアンス センターです。
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP は、contoso 社の顧客の Form.docx の文書の指紋が一致するドキュメントを検出します。
  
構文とパラメーターについては、次のように表示されます。

- [新しい-DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [新しい-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [削除 DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [セット DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [Get DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
