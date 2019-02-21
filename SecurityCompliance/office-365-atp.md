---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/20/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection には、安全な添付ファイル、安全なリンク、高度なフィッシング対策ツール、レポートツール、および脅威インテリジェンス機能が含まれています。
ms.openlocfilehash: 5db4c5ff5ae7e536bba1f8730c724d151f367b54
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123928"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="5e202-103">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5e202-103">Office 365 Advanced Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e202-p101">この記事は、Office 365 Enterprise のお客様を対象としています。Outlook.com、office 365 Home、または office 365 Personal を使用していて、Outlook での安全なリンクに関する情報をお探しの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-p101">This article is intended for Office 365 Enterprise customers. If you are using Outlook.com, Office 365 Home, or Office 365 Personal, and you're looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

## <a name="overview"></a><span data-ttu-id="5e202-106">概要</span><span class="sxs-lookup"><span data-stu-id="5e202-106">Overview</span></span>

<span data-ttu-id="5e202-p102">Office 365 Advanced Threat Protection (ATP) は、電子メールメッセージ、リンク (url)、およびコラボレーションツールがもたらす悪意のある脅威から組織を保護します。ATP の内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e202-p102">Office 365 Advanced Threat Protection (ATP) safeguards your organization against malicious threats posed by email messages, links (URLs) and collaboration tools. ATP includes:</span></span>

