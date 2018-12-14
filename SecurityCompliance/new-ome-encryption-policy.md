---
title: 機密情報の新しい Office 365 のメッセージの暗号化のポリシー
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/13/2018
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: 新しい Office 365 のメッセージの暗号化用のポリシーの機密情報。'
ms.openlocfilehash: 180050d1bf9303f6d29bc126e66ac53211c2fb34
ms.sourcegitcommit: 3aae959ea1ac5ef61a9942c681d334831e6b6038
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "27271093"
---
# <a name="new-office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="043bd-103">機密情報の新しい Office 365 のメッセージの暗号化のポリシー</span><span class="sxs-lookup"><span data-stu-id="043bd-103">New Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="043bd-p101">機密情報が含まれていると、組織外に送信されているすべての電子メールを Office 365 のメッセージの暗号化を適用する Office 365 テナントに新しい自動ポリシーを作成しています。この新規の Exchange メール フロー ルールは自動的に作成、Office 365 テナントに組織は、既定で保護されるようにします。</span><span class="sxs-lookup"><span data-stu-id="043bd-p101">We will be creating a new automatic policy in Office 365 tenants that will apply Office 365 Message Encryption to all emails that contain sensitive information and that are being sent outside your organization. This new Exchange mail flow rule will be automatically created in your Office 365 tenant so that your organization will be protected by default.</span></span>

## <a name="how-will-this-work"></a><span data-ttu-id="043bd-106">この作業をどのようにでしょうか。</span><span class="sxs-lookup"><span data-stu-id="043bd-106">How will this work?</span></span>

<span data-ttu-id="043bd-p102">組織で Office 365 のメッセージ ・ センター、テナントのこの自動ポリシーを作成するのには、日付を通知する通知が表示されます。少なくとも 30 日間の通知を指定して、オプションを無効にする必要があります。可能性があることをすることがありますシナリオでは、既に、機密性の高い型をスキャンするサード パーティ製データ損失防止ソリューションがあるかどうか、します。</span><span class="sxs-lookup"><span data-stu-id="043bd-p102">Your organization will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created in your tenant. You will be given at least a 30-day notice and you will also have the option to opt-out. A scenario in which you may want to potentially opt out is if you have a 3rd-party Data Loss Prevention solution that already scans for sensitive types.</span></span>

## <a name="new-policy-details"></a><span data-ttu-id="043bd-109">新しいポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="043bd-109">New policy details</span></span>

<span data-ttu-id="043bd-110">使用して組織外の電子メールを自動的に暗号化される組織で新しい Exchange メール フロー ルールを作成するは、*暗号化専用*ポリシーは次の種類機密情報にはが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="043bd-110">A new Exchange mail flow rule will be created in your organization that will automatically encrypt emails going outside your organization with the *Encrypt-Only* policy if they contain the following sensitive information types:</span></span>

- <span data-ttu-id="043bd-111">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="043bd-111">ABA routing number</span></span>
- <span data-ttu-id="043bd-112">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="043bd-112">Credit card Number</span></span>
- <span data-ttu-id="043bd-113">薬品執行局 (DEA) の数</span><span class="sxs-lookup"><span data-stu-id="043bd-113">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="043bd-p103">米国と英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="043bd-p103">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="043bd-116">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="043bd-116">U.S. bank account number</span></span>
- <span data-ttu-id="043bd-117">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="043bd-117">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="043bd-118">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="043bd-118">U.S. Social Security Number (SSN)</span></span>

> [!Note]
> <span data-ttu-id="043bd-119">正確な機密性の高いタイプは、組織のロケールによって異なる場合があり、メッセージ センターからの通知で伝達されます。</span><span class="sxs-lookup"><span data-stu-id="043bd-119">The exact sensitive types may differ by your organization’s locale and will be communicated in the Message Center notification.</span></span>

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="043bd-120">この変更の準備を行うには何が必要でしょうか。</span><span class="sxs-lookup"><span data-stu-id="043bd-120">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="043bd-p104">更新または新しい変更する前に既存の Office 365 の構成設定を変更する必要はありません。ただし、この変更を組織内のユーザーを準備するのには、トレーニング資料、マニュアルの該当する場合のエンド ・ ユーザーを更新することがあります。</span><span class="sxs-lookup"><span data-stu-id="043bd-p104">You do not have to update or modify any existing Office 365 configuration settings prior to this new change. However, you may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span>

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a><span data-ttu-id="043bd-123">この変更表されるか、監査ログにしますか。</span><span class="sxs-lookup"><span data-stu-id="043bd-123">How will this change be represented in the Audit log?</span></span>

<span data-ttu-id="043bd-p105">このアクティビティでは、監査され、お客様が利用します。 操作は、' 新しい TransportRule' は、監査ログの検索でセキュリティとコンプライアンスの中心から監査エントリの例のスニペットの下にある.</span><span class="sxs-lookup"><span data-stu-id="043bd-p105">This activity is audited and is available to customers.  The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="043bd-126">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"、「RecordType」: 1 の場合、"ResultStatus":"True"、"ユーザーのキー":"Microsoft オペレーター」、「UserType」: 3、[バージョン]: 1、「ワークロード」:「交換」、"ClientIP":「123.456.147.68:17584」、"オブジェクト Id":"「、」ユーザー Id":"マイクロソフトの Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters」: {[名]:「組織」、「値」:"123456 221 d-12346"{[名]:"ApplyRightsProtectionTemplate"、「値」:「暗号化」}、{[名]:「名」、「値」:「(ルール) から機密性の高い電子メールを送信を暗号化する」}、{[名]:"MessageContainsDataClassifications」などです。*</span><span class="sxs-lookup"><span data-stu-id="043bd-126">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span>
 |

## <a name="how-do-i-opt-out"></a><span data-ttu-id="043bd-127">方法の操作を行いますか脱退か。</span><span class="sxs-lookup"><span data-stu-id="043bd-127">How do I opt-out?</span></span>

<span data-ttu-id="043bd-128">この変更を中止する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="043bd-128">If you would like to opt-out of this change, please follow these steps:</span></span>

1. <span data-ttu-id="043bd-129">[Exchange オンライン PowerShell](https://aka.ms/exopowershell)グローバル管理者ロールを持つユーザーとして接続します。</span><span class="sxs-lookup"><span data-stu-id="043bd-129">Connect to [Exchange Online PowerShell](https://aka.ms/exopowershell) as a user with the global administrator role.</span></span>
2.  <span data-ttu-id="043bd-130">認証した後、次のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="043bd-130">Run the following code after authenticating:</span></span>

    ```
    Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
    ```

## <a name="how-do-i-disable-the-automatic-policy"></a><span data-ttu-id="043bd-131">自動ポリシーを無効にする方法は?</span><span class="sxs-lookup"><span data-stu-id="043bd-131">How do I disable the automatic policy?</span></span>

<span data-ttu-id="043bd-132">でしたを無効にこの変更は、Exchange のメール ルールは既に作成されている場合することができます[、ルールを無効にするの](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)には、**メールの流れ** > Exchange 管理ツールでは、**ルール**のセンター (EAC) と「*送信暗号化ルール無効にします。(ルール) から機密性の高い電子メール*」です。</span><span class="sxs-lookup"><span data-stu-id="043bd-132">If you didn’t opt-out of this change and the Exchange mail rule has already been created, you can [disable the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
