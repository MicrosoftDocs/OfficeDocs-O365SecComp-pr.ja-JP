---
title: Office 365 でサードパーティのデータをアーカイブする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理者は、ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートできます。 これにより、Office 365 で Facebook、Twitter、およびその他のサードパーティのデータソースからデータをアーカイブすることができます。 その後、サードパーティデータの Office 365 コンプライアンス機能 (法的情報保留、電子情報開示、インプレースアーカイブ、アイテム保持ポリシーなど) を使用して適用することができます。
ms.openlocfilehash: b96c4852c3c9226219120a1be014ea3988cf91a2
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402915"
---
# <a name="archive-third-party-data-in-office-365"></a>Office 365 でサードパーティのデータをアーカイブする

office 365 を使用すると、管理者はソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから office 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。 Office 365 にインポートできるサードパーティのデータソースの例を次に示します。 
  
- **ソーシャル**Twitter、Facebook、Yammer、および LinkedIn 
    
- **インスタントメッセージング**-Yahoo メッセンジャー、GoogleTalk、および Cisco jabber 
    
- **ドキュメントのコラボレーション**-ボックスとドロップボックス 
    
- **垂直産業**-顧客関係管理 (Salesforce チャターなど)、金融サービス (Bloomberg、Thomson Reuters など) 
    
- **SMS/text messaging** -BlackBerry 
    
サードパーティのデータがインポートされた後は、訴訟ホールド、電子情報開示、インプレースアーカイブ、監査、監督、Office 365 アイテム保持ポリシーなどの office 365 コンプライアンス機能をこのデータに適用できます。 たとえば、メールボックスが訴訟ホールドに配置されると、サード パーティ のデータは保存されます。 Microsoft eDiscovery ツールを使用して、サードパーティのデータを検索できます。 Microsoft のデータの場合と同じように、アーカイブ ポリシーと保持ポリシーをサード パーティのデータに適用することもできます。 簡単に言えば、Office 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

Office 365 でサードパーティのデータをインポートしてアーカイブするには、次の2つの方法があります。

- **セキュリティ & コンプライアンスセンターでサードパーティのデータコネクタを使用**します。 Office 365 のセキュリティ & コンプライアンスセンターで利用可能なカスタムデータコネクタを使用します。 コネクタをセットアップして構成すると、サードパーティのデータソースに接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、Office 365 のメールボックスにアイテムがインポートされます。 コネクタを設定するためにこれらのコネクタでサポートされているサードパーティのデータソースについては、「[サンプルコネクタを使用してサードパーティのデータを Office 365 でアーカイブする (プレビュー)](archive-third-party-data-with-sample-connector.md)」を参照してください。

- **microsoft パートナーと協力**して、組織は、サードパーティのデータソースからアイテムを抽出するように構成されたカスタムコネクタを (定期的に)、microsoft のパートナーと連携させることができます。サードパーティ API を行い、それらのアイテムを Office 365 にインポートします。 また、パートナーコネクタは、アイテムのコンテンツをサードパーティのデータソースから電子メールメッセージに変換し、それを Office 365 のメールボックスにインポートします。 この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「Office を使用して[サードパーティデータをアーカイブする 365](work-with-partner-to-archive-third-party-data.md)」を参照してください。