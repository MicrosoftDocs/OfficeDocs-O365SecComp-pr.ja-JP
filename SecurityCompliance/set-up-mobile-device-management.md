---
title: モバイル デバイス管理 (MDM) Office 365 での設定します。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_OverviewMDM
- 'O365E_OverviewMDM '
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: dd892318-bc44-4eb1-af00-9db5430be3cd
description: Office 365 には、組み込みのモバイル デバイス管理では、セキュリティで保護し、iPhones、台もの Ipad Androids などのユーザーのモバイル デバイスを管理できます。 と、Windows の電話です。開始するにはこれらの手順をアクティブにし、Office 365 のモバイル デバイスの管理を設定します。
ms.openlocfilehash: c92290170b2937067e7407787282eaaa368b25b7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272362"
---
# <a name="set-up-mobile-device-management-mdm-in-office-365"></a><span data-ttu-id="2a23b-104">モバイル デバイス管理 (MDM) Office 365 での設定します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-104">Set up Mobile Device Management (MDM) in Office 365</span></span>

<span data-ttu-id="2a23b-p102">Office 365 の組み込みモバイル デバイス管理 (MDM) には、セキュリティで保護し、iPhones、台もの Ipad Androids などのユーザーのモバイル デバイスを管理することが、Windows の電話。作成しデバイスのセキュリティ ポリシーの管理、リモートでデバイスをワイプしてデバイスの詳細なレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p102">The built-in Mobile Device Management (MDM) for Office 365 helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones. You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>
  
<span data-ttu-id="2a23b-p103">ご質問があるでしょうか。ご用意しました[アドレスのよく寄せられる質問のためによく寄せられる質問](frequently-asked-questions-about-mdm.md)です。使用できないことに注意してください、[パートナー: サービス管理の委任](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e)Office 365 のモバイル デバイスの管理を管理します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p103">Have questions? We've put together [a FAQ to help address common questions](frequently-asked-questions-about-mdm.md). Be aware that you cannot use a [Partners: Offer delegated administration](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e) to manage Mobile Device Management for Office 365.</span></span> 
  
<span data-ttu-id="2a23b-110">デバイス管理のセキュリティの一部である&amp;MDM セットアップを開始する移動する必要がありますので、コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="2a23b-110">Device management is part of the Security &amp; Compliance Center so you'll need to go there to kick off MDM setup.</span></span>
  
<span data-ttu-id="2a23b-111">Office 365 のモバイル デバイスの管理を設定するには、必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a23b-111">To set up Mobile Device Management for Office 365 you'll need to:</span></span>
  
