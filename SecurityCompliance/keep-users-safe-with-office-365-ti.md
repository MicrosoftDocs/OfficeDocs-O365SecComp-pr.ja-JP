---
title: Office 365 の脅威の調査および応答機能を使用して組織を安全に保つ
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3387bfc3-028a-42f4-8133-4cbecfaab812
ms.collection:
- M365-security-compliance
description: Office 365 の脅威調査および応答機能を使用して、組織が侵入や脅威を検出し、脅威から迅速に脅威を軽減および回復する方法について説明します。
ms.openlocfilehash: 217203c0bfa29352bc7e1b2b3976f11966034fb0
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761693"
---
# <a name="keep-your-organization-safe-with-office-365-threat-investigation-and-response-capabilities"></a>Office 365 の脅威の調査および応答機能を使用して組織を安全に保つ

どの Office 365 ユーザーが攻撃にさらされているか、または深刻な侵害になっているかどうかを確認します。 ユーザーを対象とする攻撃を緩和して回復する方法を理解していますか。 Office 365 E5 に既に提供されているセキュリティ機能を使用して、これを正確に実行できることがわかりましたか。 
  
Office [365 の脅威の調査と応答](office-365-ti.md)機能が Office 365 E5 サブスクリプション ( [Office 365 Advanced threat Protection](office-365-atp.md)プラン2の一部として) に含まれています。 これらの機能により、Microsoft IT はソーシャルエンジニアリングインシデントの解決にかかる平均時間を 80% 削減し、大文字と小文字のスループットを劇的に向上させました。 最近、脅威を検出して回復する方法を改善するために、新機能が追加されました。 この記事では、脅威の調査と応答能力が、セキュリティ運用チームの効率と効率を向上させる方法について説明します。
  
## <a name="detect-intrusions-and-threats"></a>侵入と脅威を検出する

[脅威エクスプローラー](threat-explorer.md)(エクスプローラーとも呼ばれます) は、セキュリティ管理者とアナリストが組織内でアクティブな脅威を識別し、理解するのを促進します。 セキュリティ設定の中でも、安全ではないとしても、安全ではないと思われるユーザー構成によって回避されることがあります。 エクスプローラーを使用すると、ユーザーがマルウェアやフィッシングなどの脅威によって侵害されたかどうかを、Office 365 のグローバル管理者またはセキュリティ管理者が迅速に判断できます。 これにより、脅威や必要な応答に対して、最も危険にさらされるユーザーアカウントの優先順位付けを行うことができます。 
  
エクスプローラーを使用すると、管理者はユーザーとメール間の関係を移動することができます。 特定のメールが正しくないことがわかりますか。 これを検索して、どのユーザーがメールを受信したかを確認してから、一連のイベントを実行し、それらのユーザーが実行したことを確認します。

![Office 365 の脅威エクスプローラーのスクリーンショット、マルウェアファミリによる色分け](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a>脅威を迅速に軽減および復旧する

セキュリティ管理者は、テナント内で疑わしいまたは悪意のあるものを特定すると、その脅威にすばやく対応し、**インシデントフレームワーク**を使用して対応することができます。 不要なメッセージを1回クリックしてグループ化し、ユーザーのメールボックスからすばやく電子メールメッセージを削除します。 
  
 **更新:** インシデントフレームワークから直接電子メールメッセージを削除 (ソフトまたは削除) する機能が追加されました。 以前の管理者は、ユーザーの迷惑メールフォルダーにのみメールを移動でき、ユーザーはそのアイテムを回復できます。 新たにリリースされた削除機能を使用すると、悪意のあるメールまたは不要なメールが完全に削除されていることを確認できるようになりました。 
    
![インシデント修復の電子メールリストのスクリーンショット](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a>Microsoft の脅威テレメトリを活用する

Office 365 の脅威の調査と応答機能には、 [Microsoft インテリジェントセキュリティグラフ](https://go.microsoft.com/fwlink/?linkid=2036223)からのデータが使用されています。 グラフは、10億の Windows デバイス、4500億月の Azure ログイン、および Office 365 の4000億の電子メールメッセージから最新の脅威信号を取得します。 この unrivaled threat signal は、組織に影響を与える脅威をより完全に表示するために、セキュリティ運用チームが持つ広範な可視性を提供します。 
  
## <a name="next-steps"></a>次のステップ

- 詳細については、 [「Office 365 Advanced Threat Protection](office-365-atp.md)」を参照してください。

- この記録されたセッションの Office 365 脅威の調査および応答機能の詳細について[は、「office 365 で Cyberattacks](https://myignite.microsoft.com/videos/53723)をご確認ください。

- Office 365 Advanced Threat Protection プラン2をまだお持ちでない場合は、今すぐご利用ください。 「 [Office 365 Advanced Threat Protection: プランと料金」を](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)参照してください。
    
- [Microsoft Defender Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して保護を拡張します。