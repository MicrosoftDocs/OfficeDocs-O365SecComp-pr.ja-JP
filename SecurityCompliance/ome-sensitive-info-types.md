---
title: Office 365 Message Encryption 機能を使用して、機密情報の種類のポリシーを作成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: '概要: 機密情報の種類に関する Office 365 メッセージの暗号化ポリシー。'
ms.openlocfilehash: 44966303ec7c58fdd82f733e1922073de848cf73
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834836"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a><span data-ttu-id="17e9f-103">Office 365 Message Encryption 機能を使用して、機密情報の種類のポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="17e9f-103">Create a sensitive information type policy for your organization using Office 365 Message Encryption</span></span>

<span data-ttu-id="17e9f-104">Exchange メールフロールールまたは Office 365 データ損失防止 (DLP) のいずれかを使用して、Office 365 メッセージの暗号化を使用して機密情報の種類ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="17e9f-104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="17e9f-105">Exchange メールフロールールを作成するには、Exchange 管理センター (EAC) または PowerShell のどちらかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="17e9f-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="17e9f-106">EAC でメールフロールールを使用してポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="17e9f-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="17e9f-107">Exchange 管理センター (EAC) にサインインし、[**メールフロー** > ] [**ルール**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="17e9f-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="17e9f-108">[ルール] ページで、Office 365 メッセージの暗号化を適用するルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="17e9f-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="17e9f-109">特定のキーワードの存在や、メッセージまたは添付ファイル内の機密情報の種類などの条件に基づいてルールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="17e9f-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="17e9f-110">PowerShell でメールフロールールを使用してポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="17e9f-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="17e9f-111">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="17e9f-111">Use a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="17e9f-112">手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e9f-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="17e9f-113">New-transportrule コマンドレットと新しいコマンドレットを使用して、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="17e9f-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="17e9f-114">PowerShell を使用して作成されたメールフロールールの例</span><span class="sxs-lookup"><span data-stu-id="17e9f-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="17e9f-115">メールまたは添付ファイルに次の機密情報が含まれている場合に、組織外の電子メールを自動的に*暗号化*する Exchange メールフロールールを作成するには、PowerShell で次のコマンドを実行します。各種</span><span class="sxs-lookup"><span data-stu-id="17e9f-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="17e9f-116">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="17e9f-116">ABA routing number</span></span>
- <span data-ttu-id="17e9f-117">クレジットカード番号</span><span class="sxs-lookup"><span data-stu-id="17e9f-117">Credit card Number</span></span>
- <span data-ttu-id="17e9f-118">医薬品執行機関 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="17e9f-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="17e9f-119">米国/英国</span><span class="sxs-lookup"><span data-stu-id="17e9f-119">U.S. / U.K.</span></span> <span data-ttu-id="17e9f-120">passport number</span><span class="sxs-lookup"><span data-stu-id="17e9f-120">passport number</span></span>
- <span data-ttu-id="17e9f-121">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="17e9f-121">U.S. bank account number</span></span>
- <span data-ttu-id="17e9f-122">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="17e9f-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="17e9f-123">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="17e9f-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="17e9f-124">受信者が添付ファイルにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="17e9f-124">How recipients access attachments</span></span>

<span data-ttu-id="17e9f-125">Office 365 がメッセージを暗号化した後は、受信者が暗号化された電子メールにアクセスして開くときに、添付ファイルへのアクセス権を無制限にすることができます。</span><span class="sxs-lookup"><span data-stu-id="17e9f-125">After Office 365 encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="17e9f-126">この変更を準備するには</span><span class="sxs-lookup"><span data-stu-id="17e9f-126">To prepare for this change</span></span>

<span data-ttu-id="17e9f-127">この変更に関して組織内のユーザーを準備するために、適用可能なエンドユーザードキュメントおよびトレーニング資料を更新することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="17e9f-127">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="17e9f-128">必要に応じて、これらの Office 365 メッセージ暗号化リソースをユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="17e9f-128">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="17e9f-129">Outlook for PC で暗号化されたメッセージを送信、表示、および返信する</span><span class="sxs-lookup"><span data-stu-id="17e9f-129">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="17e9f-130">Office 365 Essentials ビデオ: Office メッセージの暗号化</span><span class="sxs-lookup"><span data-stu-id="17e9f-130">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="17e9f-131">監査ログでのこれらの変更の表示</span><span class="sxs-lookup"><span data-stu-id="17e9f-131">View these changes in the Audit log</span></span>

<span data-ttu-id="17e9f-132">Office 365 は、このアクティビティを監査して、Office 365 管理者が使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="17e9f-132">Office 365 audits this activity and makes it available to Office 365 administrators.</span></span> <span data-ttu-id="17e9f-133">この操作は ' New-transportrule ' であり、Security & コンプライアンスセンターでの監査ログの検索に含まれるサンプルの監査エントリのスニペットは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="17e9f-133">The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="17e9f-134">機密情報の種類のポリシーを無効にする、またはカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="17e9f-134">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="17e9f-135">Exchange メールフロールールを作成したら、exchange 管理センター (EAC) の**メールフロー** > **ルール**に移動し、[*送信機密メールを暗号化する (すぐ*に使用できるルール)] ルールを無効にして、[ルールを無効に](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)したり、編集したりすることができます。".</span><span class="sxs-lookup"><span data-stu-id="17e9f-135">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
