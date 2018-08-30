---
title: Exchange Online が電子メールの機密情報をセキュリティで保護する方法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
description: だけでなく、Office 365 信頼センター Office 365 のセキュリティ、プライバシー、およびコンプライアンス情報を提供することもできます Office 365 がどのように役立つかを知っている、データ センターで提供する機密情報を保護します。分散キー マネージャー (DKM) と呼ばれるテクノロジを使用します。
ms.openlocfilehash: a8fe1a2c9393958a391ec69a9a476a06de8c7576
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532673"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online が電子メールの機密情報をセキュリティで保護する方法

この記事では、Microsoft がデータ センターの電子メールの機密情報をセキュリティで保護する方法について説明します。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>ユーザーの機密情報をセキュリティで保護する方法

だけでなく、Office 365 信頼センター[セキュリティ、プライバシー、および Office 365 のコンプライアンス情報](https://go.microsoft.com/fwlink/?linkid=874644)を提供することもできます Office 365 がどのように役立つかを知っている、データ センターで提供する機密情報を保護します。分散キー マネージャー (DKM) と呼ばれるテクノロジを使用します。
  
分散キー マネージャー (DKM) は、一連の秘密キーを使用して情報を暗号化および復号化するクライアント側の機能です。Active Directory ドメイン サービス内の特定のセキュリティ グループのメンバーのみが、DKM によって暗号化されたデータを解読するためにこれらのキーにアクセスできます。Exchange Online では Exchange プロセスの実行に使用する特定のサービス アカウントだけが、そのセキュリティ グループに属します。データセンター内の標準運用手順の一環として、このセキュリティ グループに属する資格情報は人間には付与されないため、人間はだれもこれらの機密情報を解読できるキーにアクセスできません。
  
デバッグ、トラブルシューティング、または監査目的のためには、セキュリティ グループに属する一時的な資格情報を取得するために、データセンターの管理者が昇格されたアクセス権限を要求する必要があります。このプロセスには複数レベルの法的な承認が必要です。アクセス権限が与えられると、すべての処理がログに記録され、監査の対象となります。さらに、アクセス権限は一定期間のみ付与され、その期間が過ぎると自動的に期限切れになります。
  
さらに保護を強化するために、DKM テクノロジには自動化されたキー ロール オーバーとアーカイブがあります。この機能によってもまた、同じキーに無期限に依存する必要なく、古いコンテンツへ引き続きアクセスできることが保証されます。

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Exchange Online での DKM の利用

Microsoft は、Exchange Online データセンター内の機密情報を暗号化するのに DKM を使用します。例をあげます。
  
- 接続されたアカウントの電子メール アカウントの資格情報。接続されるアカウントは、Hotmail、Gmail、Yahoo! メール アカウントなど、サード パーティのアカウントです。
    
- 権限管理サービス (RMS) のルート キーをします。これらは、Azure の RMS または RMS または Office 365 メッセージの暗号化 (ホーム) で電子メールを暗号化および暗号化に使用されるお客様のオンプレミスの Active Directory ドメイン サービスの RMS 展開からをインポートするかは、お客様のキーです。
    
## <a name="related-topics"></a>関連項目

[Office 365 での暗号化](encryption.md)
  
[Office 365 の暗号化についてのテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)
  
[サービスの Office 365 のセキュリティの保証&amp;コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=874645)
  

