---
title: Office 365 でのサービスの暗号化
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
description: '概要: は、Microsoft Office 365 のデータのリカバリ性を理解します。'
ms.openlocfilehash: 1273cd5556bf51dcdac9bbde1b3e8003ab818811
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532152"
---
# <a name="office-365-service-encryption"></a>Office 365 でのサービスの暗号化

ビジネスのボリューム レベルの暗号化、Exchange Online では、Skype のビジネス、SharePoint Online では、および OneDrive を使用する以外には、お客様のデータを暗号化するためにサービスの暗号化を使用します。サービスの暗号化は、キー管理の 2 つのオプションのことができます。
- マイクロソフトでは、すべての暗号化キーを管理します。(このオプションは、SharePoint のオンライン ビジネス、OneDrive、ビジネスの Skype では、現在利用可能なです。現在 Exchange Online のロードマップに掲載)。
- お客様がサービスの暗号化に使用されるルート キーを提供し、お客様が Azure キー ヴォールトを使用してこれらのキーを管理します。マイクロソフトでは、他のすべてのキーを管理します。このオプションは、お客様のキーと呼ばれ、Exchange のオンライン、SharePoint Online では、ビジネスのための OneDrive の現在使用可能になります。(以前 BYOK での高度な暗号化と呼ばれます。[Enhancing の透明度と Office 365 のお客様用のコントロール](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)の「元のお知らせ)

サービスの暗号化では、複数のメリットを提供します。などのこと。
- 権限の強力な暗号化保護に保護および管理の機能を提供します。
- テナントごとにキー管理を実現するマルチ テナント型のサービスを有効にする顧客キー オプションが含まれています。
- アクセスから顧客データが格納されているか、オペレーティング システムで処理する Windows オペレーティング システムの管理者の分離を提供します。
- 暗号化に関するコンプライアンス要件を持つお客様のニーズを満たす Office 365 の機能を強化します。

## <a name="customer-key"></a>顧客キー
顧客キーを使用すると、設置型の HSM またはキーの Azure のボルトを使用して、独自の暗号化キーを生成できます。キーの生成方法に関係なくお客様は制御し、Office 365 で使用される暗号化キーを管理する Azure キー ヴォールトを使用します。Azure キーの保管場所に、キーが保存されると、これらは、Exchange Online と SharePoint Online などのワークロードに割り当てられているし、メールボックスのデータとファイルの暗号化に使用するキーチェーンのルートとして使用できます。顧客キーを使用する他の利点の 1 つは、マイクロソフトの顧客データを処理する機能を制御します。この機能が存在するため、顧客と顧客は、マイクロソフトのサービスを終了またはクラウドに格納されたデータの一部を削除する) などの Office 365 からデータを削除する必要があることが、技術的な制御として顧客のキーを使用できないようにします。、マイクロソフトを含むアクセスしたり、データを処理します。これは、マイクロソフトのスタッフによるお客様のデータへのアクセスを制御するために使用できるユーザーのロック ボックスの機能を追加 (および補完) でします。

ビジネス、SharePoint Online では、およびビジネスのための OneDrive の Exchange Online、Skype の Office 365 用の顧客のキーを設定する方法については、[お客様のキーを使用して Office 365 のデータを制御する](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697)を参照してください。詳細については、 [Office 365 のよく寄せられる質問の顧客のキー](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)、および[顧客のキーを使用してコンプライアンスを満たすために、データが必要な管理と制御](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580)を参照してください。
