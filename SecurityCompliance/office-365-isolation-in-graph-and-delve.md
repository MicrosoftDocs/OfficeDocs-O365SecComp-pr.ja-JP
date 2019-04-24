---
title: office Graph および Delve での office 365 テナントの分離
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '概要: Office Graph および Delve のテナント分離について説明します。'
ms.openlocfilehash: 22bcf581c26ea4e334539a81861ff4dee68967ef
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262609"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a>Office Graph と Delve でのテナントの分離

## <a name="tenant-isolation-in-the-office-graph"></a>Office Graph でのテナントの分離
office [Graph](https://dev.office.com/officegraph)では、office 365 services のアクティビティ (Exchange online、SharePoint online、Yammer、Skype for business、Azure Active Directory など)、および外部サービス (他の Microsoft サービスやサードパーティ製のサービスなど) についてモデル化されています。 office Graph コンポーネントは office 365 全体で使用されます。 office Graph は、コンテンツとアクティビティのコレクション、およびそれらの間の関係を表します。これは、office スイート全体で行われます。 洗練されたマシン学習技術を使用して、ユーザーを関連するコンテンツ、会話、ユーザーに接続します。 たとえば、sharepoint online のテナントインデックスには、Delve クエリを処理するために使用される Office Graph インデックスがあり、sharepoint online の分析処理エンジンを使用してシグナルを格納し、insights を計算します。 Exchange online は各ユーザーの計算を行います。テナント分析への入力としての受信者キャッシュ。

Office Graph には、人、ドキュメントなどのエンタープライズ オブジェクト、およびこれらのオブジェクト間の関係およびやり取りに関する情報が含まれています。 関係とやり取りは、*エッジ*で表現されます。 Office Graph は、同じテナント内の*ノード*間でのみエッジが存在できるように、テナントでセグメント化されます。 *ノード*は、URI (Uniform resource Identifier)、ノードの種類、アクセス制御リスト、および*メタデータ*とエッジを含む一連のファセットを持つエンティティです。 各ノードにはメタデータとエッジが関連付けられており、共通のナレッジモデルと同じように*ファセット*に配置されています。 *メタデータ*とは、office graph 内での検索、フィルター処理、分析に使用できるノードに格納される名前付きプロパティのことです。 *ファセット*は、ノード上のメタデータとエッジの論理的なコレクションです。 各ファセットは、ノードの1つの側面について記述します。 

Office Graph では、すべてのデータが単一のリポジトリに格納されるわけではありません。代わりに、他の場所に存在するデータに関するメタデータと関係が保存されます。 Office Graph は、いくつかのデータストアと処理コンポーネントで構成されています。
- テナントグラフストアは、効率的な分析のために最適化されたバルクストレージを提供します。
- アクティブなコンテンツキャッシュを使用すると、ユーザーエクスペリエンスを促進するためにアクティブなノードとエッジにすばやくランダムにアクセスできます。
- 入力ルーターは、テナントグラフへの変更の内部および外部にあるコンポーネントに通知します。

テナント全体の計算に関連する各ワークロードの分析を推定し、テナントのグラフにプッシュします。 テナント内のすべてのアクティビティについてのテナント分析の理由。動作のパターンに関する洞察を生み出すことができます。 たとえば、Exchange Online は、分析を使用している各ユーザーの受信者キャッシュを、各ユーザーのメールボックスに対して効率的に計算します。 これらのユーザーごとの分析によって、各ユーザーに一連の*受信者キャッシュエッジ*が生成されます。これは、テナントのグラフにプッシュされます。 これにより、分析処理の多くがソースデータにできるだけ近い状態に保たれます。

## <a name="tenant-isolation-in-delve"></a>Delve でのテナントの分離
前述したように、Office Graph では、ユーザーが企業内の現在のアクティビティを見つけて共同作業する際に役立つエクスペリエンスを向上させることができます。また、ワークロード全体にわたるコンテンツとアクティビティを分析するためのエンティティ中心のプラットフォームを提供しています。Office 365 を超えています。 Delve は、Office Graph が提供する最初の作業です。
Delve は、office Graph を使用して、office の365および Yammer エンタープライズから office 365 ユーザーにコンテンツを表示する office 365 web experience です。 web experience は、データをさまざまなボードとして表示し、それぞれに** 特定のトピックを** 表示します。 各ボードは、ドキュメントの概要テキストと画像を表示する複数のドキュメントカードで構成されます。 カードを使用すると、ドキュメントまたは Yammer ページを開くなど、ユーザーがドキュメントを開くことができます。 Office 365 テナントの各ユーザーには、このユーザーに最も関連のあるドキュメントを表示するページと、Exchange Online または Skype for business を起動してその人物と対話するためのアイコンがあります。 Delve は、Office Graph api に基づいているため、api のテナントベースの分離によってバインドされています。