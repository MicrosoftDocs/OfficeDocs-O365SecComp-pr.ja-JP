---
title: ドキュメント フィンガープリンティング
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: 組織内のインフォメーション ワーカーは、日常的にさまざまな種類の機密情報を処理します。 ドキュメント フィンガープリンティングは、組織全体で使用される標準フォームを特定することによってこの情報の保護を容易にします。 このトピックでは、ドキュメントフィンガープリンティングの背後にある概念と、PowerShell を使用して作成する方法について説明します。
ms.openlocfilehash: a90cb0c7fdfe5e350c9d97adb9a8f357f526742a
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638994"
---
# <a name="document-fingerprinting"></a>ドキュメント フィンガープリンティング

組織内のインフォメーション ワーカーは、日常的にさまざまな種類の機密情報を処理します。 セキュリティ&amp;コンプライアンスセンターでは、ドキュメントフィンガープリンティングにより、組織全体で使用される標準フォームを識別することにより、この情報をより簡単に保護することができます。 このトピックでは、ドキュメントフィンガープリンティングの背後にある概念と、PowerShell を使用して作成する方法について説明します。
  
## <a name="basic-scenario-for-document-fingerprinting"></a>ドキュメント フィンガープリンティングに関する基本的なシナリオ

ドキュメントフィンガープリンティングは、標準フォームを機密情報の種類に変換するデータ損失防止 (DLP) 機能です。これは、dlp ポリシーのルールで使用できます。 たとえば、空白の特許テンプレートに基づいてドキュメントフィンガープリントを作成してから、機密コンテンツが入力されたすべての特許申請書を検出してブロックする DLP ポリシーを作成できます。 必要に応じて、機密情報を送信している可能性があることを送信者に通知する[ポリシーヒント](use-notifications-and-policy-tips.md)を設定することができます。また、送信者は、受信者が特許を受信することが認められていることを確認する必要があります。 このプロセスは、組織で使用されているテキストベースのフォームでも動作します。 アップロードできるフォームのその他の例を次に示します。 
  
- 政府機関フォーム
    
- Health Insurance Portability and Accountability Act (HIPAA) 準拠フォーム
    
- 人事部門の従業員情報フォーム
    
- 組織用に特別に作成されたカスタム フォーム
    
組織で機密情報を送信するときに特定のフォームを使用するという業務習慣が既に確立されていることが理想的です。 ドキュメントのフィンガープリントに変換される空のフォームをアップロードし、対応するポリシーを設定すると、その指紋に一致する送信メール内のすべてのドキュメントが DLP によって検出されます。
  
## <a name="how-document-fingerprinting-works"></a>ドキュメント フィンガープリンティングのしくみ

ドキュメントに実際の指紋があるわけではありませんが、名前からその機能を想像することができます。 人間の指紋に固有のパターンがあるように、ドキュメントにも固有の単語パターンがあります。 ファイルをアップロードすると、DLP はドキュメント内の一意の単語パターンを識別し、そのパターンに基づいてドキュメントフィンガープリントを作成し、そのドキュメントフィンガープリントを使用して同じパターンを含む送信ドキュメントを検出します。 これにより、フォームまたはテンプレートをアップロードすると、ドキュメント フィンガープリントの最も有効なタイプが作成されます。 フォームに記入するユーザーは全員同じオリジナルの単語セットを使用し、その上で独自の単語をドキュメントに追加します。 送信ドキュメントがパスワードで保護されておらず、元のフォームのすべてのテキストが含まれている限り、DLP でドキュメントがドキュメントフィンガープリントと一致するかどうかを判断できます。
  
次の例では、特許情報テンプレートに基づいてドキュメント フィンガープリントを作成した場合に何が行われるかを示しています。ただし、ドキュメント フィンガープリントは、任意のフォームに基づいて作成できます。
  
**特許情報テンプレートのドキュメント フィンガープリントと一致する特許情報ドキュメントの例**

![Document_Fingerprinting_diagram](media/Document_Fingerprinting_diagram.png)
  
特許テンプレートには、「特許役職」、「Inventors」、「説明」、および「Description」、および各フィールドの説明 (word パターン) が含まれています。 元の特許テンプレートをアップロードすると、サポートされているファイルの種類とテキスト形式のいずれかになります。 DLP この単語パターンは、元のテキストを表す一意のハッシュ値を含む小さな Unicode XML ファイルであるドキュメント指紋に変換され、指紋は Active Directory 内のデータ分類として保存されます。 (セキュリティ対策として、元のドキュメント自体はサービスに格納されず、ハッシュ値のみが格納され、元のドキュメントをハッシュ値から再構築することはできません)。その後、特許指紋は、DLP ポリシーに関連付けることができる機密情報の種類になります。 指紋を dlp ポリシーに関連付けた後、dlp は特許指紋に一致するドキュメントを含む送信メールを検出し、組織のポリシーに従ってそれらを処理します。 

