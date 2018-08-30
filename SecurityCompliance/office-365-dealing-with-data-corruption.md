---
title: Office 365 のデータ破損に対処します。
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: データの破損で、Office 365 との防止と回復の Microsoft の取り組みの説明。
ms.openlocfilehash: 087be23ce5dad1daf62357cb08e27c0a15962792
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532241"
---
# <a name="dealing-with-data-corruption-in-office-365"></a>Office 365 のデータ破損に対処します。

大規模なクラウド サービスを実行するの難しい側面の 1 つは、データと独立したシステムの大規模なボリュームを指定したデータの破損を処理する方法です。データの破損は、によって発生することができます。
- アプリケーションの状態の一部またはすべての破損、アプリケーションまたはインフラストラクチャのバグ 
- ハードウェアの問題、データ損失やデータを読み取ることができなくなります。 
- 運用上のミス 
- 悪意のあるハッカーや悪意のある従業員 
- データの一部が失われると、外部のサービスの問題 

データの整合性のリカバリ性の向上が少ないデータの破損の問題なので、Microsoft Office 365 の保護メカニズムから発生していると同様にシステムとプロセスが存在する場合は、データを回復することが可能の破損を防ぐために作成しました。データの破損に対して弾力性を向上させるエンジニア リングのリリース プロセスのさまざまな段階でチェックし、プロセスの存在を含みます。
- システムの設計
- コードの組織と構造 
- コード レビュー 
- 単体テスト、統合テストとシステム テスト
- トリップ ワイヤのテスト/ゲート 

Office 365 の本番環境では、データ センター間でのピア レプリケーションは、複数のライブ データのコピーは常が保証されます。標準画像とスクリプトを使用して、失われたサーバーを回復して、レプリケートされたデータは顧客データを復元するために使用します。Microsoft では、組み込みのデータ復元機能のチェック、プロセスのため、SharePoint Online と内部のコードは、組み込みのレプリケーションを使用して Office 365 の情報システムのドキュメント (セキュリティ関連のドキュメントを含む) ののみのバックアップリポジトリ ツールでは、ソース ・ デポです。SharePoint online では、システムのドキュメントが格納されているし、ソース ・ デポには、システムとアプリケーションのイメージが含まれています。SharePoint Online とソース ・ デポ バージョン管理を使用し、ほぼリアルタイムにレプリケートされます。 