---
title: Exchange Online が電子メールの機密情報をセキュリティで保護する方法
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: office 365 のセキュリティ、プライバシー、コンプライアンス情報を提供する office 365 セキュリティセンターに加えて、office 365 がデータセンターで提供する機密情報を保護する方法について理解しておく必要があります。Distributed Key Manager (DKM) というテクノロジを使用しています。
ms.openlocfilehash: ba4c661899273f5e07c2468631298f5500d0e32f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218077"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online が電子メールの機密情報をセキュリティで保護する方法

この記事では、Microsoft がデータ センターの電子メールの機密情報をセキュリティで保護する方法について説明します。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>ユーザーの機密情報をセキュリティで保護する方法

office [365 のセキュリティ、プライバシー、コンプライアンス情報](https://go.microsoft.com/fwlink/?linkid=874644)を提供する office 365 セキュリティセンターに加えて、office 365 がデータセンターで提供する機密情報を保護する方法について理解しておく必要があります。Distributed Key Manager (DKM) というテクノロジを使用しています。
  
分散キー マネージャー (DKM) は、一連の秘密キーを使用して情報を暗号化および復号化するクライアント側の機能です。Active Directory ドメイン サービス内の特定のセキュリティ グループのメンバーのみが、DKM によって暗号化されたデータを解読するためにこれらのキーにアクセスできます。Exchange Online では Exchange プロセスの実行に使用する特定のサービス アカウントだけが、そのセキュリティ グループに属します。データセンター内の標準運用手順の一環として、このセキュリティ グループに属する資格情報は人間には付与されないため、人間はだれもこれらの機密情報を解読できるキーにアクセスできません。
  
デバッグ、トラブルシューティング、または監査目的のためには、セキュリティ グループに属する一時的な資格情報を取得するために、データセンターの管理者が昇格されたアクセス権限を要求する必要があります。このプロセスには複数レベルの法的な承認が必要です。アクセス権限が与えられると、すべての処理がログに記録され、監査の対象となります。さらに、アクセス権限は一定期間のみ付与され、その期間が過ぎると自動的に期限切れになります。
  
さらに保護を強化するために、DKM テクノロジには自動化されたキー ロール オーバーとアーカイブがあります。この機能によってもまた、同じキーに無期限に依存する必要なく、古いコンテンツへ引き続きアクセスできることが保証されます。

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Exchange Online での DKM の利用

Microsoft は、Exchange Online データセンター内の機密情報を暗号化するのに DKM を使用します。例をあげます。
  
- 接続されたアカウントの電子メール アカウントの資格情報。接続されるアカウントは、Hotmail、Gmail、Yahoo! メール アカウントなど、サード パーティのアカウントです。
    
- Rights Management service (RMS) のルートキー。これは、Azure rms からインポートされるか、rms または Office 365 のメッセージ暗号化 (OME) で電子メールの暗号化と復号化に使用される、社内の Active Directory ドメインサービス RMS 展開からインポートされる顧客キーです。
    
## <a name="related-topics"></a>関連項目

[Office 365 での暗号化](encryption.md)
  
[Office 365 の暗号化についてのテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)
  
[Office 365 セキュリティ&amp; /コンプライアンスセンターのサービスアシュアランス](https://go.microsoft.com/fwlink/?linkid=874645)
  

