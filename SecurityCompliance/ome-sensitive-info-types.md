---
title: 機密情報の新しい Office 365 のメッセージの暗号化のポリシー
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/7/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: は、すべてのテナントにロールアウトの機密情報の種類の Office 365 のメッセージの暗号化ポリシーを自動的に適用します。'
ms.openlocfilehash: f5996707d1cafe8dc1bf90856878de0a4fb7b77b
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2019
ms.locfileid: "27752090"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="0f78c-103">機密情報を office 365 のメッセージの暗号化ポリシー</span><span class="sxs-lookup"><span data-stu-id="0f78c-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="0f78c-p101">機密情報が含まれていると、組織外に送信されているすべての電子メールを Office 365 のメッセージの暗号化を適用する Office 365 テナントに新しい自動ポリシーを作成しています。この新規の Exchange メール フロー ルールは自動的に作成、Office 365 テナントに組織は、既定で保護されるようにします。</span><span class="sxs-lookup"><span data-stu-id="0f78c-p101">We will be creating a new automatic policy in Office 365 tenants that will apply Office 365 Message Encryption to all emails that contain sensitive information and that are being sent outside your organization. This new Exchange mail flow rule will be automatically created in your Office 365 tenant so that your organization will be protected by default.</span></span>

## <a name="when-to-expect-the-update-for-your-tenant"></a><span data-ttu-id="0f78c-106">テナント用の更新プログラムが予想される時期</span><span class="sxs-lookup"><span data-stu-id="0f78c-106">When to expect the update for your tenant</span></span>

<span data-ttu-id="0f78c-p102">組織で Office 365 のメッセージ ・ センター、テナントのこの自動ポリシーを作成するのには、日付を通知する通知が表示されます。少なくとも 30 日間の通知を指定して、オプションを無効にする必要があります。可能性があることをすることがありますシナリオでは、既に、機密性の高い型をスキャンするサード パーティ製データ損失防止ソリューションがあるかどうか、します。無効にする方法の詳細については、この資料で後で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f78c-p102">Your organization will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created in your tenant. You will be given at least a 30-day notice and you will also have the option to opt-out. A scenario in which you may want to potentially opt out is if you have a 3rd-party Data Loss Prevention solution that already scans for sensitive types. More details on how to opt-out are available later in this article.</span></span>

## <a name="sensitive-information-type-policy-details"></a><span data-ttu-id="0f78c-110">機密性の高い情報の種類のポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="0f78c-110">Sensitive information type policy details</span></span>

<span data-ttu-id="0f78c-111">使用して組織外の電子メールを自動的に暗号化される組織で Exchange メール フロー ルールを作成するは、*暗号化専用*ポリシーは次の種類機密情報にはが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="0f78c-111">An Exchange mail flow rule will be created in your organization that will automatically encrypt emails going outside your organization with the *Encrypt-Only* policy if they contain the following sensitive information types:</span></span>

- <span data-ttu-id="0f78c-112">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="0f78c-112">ABA routing number</span></span>
- <span data-ttu-id="0f78c-113">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="0f78c-113">Credit card Number</span></span>
- <span data-ttu-id="0f78c-114">薬品執行局 (DEA) の数</span><span class="sxs-lookup"><span data-stu-id="0f78c-114">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="0f78c-p103">米国と英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="0f78c-p103">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="0f78c-117">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="0f78c-117">U.S. bank account number</span></span>
- <span data-ttu-id="0f78c-118">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="0f78c-118">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="0f78c-119">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="0f78c-119">U.S. Social Security Number (SSN)</span></span>

> [!Note]
> <span data-ttu-id="0f78c-120">正確な機密性の高いタイプは、組織のロケールによって異なる場合があり、メッセージ センターからの通知で伝達されます。</span><span class="sxs-lookup"><span data-stu-id="0f78c-120">The exact sensitive types may differ by your organization’s locale and will be communicated in the Message Center notification.</span></span>

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="0f78c-121">この変更の準備を行うには何が必要でしょうか。</span><span class="sxs-lookup"><span data-stu-id="0f78c-121">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="0f78c-p104">更新または新しい変更する前に既存の Office 365 の構成設定を変更する必要はありません。ただし、この変更を組織内のユーザーを準備するのには、トレーニング資料、マニュアルの該当する場合のエンド ・ ユーザーを更新することがあります。必要に応じてユーザーと Office 365 のメッセージの暗号化リソースを共有します。</span><span class="sxs-lookup"><span data-stu-id="0f78c-p104">You do not have to update or modify any existing Office 365 configuration settings prior to this new change. However, you may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="0f78c-125">送信、表示、および PC の Outlook で暗号化されたメッセージに返信します。</span><span class="sxs-lookup"><span data-stu-id="0f78c-125">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="0f78c-126">Office 365 に関する重要事項のビデオ: Office のメッセージの暗号化</span><span class="sxs-lookup"><span data-stu-id="0f78c-126">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a><span data-ttu-id="0f78c-127">この変更表されるか、監査ログにしますか。</span><span class="sxs-lookup"><span data-stu-id="0f78c-127">How will this change be represented in the Audit log?</span></span>

<span data-ttu-id="0f78c-p105">このアクティビティでは、監査され、お客様が利用します。 操作は、' 新しい TransportRule' は、監査ログの検索でセキュリティとコンプライアンスの中心から監査エントリの例のスニペットの下にある.</span><span class="sxs-lookup"><span data-stu-id="0f78c-p105">This activity is audited and is available to customers.  The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="0f78c-130">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"、「RecordType」: 1 の場合、"ResultStatus":"True"、"ユーザーのキー":"Microsoft オペレーター」、「UserType」: 3、[バージョン]: 1、「ワークロード」:「交換」、"ClientIP":「123.456.147.68:17584」、"オブジェクト Id":"「、」ユーザー Id":"マイクロソフトの Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters」: {[名]:「組織」、「値」:"123456 221 d-12346"{[名]:"ApplyRightsProtectionTemplate"、「値」:「暗号化」}、{[名]:「名」、「値」:「(ルール) から機密性の高い電子メールを送信を暗号化する」}、{[名]:"MessageContainsDataClassifications」などです。*</span><span class="sxs-lookup"><span data-stu-id="0f78c-130">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span>
 |

## <a name="how-do-i-opt-out"></a><span data-ttu-id="0f78c-131">方法の操作を行いますか脱退か。</span><span class="sxs-lookup"><span data-stu-id="0f78c-131">How do I opt-out?</span></span>

<span data-ttu-id="0f78c-132">この変更を中止する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="0f78c-132">If you would like to opt-out of this change, please follow these steps:</span></span>

1. <span data-ttu-id="0f78c-p106">大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f78c-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>
2. <span data-ttu-id="0f78c-135">とおりセット IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f78c-135">Run the Set-IRMConfiguration cmdlet as follows:</span></span>

   ```
   Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
   ```

## <a name="how-do-i-disable-the-automatic-policy"></a><span data-ttu-id="0f78c-136">自動ポリシーを無効にする方法は?</span><span class="sxs-lookup"><span data-stu-id="0f78c-136">How do I disable the automatic policy?</span></span>

<span data-ttu-id="0f78c-137">でしたを無効にこの変更は、Exchange のメール ルールは既に作成されている場合することができます[、ルールを無効にするの](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)には、**メールの流れ** > Exchange 管理ツールでは、**ルール**のセンター (EAC) と「*送信暗号化ルール無効にします。(ルール) から機密性の高い電子メール*」です。</span><span class="sxs-lookup"><span data-stu-id="0f78c-137">If you didn’t opt-out of this change and the Exchange mail rule has already been created, you can [disable the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
