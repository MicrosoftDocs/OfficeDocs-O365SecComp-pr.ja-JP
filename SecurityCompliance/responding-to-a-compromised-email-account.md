---
title: 侵害された Office 365 電子メール アカウントへの対応
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: 認識し、Office 365 で電子メールのセキュリティを侵害されたアカウントに対応する方法を学習します。
ms.openlocfilehash: 9a3dcc2d10c7487e525ae127674a830f9a921a60
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782184"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a><span data-ttu-id="f1018-103">侵害された Office 365 電子メール アカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="f1018-103">Responding to a Compromised Email Account in Office 365</span></span>

<span data-ttu-id="f1018-104">**概要**認識し、Office 365 で電子メールのセキュリティを侵害されたアカウントに対応する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f1018-104">**Summary** Learn how to recognize and respond to a compromised email account in Office 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-office-365"></a><span data-ttu-id="f1018-105">Office 365 では、危険にさらされた電子メール アカウントとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="f1018-105">What is a Compromised Email Account in Office 365?</span></span>
<span data-ttu-id="f1018-p101">Office 365 のメールボックス、データ、およびその他のサービスへのアクセスをユーザー名とパスワードまたは暗証番号 (pin) などの資格情報を使用して制御されます。これらの資格情報を盗み、意図したユーザー以外の誰かに盗まれた資格情報が危険にさらされると見なされます。攻撃者は元のユーザーとしてサインインし、不正な操作を実行できます。盗まれた資格情報を使用すると、ユーザーの Office 365 のメールボックス、SharePoint フォルダー、またはユーザーの OneDrive 内のファイル、攻撃者はアクセスできます。表示される 1 つのアクションは、組織の内外両方の受信者に元のユーザーとしての e メールを送信する攻撃者です。攻撃者は、データを外部の受信者にメール、ときにこのデータ exfiltration と呼びます。</span><span class="sxs-lookup"><span data-stu-id="f1018-p101">Access to Office 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN. When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised. With them the attacker can sign in as the original user and perform illicit actions. Using the stolen credentials, the attacker can access the user’s Office 365 mailbox, SharePoint folders, or files in the user's OneDrive. One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization. When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-office-365-email-account"></a><span data-ttu-id="f1018-112">危険にさらされた Office 365 の電子メール アカウントの現象</span><span class="sxs-lookup"><span data-stu-id="f1018-112">Symptoms of a Compromised Office 365 Email Account</span></span>
<span data-ttu-id="f1018-p102">ユーザーに注意してくださいし、Office 365 のメールボックスでの異常な活動を報告する可能性があります。いくつかの一般的な現象を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f1018-p102">Users might notice and report unusual activity in their Office 365 mailboxes. Here are some common symptoms:</span></span>
- <span data-ttu-id="f1018-115">存在しないか削除された電子メールなどの不審な活動です。</span><span class="sxs-lookup"><span data-stu-id="f1018-115">Suspicious activity, such as missing or deleted emails.</span></span>
- <span data-ttu-id="f1018-116">他のユーザー可能性があります受信電子メール セキュリティを侵害されたアカウントから既存の送信者の**送信済みアイテム**フォルダーに対応する電子メール。</span><span class="sxs-lookup"><span data-stu-id="f1018-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>
- <span data-ttu-id="f1018-p103">目的のユーザーまたは管理者によって作成されていない受信トレイ ルールが存在します。またはこれらの規則が自動的に不明なアドレスに e メールを転送、**メモ**、**迷惑メール**、または**RSS 購読**フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1018-p103">The presence of inbox rules that weren't created by the intended user or the administrator. These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>
- <span data-ttu-id="f1018-119">グローバル アドレス一覧では、ユーザーの表示名を変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1018-119">The user's display name might be changed in the Global Address List.</span></span>
- <span data-ttu-id="f1018-120">ユーザーのメールボックスは、電子メールを送信するからブロックされています。</span><span class="sxs-lookup"><span data-stu-id="f1018-120">The user's mailbox is blocked from sending email.</span></span>
- <span data-ttu-id="f1018-121">「3. 佐賀県にある send money」など、Microsoft Outlook または Microsoft Outlook Web App では、[送信済みアイテムまたは削除済みアイテム フォルダーがハッキングされたアカウントの一般的なメッセージは、含まれている</span><span class="sxs-lookup"><span data-stu-id="f1018-121">The Sent or Deleted Items folders in Microsoft Outlook or in Microsoft Outlook Web App contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>
- <span data-ttu-id="f1018-122">異常なプロファイルの変更内容を入力した場合、名前、電話番号、郵便番号などが更新されました。</span><span class="sxs-lookup"><span data-stu-id="f1018-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>
- <span data-ttu-id="f1018-123">複数のパスワードの変更など、通常とは異なる資格情報の変更は、必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1018-123">Unusual credential changes, such as multiple password changes are required.</span></span>
- <span data-ttu-id="f1018-124">メールの転送は、最近追加されました。</span><span class="sxs-lookup"><span data-stu-id="f1018-124">Mail forwarding was recently added.</span></span>
- <span data-ttu-id="f1018-125">異常な最近署名されて、偽の銀行の署名や処方薬の署名など。</span><span class="sxs-lookup"><span data-stu-id="f1018-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="f1018-p104">ユーザーは、上記の現象のいずれかを報告する場合は、行う必要がありますさらに調査します。Office 365 のセキュリティとコンプライアンスの中心と、Azure ポータルは、侵害される可能性があるユーザー アカウントのアクティビティを調査するためのツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="f1018-p104">If a user reports any of the above symptoms, you should perform further investigation. The Office 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>
- <span data-ttu-id="f1018-p105">Office 365 ユニファイド監査ログでセキュリティとコンプライアンス センター - は、日付範囲にわたるから現在の日付に不審なアクティビティが発生した直前の結果をフィルタ リングによって疑いのあるアカウントのすべてのアクティビティを確認します。フィルターを適用しないアクティビティの検索中にします。</span><span class="sxs-lookup"><span data-stu-id="f1018-p105">Office 365 Unified Audit Logs in the Security & Compliance Center - Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date. Do not filter on the activities during the search.</span></span>
- <span data-ttu-id="f1018-p106">Azure AD のログ、および AD の Azure ポータルで使用可能なその他のリスク ・ レポートを使用します。これらの列内の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="f1018-p106">Use the Azure AD Sign-in logs and other risk reports that are available in the Azure AD portal. Examine the values in these columns:</span></span>
    - <span data-ttu-id="f1018-132">IP アドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1018-132">Review IP address</span></span>
    - <span data-ttu-id="f1018-133">サインインの場所</span><span class="sxs-lookup"><span data-stu-id="f1018-133">sign-in locations</span></span>
    - <span data-ttu-id="f1018-134">回サインイン</span><span class="sxs-lookup"><span data-stu-id="f1018-134">sign-in times</span></span>
    - <span data-ttu-id="f1018-135">サインインが成功または失敗</span><span class="sxs-lookup"><span data-stu-id="f1018-135">sign-in success or failure</span></span>



## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a><span data-ttu-id="f1018-136">Office 365 のアカウントとメールボックスをセキュリティで保護し、疑いがあるに電子メール機能を復元する方法が侵害されました。</span><span class="sxs-lookup"><span data-stu-id="f1018-136">How to secure and restore email function to a suspected compromised Office 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="f1018-137">自分のアカウントにアクセスを回復して後に、も攻撃者が攻撃者は、アカウントの制御を再開するを有効にするバックドアのエントリを追加しました可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1018-137">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="f1018-p107">Hijacker を再開しないことを確認するのに越したことが自分のアカウントを制御する早くあなたのアカウントへのアクセスを回復するために次のすべての手順を実行する必要があります。次の手順では、お客様のアカウントに追加可能性があります、hijacker バック ドア エントリをすべて削除できます。次の手順を実行した後は、お使いのコンピューターが侵害されていないことを確認するのにはウイルス スキャンを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f1018-p107">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account. These steps help you remove any back-door entries that the hijacker may have added to your account. After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="f1018-141">ステップ 1 は、ユーザーのパスワードをリセット</span><span class="sxs-lookup"><span data-stu-id="f1018-141">Step 1 Reset the user's password</span></span>
> [!WARNING]
> <span data-ttu-id="f1018-142">攻撃者がアクセス、メールボックスにこの時点で電子メールを通じて目的のユーザーに新しいパスワードを送りません。</span><span class="sxs-lookup"><span data-stu-id="f1018-142">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="f1018-143">次ビジネス パスワードのリセット、Office 365 の他のユーザーの他のプロシージャの[管理者: ビジネスのパスワードを Office 365 のリセット](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span><span class="sxs-lookup"><span data-stu-id="f1018-143">Follow the Reset an Office 365 business password for someone else procedures in [Admins: Reset Office 365 business passwords](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span></span>

<span data-ttu-id="f1018-144">**メモ:**</span><span class="sxs-lookup"><span data-stu-id="f1018-144">**Notes:**</span></span>
- <span data-ttu-id="f1018-145">パスワードが強力であり、大文字、小文字、数字が 1 つとを少なくとも 1 つの特殊文字が含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1018-145">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span> 
- <span data-ttu-id="f1018-p108">最後の 5 つのパスワードを再利用します。パスワード履歴の要件では、新しいパスワードを再利用することができます、場合でも、攻撃者が推測できないものを選択してください。</span><span class="sxs-lookup"><span data-stu-id="f1018-p108">Don't reuse any of your last five passwords. Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
- <span data-ttu-id="f1018-148">オンプレミス id は、Office 365 で連合は場合、パスワード設置を変更する必要があり、危険にさらされるは、管理者に通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1018-148">If your on-premises identity is federated with Office 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="f1018-149">不審な電子メール転送アドレスの削除は 2 つのステップします。</span><span class="sxs-lookup"><span data-stu-id="f1018-149">Step 2 Remove suspicious email forwarding addresses</span></span>
1. <span data-ttu-id="f1018-150">開く、 **Office 365 管理者センター > ユーザーのアクティブな**です。</span><span class="sxs-lookup"><span data-stu-id="f1018-150">Open the **Office 365 Admin Center > Active Users**.</span></span>
2. <span data-ttu-id="f1018-151">対象のユーザー アカウントを検索し、**メールの設定**を展開します。</span><span class="sxs-lookup"><span data-stu-id="f1018-151">Find the user account in question and expand **Mail Settings**.</span></span>
3. <span data-ttu-id="f1018-152">**電子メールの転送**をするには、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1018-152">For **Email forwarding**, click **Edit**.</span></span>
4. <span data-ttu-id="f1018-153">不審な転送先アドレスを削除します。</span><span class="sxs-lookup"><span data-stu-id="f1018-153">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="f1018-154">ステップ 3 は、不審な受信トレイ ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f1018-154">Step 3 Disable any suspicious inbox rules</span></span>
1. <span data-ttu-id="f1018-155">Outlook Web App (OWA) を使用してユーザーのメールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1018-155">Sign in to the user's mailbox using Outlook Web App (OWA).</span></span>
2. <span data-ttu-id="f1018-156">歯車のアイコンをクリックし、[**メール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1018-156">Click on the gear icon and click **Mail**.</span></span>
3. <span data-ttu-id="f1018-157">**スイープし、受信トレイのルール**] をクリックし、ルールを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1018-157">Click **Inbox and sweep rules** and review the rules.</span></span>
4. <span data-ttu-id="f1018-158">無効にするか、不審なルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="f1018-158">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="f1018-159">手順 4 ブロックを解除するユーザーがメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="f1018-159">Step 4 Unblock the user from sending mail</span></span>
<span data-ttu-id="f1018-160">侵害された疑いがあるメールボックスがスパム メールを送信するのには不正使用された場合は、メールボックスがメールを送信するからブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1018-160">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>
1. <span data-ttu-id="f1018-161">メールボックスからのメール送信のブロックを解除するには、[ユーザー、ドメイン、またはスパムの電子メールを送信した後のブロック一覧から IP アドレスを削除する](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f1018-161">To unblock a mailbox from sending mail, follow the procedures in [Removing a user, domain, or IP Address from a block list after sending spam email](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email ).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="f1018-162">署名内のユーザー アカウントをブロックするオプションの手順 5。</span><span class="sxs-lookup"><span data-stu-id="f1018-162">Step 5 Optional: Block the user account from signing-in</span></span>
> [!IMPORTANT]
> <span data-ttu-id="f1018-163">署名でアクセスを再度有効にするは安全と思われるまで危険にさらされた疑いのあるアカウントをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="f1018-163">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="f1018-164">Office 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1018-164">Go to the Office 365 admin center.</span></span>
2. <span data-ttu-id="f1018-165">Office 365 管理センターでは、**ユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1018-165">In the Office 365 admin center, select **Users**.</span></span>
3. <span data-ttu-id="f1018-166">ブロックは、使用する従業員を選択し、[**サインイン状態**の横の**編集**を、[ユーザー] ウィンドウで選択</span><span class="sxs-lookup"><span data-stu-id="f1018-166">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane</span></span>
4. <span data-ttu-id="f1018-167">**サインイン状態**ウィンドウで、**サインインをブロック**し、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1018-167">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span> 
5. <span data-ttu-id="f1018-168">Office 365 管理センターで、左のナビゲーション ウィンドウでは、**管理センター**を展開し、**交換**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1018-168">In the Office 365 admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>
6. <span data-ttu-id="f1018-169">Exchange 管理センターで、[に移動**受信者 > メールボックス**。</span><span class="sxs-lookup"><span data-stu-id="f1018-169">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>
7. <span data-ttu-id="f1018-170">ユーザーを [ユーザーのプロパティ] ページで、[**モバイル デバイス**] をクリックして**Exchange ActivcSync を無効にして****デバイスの OWA を無効にして**両方に**yes**と答えます。</span><span class="sxs-lookup"><span data-stu-id="f1018-170">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>
8. <span data-ttu-id="f1018-171">[**メール接続****を無効にして**解答を **[はい]** です。</span><span class="sxs-lookup"><span data-stu-id="f1018-171">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span> 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="f1018-172">手順 6 のオプション: すべての管理者の役割グループからセキュリティを侵害された疑いのあるアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="f1018-172">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>
> [!NOTE]
> <span data-ttu-id="f1018-173">アカウントがセキュリティで保護された後、管理者の役割グループのメンバーシップを復元できます。</span><span class="sxs-lookup"><span data-stu-id="f1018-173">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="f1018-174">グローバル管理者アカウントを使用して Office 365 の管理センターにサインインし、**アクティブなユーザー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="f1018-174">Sign in to the Office 365 Admin Center with a global administrator account and open **Active Users**.</span></span>
2. <span data-ttu-id="f1018-175">疑いのあるアカウントが侵害され、手動であるか確認して、アカウントに割り当てられているすべての管理者の役割があるかどうかを検索します。</span><span class="sxs-lookup"><span data-stu-id="f1018-175">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>
3. <span data-ttu-id="f1018-176">は、**セキュリティとコンプライアンスのセンター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="f1018-176">Open the **Security & Compliance Center**.</span></span>
4. <span data-ttu-id="f1018-177">[**アクセス許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1018-177">Click **Permissions**.</span></span>
5. <span data-ttu-id="f1018-p109">アカウントのうちいずれかのメンバーでは、疑いのある危険にさらされた場合に表示する役割グループを手動で確認します。 ある場合: a. がロール グループをクリックし、**ロール グループの編集**] をクリックします。 b. は、役割グループからユーザーを削除する**メンバーの選択**し、**編集**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1018-p109">Manually review the role groups to see if the suspected compromised account is a member of any of them.  If it is:  a. Click the role group and click **Edit Role Group**.  b. Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>
6. <span data-ttu-id="f1018-183">**Exchange 管理センター**を開く</span><span class="sxs-lookup"><span data-stu-id="f1018-183">Open the **Exchange Admin Center**</span></span>
7. <span data-ttu-id="f1018-184">[**アクセス許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1018-184">Click **Permissions**.</span></span>
8. <span data-ttu-id="f1018-p110">アカウントのうちいずれかのメンバーでは、疑いのある危険にさらされた場合に表示する役割グループを手動で確認します。ある場合: a. がロール グループをクリックし、[**編集**] をクリックします。 b. 役割グループからユーザーを削除するのには、[**メンバー** ] セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1018-p110">Manually review the role groups to see if the suspected compromised account is a member of any of them. If it is:  a. Click the role group and click **Edit**.  b. Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="f1018-190">手順 7 オプション: 追加のための予防策</span><span class="sxs-lookup"><span data-stu-id="f1018-190">Step 7 Optional: Additional precautionary steps</span></span>
1. <span data-ttu-id="f1018-p111">送信済みアイテムを確認することを確認します。人をメンバー リストに自分のアカウントが危険にさらされたことを通知する必要があります。攻撃者は、可能性がありますもらいますにお金、なりすましが行われるなどのことが、別の国に取り残され、コストを必要とする攻撃者が送信したりも自分のコンピューターをハイジャックすることがウイルスに感染します。</span><span class="sxs-lookup"><span data-stu-id="f1018-p111">Make sure that you verify your sent items. You may have to inform people on your contacts list that your account was compromised. The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>
2. <span data-ttu-id="f1018-p112">その他のサービスを別の電子メール アカウントが侵害されたとは、この Exchange アカウントを使用します。最初に、Office 365 サブスクリプションには、次の手順を実行し、他のアカウントにこれらの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1018-p112">Any other service that used this Exchange account as its alternative email account may have been compromised. First, perform these steps for your Office 365 subscription, and then perform these steps for your other accounts.</span></span>
3. <span data-ttu-id="f1018-196">電話番号や住所など、連絡先情報が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1018-196">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="f1018-197">Pro の cybersecurity のように Office 365 をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="f1018-197">Secure Office 365 like a cybersecurity pro</span></span>
<span data-ttu-id="f1018-p113">Office 365 サブスクリプションのデータとユーザーを保護するために使用できるセキュリティ機能の強力なセットが付属します。 使用、 [Office 365 のセキュリティ ロードマップ: 最初の 30 日、90 日間での内外の優先順位のトップ](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)マイクロソフトが推奨する、Office 365 テナントのセキュリティに関するベスト プラクティスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f1018-p113">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.  Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="f1018-p114">最初の 30 日以内に実行するタスクです。 即座に影響があり、影響の少ないのはこれらのユーザーにします。</span><span class="sxs-lookup"><span data-stu-id="f1018-p114">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="f1018-p115">90 日以内に実行するタスクです。これらにより、計画し実装しますが、セキュリティ体制を大幅に改善するに少し時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="f1018-p115">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>
- <span data-ttu-id="f1018-p116">90 日が経過します。これらの拡張機能は、最初の 90 日間の作業でビルドします。</span><span class="sxs-lookup"><span data-stu-id="f1018-p116">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1018-206">参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1018-206">See also:</span></span>
- [<span data-ttu-id="f1018-207">Office 365 のセキュリティのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="f1018-207">Security best practices for Office 365</span></span>](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [<span data-ttu-id="f1018-208">Office 365 で Outlook のルールと ユーザー設定フォーム インジェクション攻撃の検出と修復を行う</span><span class="sxs-lookup"><span data-stu-id="f1018-208">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)
- [<span data-ttu-id="f1018-209">インターネット犯罪苦情センター</span><span class="sxs-lookup"><span data-stu-id="f1018-209">Internet Crime Complaint Center</span></span>](http://www.ic3.gov/preventiontips.aspx)
- [<span data-ttu-id="f1018-210">米国証券取引委員会の「フィッシング」詐欺</span><span class="sxs-lookup"><span data-stu-id="f1018-210">Securities and Exchange Commission - "Phishing" Fraud</span></span>](http://www.sec.gov/investor/pubs/phishing.htm)
