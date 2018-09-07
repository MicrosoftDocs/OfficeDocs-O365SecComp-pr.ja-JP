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
# <a name="document-fingerprinting"></a><span data-ttu-id="734bc-105">ドキュメント フィンガープリンティング</span><span class="sxs-lookup"><span data-stu-id="734bc-105">Document Fingerprinting</span></span>

<span data-ttu-id="734bc-p102">組織内のインフォメーション ワーカーは、さまざまな種類の典型的な 1 日の中に機密情報を処理します。セキュリティ&amp;コンプライアンス センター、文書の指紋と、簡単に組織全体で使用される標準のフォームを識別することによってこの情報を保護することです。このトピックでは、ドキュメントのフィンガー プリントと PowerShell を使用して作成する方法の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="734bc-p102">Information workers in your organization handle many kinds of sensitive information during a typical day. In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization. This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="734bc-109">ドキュメント フィンガープリンティングに関する基本的なシナリオ</span><span class="sxs-lookup"><span data-stu-id="734bc-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="734bc-p103">ドキュメントの Fingerprinting は、標準のフォームを DLP ポリシーの規則で使用することができます、機密性の高い情報の種類に変換するデータ損失防止 (DLP) 機能です。たとえば、特許の空のテンプレートに基づくドキュメントのフィンガー プリントを作成でき、DLP ポリシーを検出して機密性の高いコンテンツを持つすべての送信特許テンプレートの入力ブロックを作成できます。必要に応じて、機密情報を送信する可能性があります、その送信者が、受信者がこれらの特許を受け取るための資格を確認する必要があります送信者に通知する[ポリシーのヒント](use-notifications-and-policy-tips.md)を設定できます。このプロセスは、組織で使用されている任意のテキスト ベースのフォームで動作します。アップロードできるフォームの他の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="734bc-p103">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies. For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in. Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents. This process works with any text-based forms used in your organization. Additional examples of forms that you can upload include:</span></span> 
  
- <span data-ttu-id="734bc-115">政府機関フォーム</span><span class="sxs-lookup"><span data-stu-id="734bc-115">Government forms</span></span>
    
- <span data-ttu-id="734bc-116">Health Insurance Portability and Accountability Act (HIPAA) 準拠フォーム</span><span class="sxs-lookup"><span data-stu-id="734bc-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>
    
- <span data-ttu-id="734bc-117">人事部門の従業員情報フォーム</span><span class="sxs-lookup"><span data-stu-id="734bc-117">Employee information forms for Human Resources departments</span></span>
    
- <span data-ttu-id="734bc-118">組織用に特別に作成されたカスタム フォーム</span><span class="sxs-lookup"><span data-stu-id="734bc-118">Custom forms created specifically for your organization</span></span>
    
<span data-ttu-id="734bc-p104">理想的が存在する確立された業務の機密情報を送信する特定の形式を使用します。文書の指紋に変換され、対応するポリシーを設定するのには空のフォームをアップロードした後、DLP はその指紋が一致する送信メールのすべてのドキュメントを検出します。</span><span class="sxs-lookup"><span data-stu-id="734bc-p104">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information. After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>
  
## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="734bc-121">ドキュメント フィンガープリンティングのしくみ</span><span class="sxs-lookup"><span data-stu-id="734bc-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="734bc-p105">ドキュメントは、実際の指紋を持っていないが、機能を説明する名前は、既に気付いたしました。人の指紋は、独自のパターンであるのと同じように、ドキュメントでは一意な単語のパターンがあります。ファイルをアップロードすると、DLP はドキュメントの一意な単語のパターンを識別、そのパターンに基づくドキュメントのフィンガー プリントを作成し、その文書の指紋を使用して、同じパターンが含まれているドキュメントと送信ドキュメントを検出するために。フォームをアップロードするためまたはテンプレートは、最も効果的な文書の指紋の種類を作成します。すべてのユーザーがフォームの入力単語の元の同じセットを使用して、文書に、自分の単語を追加限り、送信ドキュメントはパスワードで保護をされていないし、元のフォームからすべてのテキストが含まれています、DLP は、ドキュメントにドキュメントの指紋が一致したかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="734bc-p105">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature. In the same way that a person's fingerprints have unique patterns, documents have unique word patterns. When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern. That's why uploading a form or template creates the most effective type of document fingerprint. Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document. As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>
  
