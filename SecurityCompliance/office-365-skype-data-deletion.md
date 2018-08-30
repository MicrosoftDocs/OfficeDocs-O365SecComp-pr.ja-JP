---
title: Office 365 の Skype のビジネス データの削除
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: ビジネスの Skype でのデータ削除に関する説明です。
ms.openlocfilehash: f3ddd0ad0797c465857919e8f7b28341492769ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532402"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a><span data-ttu-id="d207e-103">Skype を Office 365 でビジネス データの削除</span><span class="sxs-lookup"><span data-stu-id="d207e-103">Skype for Business Data Deletion in Office 365</span></span>

<span data-ttu-id="d207e-p101">Skype for Business は、ピアツーピアのインスタント メッセージ、マルチパーティのインスタント メッセージ、および会議中にアップロードされたコンテンツのアーカイブを提供します。アーカイブ機能には Exchange が必要で、ユーザーの Exchange メールボックスのインプレース ホールド属性によって制御されます。この属性は、電子メールと Skype for Business のコンテンツの両方をアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="d207e-p101">Skype for Business provides archiving of peer-to-peer instant messages, multiparty instant messages, and content upload activities in meetings. The archiving capability requires Exchange and is controlled by the user's Exchange mailbox In-Place Hold attribute, which archives both email and Skype for Business contents.</span></span>

<span data-ttu-id="d207e-p102">ユーザーレベルのアーカイブ ポリシーを作成、構成、適用することで、特定のユーザーまたはユーザー グループに対するアーカイブ処理を有効または無効にするため、Skype for Business のアーカイブはすべて「ユーザーレベル アーカイブ」と見なされます。Skype for Business 管理センター内部からはアーカイブ設定を直接管理できません。</span><span class="sxs-lookup"><span data-stu-id="d207e-p102">All archiving in Skype for Business is considered "user-level archiving" because you enable or disable it for one or more specific users or groups of users by creating, configuring, and applying a user-level archiving policy for those users. There is no direct control of archiving settings from within the Skype for Business admin center.</span></span>

<span data-ttu-id="d207e-108">ビジネス用の Skype では、次の種類のコンテンツはアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="d207e-108">The following types of content are not archived in Skype for Business:</span></span> 
- <span data-ttu-id="d207e-109">ピアツーピアのファイル転送</span><span class="sxs-lookup"><span data-stu-id="d207e-109">Peer-to-peer file transfers</span></span>
- <span data-ttu-id="d207e-110">ピアツーピアのインスタント メッセージおよび会議の音声/ビデオ</span><span class="sxs-lookup"><span data-stu-id="d207e-110">Audio/video for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="d207e-111">ピアツーピアのインスタント メッセージおよび会議のアプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="d207e-111">Application sharing for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="d207e-112">会議のコメント</span><span class="sxs-lookup"><span data-stu-id="d207e-112">Conferencing annotations</span></span> 

## <a name="meeting-content-retention"></a><span data-ttu-id="d207e-113">会議コンテンツの保存</span><span class="sxs-lookup"><span data-stu-id="d207e-113">Meeting Content Retention</span></span>
<span data-ttu-id="d207e-p103">ビジネスの Skype を使用しているお客様は、PowerPoint プレゼンテーション、OneNote ファイル、およびその他のファイルなどの添付ファイルとしてのビジネス会議のため、Skype にコンテンツをアップロードできます。ミーティングにアップロードされたコンテンツの保存期間は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d207e-p103">Customers using Skype for Business can upload content to a Skype for Business meeting as attachments, such as PowerPoint presentations, OneNote files, and other files. The retention period for content that has been uploaded to a meeting is as follows:</span></span>
- <span data-ttu-id="d207e-116">最後の人が会議を離れたときから、15 日の**1 回限りの会議**の内容が保持されます。</span><span class="sxs-lookup"><span data-stu-id="d207e-116">**One-time meeting** - Content is retained for 15 days starting from when the last person leaves the meeting.</span></span>
- <span data-ttu-id="d207e-p104">最後の人が会議の最後のセッションを離れた後、15 日の**定期的な会議**の内容が保持されます。他のセッションに参加、同じ会議 15 日以内の場合、保持タイマーがリセットされます。たとえば、ビジネス会議のため、Skype が 1 年間、週単位で発生することが予定されているし、最初のインスタンスの中に会議出席依頼のファイルがアップロードされます。少なくとも 1 人は、毎週の会議セッションを結合する場合、内に保持されます Skype ビジネス オンラインのサーバーの全体の年と最後のユーザーがデータ系列の最後の会議を離れた後の 15 日。</span><span class="sxs-lookup"><span data-stu-id="d207e-p104">**Recurring meeting** - Content is retained for 15 days after the last person leaves the last session of the meeting. The retention timer resets if someone joins the same meeting session within 15 days. For example, assume a Skype for Business meeting is scheduled to occur on a weekly basis for one year, and a file is uploaded to the meeting during the first instance. If at least one person joins the meeting session every week, the file is retained in Skype for Business Online servers for the entire year plus 15 days after the last person leaves the last meeting of the series.</span></span>
- <span data-ttu-id="d207e-121">**Meet Now ミーティング**のコンテンツは、8 時間後に、会議の終了時刻は保持されます。</span><span class="sxs-lookup"><span data-stu-id="d207e-121">**Meet Now meeting** - Content is retained for 8 hours after the meeting end time.</span></span>

