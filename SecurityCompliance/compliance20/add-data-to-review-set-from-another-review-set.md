---
title: 1つのレビューセットから別のレビューセットにデータを追加する
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
description: ''
ms.openlocfilehash: 9dc75717ac0a57c8ccb38b1e01ec2fcb9c5737ab
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151969"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>別のレビューセットからのレビューセットへのデータの追加

場合によっては、ドキュメントの一部を1つのレビューセットから分割して、別のレビューセットで個別に操作する必要があります。  これは、校閲セットのコンテンツをカリングし、データのサブセットに対して分析を実行する場合に特に便利です。

この記事のワークフローに従って、ある校閲セットから別のレビューセットにコンテンツを追加します。

## <a name="before-you-begin"></a>始める前に

開始する前に、データを追加するための新しいレビューセットを作成する必要があります。  ケースの [**レビューセット**] タブに新しいレビューセットを追加できます。 詳細については、「[レビューセットを作成する](managing-review-sets.md#create-a-review-set)」を参照してください。

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>手順 1: 別のレビューセットに追加するコンテンツを識別する

ソースレビューセット内の特定のドキュメントを選択するか、レビューセットクエリによって返されるすべてのアイテムを選択することによって、1つのレビューセットから別のレビューセットにコンテンツを追加できます。  選択したアイテムを追加する場合は、アイテムを選択し、[**アクション**] をクリックしてから、[**別のレビューセットに追加] を**クリックします。

![別の校閲セットに追加する](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>手順 2: 別のレビューセットに追加するためのオプションを指定する

[**別のレビューセットオプションポップアップに追加**] ページで、アイテムを追加するレビューセットを選択します。 **すべての検索結果**または**選択したアイテム**を追加するかどうかを選択します。  その他の情報には、アイテムのすべてのメタデータを含めるためのオプションと、ドキュメントが新しいレビューセットに追加されたときにソースレビューセットから (**ラベル**チェックボックスをオンにして) タグを含めるかどうかを指定するオプションがあります。  

![別の校閲セットに追加する](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

[ **Ok]** をクリックすると、別のレビューセットにコンテンツを追加するための新しいジョブ (**別のレビューセットへのデータの追加**) が作成されます。  [**ジョブ**] タブに移動して、このジョブの進行状況を監視できます。 詳細については、「 [Manage jobs](managing-jobs-ediscovery20.md)」を参照してください。