<span data-ttu-id="734bc-128">次の例では、特許情報テンプレートに基づいてドキュメント フィンガープリントを作成した場合に何が行われるかを示しています。ただし、ドキュメント フィンガープリントは、任意のフォームに基づいて作成できます。</span><span class="sxs-lookup"><span data-stu-id="734bc-128">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
<span data-ttu-id="734bc-129">**特許情報テンプレートのドキュメント フィンガープリントと一致する特許情報ドキュメントの例**</span><span class="sxs-lookup"><span data-stu-id="734bc-129">**Example of a patent document matching a document fingerprint of a patent template**</span></span>

![Document_Fingerprinting_diagram.png](media/Document_Fingerprinting_diagram.png)
  
<span data-ttu-id="734bc-p106">特許のテンプレートには、「特許のタイトル、「空白のフィールドが含まれています「発明家、」し [説明] と各フィールドの説明: 単語パターンです。特許元のテンプレートをアップロードすることがサポートされているファイルの種類のいずれかで、テキスト形式でです。DLP の変換元のテキスト、および指紋を表す一意のハッシュ値を含むファイルの小さな Unicode xml ドキュメント指紋認証にこの単語のパターンは、Active Directory 内のデータのクラス分けとして保存されます。(セキュリティ上の手段として、元のドキュメント自体がサービスに格納されていない; ハッシュ値のみが格納されているとハッシュ値から元のドキュメントを再構築することはできません)特許の指紋、DLP ポリシーに関連付けることができる機密情報の種類になります。指紋を関連付けるには、DLP ポリシーを使用して後、DLP は特許の指紋が一致するドキュメントが含まれている送信された e メールを検出し、組織のポリシーに従って処理します。</span><span class="sxs-lookup"><span data-stu-id="734bc-p106">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern. When you upload the original patent template, it's in one of the supported file types and in plain text. DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory. (As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy. After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="734bc-p107">たとえば、正規従業員が特許を含む、送信メッセージの送信を禁止する DLP ポリシーを設定する可能性があります。DLP は特許を検出し、それらの電子メールをブロックする特許のフィンガー プリントを使用します。または、これを行うに必要な業務があるために、特許を他の組織に送ることができることは、法務部門をできるようにすることができます。特定の部門、DLP ポリシーで、これらの部門の例外を作成することで機密情報を送信することができます。 または業務の妥当性を持つポリシー ヒントをオーバーライドすることを許可できます。</span><span class="sxs-lookup"><span data-stu-id="734bc-p107">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents. DLP will use the patent fingerprint to detect patents and block those emails. Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so. You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="734bc-140">サポートされているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="734bc-140">Supported file types</span></span>

<span data-ttu-id="734bc-p108">ドキュメントの Fingerprinting には、トランスポート ルールでサポートされている同じファイルの種類がサポートされています。サポートされているファイルの種類のリストは、[メール フロー ルールのコンテンツの検査のためのサポートされているファイルの種類](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)を参照してください。ファイルの種類の 1 つのクイック注: トランスポート ルールとドキュメントのフィンガー プリントのどちらもサポートしています .dotx ファイルの種類にすることが混乱を Word でテンプレート ファイルであるためです。Word およびその他の文書の指紋のトピックには、「テンプレート」を参照してください、とすると、テンプレート ファイルの種類ではない標準のフォームとして設定するドキュメントを参照します。</span><span class="sxs-lookup"><span data-stu-id="734bc-p108">Document Fingerprinting supports the same file types that are supported in transport rules. For a list of supported file types, see [Supported file types for mail flow rule content inspection](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). One quick note about file types: neither transport rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word. When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="734bc-145">ドキュメント フィンガープリンティングの制限</span><span class="sxs-lookup"><span data-stu-id="734bc-145">Limitations of document fingerprinting</span></span>

<span data-ttu-id="734bc-146">ドキュメントの Fingerprinting は、次の場合に機密情報を認識できません。</span><span class="sxs-lookup"><span data-stu-id="734bc-146">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="734bc-147">パスワードで保護されたファイル</span><span class="sxs-lookup"><span data-stu-id="734bc-147">Password protected files</span></span>
    