たとえば、通常の従業員が特許を含む送信メッセージを送信できないようにする DLP ポリシーを設定することができます。 DLP は特許指紋を使用して特許を検出し、それらの電子メールをブロックします。 別の方法として、法務部門ではそのような業務が必要になるため、他の組織に特許を送信できるようにすることもできます。 特定の部門に対して、DLP ポリシーでその部門の例外を作成することによって機密情報を送信することを許可したり、業務上の理由を使用してポリシーヒントを上書きすることを許可したりできます。
  
### <a name="supported-file-types"></a>サポートされているファイルの種類

ドキュメントフィンガープリンティングは、メールフロールール (トランスポートルールとも呼ばれる) でサポートされているものと同じ種類のファイルをサポートしています。 サポートされているファイルの種類の一覧については、「[メールフロールールコンテンツ検査でサポートされているファイルの種類](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)」を参照してください。 ファイルの種類に関するクイックメモ: メールフロールールもドキュメントフィンガープリンティングもサポートしていません。 .dotx ファイルの種類は、Word のテンプレートファイルなので、紛らわしい場合があります。 この記事とその他のドキュメントフィンガープリンティングの「テンプレート」という語が表示されている場合は、標準フォームとして設定したドキュメントを参照してください。テンプレートファイルの種類ではありません。
  
#### <a name="limitations-of-document-fingerprinting"></a>ドキュメント フィンガープリンティングの制限

ドキュメントフィンガープリンティングは、次の場合に機密情報を検出しません。
  
- パスワードで保護されたファイル
    
- イメージのみが含まれているファイル
    
- ドキュメント フィンガープリントの作成に使用されたオリジナルのフォームのテキストがすべて含まれていないドキュメント
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>PowerShell を使用してドキュメントフィンガープリントに基づいて分類ルールパッケージを作成する

現時点では、セキュリティ&amp; /コンプライアンスセンターで PowerShell を使用することによってのみ、ドキュメントフィンガープリントを作成できます。 接続するには、「 [connect to Office 365 Security & コンプライアンスセンター PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。

DLP は、分類ルールパッケージを使用して機密コンテンツを検出します。 ドキュメントのフィンガープリントに基づいて分類ルールパッケージを作成するには、**新しい-dlpfingerprint**および**set-dlpsensitiveinformationtype**コマンドレットを使用します。 **新しい-dlpfingerprint**の結果はデータ分類規則の範囲外に格納されないため**** 、常に、 **set-dlpsensitiveinformationtype**または**set-dlpsensitiveinformationtype**を同じように実行します。PowerShell セッション。 次の例では、C:\My Documents\Contoso Employee Template.docx ファイルに基づいて新しいドキュメント フィンガープリントを作成します。 同じ PowerShell セッションで **New-DlpSensitiveInformationType** コマンドレットを使用して新しい指紋を使用できるように、新しい指紋を変数として保存します。 
  
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

**set-dlpsensitiveinformationtype**コマンドレットを使用して、すべての DLP データ分類ルールパッケージを検索できるようになりました。この例では、"Contoso Customer Confidential" はデータ分類規則パッケージリストに含まれています。 
  
最後に、セキュリティ&amp;コンプライアンスセンターで、"Contoso Customer Confidential" データ分類ルールパッケージを DLP ポリシーに追加します。 この例では、"ConfidentialPolicy" という名前の既存の DLP ポリシーにルールを追加します。

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

次の例に示すように、Exchange Online のメールフロールールでデータ分類ルールパッケージを使用することもできます。 このコマンドを実行するには、まず[Exchange Online PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)する必要があります。 また、ルールパッケージがセキュリティ&amp;コンプライアンスセンターから Exchange 管理センターに同期されるまでに時間がかかることにも注意してください。
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP が、コントソ Customer Form .docx ドキュメント指紋に一致するドキュメントを検出するようになりました。
  
構文およびパラメーターの詳細については、以下を参照してください。

- [新-dlpfingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [set-dlpsensitiveinformationtype](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [set-dlpsensitiveinformationtype](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [set-dlpsensitiveinformationtype](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [set-dlpsensitiveinformationtype](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
