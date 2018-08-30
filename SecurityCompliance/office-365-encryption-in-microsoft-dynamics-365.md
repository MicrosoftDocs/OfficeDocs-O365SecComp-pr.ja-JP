---
title: Microsoft Dynamics 365 の office 365 の暗号化
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 5/31/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: は、Microsoft Dynamics 365 で暗号化を理解します。'
ms.openlocfilehash: 181db1724f140c86fb1ac1dbf4a4bfb7063d25a3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531549"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365 の office 365 の暗号化

マイクロソフトは、マイクロソフトのデータベースやユーザーのデバイスとのデータ センター間でやり取りされることはしつつ、Dynamics 365 で顧客データを保護するのに暗号化テクノロジを使用します。お客様とマイクロソフトのデータ センターとの間に確立された接続が暗号化されていると、すべてのパブリック エンドポイントは、業界標準の TLS を使用してセキュリティで保護します。TLS は、効果的にデータの機密性とデータ センターのデスクトップとの間で整合性を確保するのにはセキュリティが強化されたブラウザーからサーバーへの接続を確立します。データの暗号化を有効にすると後、は、オフにすることはできません。詳細については、[フィールド レベルのデータの暗号化](https://msdn.microsoft.com/en-us/library/dn481562.aspx)を参照してください。

Dynamics 365 では、標準の Microsoft SQL Server のセル レベルの暗号化を使用してユーザー名とメール パスワードなどの機密情報が含まれている既定のエンティティの属性のセットです。この機能には、組織の FIPS 140-2 に関連付けられているコンプライアンス要件を満たすのに役立ちます。フィールド レベルでデータの暗号化では、 [Microsoft Dynamics CRM の電子メールのルーター](https://technet.microsoft.com/en-us/library/hh699800.aspx)にユーザー名とパスワード、Dynamics 365 インスタンスと電子メール ・ サービスとの統合を有効にするを格納する必要がありますを活用するためのシナリオで特に重要です。 

Dynamics 365 のすべてのインスタンスは、データ (休息中) にディスクに書き込まれるときのリアルタイムの暗号化を実行するのに[Microsoft SQL Server の透過的なデータ暗号化](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017)(TDE) を使用します。TDE は、SQL Server、Azure SQL データベースでは、Azure の SQL のデータ ウェアハウスのデータ ファイルを暗号化します。既定では、マイクロソフトは、格納し、Dynamics 365 のインスタンスのデータベースの暗号化キーを管理します。(財務の Dynamics 365 によって使用されるキーは、.NET Framework のデータ保護 API によって生成されます)。 

Dynamics 365 管理センターの管理キーの機能は、自己 Dynamics 365 のインスタンスに関連付けられているデータベース暗号化キーを管理する機能に管理者になります。(自己管理されたデータベースの暗号化キー、Microsoft Dynamics 365 年 2017年 1 月更新プログラムでのみ使用とできる可能性のあるないそれ以降のバージョンで利用可能です。詳細についてを参照してください[、Dynamics 365 (オンライン) のインスタンスの暗号化キーを管理](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)します。)キー管理機能には、PFX と BYOK の両方の暗号化キーなどのファイル、HSM に格納されているがサポートされています。(生成して、HSM で保護されたキーをインターネット経由で転送の詳細について[を生成し、Azure キー ヴォールト用の HSM で保護されたキーを転送する方法](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys)を参照してください)。 

アップロードの暗号化キーのオプションを使用するには、パブリックおよびプライベート暗号化キーを作成する必要があります。

キー管理機能は、暗号化キーを安全に格納するキー ヴォールトの Azure を使用して暗号化キー管理の複雑さを解消します。Azure キー ヴォールトでは、暗号化キーの保護と機密情報のクラウド アプリケーションとサービスによって使用されることができます。キー ヴォールトの Azure サブスクリプションがあることと、ほとんどの状況に Dynamics 365 ボルト内で使用する暗号化キーにアクセスする必要はありません、キー管理機能は必要ありません。