- <span data-ttu-id="734bc-148">イメージのみが含まれているファイル</span><span class="sxs-lookup"><span data-stu-id="734bc-148">Files that contain only images</span></span>
    
- <span data-ttu-id="734bc-149">ドキュメント フィンガープリントの作成に使用されたオリジナルのフォームのテキストがすべて含まれていないドキュメント</span><span class="sxs-lookup"><span data-stu-id="734bc-149">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="734bc-150">PowerShell を使用して、ドキュメントのフィンガー プリントに基づくクラス分けルール パッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="734bc-150">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="734bc-p109">PowerShell を使用してセキュリティでのみドキュメントのフィンガー プリントを作成すること現在ことができます&amp;コンプライアンス センターです。接続するには、 [Office 365 のセキュリティとコンプライアンス センター PowerShell への接続](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="734bc-p109">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center. To connect, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="734bc-p110">DLP では、機密性の高いコンテンツを検出するためにクラス分け規則のパッケージを使用します。文書の指紋認証に基づくクラス分けルール パッケージを作成するには、**新規 DlpFingerprint**および**新しい DlpSensitiveInformationType**コマンドレットを使用します。同じでは、**新規 DlpFingerprint**および**新しい DlpSensitiveInformationType**または**セット DlpSensitiveInformationType**を常に実行するため、**新規 DlpFingerprint**の結果は、データの分類規則の外部に保存されていない、PowerShell セッションです。C:\My Documents\Contoso の従業員の Template.docx ファイルに基づく新しい文書の指紋を作成する例を次にします。PowerShell セッションを同時に**新規 DlpSensitiveInformationType**コマンドレットを使用できるように、変数として、新たな指紋を格納します。</span><span class="sxs-lookup"><span data-stu-id="734bc-p110">DLP uses classification rule packages to detect sensitive content. To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets. Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session. The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx. You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span> 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="734bc-158">ここで、C:\My Documents\Contoso Customer Information Form.docx ファイルのドキュメント フィンガープリントを使用する、"Contoso Employee Confidential" という名前の新しいデータ分類ルールを作成してみましょう。</span><span class="sxs-lookup"><span data-stu-id="734bc-158">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="734bc-159">DLP データのクラス分けのルール、すべてのパッケージを検索するのには、 **Get DlpSensitiveInformationType**コマンドレットを使用することができますようになりましたし、この例では、「Contoso ユーザーは社外秘」は、データのクラス分けルール パッケージ] の一覧の一部です。</span><span class="sxs-lookup"><span data-stu-id="734bc-159">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="734bc-p111">最後に、「Contoso ユーザーは社外秘」のデータのクラス分けルール パッケージをセキュリティで DLP ポリシーに追加する&amp;コンプライアンス センターです。次の使用例では、"ConfidentialPolicy"という名前の既存の DLP ポリシーに規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="734bc-p111">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center. This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="734bc-p112">次の例に示すように、Exchange online では、トランスポート ルールで、データのクラス分けルール パッケージを使用できます。このコマンドを実行するのには最初に[オンラインの PowerShell を Exchange に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)する必要があります。ルール パッケージのセキュリティの同期の時間がかかることにも注意してください&amp;Exchange 管理センターへのコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="734bc-p112">You can also use the data classification rule package in transport rules in Exchange Online, as shown in the following example. To run this command, you first need to [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange Admin Center.</span></span>
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

<span data-ttu-id="734bc-165">DLP は、contoso 社の顧客の Form.docx の文書の指紋が一致するドキュメントを検出します。</span><span class="sxs-lookup"><span data-stu-id="734bc-165">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="734bc-166">構文とパラメーターについては、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="734bc-166">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="734bc-167">新しい-DlpFingerprint</span><span class="sxs-lookup"><span data-stu-id="734bc-167">New-DlpFingerprint</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [<span data-ttu-id="734bc-168">新しい-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="734bc-168">New-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [<span data-ttu-id="734bc-169">削除 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="734bc-169">Remove-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="734bc-170">セット DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="734bc-170">Set-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="734bc-171">Get DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="734bc-171">Get-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
