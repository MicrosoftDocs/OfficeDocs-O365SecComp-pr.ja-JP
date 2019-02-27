---
title: Office 365 でのサービスの暗号化
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Microsoft Office 365 のデータ復元性について理解します。'
ms.openlocfilehash: 385bb936de2c0cfcb478f0b20d2f7367d5b55ff4
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275697"
---
# <a name="office-365-service-encryption"></a>Office 365 でのサービスの暗号化

ボリュームレベルの暗号化に加えて、Exchange online、Skype for business、SharePoint Online、および OneDrive for business では、顧客データを暗号化するためにサービス暗号化も使用されます。サービス暗号化では、2つの主要な管理オプションを使用できます。
- Microsoft は、すべての暗号化キーを管理します。(このオプションは現在、SharePoint Online、OneDrive for business、Skype for business で利用できます。現在、Exchange Online のロードマップになっています。)
- お客様は、サービスの暗号化に使用されるルートキーを提供し、お客様は Azure Key Vault を使用してこれらのキーを管理します。Microsoft は、その他のすべてのキーを管理します。このオプションは顧客キーと呼ばれ、現在、Exchange online、SharePoint Online、OneDrive for business で使用できます。(以前は byok で高度な暗号化と呼ばれています)。元のアナウンスについては、「 [Office 365 のお客様の透明性と統制の強化](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)」を参照してください)。

サービス暗号化には複数の利点があります。たとえば、次のようになります。
- 強力な暗号化保護の上に、権限の保護と管理の機能を提供します。
- マルチテナントのキー管理をマルチテナントサービスが提供できるようにする顧客キーオプションが含まれています。
- Windows オペレーティングシステム管理者と、オペレーティングシステムによって保存または処理される顧客データへのアクセスを分離します。
- 暗号化に関するコンプライアンス要件を持つお客様の要求を満たす Office 365 の能力を向上させます。

## <a name="customer-key"></a>顧客キー
Customer キーを使用すると、社内 HSM または Azure キーコンテナーを使用して独自の暗号化キーを生成できます。キーの生成方法に関係なく、お客様は、Office 365 で使用される暗号化キーを制御および管理するために、Azure key Vault を使用します。キーを Azure Key Vault に格納したら、Exchange online や SharePoint online などのワークロードにキーを割り当てて、メールボックスのデータとファイルの暗号化に使用されるキーチェーンのルートとして使用することができます。顧客キーを使用する他の利点の1つは、Microsoft が顧客データを処理する機能を制御することです。この機能は、Office 365 からデータを削除するお客様 (たとえば、お客様が Microsoft とのサービスを終了したり、クラウドに保存されているデータの一部を削除したりする場合など) に対応できるようになります。(Microsoft を含む) は、データにアクセスしたり、処理したりできます。これは、Microsoft の担当者による顧客データへのアクセスを制御するために使用できる、お客様のロックボックス機能への追加 (および補数) です。

office 365 for Exchange Online、Skype for business、SharePoint Online、および OneDrive for business の顧客キーを設定する方法については、「 [office でのデータの管理」と「顧客キーを使用](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697)したデータの管理」を参照してください。詳細については、「 [Office 365 のお客様キー](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)」の FAQ を参照してください。また、[顧客キーによる法令遵守のニーズを満たすために役立つデータを管理および制御](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580)します。