1. [<span data-ttu-id="2a23b-112">モバイル デバイス管理サービスを有効化します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-112">Activate the Mobile Device Management service</span></span>](#activate-the-mobile-device-management-service)  
2. [<span data-ttu-id="2a23b-113">モバイル デバイス管理を設定します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-113">Set up Mobile Device Management</span></span>](#set-up-mobile-device-management)
3. [<span data-ttu-id="2a23b-114">ユーザーがデバイスを登録するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-114">Make sure users enroll their devices</span></span>](#step-4-recommended-manage-device-security-policies)
  
## <a name="activate-the-mobile-device-management-service"></a><span data-ttu-id="2a23b-115">モバイル デバイス管理サービスを有効化します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-115">Activate the Mobile Device Management service</span></span>

1. <span data-ttu-id="2a23b-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2a23b-116">Sign in to Office 365 with your work or school account.</span></span> 
    
2. <span data-ttu-id="2a23b-117">移動[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)です。</span><span class="sxs-lookup"><span data-stu-id="2a23b-117">Go to [Security &amp; Compliance Center](https://protection.office.com).</span></span>
    
3. <span data-ttu-id="2a23b-118">**データ損失の防止**に移動\>**デバイス管理****では**ライセンス認証プロセスを開始する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a23b-118">Navigate to **Data loss prevention** \> **Device management** and click **Let's get started** to kick off the activation process.</span></span> 
    
    ![Office 365 でモバイル デバイス管理を設定します。](media/368e1026-9aa5-431b-a722-8f7cf528f263.png)
  
4. <span data-ttu-id="2a23b-p104">使い始めることを支援するための既定のセキュリティ ポリシーを作成しました。このページでは、セキュリティ ポリシーの名前を更新し、**セットアップを開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p104">We created a default security policy for you to help you get started. Update the name of the security policy on this page, and then click **Start setup**.</span></span>
    
    ![モバイル デバイス管理のセキュリティ ポリシーを設定します。](media/5619a2d1-f900-4268-9050-5d7eb57429a5.png)
  
5. <span data-ttu-id="2a23b-123">サービスのセットアップの進行状況が表示されるセットアップ画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a23b-123">You'll see the setup screen that shows progress on setting up the service.</span></span>
    
    ![MDM セットアップの進行状況](media/db45d1bb-d247-4ac0-9deb-1b0c1ace9bfa.png)
  
> [!TIP]
> <span data-ttu-id="2a23b-p105">検索では、 **MDM セットアップ**を検索することもできます。Office 365 管理センター内\>**ホーム**ページで、[**検索**] ボックスの種類のモバイル デバイスの管理です。>![管理センターでのモバイル デバイス管理のための検索](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)</span><span class="sxs-lookup"><span data-stu-id="2a23b-p105">You can also locate **MDM Setup** through Search. In the Office 365 admin center \> **Home** page, type mobile device management in the **Search** box. > ![Search for mobile device management in the admin center](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)</span></span>
  
<span data-ttu-id="2a23b-128">、Office 365 でモバイル デバイスの管理を有効化するのには時間がかかることができますが、それが終了すると、次の手順を説明する電子メールを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2a23b-128">It can take some time to activate Mobile Device Management for Office 365, but when it finishes, you'll receive an email that explains the next steps to take.</span></span>
  
## <a name="set-up-mobile-device-management"></a><span data-ttu-id="2a23b-129">モバイル デバイス管理を設定します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-129">Set up Mobile Device Management</span></span>

<span data-ttu-id="2a23b-p106">サービスの準備ができたら、セットアップを完了するのには次の 4 つの手順を完了します。**デバイスの管理**] ページで、セキュリティ[設定の管理]](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx)をクリックする必要があります&amp;コンプライアンス センターは、次の設定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p106">When the service is ready, complete the following four steps to finish setup. You may need to click [Manage settings](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx) on the **Device management** page in the Security &amp; Compliance Center to see the following settings.</span></span> 
  
![モバイル デバイスの管理に必要な推奨手順を設定します](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
### <a name="step-1-required-configure-domains-for-mdm"></a><span data-ttu-id="2a23b-133">MDM のステップ 1: (必須) の構成のドメイン</span><span class="sxs-lookup"><span data-stu-id="2a23b-133">Step 1: (Required) Configure domains for MDM</span></span>

<span data-ttu-id="2a23b-p107">Office 365 に関連付けられているカスタムのドメインを持っていない場合、または Windows デバイスを管理しているしない場合は、このセクションをスキップできます。それ以外の場合、お使いの DNS でドメインの DNS レコードを追加する必要があります。、Office 365 でドメインの設定の一部として、レコードを追加した場合は、すべて揃っています。レコードを追加した後に Office 365 の MDM を登録、カスタム ドメインを使用する電子メール アドレスを Windows デバイス上でサインインするユーザー、組織内のユーザーを Office 365 がリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p107">If you don't have a custom domain associated with Office 365 or if you're not managing Windows devices, you can skip this section. Otherwise, you'll need to add DNS records for the domain at your DNS host. If you've added the records already, as part of setting up your domain with Office 365, you're all set. After you add the records, Office 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in MDM for Office 365.</span></span>
  
<span data-ttu-id="2a23b-p108">レコードを設定するお手伝いが必要ですか。[Office 365 の DNS レコードを管理するときに作成する DNS レコード](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)に記載されているボックスの一覧で、ドメイン レジストラーを検索し、DNS レコードを作成するためのステップバイ ステップのヘルプを参照するのには登録名を選択します。これらの手順を使用すると、次の 2 つのレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p108">Need help setting up the records? Find your domain registrar in the list provided in [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23) and select the registrar name to go to step-by-step help for creating DNS records. Use those instructions to add the following two records:</span></span> 
  
|<span data-ttu-id="2a23b-141">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="2a23b-141">**Host name**</span></span>|<span data-ttu-id="2a23b-142">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="2a23b-142">**Record type**</span></span>|<span data-ttu-id="2a23b-143">**アドレス**</span><span class="sxs-lookup"><span data-stu-id="2a23b-143">**Address**</span></span>|<span data-ttu-id="2a23b-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2a23b-144">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a23b-145">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="2a23b-145">EnterpriseEnrollment</span></span>  <br/> |<span data-ttu-id="2a23b-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="2a23b-146">CNAME</span></span>  <br/> |<span data-ttu-id="2a23b-147">EnterpriseEnrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2a23b-147">EnterpriseEnrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="2a23b-148">3600</span><span class="sxs-lookup"><span data-stu-id="2a23b-148">3600</span></span>  <br/> |
|<span data-ttu-id="2a23b-149">EnterpriseRegistration</span><span class="sxs-lookup"><span data-stu-id="2a23b-149">EnterpriseRegistration</span></span>  <br/> |<span data-ttu-id="2a23b-150">CNAME</span><span class="sxs-lookup"><span data-stu-id="2a23b-150">CNAME</span></span>  <br/> |<span data-ttu-id="2a23b-151">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2a23b-151">EnterpriseRegistration.windows.net</span></span>  <br/> |<span data-ttu-id="2a23b-152">3600</span><span class="sxs-lookup"><span data-stu-id="2a23b-152">3600</span></span>  <br/> |
   
<span data-ttu-id="2a23b-153">2 つのレコードを追加した後に戻り、セキュリティ&amp;コンプライアンス センター**デバイスの管理**] に移動し、 \> **の設定の管理**を次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-153">After you add the two records, go back to the Security &amp; Compliance Center and navigate to **Device management** \> **Manage settings** to complete the next step.</span></span> 
  
### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="2a23b-154">手順 2: (必須) 構成 iOS デバイス用の Apn 証明書</span><span class="sxs-lookup"><span data-stu-id="2a23b-154">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="2a23b-155">IPad と iPhones のように iOS のデバイスを管理するには、Apn の証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a23b-155">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>
  
<span data-ttu-id="2a23b-156">これを行うには、**モバイル デバイスの管理] ページの設定**[**設定**のリンクから手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2a23b-156">To do this, follow the steps from the **Set up** links on the **Setup mobile device management page**.</span></span>
  
1. <span data-ttu-id="2a23b-157">**IOS デバイス用の Apn 証明書を構成する**] の横にある**設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-157">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="2a23b-158">**CSR ファイルをダウンロード**] を選択し、任意の場所に証明書署名要求を保存する、わかりやすいコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="2a23b-158">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![APN の証明書] ダイアログ ボックスをインストールします。](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="2a23b-160">**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-160">Select **Next**.</span></span>
    
4. <span data-ttu-id="2a23b-161">APN の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-161">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="2a23b-162">開くには、Apple のプッシュ証明書ポータル**アップル APN のポータル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-162">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![選択 Apple APN ポータルでの APN 通知証明書] ダイアログをインストールします。](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="2a23b-164">Apple ID でサインイン</span><span class="sxs-lookup"><span data-stu-id="2a23b-164">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2a23b-p109">Apple ID は、アカウントを管理しているユーザーを離れた場合でも、組織に残る電子メール アカウントに関連付けられている会社を使用します。証明書を更新する時と同じ ID を使用する必要がありますので、この ID を保存します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p109">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="2a23b-167">**証明書の作成**を選択し、**使用条件**に同意します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-167">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="2a23b-168">証明書署名要求**をアップロード**を選択し、Office 365 からコンピューターにダウンロードするには、**参照**をします。</span><span class="sxs-lookup"><span data-stu-id="2a23b-168">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="2a23b-169">**ダウンロード**APN の証明書は、お使いのコンピューターに Apple プッシュ証明書ポータルによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="2a23b-169">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="2a23b-170">、証明書のダウンロードで問題が発生した場合は、ブラウザーを更新します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-170">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="2a23b-171">Office 365 に戻るし、**次****アップロード APN の証明書**のページを表示するを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-171">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="2a23b-172">アップル プッシュ証明書ポータルからダウンロードした APN の証明書を参照します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-172">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![アップルからダウンロードした APN の証明書を選択するのには [参照] ボタンをクリックします。](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="2a23b-174">**終了**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-174">Select **Finish**.</span></span>
    
<span data-ttu-id="2a23b-175">APN の証明書を追加した後に戻り、セキュリティ&amp;コンプライアンス センター**デバイスの管理**] に移動し、 \> **の設定の管理**を次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-175">After you add APN Certificate, go back to the Security &amp; Compliance Center and navigate to **Device management** \> **Manage settings** to complete the next step.</span></span> 
  
### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="2a23b-176">手順 3: 複数要素の認証を設定 (推奨)</span><span class="sxs-lookup"><span data-stu-id="2a23b-176">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="2a23b-p110">**推奨の手順**では、多要素認証 (MFA) が表示されない場合は、ここを省略できます。このオプションを表示すると、Office 365 の登録プロセスのモバイル デバイス管理のセキュリティを強化する Azure AD ポータルで MFA を有効にすることをお勧めします。これは、既定でオフは。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p110">If you don't see multi-factor authentication (MFA) under **Recommended steps**, you can skip this section. If this option is listed, we recommend you turn on MFA in the Azure AD portal to increase the security of the Mobile Device Management for Office 365 enrollment process. It is turned off by default.</span></span>
  
<span data-ttu-id="2a23b-p111">MFA では、2 番目の形式の認証を要求することによって Office 365 にモバイル デバイスの登録のための記号をセキュリティで保護されたことができます。ユーザーは、電話、テキスト メッセージ、またはモバイル デバイスで正しく作業アカウント パスワードを入力した後のアプリケーション通知を確認する必要があります。そのデバイスは、この 2 番目の形式の認証が完了した後にのみ登録できます。後、ユーザーのデバイスは、Office 365 の [モバイル デバイスの管理に登録されている、ユーザーは作業が自分のアカウントだけを使用して Office 365 リソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p111">MFA helps secure the sign in to Office 365 for mobile device enrollment by requiring a second form of authentication. Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password. They can only enroll their device after this second form of authentication is completed. After users' devices are enrolled in Mobile Device Management for Office 365, users can access Office 365 resources with just their work account.</span></span>
  
<span data-ttu-id="2a23b-p112">**多要素認証を設定**すると、横にある**設定**を選択します。MFA Azure AD のポータルで有効にする方法については、[多要素認証の設定](https://go.microsoft.com/fwlink/p/?LinkId=519255)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p112">Next to **Set up multi-factor authentication**, select **Set up**. To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>
  
<span data-ttu-id="2a23b-186">MFA を設定した後に戻り、セキュリティ&amp;コンプライアンス センター**デバイスの管理**] に移動し、 \> **の設定の管理**を次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-186">After you set up MFA, go back to the Security &amp; Compliance Center and navigate to **Device management** \> **Manage settings** to complete the next step.</span></span> 
  
### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="2a23b-187">手順 4: (推奨) の管理デバイスのセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="2a23b-187">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="2a23b-p113">次に、作成し、Office 365 の組織のデータを保護するためにデバイスのセキュリティ ポリシーを展開します。などのことができますユーザーには、5 分続くと、デバイスをロックするポリシーを作成することによって、デバイスが失われた場合、データ損失を防止し、デバイスが 3 つのサインインが失敗した後に消去します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p113">The next step is to create and deploy device security policies to help protect your Office 365 organization's data. For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after 5 minutes of inactivity and have devices wiped after 3 sign-in failures.</span></span>
  
<span data-ttu-id="2a23b-190">**セキュリティ&amp;コンプライアンス センター****セキュリティ ポリシー**には、\>デバイスにセキュリティ ポリシーを作成し、ルールにアクセスする**デバイスのセキュリティ ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="2a23b-190">In the **Security &amp; Compliance Center**, go to **Security policies** \> **Device security policies** to create device security policies and access rules.</span></span> 
  
![デバイス セキュリティ ポリシーを追加します。](media/69a027f5-fbfb-482a-b850-9ccb280b8c62.png)
  
<span data-ttu-id="2a23b-192">新しいポリシーを作成する方法の手順についてを参照してください[を作成するデバイスのセキュリティ ポリシーを展開し、](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2a23b-192">For step by step instructions on how to create a new policy, see [Create and deploy device security policies](create-device-security-policies.md).</span></span>
  
> [!TIP]
>  <span data-ttu-id="2a23b-p114">新しいポリシーを作成する場合は、ユーザーのデバイスのポリシーに準拠していない場所にアクセスし、レポートのポリシー違反を許可するポリシーを設定することがします。Office 365 へのアクセスをブロックせずに、ポリシーによって影響を受ける方法の多くのモバイル デバイスを表示できます。> 組織のすべてのユーザーに新しいポリシーを展開する前に、少数のユーザーによって使用されるデバイスでのテストをお勧めします。> また、ポリシーを展開する前に、Office 365 を MDM のデバイスを登録することの潜在的な影響を知っている組織を使用できます。によってどのようにポリシーを設定すると、(非準拠のデバイス) にポリシーを遵守しないデバイスは、Office 365 へのアクセスを禁止でした。非準拠のデバイスはインストールされているアプリケーション、写真、および他の個人情報が登録されているデバイスでは、でしたを削除する場合は、デバイスが消去されているのもあります。詳細情報: [Office 365 でモバイル デバイスを無効](wipe-a-mobile-device.md)にします。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p114">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user's device isn't compliant with the policy. This lets you see how many mobile devices would be impacted by the policy without blocking access to Office 365. >  Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users. >  Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in MDM for Office 365. Depending on how you set up the policies, devices that don't comply with them (non-compliant devices) could be blocked from accessing Office 365. Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped. More info: [Wipe a mobile device in Office 365](wipe-a-mobile-device.md).</span></span> 
  
## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="2a23b-200">ユーザーがデバイスを登録するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a23b-200">Make sure users enroll their devices</span></span>

<span data-ttu-id="2a23b-p115">作成すると、モバイル デバイス管理ポリシーを展開して、ライセンスされた Office 365 のユーザーごとにデバイス ポリシーを適用する組織はメッセージが表示される登録次回モバイル デバイスから Office 365 にサインアップしています。登録とライセンス認証の手順に Office 365 の電子メールやドキュメントにアクセスする前に完了する必要があります。[職場または学校のモバイル デバイスの登録](enroll-your-mobile-device.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p115">After you've created and deployed a mobile device management policy, each licensed Office 365 user in your organization that the device policy applies to will receive an enrollment message the next time they sign into Office 365 from their mobile device. They must complete the enrollment and activation steps before they can access Office 365 email and documents. See [Enroll your mobile device for work or school](enroll-your-mobile-device.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2a23b-p116">登録プロセスによって、ユーザーの優先言語がサポートされていない場合ユーザーが表示される登録の通知と、モバイル デバイス上の手順を別の言語。モバイル デバイスの登録プロセスで、Office 365 ではサポートされていないすべての言語はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2a23b-p116">If a user's preferred language isn't supported by the enrollment process, users may receive enrollment notification and steps on their mobile devices in another language. Not all languages supported in Office 365 are currently supported for the enrollment process on mobile devices.</span></span> 
  
<span data-ttu-id="2a23b-206">Android や iOS のデバイスを持つユーザーが登録プロセスの一部として、会社のポータル アプリケーションをインストールするのには必要です。</span><span class="sxs-lookup"><span data-stu-id="2a23b-206">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2a23b-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a23b-207">Related Topics</span></span>

[<span data-ttu-id="2a23b-208">モバイル デバイス管理の機能</span><span class="sxs-lookup"><span data-stu-id="2a23b-208">Capabilities of Mobile Device Management</span></span>](capabilities-of-mobile-device-management.md)
  
[<span data-ttu-id="2a23b-209">デバイス セキュリティ ポリシーを作成して展開する</span><span class="sxs-lookup"><span data-stu-id="2a23b-209">Create and deploy device security policies</span></span>](create-device-security-policies.md)
  

