---
title: Office 365 での管理者による送信 (ATP)
ms.author: brwilcox
author: briwilcox
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 潜在的に有害なメッセージ、Url、ファイルを Microsoft に提出する方法について説明します。
ms.openlocfilehash: 6f7ea63cae4d7cafb0d1386b29d99101d290ef30
ms.sourcegitcommit: 9e2df36b05a2c93ce2629a7a5eda8f44159d114d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "35632227"
---
# <a name="admin-submissions-in-office-365-atp"></a>Office 365 での管理者による送信 (ATP)

管理者は、Microsoft が Office 365 でスキャンするために、ファイルまたはネットワークのメッセージ ID、Url、ファイルを使用してメールを送信できるようになりました。 更新された提出物セクションには、ユーザーが報告したメッセージが含まれています。 

電子メールを送信すると、受信メールがテナントに許可されている可能性のあるポリシーや、メール内のすべての Url と添付ファイルの調査に関する情報が得られます。 メールが許可されているポリシーには、個々のユーザーの信頼できる差出人のリスト、および ETR ルールなどのテナントレベルのポリシーが含まれます。 


## <a name="how-to-submit-content"></a>コンテンツを送信する方法

Microsoft にコンテンツを送信するには、送信ページの左上にある [**新しい送信**] ボタンをクリックします。 ページの右側にあるポップアップが表示され、電子メール、URL、またはファイルのいずれかを送信するオプションが表示されます。 

### <a name="email"></a>Email
![電子メール送信の例](media/submission-flyout-email.PNG)
1. 電子メールを送信するには、[**電子**メール] を選択し、電子メール**ネットワークのメッセージ ID**を指定するか、電子メールファイルをアップロードします。 

2. ポリシーチェックの実行対象となる受信者を指定します。 ポリシーチェックは、ユーザーまたはテナントレベルのポリシーによって、電子メールがスキャンをバイパスしたかどうかを判断します。 

3. 電子メールがブロックされているかどうかを指定します。 メールがブロックされている必要がある場合は、スパム、フィッシング、またはマルウェアとしてブロックされているかどうかを指定します。 可能な種類がわからない場合は、最適な judgement を使用してください。  

* 送信時のポリシーによってフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。

* 1つまたは複数のポリシーによってフィルターがバイパスされていない場合、スキャンは数分で完了します。 [状態] リンクをクリックすると、送信に関する追加情報が表示されます。 これには、ポリシーチェックの結果と rescan verdict が含まれます。 メモこれにより、Office 365 ATP の完全なフィルター処理スタックからメールが再度実行されることはありませんが、メール、URL、またはファイルの特定の属性に基づいて、部分的な再スキャンが実行されます。 

4. [**送信**] ボタンをクリックします。

### <a name="url"></a>URL
![電子メール送信の例](media/submission-url-flyout.png)
1. URL を送信するには、ポップアップから [ **url** ] を選択します。 プロトコル (**https://**) を含む完全な URL を入力します。 

* [**フィルター済み**] を選択した場合は、URL がフィッシングまたはマルウェアであるかどうかを指定します。

2. [**送信**] ボタンをクリックします。 


### <a name="file"></a>File
![電子メール送信の例](media/submission-file-flyout.PNG)
1. ファイルを送信するに**** は、ポップアップからファイルを選択し、スキャンしたいファイルをアップロードします。 

2. [**送信**] ボタンをクリックします。


## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection プラン2](office-365-ti.md)
  
[Office 365 で脅威から保護する](protect-against-threats.md)
  
[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)
  

