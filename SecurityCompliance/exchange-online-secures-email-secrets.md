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
description: office 365 のセキュリティ、プライバシー、コンプライアンス情報を提供する office 365 セキュリティセンターに加えて、office 365 がデータセンターで提供する機密情報を保護する方法について理解しておく必要があります。 Distributed Key Manager (DKM) というテクノロジを使用しています。
ms.openlocfilehash: ba4c661899273f5e07c2468631298f5500d0e32f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255485"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online が電子メールの機密情報をセキュリティで保護する方法

この記事では、Microsoft が電子メールの機密情報をデータセンターにセキュリティで保護する方法について説明します。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>自分が提供する機密情報をセキュリティで保護するにはどうすればよいですか?

office [365 のセキュリティ、プライバシー、コンプライアンス情報](https://go.microsoft.com/fwlink/?linkid=874644)を提供する office 365 セキュリティセンターに加えて、office 365 がデータセンターで提供する機密情報を保護する方法について理解しておく必要があります。 Distributed Key Manager (DKM) というテクノロジを使用しています。
  
Distributed Key Manager (DKM) は、一連の秘密キーを使用して情報を暗号化および復号化するクライアント側の機能です。 Active Directory ドメインサービス内の特定のセキュリティグループのメンバーのみが、DKM によって暗号化されたデータを復号化するためにこれらのキーにアクセスできます。 Exchange Online では Exchange プロセスの実行に使用する特定のサービス アカウントだけが、そのセキュリティ グループに属します。 データセンター内の標準運用手順の一環として、このセキュリティ グループに属する資格情報は人間には付与されないため、人間はだれもこれらの機密情報を解読できるキーにアクセスできません。
  
デバッグ、トラブルシューティング、または監査を目的として、データセンター管理者は、セキュリティグループの一部である一時的な資格情報を取得するために、昇格されたアクセスを要求する必要があります。 このプロセスでは、複数レベルの法的な承認が必要です。 アクセスが許可された場合、すべてのアクティビティがログに記録され、監査されます。 さらに、アクセスが自動的に期限切れになるように設定された時間間隔に対してのみアクセスが許可されます。
  
追加の保護では、DKM テクノロジにキーのロールオーバーとアーカイブが自動化されています。 これにより、同じキーを無期限に使用しなくても、古いコンテンツに継続してアクセスできるようになります。
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Exchange Online は、DKM を利用しますか?

Microsoft では、DKM を使用して Exchange Online データセンター内の機密情報を暗号化しています。 次に例を示します。
  
- 接続されたアカウントの電子メールアカウントの資格情報。 接続されたアカウントは、Hotmail、Gmail、yahoo! などのサードパーティのアカウントです。 メールアカウント。
    
- Rights Management service (RMS) のルートキー。 これは、Azure rms からインポートされるか、rms または Office 365 のメッセージ暗号化 (OME) で電子メールの暗号化と復号化に使用される、社内の Active Directory ドメインサービス RMS 展開からインポートされる顧客キーです。
    
## <a name="related-topics"></a>関連トピック

[Office 365 での暗号化](encryption.md)
  
[Office 365 の暗号化についてのテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)
  
[Office 365 セキュリティ&amp; /コンプライアンスセンターのサービスアシュアランス](https://go.microsoft.com/fwlink/?linkid=874645)
  

