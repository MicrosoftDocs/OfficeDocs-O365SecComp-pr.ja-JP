---
title: Exchange Online メールボックスに格納されているコンテンツ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 のクラウドベースのアプリによって生成されたデータは、Microsoft クラウド内のユーザーの Exchange Online メールボックスに格納されます。
ms.openlocfilehash: 6f7a81842df5972a03648a2f93d4bd6fbd738fec
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266899"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Exchange Online メールボックスに格納されているコンテンツ

Exchange Online のメールボックスは、主に、メッセージ、予定表アイテム、タスク、メモなどの電子メール関連のアイテムを格納するために使用されます。 しかし、クラウドベースの Office 365 アプリを追加すると、ユーザーのメールボックスにもデータが保存されることになります。 メールボックスにデータを格納する利点の1つは、コンテンツ検索、電子情報開示、高度な電子情報開示、データ調査の検索ツールを使用して、これらのクラウドベースのアプリからデータを検索、表示、およびエクスポートできることです。 これらのアプリの一部のデータは、メールボックス内の個人以外のメッセージ (IPM 以外の) サブツリーにある隠しフォルダーに格納されています。 これは、ユーザーが Outlook または他のメールクライアントを使用して自分のメールボックスにアクセスするときに、ユーザーの表示からデータが非表示になることを意味します。

次の表に、クラウドベースのメールボックスにデータを格納する Office 365 アプリの一覧を示します。 表には、各アプリに格納されるコンテンツの種類も記載されています。

|Office 365 アプリ  |説明  |
|:---------|:---------|
|フォーム     <br/> |フォーム (PDF ファイルとして保存される) とフォーム (CSV ファイルに格納されている) への返信は、電子メールメッセージに添付され、フォームを作成したユーザーのメールボックス内の隠しフォルダーに格納されます。 PST ファイルのフォームからコンテンツをエクスポートする場合、このデータは、次のグローバルに一意に識別される (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**という名前のサブフォルダーにある**applicationdataroot**フォルダーに格納されます。        <br/> |
|MyAnalytics    <br/> |   myanalytics を使用すると、ユーザーはメールボックス内のメールおよび予定表のデータに基づいて時間を費やす方法に関する洞察を得ることができます。 このデータは、ユーザーのメールボックスに非表示フォルダーに格納されます。 myanalytics データおよびエクスポート方法については、「 [myanalytics からのデータのエクスポート](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#exporting-data-from-myanalytics-and-the-office-roaming-service)」を参照してください。      <br/> |
|Office 365 グループ    <br/>|  電子メールメッセージ、予定表アイテム、連絡先 (人)、メモ、およびタスクは、Office 365 グループに関連付けられているメールボックスに格納されます。       <br/> |
|Outlook/Exchange Online<br/>|  電子メールメッセージ、予定表アイテム、連絡先 (人)、メモ、およびタスクは、ユーザーのメールボックスに格納されます。       <br/> |
|複数のユーザー    <br/> |  People アプリ (Outlook でアクセス可能な連絡先と同じ連絡先) 内の連絡先は、ユーザーのメールボックスに保存されます。      <br/> |
|プランナー     <br/> |   Planner で作成されたプランは、新しいプランの作成時に準備される対応する Office 365 グループのメールボックスに保存されます。 グループメールボックスのエイリアスは、プランの名前です。      <br/> |
|Skype for Business    <br/>  | Skype for business の会話は、ユーザーのメールボックスの [会話履歴] フォルダーに保存されます。 Skype 会議の参加者のメールボックスが訴訟ホールドの対象となっている場合、またはアイテム保持ポリシーに割り当てられている場合、会議に添付されたファイルは参加者のメールボックスに保持されます。         <br/> |
|Sway     <br/> |  sway は、電子メールメッセージに添付された HTML ファイルとして格納され、sway を作成したユーザーのメールボックス内の隠しフォルダーに格納されます。 PST ファイルの Sway からコンテンツをエクスポートする場合、このデータは、次の GUID で名前が付けられているサブフォルダーの**applicationdataroot**フォルダーに格納されます。 **905fcf2647 eb7-48a0-9ff0-8dcc7194b5ba**。       <br/> |
|タスク    <br/> |  tasks app 内のタスク (Outlook でアクセス可能なタスク) は、ユーザーのメールボックスに保存されます。       <br/> |
|Teams    <br/>  |Teams チャネルの一部である会話は、チームに関連付けられているメールボックスに格納されます。 Teams のチャットリスト (「 *1 x N」チャット*とも呼ばれます) に含まれる会話は、チャットに参加しているユーザーのメールボックスに保存されます。 また、Teams チャネルでの会議と通話の概要情報は、会議または通話にダイヤルしたユーザーのメールボックスに保存されます。 <br/> | 
|To Do  <br/> | to do アプリ** のタスク (to do リストに保存される) は、ユーザーのメールボックスに保存されます。        <br/> |
||||

> [!NOTE]
> 現時点では、Advanced eDiscovery (プレビュー) の保管担当者メールボックスにホールドが設定されている場合、フォームおよび Sway からのコンテンツは保持されません。 