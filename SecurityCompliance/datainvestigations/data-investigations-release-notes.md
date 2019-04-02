---
title: Microsoft 365 のデータ調査用リリースノート (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: この記事では、Microsoft 365 の新しいデータ調査 (プレビュー) ツールについて説明します。
ms.openlocfilehash: 648f223c136007e88a3beb6b58e692b758b5d27f
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030305"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Microsoft 365 のデータ調査用リリースノート (プレビュー)

Microsoft 365 の新しいデータ調査 (プレビュー) ツールを使用して、データ流出インシデントや内部調査などのデータ関連インシデントのトリアージ、調査、および修復を行うことができます。 データ調査のパブリックプレビューを使用すると、今後予定されている機能と更新プログラムに早期にアクセスできます。 最新の機能にいち早くアクセスするには、Security & コンプライアンスセンターでデータの調査 (プレビュー) に新しい調査を作成します。 その方法については、「 [Manage a data 流出 incident in Microsoft 365](manage-data-spillage-incidents.md)」を参照してください。

## <a name="whats-new"></a>新機能 

- **** 調査-調査を作成することで、検索とインシデントをグループ化できます。 メンバーを追加または削除することで、調査にアクセスできるユーザーを管理します。  お気に入りの調査を選択してマークすることもできます。 新しいダッシュボードを使用して、調査内および調査間でのアクティビティを追跡および監視します。 調査を完了したら、それをクローズまたは削除することができます。

- **関心のある**ユーザー–調査に関心のあるユーザーを追加すると、そのユーザーのメールボックス、OneDrive for business アカウント、および Microsoft Teams サイトが表示されます。 それらを使用して、調査対象のコンテンツ検索の範囲を作成できます。 関心のある人物をさらに調査するには、Office 365 およびその他の Microsoft サービスでのアクティビティに関連する監査レコードを表示することもできます。

- **検索**–さまざまな検索条件を使用して組織全体の検索を作成します。 検索するユーザーまたはサイトがわかっている場合は、それらのユーザーを関心のあるユーザーとして追加したり、検索作成ウィザードでサイトの場所を指定したりできます。 

- **証拠**–新しい証拠セットを作成し、確認する検索結果を追加します。 個々のドキュメントを確認し、調査メモを残すように注釈を付け、結果をエクスポートして別の環境に移動することができます。 

- **レビュー** –インシデントに追加されたドキュメントを確認するには、ネイティブ、テキスト、およびほぼネイティブのビューを使用します。 分析をドキュメントに適用して、重複、電子メールスレッド、およびテーマによってアイテムをグループ化することもできます。これは、インシデントのレビューを支援するのに役立ちます。 

- **墨消し、タグ、および注釈**: ドキュメントの校閲時に、テキストの墨消し、タグの適用、注釈の作成を行います。
  
- **高度なインデックス作成**–部分的にインデックス付けされたアイテムがある場合は、すべてのデータが検索に使用されるように、必要に応じてインデックスが再作成されます。

- **エラーの修復**–処理エラーを修復またはダウンロードします。 これには、大きなファイルの種類、パスワードで保護されたファイル、およびインデックス作成エラーに関連するその他の問題の修復サポートが含まれます。 

- **ジョブ**–長時間実行されているプロセスの状態を追跡します。

- **ハードディスクを削除するメールボックスアイテム**-緊急事態の場合は、正しく配置されていないアイテムを完全に削除する必要があります。 これを行うには、Security & コンプライアンスセンターの PowerShell で**new-compliancesearchaction-PurgeType ハード削除**コマンドを実行して、メールボックスからアイテムを完全に削除することができます。 詳細については、「 [new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)」を参照してください。
