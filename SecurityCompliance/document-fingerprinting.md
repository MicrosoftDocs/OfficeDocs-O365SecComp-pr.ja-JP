---
title: ドキュメント フィンガープリンティング
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 1e0c579c-26e0-462a-a1b0-d7506dfe05fa
description: 組織内のインフォメーションワーカーは、一般的な日にさまざまな種類の機密情報を処理します。ドキュメントフィンガープリンティングは、組織全体で使用される標準フォームを識別することにより、この情報をより簡単に保護できるようにします。このトピックでは、ドキュメントフィンガープリンティングの背後にある概念と、PowerShell を使用して作成する方法について説明します。
ms.openlocfilehash: 20b9f59902c52d347e7c439cb6f380ee9fd4a30e
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341288"
---
# <a name="document-fingerprinting"></a><span data-ttu-id="68c4c-105">ドキュメント フィンガープリンティング</span><span class="sxs-lookup"><span data-stu-id="68c4c-105">Document Fingerprinting</span></span>

<span data-ttu-id="68c4c-p102">組織内のインフォメーションワーカーは、一般的な日にさまざまな種類の機密情報を処理します。セキュリティ&amp;コンプライアンスセンターでは、ドキュメントフィンガープリンティングにより、組織全体で使用される標準フォームを識別することにより、この情報をより簡単に保護することができます。このトピックでは、ドキュメントフィンガープリンティングの背後にある概念と、PowerShell を使用して作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p102">Information workers in your organization handle many kinds of sensitive information during a typical day. In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization. This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="68c4c-109">ドキュメント フィンガープリンティングに関する基本的なシナリオ</span><span class="sxs-lookup"><span data-stu-id="68c4c-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="68c4c-p103">ドキュメントフィンガープリンティングは、標準フォームを機密情報の種類に変換するデータ損失防止 (DLP) 機能です。これは、dlp ポリシーのルールで使用できます。たとえば、空白の特許テンプレートに基づいてドキュメントフィンガープリントを作成してから、機密コンテンツが入力されたすべての特許申請書を検出してブロックする DLP ポリシーを作成できます。必要に応じて、機密情報を送信している可能性があることを送信者に通知する[ポリシーヒント](use-notifications-and-policy-tips.md)を設定することができます。また、送信者は、受信者が特許を受信することが認められていることを確認する必要があります。このプロセスは、組織で使用されているテキストベースのフォームでも動作します。アップロードできるフォームのその他の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p103">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies. For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in. Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents. This process works with any text-based forms used in your organization. Additional examples of forms that you can upload include:</span></span> 
  
- <span data-ttu-id="68c4c-115">政府機関フォーム</span><span class="sxs-lookup"><span data-stu-id="68c4c-115">Government forms</span></span>
    
- <span data-ttu-id="68c4c-116">Health Insurance Portability and Accountability Act (HIPAA) 準拠フォーム</span><span class="sxs-lookup"><span data-stu-id="68c4c-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>
    
- <span data-ttu-id="68c4c-117">人事部門の従業員情報フォーム</span><span class="sxs-lookup"><span data-stu-id="68c4c-117">Employee information forms for Human Resources departments</span></span>
    
- <span data-ttu-id="68c4c-118">組織用に特別に作成されたカスタム フォーム</span><span class="sxs-lookup"><span data-stu-id="68c4c-118">Custom forms created specifically for your organization</span></span>
    
<span data-ttu-id="68c4c-p104">組織によっては、機密情報を送信するために特定のフォームを使用するというビジネスプラクティスが既に確立されています。ドキュメントのフィンガープリントに変換される空のフォームをアップロードし、対応するポリシーを設定すると、その指紋に一致する送信メール内のすべてのドキュメントが DLP によって検出されます。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p104">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information. After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>
  
## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="68c4c-121">ドキュメント フィンガープリンティングのしくみ</span><span class="sxs-lookup"><span data-stu-id="68c4c-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="68c4c-p105">ドキュメントに実際の指紋がありませんが、名前によって機能の説明がわかります。個人の指紋に固有のパターンが設定されているのと同じように、ドキュメントには一意の単語パターンがあります。ファイルをアップロードすると、DLP はドキュメント内の一意の単語パターンを識別し、そのパターンに基づいてドキュメントフィンガープリントを作成し、そのドキュメントフィンガープリントを使用して同じパターンを含む送信ドキュメントを検出します。そのため、フォームまたはテンプレートをアップロードすると、ドキュメントフィンガープリントの最も効果的な種類が作成されます。フォームに入力したすべてのユーザーは、同じ元の単語セットを使用して、自分の単語を文書に追加します。送信ドキュメントがパスワードで保護されておらず、元のフォームのすべてのテキストが含まれている限り、DLP でドキュメントがドキュメントフィンガープリントと一致するかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p105">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature. In the same way that a person's fingerprints have unique patterns, documents have unique word patterns. When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern. That's why uploading a form or template creates the most effective type of document fingerprint. Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document. As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>
  
