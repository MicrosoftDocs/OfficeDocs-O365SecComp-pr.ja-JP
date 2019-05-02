---
title: 1つのレビューセットから別のレビューセットにデータを追加する
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
description: ''
ms.openlocfilehash: 025fd90373313f762ce1d1dab8d48286e32e3cbb
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527225"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>別のレビューセットからのレビューセットへのデータの追加

場合によっては、ドキュメントの一部を1つのレビューセットから分割して、別のレビューセットで個別に操作する必要があります。  これは、校閲セットのコンテンツをカリングし、データのサブセットに対して分析を実行する場合に特に便利です。

次のワークフローを使用して、1つのレビューセットから別のレビューセットにコンテンツを追加します。

## <a name="before-you-begin"></a>始める前に

開始する前に、データを追加するための新しいレビューセットを作成する必要があります。  ケースの [**レビューセット**] タブに新しいレビューセットを追加できます。 詳細については、「 [review sets を管理](managing-review-sets.md)する」を参照してください。

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>手順 1: 別のレビューセットに追加するコンテンツを識別する

ドキュメントグリッド内の電子メールとドキュメント、または検索結果のすべてのアイテムを選択することで、コンテンツをレビューセットに追加できます。  選択したアイテムを追加する場合は、アイテムを選択し、[**アクション**] をクリックしてから、[**別のレビューセットに追加] を**クリックします。

![別の校閲セットに追加する](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>手順 2: 別のレビューセットに追加するためのオプションを指定する

[**別のレビューセットに追加**] ページで、アイテムを追加するレビューセットを選択します。 **すべての検索結果**または**選択したアイテム**を追加するかどうかを選択します。  その他の情報には、アイテムのすべてのメタデータを含めるためのオプションと、ドキュメントタグを新しいレビューセットに含める必要があるかどうかが表示されます。  **[Ok]** をクリックすると、コンテンツをレビューセットに追加するための新しいジョブが作成されます。そのジョブの進行状況を監視するには、[**ジョブ**] タブを使用します。詳細については、「 [Manage jobs](managing-jobs-ediscovery20.md)」を参照してください。

![別の校閲セットに追加する](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)
