---
title: Office 365 の ATP の安全な添付ファイルの動作
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: '[安全な添付ファイル] 機能を使用すると、電子メールの添付ファイルの確認時間を確認できます。 安全な添付ファイルを使用して、ユーザーが電子メールで送受信する悪意のあるファイルから組織を保護します。'
ms.openlocfilehash: 99d31e327343971f6a7630e2a43ffd3044fbf976
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34592267"
---
# <a name="how-ffice-365-atp-safe-attachments-works"></a>Ffice> office 365 の ATP の安全な添付ファイルの動作方法

## <a name="how-it-works"></a>メカニズム

ATP の安全な添付ファイル機能は、組織内のユーザーの電子メールの添付ファイルを確認します。 ATP の安全な添付ファイルポリシーが設定されている場合に、そのポリシーの対象となるユーザーが Office 365 で電子メールを表示すると、そのメール添付ファイルがチェックされ、ATP の安全な添付ファイルのポリシーに基づいて適切な操作が実行されます。 ポリシーの定義によっては、悪意のあるファイルが送信されたことを知らなくても、ユーザーは作業を続けることができます。
  
次に、作業中の ATP の安全な添付ファイルの2つの例を示します。
  
- **例 1: 電子メールの添付ファイル**Lee が添付ファイル付きの電子メールメッセージを受信するとします。 Lee のユーザー資格情報を盗もうとするように設計されたマルウェアが安全か実際に添付されているかは、Lee では明白ではありません。 Lee の組織では、セキュリティ管理者が ATP の安全な添付ファイルポリシーを数日前に定義しています。 ATP の安全な添付ファイル機能を使用すると、Lee が受信する前に、仮想環境で電子メール添付ファイルが開かれ、テストされます。 添付ファイルが悪意があると判断された場合は、自動的に削除されます。 添付ファイルが安全な場合は、Lee がクリックしたときに正常に開かれます。

- **例 2: SharePoint Online のファイル**田中がファイルを受信し、SharePoint Online のライブラリにアップロードしたとします。 田中は、ファイルが実際に悪意があることを知らずに、そのファイルへのリンクを他のチームと共有します。 幸いなことに、 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)は、悪意のあるファイルを検出してブロックしています。 数日後に、Chris はドキュメントを開きます。 Chris はファイルを見ることはできますが、そのファイルを開いたり共有したりすることはできません。

ATP の安全な添付ファイルポリシーは、組織内の特定のユーザーやグループ、またはドメイン全体に適用できます。 また、ATP の安全な添付ファイルのポリシーでは、実際の添付ファイルがスキャンされている間は、プレースホルダーの添付ファイルを使用するように構成できます。 詳細については、「 **[Office 365 で ATP の安全な添付ファイルのポリシーを設定](set-up-atp-safe-attachments-policies.md)** する」を参照してください。

> [!NOTE]
> ATP の安全な添付ファイルのスキャンは、Office 365 データが存在する地域と同じ地域で行われます。 データセンター地理の詳細については、「[データの保存場所](https://products.office.com/where-is-your-data-located?geo=All)」を参照してください。 