- <span data-ttu-id="5e202-109">[脅威保護ポリシー](#configure-atp-policies): 脅威保護ポリシーを定義して、組織に適したレベルの保護を設定します。</span><span class="sxs-lookup"><span data-stu-id="5e202-109">[Threat protection policies](#configure-atp-policies): Define threat-protection policies to set the appropriate level of protection for your organization.</span></span> 

- <span data-ttu-id="5e202-110">[レポート](#view-atp-reports): 組織内の ATP のパフォーマンスを監視するためのリアルタイムレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e202-110">[Reports](#view-atp-reports): View real-time reports to monitor ATP performance in your organization.</span></span> 

- <span data-ttu-id="5e202-111">[脅威インテリジェンス機能](#utilize-threat-intelligence-capabilities): トップエッジツールを使用して、脅威を調査、理解、シミュレーション、および防止します。</span><span class="sxs-lookup"><span data-stu-id="5e202-111">[Threat intelligence capabilities](#utilize-threat-intelligence-capabilities): Utilize leading-edge tools to investigate, understand, simulate, and prevent threats.</span></span> 
 

## <a name="configure-atp-policies"></a><span data-ttu-id="5e202-112">ATP ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="5e202-112">Configure ATP policies</span></span>

<span data-ttu-id="5e202-113">Office 365 ATP には、組織に適したレベルの保護を設定するための多数のツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5e202-113">Office 365 ATP provides numerous tools to set an appropriate level of protection for your organization.</span></span> 

<span data-ttu-id="5e202-p103">組織のセキュリティチームは、Office 365 security & コンプライアンスセンターの各 ATP ツールに対してポリシーを定義する必要があります。[**脅威管理** > **ポリシー** ] に移動して、[ポリシーオプションにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5e202-p103">Your organization's security team must define policies for each ATP tool in the Office 365 Security & Compliance Center. Go to **Threat management** > **Policy** to access policy options.</span></span> 

<span data-ttu-id="5e202-p104">組織に対して定義されているポリシーによって、定義済みの脅威の動作と保護レベルが決まります。ポリシーオプションは、非常に柔軟です。たとえば、組織のセキュリティチームは、ユーザー、組織、受信者、およびドメインレベルできめ細かな脅威保護を設定できます。新しい脅威や課題が日々浮上するため、ポリシーを定期的に確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="5e202-p104">The policies that are defined for your organization determine the behavior and protection level for predefined threats. Policy options are extremely flexible. For example, your organization's security team can set fine-grained threat protection at the user, organization, recipient, and domain level. It is important to review your policies regularly because new threats and challenges emerge daily.</span></span>  

- <span data-ttu-id="5e202-p105">[ATP の安全な添付ファイル](atp-safe-attachments.md): 悪意のあるコンテンツの電子メールの添付ファイルを確認することによって、メッセージングシステムを保護するゼロ日の保護を提供します。ウイルス/マルウェアの署名を持たないすべてのメッセージと添付ファイルを特別な環境にルーティングし、機械学習と分析の手法を使用して悪意のある目的を検出します。疑わしい動作が見つからない場合、メッセージはメールボックスに転送されます。詳細については、「 [Office 365 ATP の安全な添付ファイルのポリシーを](set-up-atp-safe-attachments-policies.md)セットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-p105">[ATP Safe Attachments](atp-safe-attachments.md): Provides zero-day protection to safeguard your messaging system, by checking email attachments for malicious content. It routes all messages and attachments that do not have a virus/malware signature to a special environment, and then uses machine learning and analysis techniques to detect malicious intent. If no suspicious activity is found, the message is forwarded to the mailbox. To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

- <span data-ttu-id="5e202-p106">[ATP の安全なリンク](atp-safe-links.md): 電子メールメッセージおよび Office ファイル内での url の確認時間の確認を提供します。保護は進行中で、メッセージングおよび Office 環境全体に適用されます。各クリックでリンクがスキャンされます。安全なリンクは常にアクセス可能で、悪意のあるリンクは動的にブロックされます。詳細については、「 [Office 365 ATP 安全リンクポリシー](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)のセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-p106">[ATP Safe Links](atp-safe-links.md): Provides time-of-click verification of URLs in emails messages and Office files. Protection is ongoing and applies across your messaging and Office environment. Links are scanned for each click: safe links remain accessible and malicious links are dynamically blocked. To learn more, see [Set up Office 365 ATP Safe Links policies](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies).</span></span> 

- <span data-ttu-id="5e202-p107">[SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md): チームサイトおよびドキュメントライブラリ内の悪意のあるファイルを特定してブロックすることにより、ユーザーがファイルを共同作業したり、共有したりするときに組織を保護します。詳細については、「 [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-p107">[ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md): Protects your organization when users collaborate and share files, by identifying and blocking malicious files in team sites and document libraries. To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span> 

- <span data-ttu-id="5e202-p108">[ATP のフィッシング対策保護](atp-anti-phishing.md): ユーザーおよびカスタムドメインの偽装の試行を検出します。これは、機械学習モデルと高度な偽造検知アルゴリズムを avert フィッシング攻撃に適用します。詳細については、「 [Office 365 の ATP のフィッシング対策およびフィッシング対策ポリシー](set-up-anti-phishing-policies.md)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-p108">[ATP anti-phishing protection](atp-anti-phishing.md): Detects attempts to impersonate your users and custom domains. It applies machine learning models and advanced impersonation-detection algorithms to avert phishing attacks. To learn more, see [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="view-atp-reports"></a><span data-ttu-id="5e202-133">ATP レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="5e202-133">View ATP reports</span></span>

<span data-ttu-id="5e202-p109">Office 365 atp には、atp のパフォーマンスを監視するための高度な[レポートダッシュボード](view-reports-for-atp.md)が含まれています。これは、Security & コンプライアンスセンターの**Reports > Dashboard**でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5e202-p109">Office 365 ATP includes an advanced [reporting dashboard](view-reports-for-atp.md) to monitor your ATP performance. You can access it at **Reports > Dashboard** in the Security & Compliance Center.</span></span> 

<span data-ttu-id="5e202-p110">最新の洞察を提供して、リアルタイムで更新を報告します。これらのレポートでは、推奨事項も提供されており、脅威を差し迫っていることを警告します。定義済みのレポートには、[脅威保護の状態レポート](view-reports-for-atp.md#threat-protection-status-report)、 [atp ファイルの種類レポート](view-reports-for-atp.md#atp-file-types-report)、 [atp メッセージ廃棄レポート](view-reports-for-atp.md#atp-message-disposition-report)などがあります。</span><span class="sxs-lookup"><span data-stu-id="5e202-p110">Reports update in real-time, providing you with the latest insights. These reports also provide recommendations and alert you to imminent threats. Predefined reports include the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report), [ATP File Types report](view-reports-for-atp.md#atp-file-types-report), [ATP Message Disposition report](view-reports-for-atp.md#atp-message-disposition-report) and more.</span></span> 

## <a name="utilize-threat-intelligence-capabilities"></a><span data-ttu-id="5e202-139">脅威インテリジェンス機能を活用する</span><span class="sxs-lookup"><span data-stu-id="5e202-139">Utilize threat intelligence capabilities</span></span>

<span data-ttu-id="5e202-140">Office 365 ATP には、組織のセキュリティチームが悪意のある攻撃を予測、理解、および阻止できるようにするためのクラス最高の[脅威インテリジェンスツール](office-365-ti.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e202-140">Office 365 ATP includes best-of-class [threat intelligence tools](office-365-ti.md) that enable your organization's security team to anticipate, understand, and prevent malicious attacks.</span></span> 

- <span data-ttu-id="5e202-p111">[脅威のトラッカー](threat-trackers.md)は、優先 cybersecurity の問題に関する最新のインテリジェンスを提供します。たとえば、最新のマルウェアに関する情報を表示して、組織の実際の脅威になる前に対策を実行できます。利用可能なトラッカーには、[注目すべきトラッカー](threat-trackers.md#noteworthy-trackers)、[傾向分析](threat-trackers.md#trending-trackers)、[追跡クエリ](threat-trackers.md#tracked-queries)、および[保存されたクエリ](threat-trackers.md#saved-queries)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e202-p111">[Threat trackers](threat-trackers.md) provide the latest intelligence on prevailing cybersecurity issues. For example, you can view information about the latest malware, and take countermeasures before it becomes an actual threat to your organization. Available trackers include [Noteworthy trackers](threat-trackers.md#noteworthy-trackers), [Trending trackers](threat-trackers.md#trending-trackers), [Tracked queries](threat-trackers.md#tracked-queries), and [Saved queries](threat-trackers.md#saved-queries).</span></span>

- <span data-ttu-id="5e202-p112">[エクスプローラー](use-explorer-in-security-and-compliance.md)(脅威エクスプローラーとも呼ばれます) は、最新の脅威を特定して分析できるリアルタイムレポートです。カスタムの期間のデータを表示するようにエクスプローラーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5e202-p112">[Explorer](use-explorer-in-security-and-compliance.md) (also referred to as Threat Explorer) is a real-time report that allows you to identify and analyze recent threats. You can configure Explorer to show data for custom periods.</span></span>

- <span data-ttu-id="5e202-p113">[アタックシミュレータ](attack-simulator.md)を使用すると、組織内で現実的な攻撃シナリオを実行して vulnerabilites を識別できます。[表示名のスピアーフィッシング攻撃](attack-simulator.md#display-name-spear-phishing-attack)、[パスワードスプレー攻撃](attack-simulator.md#password-spray-attack)、[ブルートフォースパスワード攻撃](attack-simulator.md#brute-force-password-attack)など、現在の種類の攻撃のシミュレーションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="5e202-p113">[Attack Simulator](attack-simulator.md) allows you to run realistic attack scenarios in your organization to identify vulnerabilites. Simulations of current types of attacks are available, including a [display name spear-phishing attack](attack-simulator.md#display-name-spear-phishing-attack), a [password-spray attack](attack-simulator.md#password-spray-attack), a [brute-force password attack](attack-simulator.md#brute-force-password-attack), and more.</span></span>
    
## <a name="permissions-required-to-use-atp-features"></a><span data-ttu-id="5e202-148">ATP 機能を使用するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5e202-148">Permissions required to use ATP features</span></span>

<span data-ttu-id="5e202-p114">セキュリティ & コンプライアンスセンターの ATP 機能にアクセスするには、適切な役割が割り当てられている必要があります。次の表は、いくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e202-p114">To access ATP features in the Security & Compliance Center, you must be assigned an appropriate role. The following table includes some examples:</span></span>

|<span data-ttu-id="5e202-151">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="5e202-151">Role or role group</span></span>  |<span data-ttu-id="5e202-152">詳細については、リソースを参照してください</span><span class="sxs-lookup"><span data-stu-id="5e202-152">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="5e202-153">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="5e202-153">Office 365 Global Administrator</span></span> |[<span data-ttu-id="5e202-154">Office 365 の管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="5e202-154">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="5e202-155">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="5e202-155">Security Administrator</span></span> |[<span data-ttu-id="5e202-156">Azure Active Directory での管理者の役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5e202-156">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="5e202-157">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="5e202-157">Exchange Online Organization Management</span></span> |[<span data-ttu-id="5e202-158">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5e202-158">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="5e202-159">および</span><span class="sxs-lookup"><span data-stu-id="5e202-159">and</span></span><br> [<span data-ttu-id="5e202-160">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e202-160">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="5e202-161">関連項目:</span><span class="sxs-lookup"><span data-stu-id="5e202-161">See also:</span></span>
- [<span data-ttu-id="5e202-162">Office 365 Security & コンプライアンスセンターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5e202-162">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) 

- [<span data-ttu-id="5e202-163">ユーザーに Office 365 Security & コンプライアンスセンターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="5e202-163">Give users access to the Office 365 Security & Compliance Center</span></span>](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a><span data-ttu-id="5e202-164">Office 365 ATP を取得する</span><span class="sxs-lookup"><span data-stu-id="5e202-164">Get Office 365 ATP</span></span>

<span data-ttu-id="5e202-p115">office 365 ATP は、office 365 Enterprise E5、office 365 エデュケーション A5、および Microsoft 365 Business に含まれています。サブスクリプションに Office 365 atp が含まれていない場合は、atp をアドオンとして購入する可能性があります。詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-p115">Office 365 ATP is included in Office 365 Enterprise E5, Office 365 Education A5, and Microsoft 365 Business. If your subscription does not include Office 365 ATP, you can potentially purchase ATP as an add-on. To learn more, see the following resources:</span></span>

- <span data-ttu-id="5e202-168">atp プランを含むサブスクリプションの一覧については、「 [Office 365 Advanced Threat Protection (ATP) availability](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-168">See [Office 365 Advanced Threat Protection (ATP) availability](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) for a list of subscriptions that include ATP plans.</span></span>

- <span data-ttu-id="5e202-169">プラン1および2に含まれる機能の一覧については、「 [Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) Plan」の「機能の可用性」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-169">See [Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) for a list of features included in Plan 1 and 2.</span></span>

- <span data-ttu-id="5e202-170">プランを比較し、office 365 ATP を購入するに[は、「適切な office 365 Advanced Threat Protection を入手](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-170">See [Get the right Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) to compare plans and purchase Office 365 ATP.</span></span>

## <a name="new-features-in-office-365-atp"></a><span data-ttu-id="5e202-171">Office 365 の新機能 ATP</span><span class="sxs-lookup"><span data-stu-id="5e202-171">New features in Office 365 ATP</span></span>

<span data-ttu-id="5e202-p116">新機能が Office 365 ATP に継続的に追加されます。詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e202-p116">New features are added to Office 365 ATP continually. To learn more, see the following resources:</span></span>

- <span data-ttu-id="5e202-174">[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)は、開発時に新機能の一覧を提供し、ロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="5e202-174">The [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) provides a list of new features in development and rolling out.</span></span>

- <span data-ttu-id="5e202-175">[Office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)では、ATP プラン全体での機能と可用性について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e202-175">The [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) describes features and availability across ATP plans.</span></span>
