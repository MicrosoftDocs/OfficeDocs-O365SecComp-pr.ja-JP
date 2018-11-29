---
title: Office 365 のクラウド アプリケーションのセキュリティの新機能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 11/28/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d674763c-a4c9-4604-8623-68c1836d27f3
description: Office 365 のクラウド アプリケーションのセキュリティの新機能を参照してください。
ms.openlocfilehash: a3ca4504d80cbb39b51ecbcf3a5165bc5139e07c
ms.sourcegitcommit: bf628da123a89d9422e8cff02165b1e2d35dfe12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26872015"
---
# <a name="what-is-new-in-office-365-cloud-app-security"></a><span data-ttu-id="2300b-103">Office 365 のクラウド アプリケーションのセキュリティの新機能</span><span class="sxs-lookup"><span data-stu-id="2300b-103">What is new in Office 365 Cloud App Security</span></span>

<span data-ttu-id="2300b-104">**概要**Office 365 クラウド アプリケーションのセキュリティ (旧称 Office 365 の高度なセキュリティ管理)、[マイクロソフトのクラウド アプリケーションのセキュリティ](https://aka.ms/whatiscas)での電源がオンのアップデートおよび新機能の概要を取得するには、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2300b-104">**Summary** Read this article to get a quick overview of updates and new features in Office 365 Cloud App Security (formerly known as Office 365 Advanced Security Management), which is powered by [Microsoft Cloud App Security](https://aka.ms/whatiscas).</span></span>
  
<span data-ttu-id="2300b-p101">機能が追加または強化、この資料は頻繁に更新されます。約 2 週間後、マイクロソフトのクラウド アプリケーションのセキュリティ更新プログラム、office 365 のクラウド アプリケーションのセキュリティ更新プログラムがリリースされ、すべてのマイクロソフトのクラウド アプリケーションのセキュリティ更新プログラムが Office 365 のクラウド アプリケーションのセキュリティを適用します。さらに、新しい機能は、Office 365 のクラウド アプリケーションのセキュリティ環境で表示するには、そのリリース日の後 1 週間以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2300b-p101">This article is updated frequently, as features are added or improved. Office 365 Cloud App Security updates are released approximately two weeks after Microsoft Cloud App Security updates, and not all Microsoft Cloud App Security updates apply to Office 365 Cloud App Security. In addition, new features might take a week or more after their release date to show up in your Office 365 Cloud App Security environment.</span></span>

## <a name="office-365-cloud-app-security-release-136"></a><span data-ttu-id="2300b-108">Office 365 のクラウド アプリケーションのセキュリティ情報公開 136</span><span class="sxs-lookup"><span data-stu-id="2300b-108">Office 365 Cloud App Security release 136</span></span>

<span data-ttu-id="2300b-109">*2018 年 11 月 25日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-109">*Released November 25, 2018*</span></span>

<span data-ttu-id="2300b-110">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、136 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-110">**Following [Microsoft Cloud App Security release 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:</span></span>

- <span data-ttu-id="2300b-p102">**クラウドの検出の更新**追加をサポートするカスタム ログ パーサーが強化されより複雑な web トラフィックをログに記録形式です。これらのユーザーが拡張機能の一部では、headerless の CSV ログ ファイル用のカスタム ヘッダーを入力できるようになりました、特殊な区切り記号を使用して、キーと値のファイルを Syslog ファイルの形式を処理します。</span><span class="sxs-lookup"><span data-stu-id="2300b-p102">**Cloud Discovery updates** The custom log parser was enhanced to support additional and more complex web traffic logs formats. As part of these enhancements users can now input custom headers for headerless CSV log files, use special delimiters for key-value files, process Syslog file format, and more.</span></span>

- <span data-ttu-id="2300b-p103">**新しい異常検出ポリシー: 受信トレイの不審な操作の規則**このポリシーは、ユーザーの受信トレイで削除するか、メッセージまたはフォルダーを移動する不審なルールが設定されている場合、お客様の環境およびアラートのトリガーをプロファイルします。あるユーザーのアカウントが侵害されたことメッセージが意図的に非表示、およびメールボックスがスパムやマルウェア、組織内の配布に使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2300b-p103">**New anomaly detection policy: Suspicious inbox manipulation rules** This policy profiles your environment and triggers alerts when suspicious rules that delete or move messages or folders are set on a user's inbox. This may indicate that the user’s account is compromised, that messages are being intentionally hidden, and that the mailbox is being used to distribute spam or malware in your organization.</span></span>

- <span data-ttu-id="2300b-p104">**アプリケーションのアクセス許可ポリシーのグループのサポート**クラウド アプリケーションのセキュリティになりましたより細かく、アプリケーションのアクセス許可ポリシーを定義する機能、アプリケーションを承認するユーザーのグループ メンバーシップに基づきます。などのアクセス許可を承認したユーザーが管理者グループのメンバーである場合にのみ、高いアクセス許可の要求という場合は、一般的でないアプリケーションを無効にするポリシーを設定するのには管理者が決定できます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p104">**Support for groups in app permission policies** Cloud App Security now gives you the ability to define app permission policies more granularly, based on the group memberships of the users who authorized the apps. For example, an admin can decide to set a policy that revokes uncommon apps if they ask for high permissions, only if the user who authorized the permissions is a member of the administrators group.</span></span>


## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a><span data-ttu-id="2300b-117">133、134、135 の office 365 のクラウド アプリケーションのセキュリティ リリース</span><span class="sxs-lookup"><span data-stu-id="2300b-117">Office 365 Cloud App Security releases 133, 134, and 135</span></span>

<span data-ttu-id="2300b-118">*2018 年 10 月 11 月にリリースされました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-118">*Released in October-November, 2018*</span></span>

<span data-ttu-id="2300b-119">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、133、134、135 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-119">**Following [Microsoft Cloud App Security release 133, 134, and 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:</span></span>

- <span data-ttu-id="2300b-120">**新しい異常検出のポリシー**のロールアウトを段階的にします。</span><span class="sxs-lookup"><span data-stu-id="2300b-120">**New anomaly detection policies** are rolling out gradually:</span></span>
    
    - <span data-ttu-id="2300b-121">新しい**承認されていないアプリケーションにデータ exfiltration**ポリシーはユーザーまたは IP アドレスは、組織内の exfiltrate 情報への試みのような活動を実行する制裁措置されていないアプリケーションを使用する場合に警告するために自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="2300b-121">The new **Data exfiltration to unsanctioned apps** policy is automatically enabled to alert you when a user or IP address uses an app that isn't sanctioned to perform an activity that resembles an attempt to exfiltrate information from your organization.</span></span>
    
    - <span data-ttu-id="2300b-122">新しい**削除して複数の VM 活動**ポリシーでは、プロファイル、環境と、ユーザーが組織のベースラインを基準として、1 つのセッションで複数の Vm を削除するときにアラートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="2300b-122">The new **Multiple delete VM activities** policy profiles your environment and triggers alerts when users delete multiple VMs in a single session, relative to the baseline in your organization.</span></span>

- <span data-ttu-id="2300b-123">**I フィルターのクラウドの検出をサポート**今すぐクラウド アプリケーションのセキュリティのクラウドの検出機能は、i フィルターの syslog パーサーのサポートを拡張しています。</span><span class="sxs-lookup"><span data-stu-id="2300b-123">**Cloud Discovery support for i-Filter** The Cloud App Security Cloud Discovery feature now has enhanced support for the i-Filter syslog parser.</span></span>


## <a name="office-365-cloud-app-security-release-131"></a><span data-ttu-id="2300b-124">Office 365 のクラウド アプリケーションのセキュリティ情報公開 131</span><span class="sxs-lookup"><span data-stu-id="2300b-124">Office 365 Cloud App Security release 131</span></span>

<span data-ttu-id="2300b-125">*、2018 年 9 月 16 日を公開しました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-125">*Released September 16, 2018*</span></span>

<span data-ttu-id="2300b-126">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、131 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-126">**Following [Microsoft Cloud App Security release 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:</span></span>

- <span data-ttu-id="2300b-p105">**危険な OAuth のアプリケーションに対するアクセス許可を自動的に無効**どの OAuth アプリケーションを制御できるよう、ユーザーは Office の OAuth のアプリケーションのアプリケーションのアクセス許可を取り消すと、それらにアクセスします。アプリケーションのアクセス許可ポリシーを作成するには、アプリケーションのアクセス許可を失効するポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p105">**Automatically revoke permissions on risky OAuth apps** You can now control which OAuth apps your users have access to, by revoking app permission for OAuth apps on Office. When creating an App permission policy, you can now set the policy to revoke an app’s permission.</span></span>

- <span data-ttu-id="2300b-129">**クラウドの検出の追加組み込みパーサーがサポートされています。** クラウドの検出は、Forcepoint Web セキュリティのクラウドのログ形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2300b-129">**Cloud Discovery additional built-in parser supported** Cloud Discovery now supports the Forcepoint Web Security Cloud log format.</span></span>

  
## <a name="office-365-cloud-app-security-release-130"></a><span data-ttu-id="2300b-130">Office 365 のクラウド アプリケーションのセキュリティ情報公開 130</span><span class="sxs-lookup"><span data-stu-id="2300b-130">Office 365 Cloud App Security release 130</span></span>

<span data-ttu-id="2300b-131">*2018 年 9 月 5日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-131">*Released September 5, 2018*</span></span>

<span data-ttu-id="2300b-132">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、130 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-132">**Following [Microsoft Cloud App Security release 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:</span></span>

- <span data-ttu-id="2300b-p106">**新しいメニュー バー**365 の Microsoft 製品では、全体でより一貫した管理機能を提供し、使用すると、マイクロソフトのセキュリティ ・ ソリューションの間でより簡単にピボットは、クラウド アプリケーションのセキュリティのポータルのメニュー バーを画面の左側に移動します。この一貫性のあるナビゲーションには、1 つのマイクロソフト セキュリティ ポータルから移動するときに自分で回転することが発生します。</span><span class="sxs-lookup"><span data-stu-id="2300b-p106">**New menu bar** To provide a more consistent admin experience across Microsoft 365 products, and to enable you to pivot more easily between Microsoft security solutions, the Cloud App Security portal menu bar has moved to the left side of the screen. This consistent navigation experience helps you orient yourself when moving from one Microsoft security portal to another.</span></span><br/><span data-ttu-id="2300b-135">![クラウド アプリケーションのセキュリティを Office のメニュー バー](media/OCAS-MenuBar.png)</span><span class="sxs-lookup"><span data-stu-id="2300b-135">![Menu bar in Office Cloud App Security](media/OCAS-MenuBar.png)</span></span><br/>

- <span data-ttu-id="2300b-p107">**影響 OAuth アプリのスコア**今すぐご連絡くださいかどうかは、悪意のあると思われる組織で発見された OAuth アプリケーションをクラウド アプリケーションのセキュリティ チームからのフィードバックを送信できます。この新しい機能を使用すると、セキュリティ コミュニティの一部にして、OAuth アプリケーション リスク ・ スコアと分析を強化できます。詳細については、[アプリケーションのアクセス権の管理](manage-app-permissions-in-ocas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2300b-p107">**Impact OAuth app score** You can now send the Cloud App Security team feedback to let us know if there’s an OAuth app discovered in your organization that seems malicious. This new feature enables you to be part of our security community and enhance OAuth app risk score and analysis. For more information see [Manage app permissions](manage-app-permissions-in-ocas.md).</span></span>

- <span data-ttu-id="2300b-139">**新しいクラウド検出パーサー**クラウドの探索のパーサーは、クラウドのセキュリティで保護されたゲートウェイと Sophos XG の iboss をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2300b-139">**New Cloud Discovery parsers** The Cloud Discovery parsers now support iboss Secure Cloud Gateway and Sophos XG.</span></span>


## <a name="office-365-cloud-app-security-release-128"></a><span data-ttu-id="2300b-140">Office 365 のクラウド アプリケーションのセキュリティ情報公開 128</span><span class="sxs-lookup"><span data-stu-id="2300b-140">Office 365 Cloud App Security release 128</span></span>

<span data-ttu-id="2300b-141">*、2018 年 8 月 5日を公開しました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-141">*Released August 5, 2018*</span></span> 
  
<span data-ttu-id="2300b-142">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、128 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-142">**Following [Microsoft Cloud App Security release 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**:</span></span> 
  
- <span data-ttu-id="2300b-p108">**複数のアプリケーション間でのアプリケーションのアクセス許可**アプリケーションのアクセス許可が付与されているアプリケーションでは、今すぐアクセスを禁止したり、1 つのアクションで複数のアプリケーションを承認できます。など、組織内のユーザーからアクセス許可が与えられている、アクセスを禁止するすべてのアプリケーションを選択し、禁止ユーザーのアプリケーションを許可するすべての同意を取り消すにはすべてのアプリケーションを確認することができ、ユーザーがアプリケーションにアクセス許可を付与すると、不要になった。</span><span class="sxs-lookup"><span data-stu-id="2300b-p108">**App permissions across multiple apps** For apps that have been granted app permissions, you can now ban or approve multiple apps in a single action. For example, you can review all the apps that have been granted permission by users in your organization, select all the apps you want to ban, and then click ban apps to revoke all consent granted and will no longer allow users to grant permission to those apps.</span></span> 
    
- <span data-ttu-id="2300b-p109">**新しい推奨されるクエリ: GDPR の準備完了**GDPR の準備は、検出されたアプリケーションを識別できるようにするための新しい推奨されるクエリがあります。GDPR は、セキュリティ管理者の最優先事項と最後になりました。このクエリでは、容易に GDPR の準備ができて、あるアプリケーションを特定しではないアプリケーションのリスク評価を行い、脅威を軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p109">**New suggested query: GDPR ready** There is a new suggested query to enable you to identify discovered apps that are GDPR ready. GDPR has recently became a top priority for security admins. This query helps you easily identify apps that are GDPR ready, and mitigate threat by assessing the risk of the apps that aren't.</span></span> 
    
## <a name="office-365-cloud-app-security-release-126"></a><span data-ttu-id="2300b-148">Office 365 のクラウド アプリケーションのセキュリティ情報公開 126</span><span class="sxs-lookup"><span data-stu-id="2300b-148">Office 365 Cloud App Security release 126</span></span>

<span data-ttu-id="2300b-149">*2018 年 7 月 7日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-149">*Released July 7, 2018*</span></span> 
  
<span data-ttu-id="2300b-150">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、126 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-150">**Following [Microsoft Cloud App Security release 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**:</span></span> 
  
- <span data-ttu-id="2300b-p110">**不審なアクティビティの自動修復**異常検出のポリシーによって発生した、不審なセッションの自動修復アクションを設定できます。この拡張機能を使用すると、侵害が発生したときに通知を受け取るとガバナンスのアクションを自動的に適用、次のようにユーザーを中断できます。詳細については、 [Office 365 のクラウド アプリケーションのセキュリティでの異常検出ポリシー](anomaly-detection-policies-in-ocas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2300b-p110">**Automated remediation for suspicious activities** You can now set automatic remediation actions for suspicious session triggered by the anomaly detection policies. This enhancement enables you to be alerted instantly when a breach occurs and apply governance actions automatically, such as suspend user. For more information, see [Anomaly detection policies in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md).</span></span>
    
- <span data-ttu-id="2300b-p111">**危険な OAuth アプリケーションの自動検出**だけでなく、環境に接続されている OAuth アプリケーションの既存の調査、Office 365 のクラウド アプリケーションのセキュリティできるようになりましたが、OAuth のアプリケーションが特定の条件を満たしていることへの自動通知を設定します。などを自動的に警告を発行アプリケーションがある場合に高いアクセス許可レベルを必要として 50 以上のユーザーによって承認されていました。詳細については、 [Office 365 のクラウド アプリケーションのセキュリティを使用してアプリケーションのアクセス許可の管理](manage-app-permissions-in-ocas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2300b-p111">**Automated detection of risky OAuth Apps** In addition to the existing investigate of OAuth apps connected to your environment, Office 365 Cloud App Security now allows you to set automated notifications to let you know when an OAuth app meets certain criteria. For example, you can automatically be alerted when there are apps that require a high permission level and were authorized by more than 50 users. For more information, see [Manage app permissions using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).</span></span>
    
- <span data-ttu-id="2300b-p112">**マネージド セキュリティ サービス プロバイダーの管理 (MSSP) のサポート**Office 365 のクラウド アプリケーションのセキュリティ今すぐ管理エクスペリエンスを向上させる Mssp には、Office 365 のクラウド アプリケーションのセキュリティでは、現在利用可能なロールを持つ管理者として外部のパートナーを構成できます。さらに、複数のテナントへのアクセス権を持つ管理者ことができます今すぐ簡単にピボット、テナントとの間。</span><span class="sxs-lookup"><span data-stu-id="2300b-p112">**Managed Security Service Provider management (MSSP) support** Office 365 Cloud App Security now provides a better management experience to MSSPs, and allows you to configure external partners as administrators with any of the roles currently available in Office 365 Cloud App Security. In addition, Administrators with access rights to more than one tenant can now easily pivot between the tenants.</span></span> 
    
## <a name="office-365-cloud-app-security-release-124"></a><span data-ttu-id="2300b-159">Office 365 のクラウド アプリケーションのセキュリティ情報公開 124</span><span class="sxs-lookup"><span data-stu-id="2300b-159">Office 365 Cloud App Security release 124</span></span>

<span data-ttu-id="2300b-160">*2018 年 6 月 10日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-160">*Released June 10, 2018*</span></span> 
  
<span data-ttu-id="2300b-161">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、124 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-161">**Following [Microsoft Cloud App Security release 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**:</span></span> 
  
- <span data-ttu-id="2300b-p113">**スコープ ベースの展開**企業は、グループ メンバーシップに基づいて、ユーザーを監視し、保護するために細かく確認できます。この機能を使用すると、すべての活動が表示されません、保護されたアプリケーションのいずれかのユーザーを選択できます。スコープ指定された監視では、コンプライアンス、およびライセンスに特に便利です。一部のコンプライアンス要件では、ローカルの規制により、特定の国からのユーザーを監視しないことが必要となります。より少ないユーザーは、Office 365 のクラウド アプリケーションのセキュリティのライセンスの制限の範囲内を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p113">**Scoped deployments** Enterprise organizations can granularly determine which users to monitor and protect based on group membership. This feature enables you to select users whose activities will not show up for any of the protected applications. Scoped monitoring is especially useful for compliance and licensing. Some compliance regulations necessitate that you refrain from monitoring users from certain countries due to local regulations. And, you can monitor fewer users to stay within the limits of your Office 365 Cloud App Security licenses.</span></span> 
    
- <span data-ttu-id="2300b-p114">**新しい電子メール サーバー**Office 365 のクラウド アプリケーションのセキュリティ用の電子メール サーバーが変更され、別の IP アドレス範囲を使用します。通知を受信できるようにするには、新しい IP アドレスをスパム対策のホワイト リストに追加します。組織の通知をカスタマイズするには、クラウド アプリケーションのセキュリティは、これを MailChimp、サード ・ パーティ製の電子メール サービスを使用して使用できます。、メール サーバーの IP アドレス、および MailChimp での作業を有効にする方法の一覧は、[ネットワーク要件 (マイクロソフトのクラウド アプリケーションのセキュリティ)](https://docs.microsoft.com/cloud-app-security/network-requirements)と[メールの設定 (マイクロソフトのクラウド アプリケーションのセキュリティ)](https://docs.microsoft.com/cloud-app-security/mail-settings)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2300b-p114">**New email server** The email server for Office 365 Cloud App Security has changed and uses different IP address ranges. To make sure you can get notifications, add the new IP addresses to your anti-spam whitelist. For organizations who customize their notifications, Cloud App Security enables this for you using MailChimp, a third-party email service. For the list of mail server IP addresses, and instructions for enabling work with MailChimp, see [Network requirements (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/network-requirements) and [Mail settings (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/mail-settings).</span></span>
    
## <a name="office-365-cloud-app-security-release-121"></a><span data-ttu-id="2300b-171">Office 365 のクラウド アプリケーションのセキュリティ情報公開 121</span><span class="sxs-lookup"><span data-stu-id="2300b-171">Office 365 Cloud App Security release 121</span></span>

<span data-ttu-id="2300b-172">*、2018 年 5 月月 6 日を公開しました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-172">*Released May 6, 2018*</span></span> 
  
<span data-ttu-id="2300b-173">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、121 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-173">**Following [Microsoft Cloud App Security release 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**:</span></span> 
  
- <span data-ttu-id="2300b-p115">**異常検出ポリシーの改善**。ロールアウトを段階的に脅威の検出の 2 つの新しいタイプを含めるには、office 365 のクラウド アプリケーション セキュリティの異常検出ポリシーが強化されました。</span><span class="sxs-lookup"><span data-stu-id="2300b-p115">**Anomaly detection policy improvements**. Office 365 Cloud App Security's anomaly detection policies have been improved to include two new types of threat detection that are gradually rolling out:</span></span> 
    
  - <span data-ttu-id="2300b-p116">**Ransomware アクティビティ**。Ransomware の高度な攻撃に対してより包括的なカバレッジを提供する異常の検出と Ransomware 検出機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p116">**Ransomware activity.** Ransomware detection capabilities are extended with anomaly detection to give you more comprehensive coverage against sophisticated ransomware attacks.</span></span> 
    
  - <span data-ttu-id="2300b-p117">**ユーザー ・ アクティビティを終了します**。ユーザー アクティビティを有効にあった可能性があります、企業のアプリケーションから、準備されたが、誰もが、退職したユーザーのアカウントを監視することがある企業の特定のリソースへのアクセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="2300b-p117">**Terminated user activity.** Terminated user activity enables you to monitor the accounts of terminated users who may have been de-provisioned from corporate applications, but who might still have access to certain corporate resources.</span></span> 
    
    <span data-ttu-id="2300b-180">Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに、[異常の検出ポリシー](anomaly-detection-policies-in-ocas.md)を表示するには、**コントロール**を選択\>**のポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="2300b-180">To view your [Anomaly detection policies](anomaly-detection-policies-in-ocas.md), in the Office 365 Cloud App Security portal, choose **Control** \> **Policies**.</span></span>
    
## <a name="office-365-cloud-app-security-release-120"></a><span data-ttu-id="2300b-181">Office 365 のクラウド アプリケーションのセキュリティ情報公開 120</span><span class="sxs-lookup"><span data-stu-id="2300b-181">Office 365 Cloud App Security release 120</span></span>

<span data-ttu-id="2300b-182">*、2018 年 4 月 22日を公開しました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-182">*Released April 22, 2018*</span></span> 
  
<span data-ttu-id="2300b-183">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、120 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-183">**Following [Microsoft Cloud App Security release 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**:</span></span> 
  
- <span data-ttu-id="2300b-p118">**ユーザーの活動として、社内のアプリケーション**です。Office 365 と Azure Active Directory (AD の Azure) は、ここで徐々 に進行として Office 365 と AD の Azure アプリケーション (内部および外部の両方) によって実行されるユーザー ・ アカウント ・ アクティビティの内部アプリケーションを検出する機能をします。これにより、アプリケーションが予期しないと、許可されていないアクティビティを実行する場合に警告するためポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p118">**Internal applications as user activities**. For Office 365 and Azure Active Directory (Azure AD), we are now gradually rolling out the ability to detect internal applications as user account activities performed by the Office 365 and Azure AD applications (both internal and external). This enables you to create policies to alert you if an application performs unexpected and unauthorized activities.</span></span> 
    
- <span data-ttu-id="2300b-p119">**アプリケーションのアクセス許可] ボックスの一覧で複数のフィールドをエクスポート**します。Csv、出版社などの他のフィールドに、アプリケーションのアクセス許可] ボックスの一覧をエクスポートするとき、アクセス許可レベルおよびコミュニティの利用状況は、コンプライアンスおよび調査のプロセスを支援するために含まれます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p119">**More fields in app permissions list export**. When exporting an app permissions list to csv, additional fields such as publisher, permissions level and community usage are included to assist with the compliance and investigation process.</span></span> 
    
## <a name="office-365-cloud-app-security-release-119"></a><span data-ttu-id="2300b-189">Office 365 のクラウド アプリケーションのセキュリティ情報公開 119</span><span class="sxs-lookup"><span data-stu-id="2300b-189">Office 365 Cloud App Security release 119</span></span>

<span data-ttu-id="2300b-190">*、2018 年 4 月 1 日を公開しました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-190">*Released April 1, 2018*</span></span> 
  
<span data-ttu-id="2300b-191">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、119 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-191">**Following [Microsoft Cloud App Security release 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**:</span></span> 
  
- <span data-ttu-id="2300b-p120">**クラウドの検出を改善**します。クラウドの検出では、Office 365 の使用方法の詳細を表示し、他のアプリケーションを容易にすること上のユーザーと IP アドレスの詳細についてを提供します。詳細については、 [Office 365 のクラウド アプリケーションのセキュリティでアプリケーションの検出調査結果のレビュー](review-app-discovery-findings-in-ocas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2300b-p120">**Improvements to Cloud Discovery**. The Cloud Discovery provides more information about top users and IP addresses, making it easier to view usage details about Office 365 and other apps. To learn more, see [Review app discovery findings in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md).</span></span>
    
    ![クラウドの探索のダッシュ ボードが更新されました](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a><span data-ttu-id="2300b-196">Office 365 のクラウド アプリケーションのセキュリティ情報公開 118</span><span class="sxs-lookup"><span data-stu-id="2300b-196">Office 365 Cloud App Security release 118</span></span>

<span data-ttu-id="2300b-197">*、2018 年 3 月 18日を公開しました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-197">*Released March 18, 2018*</span></span> 
  
<span data-ttu-id="2300b-198">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、118 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-198">**Following [Microsoft Cloud App Security release 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**:</span></span> 
  
- <span data-ttu-id="2300b-p121">**Barracuda をサポート**しています。クラウドの探索は、Barracuda F シリーズのファイアウォールおよび Barracuda F シリーズ ファイアウォールの web ログのストリーミングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2300b-p121">**Barracuda support**. Cloud Discovery now supports Barracuda F Series firewalls and Barracuda F-Series firewall web log streaming.</span></span> 
    
## <a name="office-365-cloud-app-security-release-117"></a><span data-ttu-id="2300b-201">Office 365 のクラウド アプリケーションのセキュリティ情報公開 117</span><span class="sxs-lookup"><span data-stu-id="2300b-201">Office 365 Cloud App Security release 117</span></span>

<span data-ttu-id="2300b-202">*、2018 年 3 月 6日を公開しました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-202">*Released March 6, 2018*</span></span> 
  
<span data-ttu-id="2300b-203">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、117 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-203">**Following [Microsoft Cloud App Security release 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**:</span></span> 
  
- <span data-ttu-id="2300b-p122">**i フィルターをサポート**しています。クラウドの探索は、i フィルターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2300b-p122">**i-FILTER support**. Cloud Discovery now supports i-FILTER.</span></span> 
    
## <a name="office-365-cloud-app-security-release-116"></a><span data-ttu-id="2300b-206">Office 365 のクラウド アプリケーションのセキュリティ情報公開 116</span><span class="sxs-lookup"><span data-stu-id="2300b-206">Office 365 Cloud App Security release 116</span></span>

<span data-ttu-id="2300b-207">*2018 年 2 月 18日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-207">*Released February 18, 2018*</span></span> 
  
<span data-ttu-id="2300b-208">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、116 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-208">**Following [Microsoft Cloud App Security release 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**:</span></span> 
  
- <span data-ttu-id="2300b-p123">**異常検出ポリシーの拡張機能**です。異常検出のポリシーで不可能な旅行、不審な IP アドレスからの活動を含む新規のシナリオに基づく検出と Office 365 のクラウド アプリケーションのセキュリティが強化され、複数の失敗したログイン試行します。ボックスの脅威の検出を提供する、クラウド環境全体にわたって、新しいポリシーが自動的に有効。 にします。さらに、新しいポリシーは、調査のプロセスを高速化し、継続的な脅威が含まれていることができます、Office 365 のクラウド アプリケーションのセキュリティ検出エンジンからより多くのデータを公開します。詳細については、[瞬間的な動作分析と異常検出](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)、マイクロソフトのクラウド アプリケーションのセキュリティの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2300b-p123">**Anomaly detection policy enhancements**. Anomaly detection polices in Office 365 Cloud App Security were enhanced with new scenario-based detections including impossible travel, activity from a suspicious IP address and multiple failed login attempts. The new policies are automatically enabled, providing out-of-the-box threat detection across your cloud environment. In addition, the new policies expose more data from the Office 365 Cloud App Security detection engine, which can help speed up the investigation process and contain ongoing threats. To learn more, see the Microsoft Cloud App Security article, [Get instantaneous behavioral analytics and anomaly detection](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy).</span></span>
    
- <span data-ttu-id="2300b-p124">**チェックポイント形式では、ログ パーサー サポート**します。クラウド検出ログ パーサーをサポートして追加の 2 つのチェックポイント形式: XML、および KPC。</span><span class="sxs-lookup"><span data-stu-id="2300b-p124">**Log parser support for Checkpoint formats**. The Cloud Discovery log parsers now support two additional Checkpoint formats: XML, and KPC.</span></span> 
    
## <a name="office-365-cloud-app-security-release-114"></a><span data-ttu-id="2300b-216">Office 365 のクラウド アプリケーションのセキュリティ情報公開 114</span><span class="sxs-lookup"><span data-stu-id="2300b-216">Office 365 Cloud App Security release 114</span></span>

<span data-ttu-id="2300b-217">*、2018 年 1 月 21 日を公開しました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-217">*Released January 21, 2018*</span></span> 
  
<span data-ttu-id="2300b-218">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、114 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-218">**Following [Microsoft Cloud App Security release 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**:</span></span> 
  
- <span data-ttu-id="2300b-p125">**サービスの状態**です。**ヘルプ**に移動して Office 365 のクラウド アプリケーションのセキュリティ サービスの現在の状態を確認できる\>**システムの状態**です。</span><span class="sxs-lookup"><span data-stu-id="2300b-p125">**Service status**. You can now check the current Office 365 Cloud App Security service status by going to **Help** \> **System status**.</span></span> 
    
    ![[ヘルプ] をクリックして\>システムのヘルス ステータスを表示するのにはシステムの状態](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- <span data-ttu-id="2300b-p126">**アクティビティ ・ ログのユーザー設定のクエリ**です。114 のバージョン以降では、作成し、アクティビティ ・ ログにカスタム クエリを保存する機能は、ロールアウト徐々 にします。カスタム クエリを使用すると、詳しく調査を再利用できるフィルター テンプレートを作成します。クエリがされているがさらに、提示、アクティビティをフィルター処理するテンプレートを初期状態の調査を提供する追加され、アプリケーションを検出します。推奨されるクエリには、脆弱な暗号化およびセキュリティ上のリスクと偽装活動、管理者の活動、危険な非準拠のクラウド ・ ストレージ ・ アプリケーション、エンタープライズ アプリケーションなどのリスクを識別するカスタム フィルターが含まれます。推奨されるクエリを使用して、開始点として、必要に応じて、変更し、新しいクエリとして保存します。</span><span class="sxs-lookup"><span data-stu-id="2300b-p126">**Custom queries for Activity log**. Beginning in version 114, the ability to create and save custom queries in the Activity log is rolling out gradually. Custom queries enable you to create filter templates that can be reused for deep-dive investigation. In addition, suggested queries have been added to provide out-of-the-box investigation templates to filter your activities and discovered apps. Suggested queries include custom filters to identify risks such as impersonation activities, administrator activities, risky non-compliant cloud storage apps, enterprise apps with weak encryption, and security risks. Use the suggested queries as a starting point, modify them as needed, and then save them as a new query.</span></span> 
    
## <a name="office-365-cloud-app-security-release-113"></a><span data-ttu-id="2300b-228">Office 365 のクラウド アプリケーションのセキュリティ情報公開 113</span><span class="sxs-lookup"><span data-stu-id="2300b-228">Office 365 Cloud App Security release 113</span></span>

<span data-ttu-id="2300b-229">*、2018 年 1 月 8日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-229">*Released January 8, 2018*</span></span> 
  
<span data-ttu-id="2300b-230">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、113 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-230">**Following [Microsoft Cloud App Security release 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**:</span></span> 
  
- <span data-ttu-id="2300b-p127">**汎用的な形式では、ログ パーサー サポート**します。クラウド検出ログ パーサーをサポートして、次の一般的な形式: LEEF、CEF、および W3C。</span><span class="sxs-lookup"><span data-stu-id="2300b-p127">**Log parser support for generic formats**. The Cloud Discovery log parsers now support the following generic formats: LEEF, CEF, and W3C.</span></span> 
    
## <a name="office-365-cloud-app-security-release-112"></a><span data-ttu-id="2300b-233">Office 365 のクラウド アプリケーションのセキュリティ情報公開 112</span><span class="sxs-lookup"><span data-stu-id="2300b-233">Office 365 Cloud App Security release 112</span></span>

<span data-ttu-id="2300b-234">*2017 年 12 月 24日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-234">*Released December 24, 2017*</span></span> 
  
<span data-ttu-id="2300b-235">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、112 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-112)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-235">**Following [Microsoft Cloud App Security release 112](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-112)**:</span></span> 
  
- <span data-ttu-id="2300b-p128">**関連情報の引き出し**です。アクティビティ ・ ログにユーザー名または IP アドレスをクリックして関連する情報の引き出しをアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p128">**Relevant insight drawer**. In the Activity log, you can now access the relevant insight drawer by clicking on a user name or IP address.</span></span> 
    
    ![ユーザー名またはアクティビティ ・ ログに関連する情報の引き出しを使用して IP アドレスをクリックします。](media/8e32b3fa-8c0c-4c5e-b248-fe7d7e1b516d.png)
  
- <span data-ttu-id="2300b-p129">**クリックするだけで複数のアクティビティを表示する機能**です。関連情報給紙トレイで選択したアクティビティの 48 時間以内に実行されるすべてのアクティビティを表示する時計のアイコンをクリックできます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p129">**Ability to view more activities with a click**. In the relevant insight drawer, you can click the clock icon to view all activities performed within 48 hours of a selected activity.</span></span> 
    
    ![プラットフォームとして活用する給紙トレイで選択したアクティビティの 48 時間以内に実行されるアクティビティを表示する時計のアイコンを選択できます。](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
- <span data-ttu-id="2300b-p130">**ビャクシン SRX のログ パーサーを向上**します。改良クラウド検出ログ パーサー ビャクシン SRX 用です。</span><span class="sxs-lookup"><span data-stu-id="2300b-p130">**Log parser improvements for Juniper SRX**. Improvements were made to the Cloud Discovery log parser for Juniper SRX.</span></span> 
    
## <a name="office-365-cloud-app-security-release-111"></a><span data-ttu-id="2300b-244">111 office 365 のクラウド アプリケーションのセキュリティ情報公開</span><span class="sxs-lookup"><span data-stu-id="2300b-244">Office 365 Cloud App Security release 111</span></span>

<span data-ttu-id="2300b-245">*2017 年 12 月 10日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-245">*Released December 10, 2017*</span></span> 
  
<span data-ttu-id="2300b-246">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、111 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-111)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-246">**Following [Microsoft Cloud App Security release 111](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-111)**:</span></span> 
  
- <span data-ttu-id="2300b-p131">**時間フィルターの機能強化**します。時間フィルターは、使いやすくなりました。ビューでは、アクティビティ ・ ログ、ポリシー、詳細の表示を使用して、アラートなどの時間フィルターにアクセスするには、フィルターの一覧で**日付**を選択します。オプションを選択などの前に、後、または間に時間フィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="2300b-p131">**Time filter improvements**. Time filters are now easier to use. To access a time filter, in a view, such as Activity log, Policies, Alerts, using the Advanced view, choose **Date** in the list of filters. Then choose an option, such as before, after, or in between to apply the time filter.</span></span> 
    
    ![前に、か、後ろの日付の間の情報を表示するのにには、日付フィルターを使用します。](media/9dbb2a10-f68f-413b-8b4e-88911152cb92.png)
  
## <a name="office-365-cloud-app-security-release-110"></a><span data-ttu-id="2300b-252">Office 365 のクラウド アプリケーションのセキュリティ情報公開 110</span><span class="sxs-lookup"><span data-stu-id="2300b-252">Office 365 Cloud App Security release 110</span></span>

<span data-ttu-id="2300b-253">*2017 年 11 月 26日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-253">*Released November 26, 2017*</span></span> 
  
<span data-ttu-id="2300b-254">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、110 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-110)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-254">**Following [Microsoft Cloud App Security release 110](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-110)**:</span></span> 
  
- <span data-ttu-id="2300b-p132">**SIEM サーバの統合が一般に利用可能なようになりました**。Office 365 のクラウド アプリケーションのセキュリティ、SIEM のサーバーに接続します。今すぐ送信できます警告および活動に自動的に SIEM 任意のサーバーに SIEM のエージェントを構成することによって。[統合 SIEM サーバーに Office 365 のクラウド アプリケーションのセキュリティ](integrate-your-siem-server-with-office-365-cas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2300b-p132">**SIEM server integration now generally available**. Connect your SIEM server to Office 365 Cloud App Security. You can now send alerts and activities automatically to your SIEM server of choice by configuring SIEM Agents. See [Integrate your SIEM server with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).</span></span>
    
- <span data-ttu-id="2300b-p133">**ヘルプ コンテンツに容易にアクセス**します。右上隅の新しいの疑問符 () を使用すると、Office 365 のクラウド アプリケーションのセキュリティ関連ポータルのページ内からヘルプの内容を今すぐアクセスできます。各リンクは、実行することが必要な情報を上のページに基づく状況依存です。</span><span class="sxs-lookup"><span data-stu-id="2300b-p133">**Easier access to help content**. Using the new question mark in the upper right corner, you can now access the help content from within the pages of the Office 365 Cloud App Security portal. Each link is context-sensitive, taking you to the information you need, based on the page you're on.</span></span> 
    
- <span data-ttu-id="2300b-p134">**フィードバックをお送り**します。スマイリー フェイスを使用して、右上隅で、Office 365 のクラウド アプリケーションのセキュリティ関連ポータルのすべてのページからフィードバックを送信することができますようになりました。これにより、バグを報告し、新機能を要求し、Office 365 のクラウド アプリケーションのセキュリティ チームとの直接の経験を共有することができます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p134">**Send us feedback**. Using the smiley face in the upper right corner, you can now send feedback from every page of the Office 365 Cloud App Security portal. This enables you to report bugs, request new features and share your experience directly with the Office 365 Cloud App Security team.</span></span> 
    
## <a name="office-365-cloud-app-security-release-102"></a><span data-ttu-id="2300b-265">Office 365 のクラウド アプリケーションのセキュリティ情報公開 102</span><span class="sxs-lookup"><span data-stu-id="2300b-265">Office 365 Cloud App Security release 102</span></span>

<span data-ttu-id="2300b-266">*2017 年 8 月 13日をリリースしました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-266">*Released August 13, 2017*</span></span> 
  
<span data-ttu-id="2300b-267">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、102 を解放](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-102)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-267">**Following [Microsoft Cloud App Security release 102](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-102)**:</span></span> 
  
- <span data-ttu-id="2300b-p135">**新しいユーザー調査の操作**は、ドリル ダウンのレベルを追加を有効にするユーザーの調査をします。[調査] ページでは、アクティビティ、ユーザ、またはアカウントをポイントして、フィルターとして適用して、そこから関連の活動やイベントを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2300b-p135">**New user investigation actions** enable an added level of drill-down to user investigations. On an Investigate page, you can hover on an activity, user, or account and apply it as a filter, and from there, you can view related activities or events.</span></span> 
    
## <a name="office-365-cloud-app-security-release-100"></a><span data-ttu-id="2300b-270">Office 365 のクラウド アプリケーションのセキュリティ情報公開 100</span><span class="sxs-lookup"><span data-stu-id="2300b-270">Office 365 Cloud App Security release 100</span></span>

<span data-ttu-id="2300b-271">*、2017 年 7 月 17日を公開しました。*</span><span class="sxs-lookup"><span data-stu-id="2300b-271">*Released July 17, 2017*</span></span> 
  
<span data-ttu-id="2300b-272">の**次の[マイクロソフトのクラウド アプリケーションのセキュリティは、100 をリリース](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-100)** します。</span><span class="sxs-lookup"><span data-stu-id="2300b-272">**Following [Microsoft Cloud App Security release 100](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-100)**:</span></span> 
  
- <span data-ttu-id="2300b-p136">**セキュリティ拡張機能**は、一元的に管理できる、すべてのセキュリティ拡張機能 API トークンと SIEM のエージェントを含む、Office 365 クラウド アプリケーション セキュリティの新しいダッシュ ボードです。セキュリティ拡張機能のダッシュ ボードを表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2300b-p136">**Security extensions** is a new dashboard where you can centrally manage all your security extensions for Office 365 Cloud App Security, including API tokens and SIEM agents. To view the Security extensions dashboard, follow these steps:</span></span> 
    
1. <span data-ttu-id="2300b-p137">[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="2300b-p137">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="2300b-277">**アラート**を参照して\>**詳細なアラートを管理**します。</span><span class="sxs-lookup"><span data-stu-id="2300b-277">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="2300b-278">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2300b-278">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![セキュリティ&amp;コンプライアンス センターでは、アラートを選択して\>アラートを高度な管理\>高度なセキュリティ管理に移動します](media/9792b121-9cd4-4faa-a6e0-81cfab4bf2f2.png)
  
4. <span data-ttu-id="2300b-280">**設定**を選択して\>**セキュリティ拡張機能**です。</span><span class="sxs-lookup"><span data-stu-id="2300b-280">Choose **Settings** \> **Security extensions**.</span></span>
    
    ![ASM ポータルでは、設定を選択します\>セキュリティ拡張機能](media/f03d47a1-91ff-41b9-9baf-b514cffe41a8.png)
  
- <span data-ttu-id="2300b-p138">**解析を向上**します。クラウド検出ログ メカニズムの解析に改良が加えられました。内部のエラーは、大幅に発生しにくくします。</span><span class="sxs-lookup"><span data-stu-id="2300b-p138">**Improved parsing**. Improvements were made in the Cloud Discovery log parsing mechanism. Internal errors are significantly less likely to occur.</span></span> 
    
- <span data-ttu-id="2300b-p139">**期待されるログ形式**です。クラウド検出ログの予想されるログの形式は、ここで Syslog 形式と形式の FTP の両方の例を示します。</span><span class="sxs-lookup"><span data-stu-id="2300b-p139">**Expected log formats**. The expected log format for Cloud Discovery logs now provides examples for both Syslog format and FTP format.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="2300b-287">関連項目</span><span class="sxs-lookup"><span data-stu-id="2300b-287">Related topics</span></span>

[<span data-ttu-id="2300b-288">Office 365 のクラウド アプリケーションのセキュリティのヘルプ コンテンツ</span><span class="sxs-lookup"><span data-stu-id="2300b-288">Office 365 Cloud App Security help content</span></span>](office-365-cas-help.md)
  
[<span data-ttu-id="2300b-289">Office 365 Cloud App Security 展開後の利用に関する作業</span><span class="sxs-lookup"><span data-stu-id="2300b-289">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
  
[<span data-ttu-id="2300b-290">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="2300b-290">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

