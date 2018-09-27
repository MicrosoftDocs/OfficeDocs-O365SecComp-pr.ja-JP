---
title: Office 365 ATP の安全な添付ファイル ポリシーを設定します
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/8/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
description: 電子メールに悪意のあるファイルから組織を保護するために安全な添付ファイル ポリシーを定義します。
ms.openlocfilehash: bc52522a45071776835efe20f57cf37c415d2436
ms.sourcegitcommit: 9826013c3e0532ae5d01b3d88a14691f8dd0f6b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2018
ms.locfileid: "25092943"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a><span data-ttu-id="6cca1-103">Office 365 ATP の安全な添付ファイル ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="6cca1-103">Set up Office 365 ATP Safe Attachments policies</span></span>

<span data-ttu-id="6cca1-p101">人が定期的に送信すると、受信、および、ドキュメント、プレゼンテーション、スプレッドシート、および詳細などの添付ファイルを共有します。常に簡単に、電子メール メッセージを見ているだけでは、安全なまたは悪意のあるに添付ファイルかどうかを識別できます。最も避けことを悪意のある添付ファイル、組織の混乱を悪事します。幸いなことに、 [Office 365 の高度な脅威保護](office-365-atp.md)(ATP) ことができます。[ATP の安全な添付ファイル](atp-safe-attachments.md)のポリシーをセットアップするには確実に安全でない電子メールの添付ファイルでの攻撃に対して、組織が保護されています。</span><span class="sxs-lookup"><span data-stu-id="6cca1-p101">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more. It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message. And the last thing you want is a malicious attachment to get through, wreaking havoc for your organization. Fortunately, [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) can help. You can set up [ATP Safe Attachments](atp-safe-attachments.md) policies to help ensure that your organization is protected against attacks by unsafe email attachments.</span></span> 
  
## <a name="what-to-do"></a><span data-ttu-id="6cca1-109">行うこと</span><span class="sxs-lookup"><span data-stu-id="6cca1-109">What to do</span></span> 
  
