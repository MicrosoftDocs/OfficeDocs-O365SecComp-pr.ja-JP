---
title: Office 365 の機密情報のメッセージ暗号化ポリシー
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Office 365 では、機密情報の種類のメッセージ暗号化ポリシーが利用可能になりました。'
ms.openlocfilehash: 99cb7a9f94c9cf4036c11b74a5208ddf0e819ceb
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213981"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="f3031-103">Office 365 の機密情報のメッセージ暗号化ポリシー</span><span class="sxs-lookup"><span data-stu-id="f3031-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="f3031-p101">更新プログラム (1/30/19): 2018 年10月に、お客様の小規模なサンプルを使用して、特定の機密情報の種類に基づいて機密メールを自動的に暗号化することによって保護を簡略化できるかどうかを理解しています。このサンプルからの肯定的なフィードバックに基づき、2018年12月に、より多様なテナントのプロファイルに拡張することを決定しました。次のロールアウトを送信してテナントを選択したら、フィードバックを検討して、より複雑な環境を使用しているお客様がルールをより慎重に実装する必要があると判断しました。そのため、計画を調整しています。</span><span class="sxs-lookup"><span data-stu-id="f3031-p101">Update (1/30/19): In October 2018, we worked with a small sample of customers to understand if we can simplify protection by automatically encrypting sensitive emails based on certain sensitive information types. Based on positive feedback from this sample, we decided to expand to a more diverse profile of tenants in December 2018. After communicating the next roll-out to select tenants, we listened to your feedback and determined that customers with more complex environments wanted to implement the rules more cautiously, and we are therefore adjusting our plans.</span></span>

<span data-ttu-id="f3031-p102">2019年1月15日の展開のために組織が選択されている場合、自動ポリシーはロールアウトされません。代わりに、この記事では、ロールアウト yourselves を完了する方法について説明しています。詳細については、「how to」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3031-p102">If your organization was selected for the roll-out starting January 15, 2019, we will not roll out the automatic policy. Instead, we are providing instructions in this article on how you can complete the roll-out yourselves. Keep reading to find out how.</span></span>

||
|:-----|
|<span data-ttu-id="f3031-p103">この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。この記事は、管理者および it 担当者を対象としています。暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。</span><span class="sxs-lookup"><span data-stu-id="f3031-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a><span data-ttu-id="f3031-113">テナントの機密情報の種類のポリシーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f3031-113">How to create the sensitive information type policy for your tenant</span></span>

<span data-ttu-id="f3031-p104">Exchange メールフロールールまたは Office 365 データ損失防止 (DLP) のいずれかを使用して、機密情報の種類のポリシーを作成できます。exchange メールフロールールを作成するには、exchange 管理センター (EAC) または PowerShell のどちらかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3031-p104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create the sensitive information type policy. To create an Exchange mail flow rule you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="f3031-116">EAC でメールフロールールを使用してポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="f3031-116">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="f3031-p105">Exchange 管理センター (EAC) にサインインし、[**メールフロー** > **ルール**] に移動します。ここで、メッセージまたは添付ファイルに特定のキーワードや機密情報の種類が存在するなどの条件に基づいて、Office 365 メッセージの暗号化を適用するルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3031-p105">Sign-in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**. There, create a rule that applies Office 365 Message Encryption based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="f3031-119">PowerShell でメールフロールールを使用してポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="f3031-119">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="f3031-p106">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。TransporRule コマンドレットと新しいコマンドレットを使用して、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3031-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell). Use the Set-IRMConfiguration and New-TransporRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="f3031-123">PowerShell を使用して作成されたメールフロールールの例</span><span class="sxs-lookup"><span data-stu-id="f3031-123">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="f3031-124">PowerShell で次のコマンドを実行すると、電子メールまたは添付ファイルに次の機密情報が含まれている場合に、組織外のメールを自動的に*暗号化*する Exchange メールフロールールを作成します。情報の種類:</span><span class="sxs-lookup"><span data-stu-id="f3031-124">Running the following commands in PowerShell create an Exchange mail flow rule that automatically encrypts emails going outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="f3031-125">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="f3031-125">ABA routing number</span></span>
- <span data-ttu-id="f3031-126">クレジットカード番号</span><span class="sxs-lookup"><span data-stu-id="f3031-126">Credit card Number</span></span>
- <span data-ttu-id="f3031-127">医薬品執行機関 (dea) 番号</span><span class="sxs-lookup"><span data-stu-id="f3031-127">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="f3031-p107">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="f3031-p107">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="f3031-130">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="f3031-130">U.S. bank account number</span></span>
- <span data-ttu-id="f3031-131">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="f3031-131">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="f3031-132">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="f3031-132">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="f3031-133">受信者が添付ファイルにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="f3031-133">How recipients access attachments</span></span>

<span data-ttu-id="f3031-134">メッセージが暗号化されると、受信者は暗号化された電子メールにアクセスして開くと、添付ファイルに無制限にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f3031-134">Once a message is encrypted, recipients will have unrestricted access to attachments once they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="f3031-135">この変更を準備するには</span><span class="sxs-lookup"><span data-stu-id="f3031-135">To prepare for this change</span></span>

<span data-ttu-id="f3031-p108">この変更に関して組織内のユーザーを準備するために、適用可能なエンドユーザードキュメントおよびトレーニング資料を更新することが必要な場合があります。必要に応じて、これらの Office 365 メッセージ暗号化リソースをユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="f3031-p108">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="f3031-138">Outlook for PC で暗号化されたメッセージを送信、表示、および返信する</span><span class="sxs-lookup"><span data-stu-id="f3031-138">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="f3031-139">office 365 Essentials ビデオ: office メッセージの暗号化</span><span class="sxs-lookup"><span data-stu-id="f3031-139">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="f3031-140">監査ログでのこれらの変更の表示</span><span class="sxs-lookup"><span data-stu-id="f3031-140">View these changes in the Audit log</span></span>

<span data-ttu-id="f3031-p109">このアクティビティは監査され、Office 365 管理者が使用できます。この操作は ' new-transportrule ' であり、Security & コンプライアンスセンターでの監査ログの検索に含まれるサンプルの監査エントリのスニペットは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f3031-p109">This activity is audited and is available to Office 365 administrators. The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="f3031-143">*{"設定時刻": "2018-28t23:35:01", "Id": "a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c", "Operation": "New-new-transportrule", "": "", "UserKey": "", "RecordType": "", "": "Microsoft Operator", "UserType ": 3"、"バージョン": 1, "ワークロード": "Exchange", "clientip": "123.456.147.68: 17584", "": "", "UserId": "" or ":": "" 組織名 "、" "、" "、" CY4PR13MBXXXX (15.20.1382.008) "," パラメーター ": {" name ":" Organization "、" value ":" 123456-221d-12346 "{" name ":" ApplyRightsProtectionTemplate "、" value ":" Encrypt "}、{" name ":" name "、" Value ":" 送信機密性の高いメールの暗号化 (アウトボックスルール) "}, {" name ":"MessageContainsDataClassificationsいう.*</span><span class="sxs-lookup"><span data-stu-id="f3031-143">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span> |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="f3031-144">機密情報の種類のポリシーを無効にする、またはカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="f3031-144">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="f3031-145">exchange メールフロールールを作成したら、exchange 管理センター (EAC) の**メールフロー** > **ルール**に移動し、[*送信機密メールを暗号化する (すぐ*に使用できるルール)] ルールを無効にして、[ルールを無効に](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)したり、編集したりすることができます。".</span><span class="sxs-lookup"><span data-stu-id="f3031-145">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
