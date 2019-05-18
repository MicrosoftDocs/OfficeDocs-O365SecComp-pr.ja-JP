---
title: Advanced eDiscovery で保管担当者を操作する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced 電子情報開示の保管担当者管理ツールを使用すると、法的訴訟で関心のある人物に関連付けられているデータを識別、保持、および収集することに関するワークフローを管理できます。
ms.openlocfilehash: 6e365f0b7f80a0a5caa050b2e0b08c94dbed4746
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151599"
---
# <a name="work-with-custodians-in-advanced-ediscovery"></a>Advanced eDiscovery で保管担当者を操作する

組織が法的調査に応答した場合、関連するデータを保管担当者する組織内のユーザーに基づいて、潜在的な関連性のあるコンテンツを特定し、保持し、収集することに関するワークフローを作成できます。 電子情報開示では、これらの個人は*data 保管担当者*(または*保管担当者*) と呼ばれ、"ドキュメントまたは電子ファイルの管理制御を持つ人" として定義されています。 たとえば、電子メールメッセージの保管担当者は、関連するメッセージが含まれるメールボックスの所有者である場合があります。  

調査の開始時に、電子情報開示チームは、ケースに関連するすべての関連保管担当者とデータソースを迅速に特定する必要があります。 時間の経過と共に、保管担当者のリストとそのデータソースが増加または decreasse ことがあります。 その結果、組織は、ケースのライフサイクルを通じて、custodial コンテンツを識別、保持、および収集するための制御されたプロセスを維持する必要があります。

高度な電子情報開示ケースでは、法務部門が組織内の個人を保管担当者として追加し、Exchange メールボックス、OneDrive アカウント、SharePoint、Teams サイトなどの、custodial データソースを自動的に識別して保持することができます。 高度な電子情報開示の組み込みの保管担当者管理ツールを使用することにより、組織は不用意 (または故意) による削除から電子的に保存された情報を保護することができます。 これにより、訴訟ホールドプロセスを手動で実行するための時間がかかり、エラーが発生しやすいプロセスを排除することができます。 

保管担当者の使用の詳細については、以下を参照してください。 

- [ケースにカストディアンを追加する](add-custodians-to-case.md)

- [ケースで保管担当者を管理する](manage-new-custodians.md)

- [カストディアンのアクティビティを表示する](view-custodian-activity.md)

## <a name="advanced-ediscovery-permissions"></a>高度な電子情報開示のアクセス許可

Advanced eDiscovery では、組み込みの電子情報開示マネージャーの役割グループを使用して、高度な電子情報開示でエンドツーエンドのワークフローを管理できるように、必要なアクセス許可を法的調査官に割り当てることができます。 または、高度な電子情報開示のケースで特定の操作を実行するために必要な役割のサブセットを使用して、カスタムの役割グループを作成することもできます。 電子情報開示関連のロールの詳細については、「 [Security _AMP_ コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](../assign-ediscovery-permissions.md)」を参照してください。