1. [<span data-ttu-id="6cca1-110">前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-110">Review the prerequisites</span></span>](#review-the-prerequisites)
    
2. [<span data-ttu-id="6cca1-111">ATP の安全な添付ファイル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-111">Set up an ATP Safe Attachments policy</span></span>](#set-up-an-atp-safe-attachments-policy)
    
3. [<span data-ttu-id="6cca1-112">ATP の安全な添付ファイル ポリシーのオプションについてください。</span><span class="sxs-lookup"><span data-stu-id="6cca1-112">Learn about ATP Safe Attachments policy options</span></span>](#learn-about-atp-safe-attachments-policy-options)
    
## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="6cca1-113">手順 1: 前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-113">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="6cca1-114">組織が[Office 365 の高度な脅威保護](office-365-atp.md)を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-114">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="6cca1-115">必要があるかどうかを確認[Office 365 のセキュリティに割り当てられたアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="6cca1-115">Make sure that you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="6cca1-p102">[ATP の安全な添付ファイル ポリシーのオプションについて理解します。](#learn-about-atp-safe-attachments-policy-options)(この記事で)。モニター] または [置換のオプションなど、いくつかのオプションが遅延が生じますマイナー電子メールの添付ファイルをスキャン中にします。メッセージの遅延を避けるためには、[動的な配信およびプレビュー](dynamic-delivery-and-previewing.md)を使用して検討してください。</span><span class="sxs-lookup"><span data-stu-id="6cca1-p102">[Learn about ATP Safe Attachments policy options](#learn-about-atp-safe-attachments-policy-options) (in this article). Some options, such as the Monitor or Replace options, can result in a minor delay of email while attachments are scanned. To avoid message delays, consider using [dynamic delivery and previewing](dynamic-delivery-and-previewing.md).</span></span>
    
- <span data-ttu-id="6cca1-119">最大 30 分間のすべての Office 365 のデータ センターに展開するのには、新規または更新されたポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6cca1-119">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a><span data-ttu-id="6cca1-120">ATP の安全な添付ファイル ポリシーを手順 2: を設定する (または編集)</span><span class="sxs-lookup"><span data-stu-id="6cca1-120">Step 2: Set up (or edit) an ATP Safe Attachments policy</span></span>

> [!TIP]
> <span data-ttu-id="6cca1-p103">Office 365 のセキュリティいずれかの方法を使用して、ATP の安全な添付ファイル ポリシーを設定できます&amp;コンプライアンス センターまたは Exchange 管理センター (EAC)。**Office 365 のセキュリティを使用することをお勧めします。&amp;コンプライアンス センター**です。</span><span class="sxs-lookup"><span data-stu-id="6cca1-p103">You can set up an ATP Safe Attachments policy using either the Office 365 Security &amp; Compliance Center or the Exchange admin center (EAC). **We recommend using the Office 365 Security &amp; Compliance Center**.</span></span> 
  
1. <span data-ttu-id="6cca1-123">グローバル管理者またはセキュリティ管理者には、[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="6cca1-123">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="6cca1-124">Office 365 のセキュリティで&amp;コンプライアンス センターでは、**脅威の管理**の下で、左側のナビゲーション ペインで**ポリシー**を選択する\>**安全な添付ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="6cca1-124">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>
    
3. <span data-ttu-id="6cca1-p104">**SharePoint、OneDrive、およびマイクロソフトのチームの分析ツールを有効にする**場合は、このオプションを選択することをお勧めします。[Office 365 高度な脅威保護](atp-for-spo-odb-and-teams.md)SharePoint、OneDrive、およびマイクロソフトのチームにこれにより、Office 365 環境に。</span><span class="sxs-lookup"><span data-stu-id="6cca1-p104">If you see **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, we recommend that you select this option. This will enable [Office 365 Advanced Threat Protection for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) for your Office 365 environment.</span></span> 
    
4. <span data-ttu-id="6cca1-127">**新規**を選択 ([新規] ボタンのようなプラス記号 ( **+**))、ポリシーの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-127">Choose **New** (the New button resembles a plus sign ( **+**)) to start creating your policy.</span></span>
    
5. <span data-ttu-id="6cca1-128">名前、説明、およびポリシーの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-128">Specify the name, description, and settings for the policy.</span></span>
    
    <span data-ttu-id="6cca1-129">**の使用例:**「待ち時間なし」と呼ばれる全員のメッセージをすぐに提供しそれらをスキャンしている後に添付ファイルを再接続されるポリシーを設定するには、次の設定を指定する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6cca1-129">**Example:** To set up a policy called "no delays" that delivers everyone's messages immediately and then reattaches attachments after they're scanned, you might specify the following settings:</span></span> 
    
      - <span data-ttu-id="6cca1-130">[**名**] ボックスで、入力ない遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-130">In the **Name** box, type no delays.</span></span>
    
      - <span data-ttu-id="6cca1-131">**[説明**] ボックスで、配信メッセージをすぐに再接続されると添付ファイルなどをスキャンした後の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-131">In the **Description** box, type a description like, Delivers messages immediately and reattaches attachments after scanning.</span></span>
    
      - <span data-ttu-id="6cca1-p105">[応答] セクションでは、**動的な配信**オプションを選択します。([動的な配信および ATP の安全な添付ファイルのプレビューについての詳細を表示](dynamic-delivery-and-previewing.md)) します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-p105">In the response section, choose the **Dynamic Delivery** option. ([Learn more about dynamic delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).)</span></span>
    
      - <span data-ttu-id="6cca1-134">**添付ファイルのリダイレクト**] で、リダイレクトを有効にして、Office 365 グローバル管理者、セキュリティ管理者は、悪意のある添付ファイルを調べて、セキュリティ アナリストのメール アドレスを入力するためのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-134">In the **Redirect attachment** section, select the option to enable redirect and type the email address of your Office 365 global administrator, security administrator, or security analyst who will investigate malicious attachments.</span></span> 
    
      - <span data-ttu-id="6cca1-p106">[**適用先**] セクションでは、**受信者のドメインと**を選択し、自分のドメインを選択します。**追加**を選択し、[ **ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cca1-p106">In the **Applied To** section, choose **The recipient domain is**, and then select your domain. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="6cca1-137">[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-137">Choose **Save**.</span></span>
    
<span data-ttu-id="6cca1-p107">組織の複数の分析ツールの安全な添付ファイル ポリシーの設定を検討してください。**ATP の安全な添付ファイル**のページに記載されている順序でこれらのポリシーが適用されます。ポリシーを定義または編集すると、少なくとも 30 分を許可する、マイクロソフトのデータ センター全体で有効にするポリシーです。</span><span class="sxs-lookup"><span data-stu-id="6cca1-p107">Consider setting up multiple ATP Safe Attachments policies for your organization. These policies will be applied in the order they're listed on the **ATP Safe Attachments** page. After a policy has been defined or edited, allow at least 30 minutes for the polices to take effect throughout Microsoft datacenters.</span></span> 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a><span data-ttu-id="6cca1-141">ATP の安全な添付ファイル ポリシーのオプションについて、手順 3。</span><span class="sxs-lookup"><span data-stu-id="6cca1-141">Step 3: Learn about ATP Safe Attachments policy options</span></span>

<span data-ttu-id="6cca1-p108">ATP の安全な添付ファイル ポリシーを設定する場合とは、モニター、ブロック、置換、動的な配信など、多くのオプションから選択します。場合に、ご参考までにこれらのオプションとは何かについて、次の表の概要を効果です。</span><span class="sxs-lookup"><span data-stu-id="6cca1-p108">As you set up your ATP Safe Attachments policies, you choose from among many options, including Monitor, Block, Replace, Dynamic Delivery, and so on. In case you're wondering about what these options do, the following table summarizes each and its effect.</span></span>
  
|<span data-ttu-id="6cca1-144">**オプション**</span><span class="sxs-lookup"><span data-stu-id="6cca1-144">**Option**</span></span>|<span data-ttu-id="6cca1-145">**効果**</span><span class="sxs-lookup"><span data-stu-id="6cca1-145">**Effect**</span></span>|<span data-ttu-id="6cca1-146">**するときに使用します。**</span><span class="sxs-lookup"><span data-stu-id="6cca1-146">**Use when you want to:**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6cca1-147">**Off**</span><span class="sxs-lookup"><span data-stu-id="6cca1-147">**Off**</span></span> <br/> |<span data-ttu-id="6cca1-148">マルウェアの添付ファイルをスキャンしません。</span><span class="sxs-lookup"><span data-stu-id="6cca1-148">Does not scan attachments for malware</span></span>  <br/> <span data-ttu-id="6cca1-149">メッセージ配信の遅延を起こさない</span><span class="sxs-lookup"><span data-stu-id="6cca1-149">Does not delay message delivery</span></span>  <br/> |<span data-ttu-id="6cca1-150">スキャンをオフにする内部の送信者、スキャナー、fax、または不明な添付ファイルのみを送信するためのスマート ホストの</span><span class="sxs-lookup"><span data-stu-id="6cca1-150">Turn scanning off for internal senders, scanners, faxes, or smart hosts that will only send known, good attachments</span></span>  <br/> <span data-ttu-id="6cca1-151">メールをルーティングする内部での不要な遅延を回避します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-151">Prevent unnecessary delays in routing internal mail</span></span>  <br/> <span data-ttu-id="6cca1-152">**ほとんどのユーザーは、このオプションはお勧めしません。ATP の安全な添付ファイルのスキャンをオフにする内部の送信者の小規模なグループにすることができます。**</span><span class="sxs-lookup"><span data-stu-id="6cca1-152">**This option is not recommended for most users. It enables you to turn ATP Safe Attachments scanning off for a small group of internal senders.**</span></span>           |
|<span data-ttu-id="6cca1-153">**モニター**</span><span class="sxs-lookup"><span data-stu-id="6cca1-153">**Monitor**</span></span> <br/> |<span data-ttu-id="6cca1-154">添付ファイル付きのメッセージを配信し、検出されたマルウェアの動作を追跡し、</span><span class="sxs-lookup"><span data-stu-id="6cca1-154">Delivers messages with attachments and then tracks what happens with detected malware</span></span>  <br/> |<span data-ttu-id="6cca1-155">組織内で検出されたマルウェアのどこを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cca1-155">See where detected malware goes in your organization</span></span>  <br/> |
|<span data-ttu-id="6cca1-156">**ブロック**</span><span class="sxs-lookup"><span data-stu-id="6cca1-156">**Block**</span></span> <br/> |<span data-ttu-id="6cca1-157">次に進むから検出されたマルウェアの添付ファイル付きメッセージを防止します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-157">Prevents messages with detected malware attachments from proceeding</span></span>  <br/> <span data-ttu-id="6cca1-158">[Office 365 の検査](manage-quarantined-messages-and-files.md)セキュリティ管理者またはアナリストことができますを確認し、リリース (または削除) これらのメッセージにマルウェアが検出されたメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-158">Sends messages with detected malware to [quarantine in Office 365](manage-quarantined-messages-and-files.md) where a security administrator or analyst can review and release (or delete) those messages</span></span>  <br/> <span data-ttu-id="6cca1-159">将来のメッセージと添付ファイルを自動的にブロックします。</span><span class="sxs-lookup"><span data-stu-id="6cca1-159">Blocks future messages and attachments automatically</span></span>  <br/> |<span data-ttu-id="6cca1-160">同じマルウェアの添付ファイルを使用して繰り返しの攻撃から組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-160">Safeguard your organization from repeated attacks using the same malware attachments</span></span>  <br/> |
|<span data-ttu-id="6cca1-161">**置換**</span><span class="sxs-lookup"><span data-stu-id="6cca1-161">**Replace**</span></span> <br/> |<span data-ttu-id="6cca1-162">検出されたマルウェアの添付ファイルを削除します</span><span class="sxs-lookup"><span data-stu-id="6cca1-162">Removes detected malware attachments</span></span>  <br/> <span data-ttu-id="6cca1-163">受信者に添付ファイルが削除されていることを通知します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-163">Notifies recipients that attachments have been removed</span></span>  <br/> <span data-ttu-id="6cca1-164">[Office 365 の検査](manage-quarantined-messages-and-files.md)セキュリティ管理者またはアナリストことができますを確認し、リリース (または削除) これらのメッセージにマルウェアが検出されたメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-164">Sends messages with detected malware to [quarantine in Office 365](manage-quarantined-messages-and-files.md) where a security administrator or analyst can review and release (or delete) those messages</span></span>  <br/> |<span data-ttu-id="6cca1-165">マルウェアが検出されたため、添付ファイルが削除されたことを受信者に可視性を上げる</span><span class="sxs-lookup"><span data-stu-id="6cca1-165">Raise visibility to recipients that attachments were removed because of detected malware</span></span>  <br/> |
|<span data-ttu-id="6cca1-166">**動的な配信**</span><span class="sxs-lookup"><span data-stu-id="6cca1-166">**Dynamic Delivery**</span></span> <br/> |<span data-ttu-id="6cca1-167">すぐにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-167">Delivers messages immediately</span></span>  <br/> <span data-ttu-id="6cca1-168">スキャンが完了し、添付ファイルがマルウェアが検出されない場合に再接続されるまで、プレース ホルダー ファイルで添付ファイルを置き換えます</span><span class="sxs-lookup"><span data-stu-id="6cca1-168">Replaces attachments with a placeholder file until scanning is complete, and then reattaches the attachments if no malware is detected</span></span>  <br/> <span data-ttu-id="6cca1-169">ほとんどの Pdf や Office の機能をプレビューする添付ファイルを含むファイルをスキャン中に</span><span class="sxs-lookup"><span data-stu-id="6cca1-169">Includes attachment previewing capabilities for most PDFs and Office files during scanning</span></span>  <br/> <span data-ttu-id="6cca1-170">検疫は、セキュリティ管理者またはアナリストことができますを確認し、リリース (または削除) これらのメッセージに検出されたマルウェアにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-170">Sends messages with detected malware to Quarantine where a security administrator or analyst can review and release (or delete) those messages</span></span>  <br/> [<span data-ttu-id="6cca1-171">動的な配信および ATP の安全な添付ファイルのプレビューについてください。</span><span class="sxs-lookup"><span data-stu-id="6cca1-171">Learn about dynamic delivery and previewing with ATP Safe Attachments</span></span>](dynamic-delivery-and-previewing.md) <br/> |<span data-ttu-id="6cca1-172">メッセージの遅延を避けるため、悪意のあるファイルから受信者を保護しながら</span><span class="sxs-lookup"><span data-stu-id="6cca1-172">Avoid message delays while protecting recipients from malicious files</span></span>  <br/> <span data-ttu-id="6cca1-173">スキャンの実行中に、セーフ モードで添付ファイルをプレビューするのには受信者を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6cca1-173">Enable recipients to preview attachments in safe mode while scanning is taking place</span></span>  <br/> |
|<span data-ttu-id="6cca1-174">**リダイレクトを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="6cca1-174">**Enable redirect**</span></span> <br/> |<span data-ttu-id="6cca1-175">モニター、ブロック、または置換オプションを選択した場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6cca1-175">Applies when the Monitor, Block, or Replace option is chosen</span></span>  <br/> <span data-ttu-id="6cca1-176">指定された電子メール アドレスに添付ファイルの送信、セキュリティ管理者またはアナリストを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="6cca1-176">Sends attachments to a specified email address where security administrators or analysts can investigate</span></span>  <br/> |<span data-ttu-id="6cca1-177">不審な添付ファイルを調査するには、セキュリティ管理者やアナリストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6cca1-177">Enable security administrators and analysts to research suspicious attachments</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="6cca1-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cca1-178">Related topics</span></span>

[<span data-ttu-id="6cca1-179">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6cca1-179">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="6cca1-180">ATP の安全な添付ファイルを Office 365 で</span><span class="sxs-lookup"><span data-stu-id="6cca1-180">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="6cca1-181">Office 365 で ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="6cca1-181">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="6cca1-182">Office 365 の ATP の安全なリンクのポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="6cca1-182">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="6cca1-183">脅威の高度な保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="6cca1-183">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="6cca1-184">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="6cca1-184">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

