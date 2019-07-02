---
title: Microsoft 365 セキュリティセンターのデバイスの監視とレポート
description: 組織において、デバイスのセキュリティを確保し、最新の状態を維持し、潜在的な脅威を特定する方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、デバイス
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 44fd28a0ba2ec72d999c89d183d85ccb496903ec
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852871"
---
# <a name="device-monitoring-and-reporting-in-microsoft-365-security-center"></a><span data-ttu-id="35fc2-104">Microsoft 365 セキュリティセンターのデバイスの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="35fc2-104">Device monitoring and reporting in Microsoft 365 security center</span></span>

<span data-ttu-id="35fc2-105">モバイルデバイスのセキュリティを確保し、最新の状態に保つことができます。また、潜在的な脅威については、Microsoft 365 セキュリティセンターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="35fc2-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="35fc2-106">デバイスの通知を表示する</span><span class="sxs-lookup"><span data-stu-id="35fc2-106">View device alerts</span></span>

<span data-ttu-id="35fc2-107">Microsoft Defender ATP (E5 ライセンス付き) から、デバイスに対する違反アクティビティやその他の脅威に関する最新の通知を入手できます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="35fc2-108">Microsoft 365 セキュリティセンターは、優先ワークフローを使用して、これらのアラートを高レベルで効果的に監視します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="35fc2-109">影響度の高いアラートを監視する</span><span class="sxs-lookup"><span data-stu-id="35fc2-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="35fc2-110">Microsoft Defender ATP の各アラートには、対応する重要度 (高、中、低、または情報) があります。これは、無人のままでネットワークに影響を与える可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-110">Each Microsoft Defender ATP alert has a corresponding severity—high, medium, low, or informational—that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="35fc2-111">**デバイスアラートの重要度**カードを使用して、より深刻で、即時応答を必要とする可能性があるアラートに特に注目します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="35fc2-112">このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![デバイス通知の重要度カード](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="35fc2-114">通知のソースを理解する</span><span class="sxs-lookup"><span data-stu-id="35fc2-114">Understand sources of alerts</span></span>

<span data-ttu-id="35fc2-115">Microsoft Defender ATP は、さまざまなセキュリティセンサーおよびインテリジェンスソースからのデータを利用して、アラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="35fc2-116">たとえば、web サービス API によって提供される独自のカスタム脅威インテリジェンスに加えて、Windows Defender ウイルス対策およびサードパーティのマルウェア対策の検出情報を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="35fc2-117">**デバイスアラート検出**ソースカードは、通知のソース別の配布を示しています。</span><span class="sxs-lookup"><span data-stu-id="35fc2-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="35fc2-118">このカードは、特定のソース (特にカスタムソース) に関連するアクティビティを追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="35fc2-119">また、これを使用して、悪意のあるアクティビティやコンポーネントを自動的にブロックするように構成されていないセンサーからのアラートに焦点を当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![デバイスアラート検出ソースカード](./media/security-docs/device-alert-detection-sources.png)

<span data-ttu-id="35fc2-121">このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="35fc2-122">アラートを発生させる脅威の種類を理解する</span><span class="sxs-lookup"><span data-stu-id="35fc2-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="35fc2-123">Microsoft Defender ATP は、各アラートを、アタックチェーンまたは脅威コンポーネントの特定の段階を表すカテゴリに分類します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="35fc2-124">たとえば、検出された脅威アクティビティは、ネットワーク上の他のデバイスに接続しようとしたときに、攻撃者が初期 foothold を取得した後に発生した可能性があることを示すために、"左右の移動" に分類されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-124">For example, detected threat activity might be categorized into “lateral movement” to indicate that the activity involved an attempt to reach other devices on the network and has likely occurred after attackers have gained an initial foothold.</span></span> <span data-ttu-id="35fc2-125">検出された場合、脅威コンポーネントは、「マルウェア」、または特に「ランサムウェア」、「資格情報の盗用」、またはその他の悪意のあるソフトウェアまたは望ましくないソフトウェアとして分類されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-125">When detected, a threat component might either be classified broadly as “malware” or more specifically as “ransomware”, “credential stealing” or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="35fc2-126">**デバイスの脅威カテゴリ**カードには、これらのカテゴリへのアラートの配布が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-126">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="35fc2-127">この情報を使用して、資格情報の盗難などの脅威のアクティビティを識別できます。たとえば、ソーシャルエンジニアリングの試行と比較して、より重大な影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35fc2-127">You can use this information to identify threat activity, such as attempts at credential theft, which can have more significant impact compared to attempts at social engineering, for example.</span></span> <span data-ttu-id="35fc2-128">これを使用して、ランサムウェアなどの潜在的な破壊的脅威を監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-128">You can also use this to monitor for potentially destructive threats like ransomware.</span></span>

![デバイスの脅威カテゴリカード](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="35fc2-130">アクティブなアラートを監視する</span><span class="sxs-lookup"><span data-stu-id="35fc2-130">Monitor active alerts</span></span>

<span data-ttu-id="35fc2-131">**デバイス通知ステータス**カードは、解決されておらず、注意が必要なアラートの数を示しています。</span><span class="sxs-lookup"><span data-stu-id="35fc2-131">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="35fc2-132">このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-132">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![デバイスアラートステータスカード](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="35fc2-134">解決されたアラートの分類を監視する</span><span class="sxs-lookup"><span data-stu-id="35fc2-134">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="35fc2-135">Microsoft Defender ATP 通知を解決するとき、セキュリティ担当者は通知を次のように確認するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-135">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="35fc2-136">実際の違反アクティビティまたは脅威コンポーネントを識別する真の通知</span><span class="sxs-lookup"><span data-stu-id="35fc2-136">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="35fc2-137">通常のアクティビティを誤って検出した false アラート</span><span class="sxs-lookup"><span data-stu-id="35fc2-137">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="35fc2-138">**デバイス通知分類**カードは、解決済みのアラートが true または誤通知として分類されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-138">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="35fc2-139">このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-139">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="35fc2-140">注: 状況によっては、特定の通知に対して分類情報を使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="35fc2-140">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![デバイスアラート分類カード](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="35fc2-142">解決されたアラートの決定を監視する</span><span class="sxs-lookup"><span data-stu-id="35fc2-142">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="35fc2-143">解決時にアラートが true であるか false であるかを分類するだけでなく、セキュリティ担当者は、通知の検証中に検出された通常または悪意のあるアクティビティの種類を示す判断を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-143">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="35fc2-144">**デバイス通知判別**カードは、各アラートに対して提供される決定を示します。具体的には次のようになります。</span><span class="sxs-lookup"><span data-stu-id="35fc2-144">The **Device alert determination** card shows the determination provided for each alert, specifically:</span></span>

* <span data-ttu-id="35fc2-145">**APT** –高度な永続的脅威。検出されたアクティビティまたは脅威コンポーネントが、影響を受けるネットワークで foothold を取得するように設計された高度な違反の一部であることを示します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-145">**APT** – advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="35fc2-146">**マルウェア**–悪意のあるファイルまたはコード</span><span class="sxs-lookup"><span data-stu-id="35fc2-146">**Malware** – malicious file or code</span></span>
* <span data-ttu-id="35fc2-147">**セキュリティ担当者**–セキュリティスタッフによって実行される通常のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="35fc2-147">**Security personnel** – normal activity performed by security staff</span></span>
* <span data-ttu-id="35fc2-148">**セキュリティテスト**–実際の脅威をシミュレートし、セキュリティセンサーをトリガーし、通知を生成するように設計されたアクティビティまたはコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="35fc2-148">**Security testing** – activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="35fc2-149">**不要なソフトウェア**–悪意のあるアプリやその他のソフトウェア。それ以外の場合は、ポリシーや使用規約に違反する</span><span class="sxs-lookup"><span data-stu-id="35fc2-149">**Unwanted software** – apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="35fc2-150">\*\*\*\* その他: 指定された種類の下にない他の決定</span><span class="sxs-lookup"><span data-stu-id="35fc2-150">**Others** – any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="35fc2-151">このカードから、Microsoft Defender セキュリティセンターの詳細情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-151">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![デバイスのアラート判別カード](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="35fc2-153">危険にさらされているデバイスを理解する</span><span class="sxs-lookup"><span data-stu-id="35fc2-153">Understand which devices are at risk</span></span>

<span data-ttu-id="35fc2-154">**デバイス保護**は、デバイスのリスクレベルを示しています。</span><span class="sxs-lookup"><span data-stu-id="35fc2-154">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="35fc2-155">リスクレベルは、デバイス上のアラートの種類や重要度などの要因に基づいています。</span><span class="sxs-lookup"><span data-stu-id="35fc2-155">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![デバイス保護カード](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="35fc2-157">Intune で管理されているデバイスの状態を監視および報告する</span><span class="sxs-lookup"><span data-stu-id="35fc2-157">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="35fc2-158">次のレポートには、Intune に登録されたデバイスからのデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="35fc2-158">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="35fc2-159">未登録のデバイスからのデータは含まれません。</span><span class="sxs-lookup"><span data-stu-id="35fc2-159">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="35fc2-160">これらのカードを表示できるのは、全体管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="35fc2-160">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="35fc2-161">Intune 登録デバイスデータには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-161">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="35fc2-162">デバイスのポリシー準拠</span><span class="sxs-lookup"><span data-stu-id="35fc2-162">Device compliance</span></span>
* <span data-ttu-id="35fc2-163">アクティブなマルウェアがあるデバイス</span><span class="sxs-lookup"><span data-stu-id="35fc2-163">Devices with active malware</span></span>
* <span data-ttu-id="35fc2-164">デバイス上のマルウェアの種類</span><span class="sxs-lookup"><span data-stu-id="35fc2-164">Types of malware on devices</span></span>
* <span data-ttu-id="35fc2-165">デバイスのマルウェア</span><span class="sxs-lookup"><span data-stu-id="35fc2-165">Malware on devices</span></span>
* <span data-ttu-id="35fc2-166">マルウェアが検出されるデバイス</span><span class="sxs-lookup"><span data-stu-id="35fc2-166">Devices with malware detections</span></span>
* <span data-ttu-id="35fc2-167">マルウェアが検出されるユーザー</span><span class="sxs-lookup"><span data-stu-id="35fc2-167">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="35fc2-168">デバイスコンプライアンスを監視する</span><span class="sxs-lookup"><span data-stu-id="35fc2-168">Monitor device compliance</span></span>

<span data-ttu-id="35fc2-169">**デバイスのコンプライアンス**Intune に登録されているデバイスの数が、構成ポリシーに準拠していることを示します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-169">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![デバイスコンプライアンスカード](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="35fc2-171">マルウェアが検出されるデバイスを検出する</span><span class="sxs-lookup"><span data-stu-id="35fc2-171">Discover devices with malware detections</span></span>

<span data-ttu-id="35fc2-172">**デバイスマルウェアの検出**は、保留中のアクション (再起動、完全なスキャン、または手動のユーザー操作) によって完全に解決されていないマルウェアを含む Intune 登録済みデバイスの数を示します。また、修復アクションが正常に完了していない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="35fc2-172">**Device malware detections** provides the number of Intune enrolled devices with malware that have not been fully resolved due to pending actions—a restart, a full scan or manual user actions—or if the remediation action did not complete successfully.</span></span>

![デバイスマルウェア検出カード](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="35fc2-174">検出されたマルウェアの種類を理解する</span><span class="sxs-lookup"><span data-stu-id="35fc2-174">Understand the types of malware detected</span></span>

<span data-ttu-id="35fc2-175">**デバイス上のマルウェアの種類**は、Intune に登録されたデバイスで検出されたさまざまな種類のマルウェアを示しています。</span><span class="sxs-lookup"><span data-stu-id="35fc2-175">**Types of malware on devices** shows different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="35fc2-176">Microsoft 365 セキュリティセンターでは、それぞれの種類を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-176">You can investigate each type in Microsoft 365 security center.</span></span>

![デバイスカードのマルウェアの種類](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="35fc2-178">デバイスで検出された特定のマルウェアについて理解する</span><span class="sxs-lookup"><span data-stu-id="35fc2-178">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="35fc2-179">**デバイス上のマルウェア**は、デバイスで検出された特定のマルウェアの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-179">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![デバイスカードのマルウェア](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="35fc2-181">最もマルウェアがあるデバイスを理解する</span><span class="sxs-lookup"><span data-stu-id="35fc2-181">Understand which devices have the most malware</span></span>

<span data-ttu-id="35fc2-182">**マルウェアが検出**されたデバイスには、マルウェアの検出数が最も多いデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-182">**Devices with malware detections** shows which devices have the most malware detections.</span></span> <span data-ttu-id="35fc2-183">Microsoft 365 セキュリティセンターでは、マルウェアがアクティブであるかどうか、デバイスを使用しているかどうか、および Intune での管理状態を調査できます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-183">In Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![マルウェア検出カードがあるデバイス](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="35fc2-185">最も多くのマルウェアがあるデバイスをどのユーザーが所有しているかを理解する</span><span class="sxs-lookup"><span data-stu-id="35fc2-185">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="35fc2-186">**マルウェアが検出**されたユーザーには、マルウェアが検出されたデバイスを持つユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-186">**Users with malware detections** shows users with devices that had the most malware detections.</span></span> <span data-ttu-id="35fc2-187">Microsoft 365 セキュリティセンターでは、各ユーザーに割り当てられているデバイスの数と、各デバイスおよびマルウェアの種類に関する詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-187">In Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![マルウェア検出カードを使用するユーザー](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="35fc2-189">ASR ルールの展開と検出を監視および管理する</span><span class="sxs-lookup"><span data-stu-id="35fc2-189">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="35fc2-190">[Attack Surface Reduction (ASR) ルール](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)は、一般的に悪用される行為やアプリを阻止するのに役立ちます。マルウェアに感染したコンピューターに感染します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-190">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) help prevent actions and apps that are typically used by exploit-seeking malware to infect machines.</span></span> <span data-ttu-id="35fc2-191">これらのルールは、実行可能ファイルをいつどのように実行するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-191">These rules control when and how executables can run.</span></span> <span data-ttu-id="35fc2-192">たとえば、JavaScript または VBScript がダウンロードされた実行可能ファイルを起動したり、Office マクロからの Win32 API 呼び出しをブロックしたり、USB ドライブから実行するブロックプロセスを禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-192">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![アタック表面減少カード](./media/security-docs/attack-surface-reduction-rules.png)

<span data-ttu-id="35fc2-194">「 **Attack surface reduction rules** card」では、デバイス全体にわたるルールの展開の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-194">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="35fc2-195">カードの上部のバーには、次の展開モードになっているデバイスの合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-195">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="35fc2-196">**ブロックモード**–検出されたアクティビティをブロックするように少なくとも1つのルールを持つデバイス</span><span class="sxs-lookup"><span data-stu-id="35fc2-196">**Block mode** – devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="35fc2-197">**監査モード**–検出されたアクティビティをブロックするようにルールが設定されていないデバイスが検出されたアクティビティを監査するために少なくとも1つのルールを設定している</span><span class="sxs-lookup"><span data-stu-id="35fc2-197">**Audit mode** – devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="35fc2-198">**オフ**–すべての ASR ルールがオフになっているデバイス</span><span class="sxs-lookup"><span data-stu-id="35fc2-198">**Off** – devices with all ASR rules turned off</span></span>

<span data-ttu-id="35fc2-199">このカードの下の部分には、デバイス全体の設定がルール別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-199">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="35fc2-200">各棒は、検出をブロックまたは監査するように設定されているデバイスの数、または規則が完全にオフになっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-200">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="35fc2-201">ASR 検出を表示する</span><span class="sxs-lookup"><span data-stu-id="35fc2-201">View ASR detections</span></span>

<span data-ttu-id="35fc2-202">ネットワーク内の ASR ルールの検出に関する詳細情報を表示するには、[ **Attack surface reduction ルール**カード] の [**検出の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-202">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="35fc2-203">[詳細レポート] ページの [**検出**] タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-203">The **Detections** tab in the detailed report page will open.</span></span>

![[検出] タブ](./media/security-docs/detections-tab.png)

<span data-ttu-id="35fc2-205">ページ上部のグラフには、ブロックまたは監査された時間帯の検出の検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-205">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="35fc2-206">下部の表には、最新の検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-206">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="35fc2-207">次の表の情報を使用して、検出の性質を理解してください。</span><span class="sxs-lookup"><span data-stu-id="35fc2-207">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="35fc2-208">**検出さ**れたファイル–通常はスクリプトまたはドキュメントで、発生の疑いがある攻撃の内容を引き起こしたファイル。</span><span class="sxs-lookup"><span data-stu-id="35fc2-208">**Detected file** – the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="35fc2-209">**ルール**: ルールが検出するように設計されたアタックアクティビティを記述する名前。</span><span class="sxs-lookup"><span data-stu-id="35fc2-209">**Rule** – name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="35fc2-210">既存の ASR ルールについての情報を読む</span><span class="sxs-lookup"><span data-stu-id="35fc2-210">Read about existing ASR rules</span></span>
* <span data-ttu-id="35fc2-211">**ソースアプリ**–攻撃の疑いのある活動をトリガーするコンテンツを読み込んだ、または実行したアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="35fc2-211">**Source app** – the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="35fc2-212">これは、web ブラウザー、Office アプリケーション、PowerShell のようなシステムツールなどの正当なアプリケーションである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35fc2-212">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="35fc2-213">**Publisher** –ソースアプリをリリースしたベンダー</span><span class="sxs-lookup"><span data-stu-id="35fc2-213">**Publisher** – the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="35fc2-214">デバイス ASR ルールの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="35fc2-214">Review device ASR rule settings</span></span>

<span data-ttu-id="35fc2-215">[ **Attack surface reduction ルール**レポート] ページで、[**構成**] タブに移動して個々のデバイスのルールの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-215">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="35fc2-216">デバイスを選択して、各ルールがブロックモード、監査モード、または完全にオフになっているかどうかに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-216">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![[構成] タブ](./media/security-docs/configuration-tab.png)

<span data-ttu-id="35fc2-218">Microsoft Intune は、ASR ルールの管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-218">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="35fc2-219">設定を更新する場合は、タブの [デバイスの**構成**] の [**開始**] を選択して、Intune でデバイス管理を開きます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-219">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="35fc2-220">ASR ルールからファイルを除外する</span><span class="sxs-lookup"><span data-stu-id="35fc2-220">Exclude files from ASR rules</span></span>

<span data-ttu-id="35fc2-221">Microsoft 365 セキュリティセンターでは、攻撃対象から[除外する可能性のあるファイル](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive)の名前を検出します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-221">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="35fc2-222">ファイルを除外することで、誤検知を減らすことができます。ブロックモードでは、攻撃対象領域の削減ルールをより確実に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-222">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="35fc2-223">除外は Microsoft Intune で管理されますが、Microsoft 365 セキュリティセンターには、ファイルを理解するのに役立つ分析ツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="35fc2-223">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="35fc2-224">除外するファイルの収集を開始するには、[ **Attack surface reduction ルール**レポート] ページの [**除外の追加**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-224">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="35fc2-225">このツールでは、すべての攻撃対象領域の削減ルールによって検出が分析されますが、[一部のルールのみが除外をサポート](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules)します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-225">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules).</span></span>

![[除外の追加] タブ](./media/security-docs/add-exclusions-tab.png)

<span data-ttu-id="35fc2-227">攻撃対象領域の削減ルールによって検出されたすべてのファイル名の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-227">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="35fc2-228">ファイルを選択して、それらを除外した場合の影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-228">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="35fc2-229">検出回数を減らす</span><span class="sxs-lookup"><span data-stu-id="35fc2-229">How many fewer detections</span></span>
* <span data-ttu-id="35fc2-230">検出を報告するデバイス数の削減</span><span class="sxs-lookup"><span data-stu-id="35fc2-230">How many fewer devices report the detections</span></span>

<span data-ttu-id="35fc2-231">選択したファイルの完全パスを除外するには、[除外する**パスを取得**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-231">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="35fc2-232">**Windows ローカルセキュリティ機関サブシステム (lsass.exe) から**の ASR ルールブロックの資格情報のログは、ソースアプリ**lsass.exe**(通常のシステムファイル) を検出されたファイルとしてキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="35fc2-232">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="35fc2-233">そのため、生成された除外パスの一覧には、このファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-233">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="35fc2-234">**Lsass.exe**ではなく、このルールをトリガーしたファイルを除外するには、検出されたファイルの代わりにソースアプリへのパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-234">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="35fc2-235">ソースアプリを見つけるには、この特定のルールに対して次の[高度な検索クエリ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)を実行します (ルール ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 によって識別されます)。</span><span class="sxs-lookup"><span data-stu-id="35fc2-235">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="35fc2-236">ファイルの除外を確認する</span><span class="sxs-lookup"><span data-stu-id="35fc2-236">Check files for exclusion</span></span>
<span data-ttu-id="35fc2-237">ASR からファイルを除外する前に、ファイルを検査して、悪意がないかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35fc2-237">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="35fc2-238">ファイルを確認するには、Microsoft Defender セキュリティセンターの [[ファイル情報] ページ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files)を使用します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-238">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="35fc2-239">このページには、流行の情報と、VirusTotal のウイルス検出率が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-239">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="35fc2-240">ページを使用して、詳細な分析のためにファイルを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-240">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="35fc2-241">Microsoft Defender セキュリティセンターで検出されたファイルを特定するには、次の高度な検索クエリを使用して、すべての ASR 検出を検索します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-241">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="35fc2-242">結果で**SHA1**または**InitiatingProcessSHA1**を使用して、Microsoft Defender セキュリティセンターのユニバーサル検索バーを使用してファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-242">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