<span data-ttu-id="68c4c-128">次の例では、特許情報テンプレートに基づいてドキュメント フィンガープリントを作成した場合に何が行われるかを示しています。ただし、ドキュメント フィンガープリントは、任意のフォームに基づいて作成できます。</span><span class="sxs-lookup"><span data-stu-id="68c4c-128">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
<span data-ttu-id="68c4c-129">**特許情報テンプレートのドキュメント フィンガープリントと一致する特許情報ドキュメントの例**</span><span class="sxs-lookup"><span data-stu-id="68c4c-129">**Example of a patent document matching a document fingerprint of a patent template**</span></span>

![Document_Fingerprinting_diagram](media/Document_Fingerprinting_diagram.png)
  
<span data-ttu-id="68c4c-p106">特許テンプレートには、「特許役職」、「Inventors」、「説明」、および「Description」、および各フィールドの説明 (word パターン) が含まれています。元の特許テンプレートをアップロードすると、サポートされているファイルの種類とテキスト形式のいずれかになります。DLP この単語パターンは、元のテキストを表す一意のハッシュ値を含む小さな Unicode XML ファイルであるドキュメント指紋に変換され、指紋は Active Directory 内のデータ分類として保存されます。(セキュリティ対策として、元のドキュメント自体はサービスに格納されず、ハッシュ値のみが格納され、元のドキュメントをハッシュ値から再構築することはできません)。その後、特許指紋は、DLP ポリシーに関連付けることができる機密情報の種類になります。指紋を dlp ポリシーに関連付けた後、dlp は特許指紋に一致するドキュメントを含む送信メールを検出し、組織のポリシーに従ってそれらを処理します。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p106">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern. When you upload the original patent template, it's in one of the supported file types and in plain text. DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory. (As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy. After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="68c4c-p107">たとえば、通常の従業員が特許を含む送信メッセージを送信できないようにする DLP ポリシーを設定することができます。DLP は特許指紋を使用して特許を検出し、それらの電子メールをブロックします。別の方法として、法務部門ではそのような業務が必要になるため、他の組織に特許を送信できるようにすることもできます。特定の部門に対して、DLP ポリシーでその部門の例外を作成することによって機密情報を送信することを許可したり、業務上の理由を使用してポリシーヒントを上書きすることを許可したりできます。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p107">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents. DLP will use the patent fingerprint to detect patents and block those emails. Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so. You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="68c4c-140">サポートされているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="68c4c-140">Supported file types</span></span>

<span data-ttu-id="68c4c-p108">ドキュメントフィンガープリンティングは、メールフロールール (トランスポートルールとも呼ばれる) でサポートされているものと同じ種類のファイルをサポートしています。サポートされているファイルの種類の一覧については、「[メールフロールールコンテンツ検査でサポートされているファイルの種類](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)」を参照してください。ファイルの種類に関するクイックメモ: メールフロールールもドキュメントフィンガープリンティングもサポートしていません。 .dotx ファイルの種類は、Word のテンプレートファイルなので、紛らわしい場合があります。この記事とその他のドキュメントフィンガープリンティングの「テンプレート」という語が表示されている場合は、標準フォームとして設定したドキュメントを参照してください。テンプレートファイルの種類ではありません。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p108">Document Fingerprinting supports the same file types that are supported in mail flow rules (also known as transport rules). For a list of supported file types, see [Supported file types for mail flow rule content inspection](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). One quick note about file types: neither mail flow rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word. When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="68c4c-145">ドキュメント フィンガープリンティングの制限</span><span class="sxs-lookup"><span data-stu-id="68c4c-145">Limitations of document fingerprinting</span></span>

<span data-ttu-id="68c4c-146">ドキュメントフィンガープリンティングは、次の場合に機密情報を検出しません。</span><span class="sxs-lookup"><span data-stu-id="68c4c-146">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="68c4c-147">パスワードで保護されたファイル</span><span class="sxs-lookup"><span data-stu-id="68c4c-147">Password protected files</span></span>
    