> [!NOTE]
> <span data-ttu-id="d207e-122">ユーザーにライセンスがない場合場合 (たとえば、 **msRTCSIP userenabled**は、 *False*に設定されます) が無効になってとし、再ライセンスまたは再度有効に、ミーティング コンテンツは保持されません。</span><span class="sxs-lookup"><span data-stu-id="d207e-122">If a user is unlicensed or disabled (e.g., if **msRTCSIP-userenabled** is set to *False*), and is then re-licensed or reenabled, meeting content is not retained.</span></span>

## <a name="meeting-expiration"></a><span data-ttu-id="d207e-123">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="d207e-123">Meeting Expiration</span></span>
<span data-ttu-id="d207e-124">ユーザーは、以下の有効期間に応じて会議の終了後に、特定の会議にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d207e-124">Users can access a specific meeting after the meeting has ended, subject to the following expiration time periods:</span></span>
- <span data-ttu-id="d207e-125">**1 回限りの会議**の会議には、スケジュールされたミーティング時間の終了後、14 日間が有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="d207e-125">**One-time meeting** - Meeting expires 14 days after the scheduled meeting end time.</span></span>
- <span data-ttu-id="d207e-126">**終了日との定期的な会議**の会議には、最後の会議の予定のスケジュールされた終了時間後の 14 日間が有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="d207e-126">**Recurring meeting with end date** - Meeting expires 14 days after the scheduled end time of the last meeting occurrence.</span></span>
- <span data-ttu-id="d207e-127">**Meet Now ミーティング**の会議は、8 時間後に有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="d207e-127">**Meet Now meeting** - Meeting expires after 8 hours.</span></span>

## <a name="whiteboard-collaboration"></a><span data-ttu-id="d207e-128">ホワイト ボードのコラボレーション</span><span class="sxs-lookup"><span data-stu-id="d207e-128">Whiteboard Collaboration</span></span>
<span data-ttu-id="d207e-p105">すべての参加者がホワイト ボード上に作成した注釈が表示されます。ホワイト ボードを保存するとき、ホワイト ボードとすべての注釈はビジネスのサーバーで、Skype で、ミーティング コンテンツの有効期限ポリシーを管理者が設定したサーバーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="d207e-p105">Annotations made on whiteboards will be seen by all participants. When saving a whiteboard, the whiteboard and all annotations will be stored on a Skype for Business server, and it will be retained on the server according to meeting content expiration policies set by the administrator.</span></span>

## <a name="audio-test-service"></a><span data-ttu-id="d207e-131">オーディオ テスト サービス</span><span class="sxs-lookup"><span data-stu-id="d207e-131">Audio Test Service</span></span>
<span data-ttu-id="d207e-p106">音声の短い (約 5 秒間) のサンプルが記録されているオーディオ テスト サービスの呼び出し中にします。音声のサンプルが使用する確認と、録画の品質に基づくビジネスの呼び出しを Skype のサウンドの品質を確認します。オーディオ テスト サービスの呼び出しが終了すると、音声のサンプルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d207e-p106">A short (approximately 5 seconds) sample of your voice is recorded during the Audio Test Service call. The voice sample is used by you to check and/or verify the sound quality of your Skype for Business call based on the quality of the recording. When the Audio Test Service call ends, the voice sample is deleted.</span></span>

## <a name="persistent-group-chat"></a><span data-ttu-id="d207e-135">永続的なグループ チャット</span><span class="sxs-lookup"><span data-stu-id="d207e-135">Persistent Group Chat</span></span>
<span data-ttu-id="d207e-p107">持続グループ チャットでは、グループ チャットの会話の内容を格納します。有効な場合、管理者は、コンプライアンスや、他の目的のグループのチャットの履歴がアーカイブされている場合、この情報を格納するサーバーの保存期間を制御し、ルームのプロパティの管理と変更します。異なるロールを持つユーザーでは、次のように、永続化されたデータを別のアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="d207e-p107">Persistent Group Chat stores the content of group chat conversations. If enabled, the administrator can control the retention period, the server on which this information is stored, if Group Chat history is archived for compliance or other purposes, and manage/modify any properties on a room. Users with different roles have different access to the persisted data, as follows:</span></span>
- <span data-ttu-id="d207e-p108">管理者は、古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を大幅に増加してから、データベースのサイズを保持するすべてのチャット ルームから削除できます。削除またはメッセージを交換できるか、特定のチャット ルームには不適切とみなされ (または不適切と見なされます)。</span><span class="sxs-lookup"><span data-stu-id="d207e-p108">Administrators can delete older content (for example, content posted before a certain date) from any chat room to keep the size of the database from growing greatly. Or, they can remove or replace messages considered inappropriate for a given chat room (or considered unsuitable).</span></span>
- <span data-ttu-id="d207e-141">メッセージの著者を含む、エンド ・ ユーザーは、すべてのチャット ルームからコンテンツを削除できません。</span><span class="sxs-lookup"><span data-stu-id="d207e-141">End-users, including message authors, cannot delete content from any chat room.</span></span>
- <span data-ttu-id="d207e-p109">チャット ルームの管理者は、ルームを無効にすることができますが、ルームを削除することはできません。管理者のみが作成された後、チャット ルームを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d207e-p109">Chat room managers can disable rooms but cannot delete rooms. Only administrators can delete a chat room after it is created.</span></span>