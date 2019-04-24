---
title: Office 365 セキュア スコア
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: Office 365 で組織が実際にセキュリティで保護されているかどうかが疑問になるかもしれません。 セキュリティで保護されたスコアは、ヘルプを提供します。 セキュリティで保護されたスコア Office 365 の通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てます。
ms.openlocfilehash: dd0dc87910853eba9f2ec3ec6752e857462b46e5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262471"
---
# <a name="office-365-secure-score"></a>Office 365 セキュア スコア

**概要**Office 365 で組織が実際にセキュリティで保護されているかどうかが疑問になるかもしれません。 セキュリティで保護されたスコアは、ヘルプを提供します。 セキュリティで保護されたスコア Office 365 の通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てます。 この記事では、セキュリティで保護されたスコアの概要とその使用方法について説明します。
  
## <a name="how-to-get-to-secure-score"></a>セキュリティで保護されたスコアを得る方法

[office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/)、 [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/)、または office 365 Business Premium を含むサブスクリプションが組織にあり、[必要なアクセス許可](#required-permissions)を持っている場合は、にアクセスして、組織のセキュリティスコアを表示することができます。[https://securescore.office.com](https://securescore.office.com). 

または、セキュリティ & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) にアクセスすることもできます。ここでは、現在のスコアを提供するセキュリティで保護されたスコアウィジェットを検索できます。

![セキュリティで保護されたスコアウィジェット](media/SecureScoreWidget-o365.png)

ウィジェットには、セキュリティで保護されたスコアダッシュボードへのリンクが含まれています。

![セキュリティスコアダッシュボード](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a>メカニズム

セキュリティで保護されたスコアは、使用している Office 365 サービス (OneDrive、SharePoint、Exchange など) を決定し、Microsoft によって確立されたベースラインに設定とアクティビティを比較します。 セキュリティのベストプラクティスを使用して、組織がどの程度適切に調整されているかに基づいてスコアを得られます。 組織のスコアを向上させるための手順についても、推奨事項を確認できます。 
  
![Office 365 のセキュリティスコアツールのアクションキュー](media/SecureScore-ActionsToTake.png)
  
セキュリティで保護されたスコアは、購入したサービスに基づいてスコアを計算します。 たとえば、Exchange online プランのみを購入した場合、SharePoint online のセキュリティ機能はスコアされません。 スコアの分母は、購入した製品に適用されるコントロールのすべてのベースラインの合計です。 分子は、完了または部分的に完了したすべてのコントロールを合計したもので、そのコントロールを満たす操作を実行します。

アクションを展開して、実行する手順、保護に役立つ脅威、および推奨事項に従ってスコアを上げるポイント数について説明します。
  
![Office 365 のセキュリティスコアツールの拡張されたアクション](media/SecureScore-DetailedActionToTake.png)
  
組織のセキュリティに対する操作の影響を確認するには、[**スコアアナライザー** ] タブを選択し、履歴を確認します。 
  
![Office 365 セキュリティスコアツールのスコアアナライザータブ](media/SecureScore-ScoreAnalyzer-7days.png)
  
グラフの下に、カテゴリ別のスコアとアクションの一覧が表示されます。 
  
![データポイントが選択されたことを示すスコアアナライザータブのグラフ](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
**[採点なし]** というラベルの付いたアクションは、組織に対して実行できるものですが、セキュリティで保護されたスコアに接続されていないため、スコアされません。  

[**スコアアナライザー** ] ページで、特定の日のデータポイントをクリックし、下にスクロールして、その日の完了および未完了のアクションを確認し、変更内容を確認します。 スコアは1日に1回 (約 1:00 AM PST) 計算されます。 測定されたアクションに変更を加えると、スコアは翌日を自動的に更新します。 スコアに変更を反映するには、最大48時間かかります。

セキュリティで保護されたスコアは、どの程度違反が発生する可能性があるかを絶対的に測定するものではありません。 これは、侵害される危険性を相殺できる機能を採用した範囲を表します。 サービスは違反しないことを保証できず、セキュリティで保護されたスコアは何らかの保証として解釈されないようにする必要があります。
 
## <a name="how-secure-score-helps"></a>セキュリティで保護されたスコアの活用

セキュリティで保護されたスコアを使用すると、Office 365 の組み込みのセキュリティ機能を使用することによって、組織のセキュリティ状況を向上させることができます (既に購入しているが、認識されない場合があります)。 これらの機能の詳細を理解することで、組織を脅威から保護するための適切な手順を実行していることを安心していただくことができます。
  
しかし、そのような単語を取得するだけではありません。 セキュリティで保護されたスコアを使用しているお客様は、そのスコアを使用していないお客様よりも5倍増加しています。 (スコアが増加するのは、組織で使用されているセキュリティ機能に対応します)。
  
> [!NOTE]
> セキュリティで保護されたスコアは、どの程度違反が発生する可能性があるかを絶対的に測定するものではありません。 これは、侵害される可能性があるリスクを相殺できる制御を採用した範囲を表します。 サービスは違反しないことを保証できず、セキュリティで保護されたスコアは何らかの保証として解釈されないようにする必要があります。 
  
## <a name="required-permissions"></a>必要なアクセス許可

セキュリティで保護されたスコアダッシュボードを表示して使用するには、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)に次のいずれかのロールが割り当てられている必要があります。
- グローバル管理者
- 課金管理者
- ユーザー管理者
- パスワード管理者
- セキュリティ管理者
- セキュリティリーダ
- Exchange 管理者
- SharePoint 管理者

 管理者の役割を割り当てられていないユーザーは、セキュリティで保護されたスコアにアクセスできません。

## <a name="related-topics"></a>関連トピック

[セキュリティ ダッシュボードの概要](security-dashboard.md)

[取得しているサブスクリプションが不明な場合](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