- <span data-ttu-id="68c4c-148">イメージのみが含まれているファイル</span><span class="sxs-lookup"><span data-stu-id="68c4c-148">Files that contain only images</span></span>
    
- <span data-ttu-id="68c4c-149">ドキュメント フィンガープリントの作成に使用されたオリジナルのフォームのテキストがすべて含まれていないドキュメント</span><span class="sxs-lookup"><span data-stu-id="68c4c-149">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="68c4c-150">PowerShell を使用してドキュメントフィンガープリントに基づいて分類ルールパッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="68c4c-150">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="68c4c-p109">現時点では、セキュリティ&amp; /コンプライアンスセンターで PowerShell を使用することによってのみ、ドキュメントフィンガープリントを作成できます。接続するには、「 [connect to Office 365 Security & コンプライアンスセンター PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p109">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center. To connect, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="68c4c-p110">DLP は、分類ルールパッケージを使用して機密コンテンツを検出します。ドキュメントのフィンガープリントに基づいて分類ルールパッケージを作成するには、**新しい-dlpfingerprint**および**set-dlpsensitiveinformationtype**コマンドレットを使用します。**新しい-dlpfingerprint**の結果はデータ分類規則の範囲外に格納されないため\*\*\*\* 、常に、 **set-dlpsensitiveinformationtype**または**set-dlpsensitiveinformationtype**を同じように実行します。PowerShell セッション。次の例では、ファイル C:\My documents\contoso employee template.docx Employee テンプレート .docx に基づいて新しいドキュメントフィンガープリントを作成します。新しい指紋を変数として保存し、同じ PowerShell セッションで**set-dlpsensitiveinformationtype**コマンドレットで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p110">DLP uses classification rule packages to detect sensitive content. To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets. Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session. The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx. You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span> 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="68c4c-158">ここで、C:\My Documents\Contoso Customer Information Form.docx ファイルのドキュメント フィンガープリントを使用する、"Contoso Employee Confidential" という名前の新しいデータ分類ルールを作成してみましょう。</span><span class="sxs-lookup"><span data-stu-id="68c4c-158">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="68c4c-159">**set-dlpsensitiveinformationtype**コマンドレットを使用して、すべての DLP データ分類ルールパッケージを検索できるようになりました。この例では、"Contoso Customer Confidential" はデータ分類規則パッケージリストに含まれています。</span><span class="sxs-lookup"><span data-stu-id="68c4c-159">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="68c4c-p111">最後に、セキュリティ&amp;コンプライアンスセンターで、"Contoso Customer Confidential" データ分類ルールパッケージを DLP ポリシーに追加します。この例では、"ConfidentialPolicy" という名前の既存の DLP ポリシーにルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p111">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center. This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="68c4c-p112">次の例に示すように、Exchange Online のメールフロールールでデータ分類ルールパッケージを使用することもできます。このコマンドを実行するには、まず[Exchange Online PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)する必要があります。また、ルールパッケージがセキュリティ&amp;コンプライアンスセンターから Exchange 管理センターに同期されるまでに時間がかかることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="68c4c-p112">You can also use the data classification rule package in mail flow rules in Exchange Online, as shown in the following example. To run this command, you first need to [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange admin center.</span></span>
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

<span data-ttu-id="68c4c-165">DLP が、コントソ Customer Form .docx ドキュメント指紋に一致するドキュメントを検出するようになりました。</span><span class="sxs-lookup"><span data-stu-id="68c4c-165">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="68c4c-166">構文およびパラメーターの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68c4c-166">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="68c4c-167">新-dlpfingerprint</span><span class="sxs-lookup"><span data-stu-id="68c4c-167">New-DlpFingerprint</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [<span data-ttu-id="68c4c-168">set-dlpsensitiveinformationtype</span><span class="sxs-lookup"><span data-stu-id="68c4c-168">New-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [<span data-ttu-id="68c4c-169">set-dlpsensitiveinformationtype</span><span class="sxs-lookup"><span data-stu-id="68c4c-169">Remove-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="68c4c-170">set-dlpsensitiveinformationtype</span><span class="sxs-lookup"><span data-stu-id="68c4c-170">Set-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="68c4c-171">set-dlpsensitiveinformationtype</span><span class="sxs-lookup"><span data-stu-id="68c4c-171">Get-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
