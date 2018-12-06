---
title: Outlook デスクトップ用の監督アドインをインストールする
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: Outlook のデスクトップのバージョンの Office 365 の監視アドインのインストールします。
ms.openlocfilehash: b0cb0d78ab5f8887628528dd53b49fb15de44126
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180867"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a><span data-ttu-id="b08b4-103">Outlook デスクトップ用の監督アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="b08b4-103">Install the Supervision add-in for Outlook desktop</span></span>

<span data-ttu-id="b08b4-p101">監督ポリシーによって特定の通信を確認するには、監督を追加で、Outlook および Outlook の校閲者の使用の web アプリケーション。アドインが自動的にインストール Outlook web app で、ポリシーで指定したすべての校閲者の。ただし、レビュー担当者は、デスクトップのバージョンの Outlook をインストールするのにはいくつかの手順を実行しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b08b4-p101">To review communications identified by a supervision policy, reviewers use the Supervision add-in for Outlook and Outlook web app. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. However, reviewers must run through some steps to install it in the desktop version of Outlook.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b08b4-p102">監督ポリシーで監視対象のユーザーは、準拠の高度なアドオンをいずれかの Office 365 エンタープライズ E3 ライセンスを取得する必要がありますか、Office 365 エンタープライズ E5 のサブスクリプションに含まれます。しない既存のエンタープライズ E5 計画して監視を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="b08b4-p102">Users monitored by supervision policies must have either an Office 365 Enterprise E3 license with the Advanced Compliance add-on or be included in an Office 365 Enterprise E5 subscription. If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="b08b4-109">監督のメールボックスのアドレスをコピーする手順 1。</span><span class="sxs-lookup"><span data-stu-id="b08b4-109">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="b08b4-110">Outlook デスクトップ用のアドインをインストールするには、監督のポリシー設定の一部として作成された監督のメールボックスのアドレスを必要があります。</span><span class="sxs-lookup"><span data-stu-id="b08b4-110">To install the add-in for Outlook desktop, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b08b4-111">だれかそれ以外の場合、ポリシーを作成する場合は、アドインをインストールするのにはこれらのファイルからこのアドレスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b08b4-111">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span>
 
 <span data-ttu-id="b08b4-112">**監督のメールボックスのアドレスを検索するには**</span><span class="sxs-lookup"><span data-stu-id="b08b4-112">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="b08b4-113">サインイン、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-113">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>
    
2. <span data-ttu-id="b08b4-114">**データ ・ ガバナンス**に\>**監督**します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-114">Go to **Data governance** \> **Supervision**.</span></span>
    
3. <span data-ttu-id="b08b4-115">監督ポリシーを確認する通信を収集する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b08b4-115">Click the supervision policy that's gathering the communications you want to review.</span></span>
    
4. <span data-ttu-id="b08b4-116">ポリシーの詳細] の [フライアウトを表示 \* \* 監督メールボックス \* \*、アドレスをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b08b4-116">In the policy details flyout, under \*\* Supervision mailbox \*\*, copy the address.</span></span><br/>![監督ポリシーの詳細のフライアウトが強調表示されている監督のメールボックスのアドレスが表示されているの「メールボックスの監視」セクション](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a><span data-ttu-id="b08b4-118">ステップ 2: Outlook デスクトップからのアクセスの監視のメールボックスを構成します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-118">Step 2: Configure the supervision mailbox for Outlook desktop access</span></span>

<span data-ttu-id="b08b4-119">次に、校閲者は、監督のメールボックスを Outlook に接続するためにはいくつかの Exchange のオンラインの PowerShell コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b08b4-119">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="b08b4-p103">オンライン PowerShell を交換するために接続します。[これはどのようにしますか?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="b08b4-p103">Connect to Exchange Online PowerShell. [How do I do this?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span></span>
    
2. <span data-ttu-id="b08b4-122">*SupervisoryReview{GUID}@domain.onmicrosoft.com*が、上記の手順 1 でコピーしたアドレスであり、*ユーザー*は、手順 3 で監督のメールボックスに接続する人の校閲者の名前を次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-122">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in Step 3.</span></span>
    - ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```<br/>
    - ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```
    
3. <span data-ttu-id="b08b4-123">以下の手順 3 移動する前に 1 時間以上まで待機します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-123">Wait at least an hour before moving on to Step 3 below.</span></span>
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="b08b4-124">監督のメールボックスに接続する Outlook プロファイルを作成する手順 3。</span><span class="sxs-lookup"><span data-stu-id="b08b4-124">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="b08b4-125">最後の手順では、校閲者は、監督のメールボックスに接続する Outlook プロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b08b4-125">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span>
 
> [!NOTE]
> <span data-ttu-id="b08b4-p104">新しい Outlook プロファイルを作成するには、Windows コントロール パネルの [メールの設定を使用します。これらの設定を取得するためのパスは、Windows オペレーティング システム (Windows 7、Windows 8 の場合、または Windows の 10) を使用している Outlook のバージョンがインストールされているによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b08b4-p104">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="b08b4-128">[コントロール パネル] を開き、ウィンドウの上部にある [**検索**] ボックスで**メール**を入力します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-128">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="b08b4-p105">(されないことを確認してコントロール パネルを取得する方法ですか。参照してください[場所は、コントロール パネルの [?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span><span class="sxs-lookup"><span data-stu-id="b08b4-p105">(Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="b08b4-131">**メール**アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="b08b4-131">Open the **Mail** app.</span></span>
    
3. <span data-ttu-id="b08b4-132">**メール設定 - Outlook\*\*\*\*プロファイルの表示**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b08b4-132">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="b08b4-133">![' メール設定 - Outlook] ダイアログ ボックスに、プロファイルの表示] ボタンがハイライトされます](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="b08b4-133">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="b08b4-p106">[**メール**] の [**追加**を] をクリックします。**新しいプロファイル**(**監督**) などの監督のメールボックスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-p106">In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="b08b4-136">!['監督' の名前を示す、[プロファイル名] ボックスで [新しいプロファイル] ダイアログ ボックス](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="b08b4-136">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="b08b4-137">**Outlook に接続**、**別のアカウントへの接続**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b08b4-137">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="b08b4-138">![強調表示されている別のアカウントへ接続] リンクを使用して Office 365 に Outlook を接続する ' メッセージ](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="b08b4-138">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="b08b4-139">**自動アカウント セットアップ**では、**手動設定] または [その他のサーバー**を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b08b4-139">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="b08b4-p107">**アカウント タイプの選択**] では、 **Office 365**を選択します。**電子メール アドレス**] ボックスで、以前にコピーした監督のメールボックスのアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-p107">In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="b08b4-142">![強調表示されている [電子メール アドレス] ボックスを表示する Outlook の [アカウントの追加] ダイアログ ボックスの ' のアカウントの種類の選択] ページです。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="b08b4-142">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="b08b4-143">ダイアログ ボックスが表示されたら、Office 365 のユーザーの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-143">When prompted, enter your Office 365 credentials.</span></span>
    
9. <span data-ttu-id="b08b4-144">成功すると、表示されます、**監督 -\<ポリシー名\>** フォルダーが Outlook のフォルダー一覧ビューで表示します。</span><span class="sxs-lookup"><span data-stu-id="b08b4-144">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>