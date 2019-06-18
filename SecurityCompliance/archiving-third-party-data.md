---
title: Office 365 でサードパーティのデータをアーカイブする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理者は、ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートできます。 これにより、Office 365 で Facebook、Twitter、およびその他のサードパーティのデータソースからデータをアーカイブすることができます。 その後、サードパーティデータの Office 365 コンプライアンス機能 (法的情報保留、電子情報開示、インプレースアーカイブ、アイテム保持ポリシーなど) を使用して適用することができます。
ms.openlocfilehash: 796ad0314374dca60d1ff5f6b9317be491b757a1
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014606"
---
# <a name="archive-third-party-data-in-office-365"></a>Office 365 でサードパーティのデータをアーカイブする

Office 365 を使用すると、管理者はソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。 Office 365 にインポートできるサードパーティのデータソースの例としては、次のサービスがあります。 
  
- **Social** – Facebook、LinkedIn、Twitter、Yammer 
    
- **インスタントメッセージング**– Yahoo メッセンジャー、GoogleTalk、および Cisco Jabber 
    
- **ドキュメントのコラボレーション**-ボックスとドロップボックス 
    
- **縦型産業**–顧客関係管理 (Salesforce チャターなど) や金融サービス (Bloomberg、Thomson Reuters など) 
    
- **SMS/text messaging** – BlackBerry 
    
サードパーティのデータがインポートされた後は、訴訟ホールド、電子情報開示、インプレースアーカイブ、監査、監督、Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能をこのデータに適用できます。 たとえば、メールボックスが訴訟ホールドに配置されると、サード パーティ のデータは保存されます。 Microsoft eDiscovery ツールを使用して、サードパーティのデータを検索できます。 Microsoft のデータの場合と同じように、アーカイブ ポリシーと保持ポリシーをサード パーティのデータに適用することもできます。 簡単に言えば、Office 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

Office 365 でサードパーティのデータをインポートしてアーカイブするには、次の2つの方法があります。

- **セキュリティ & コンプライアンスセンターでサードパーティのデータコネクタを使用**する-Office 365 のセキュリティ & コンプライアンスセンターで利用可能なカスタムデータコネクタを使用します。 コネクタをセットアップして構成すると、サードパーティのデータソースに接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、Office 365 のメールボックスにアイテムがインポートされます。 現時点では、Facebook のビジネスページ、企業 Twitter アカウント、インスタント Bloomberg、LinkedIn からデータをインポートしてアーカイブするためのコネクタを実装できます。 コネクタを設定するための詳しい手順については、以下を参照してください。
   
   - **Facebook** –[サンプルコネクタを使用して Office 365 で Facebook データをアーカイブする](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter** –[サンプルコネクタを使用して Office 365 で Twitter データをアーカイブする](archive-twitter-data-with-sample-connector.md)
    
   - **Linkedin** – [Office 365 で linkedin データをアーカイブするためのコネクタの設定](archive-linkedin-data.md)

- **Microsoft パートナーと連携**する-組織は、サードパーティのデータソースからアイテムを抽出するように構成されたカスタムコネクタを (定期的に) 提供する microsoft パートナーと連携して、次に microsoft クラウドに接続します。サードパーティ API を行い、それらのアイテムを Office 365 にインポートします。 また、パートナーコネクタは、アイテムのコンテンツをサードパーティのデータソースから電子メールメッセージに変換し、それを Office 365 のメールボックスにインポートします。 この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「Office を使用して[サードパーティデータをアーカイブする 365](work-with-partner-to-archive-third-party-data.md)」を参照してください。