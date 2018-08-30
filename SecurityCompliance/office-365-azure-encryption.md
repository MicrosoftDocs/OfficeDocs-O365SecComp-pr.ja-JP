---
title: Azure で office 365 の暗号化
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
description: '概要: Azure での暗号化の説明。'
ms.openlocfilehash: 5e1d0fc02daa7fe057e14045d1948762612b3674
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532198"
---
# <a name="office-365-encryption-in-azure"></a>Azure で office 365 の暗号化

## <a name="introduction"></a>概要
データを安全に保つための Azure で通信の暗号化や、運用プロセスなどの技術的な安全対策に役立ちます。追加の暗号化機能を実装し、独自の暗号化キーを管理できる柔軟性もあります。お客様の構成に関係なくは、マイクロソフトは、Azure で顧客データを保護するために暗号化を適用します。マイクロソフトでは、データの暗号化し、制御、暗号化キーを管理する高度な技術の範囲を Azure でホストされているデータを制御することも、データへのアクセスを制御し、監査します。さらに、Azure ストレージは、包括的な一連のセキュリティで保護されたアプリケーションを構築する開発者を組み合わせることにより実現されるセキュリティ機能を提供します。

Azure には、別に 1 つの場所から移動するときにデータを保護するための多くの機構が用意されています。マイクロソフトでは、クラウド サービスとお客様の間で移動するときにデータを保護するために TLS を使用します。マイクロソフトのデータ センターでは、Azure のサービスに接続しているクライアント システムの TLS 接続をネゴシエートします。完全な前方秘密 (PFS) は、一意のキーを使用してユーザーのクライアント システムとマイクロソフトのクラウド サービスとの間の接続を保護します。接続では、キーの長さが 2,048 ビットの RSA ベースの暗号化も使用します。この組み合わせでは、誰かをインターセプトし、アクセスのデータを転送中にします。

[クライアント側で暗号化](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)HTTPS、または SMB 3.0 を使用してアプリケーションと Azure の間で転送中のデータを保護できます。独自の仮想マシン (Vm) と、ユーザーとの間のトラフィックの暗号化を有効にできます。[Azure の仮想ネットワーク](https://azure.microsoft.com/services/virtual-network/)では、Azure を仮想ネットワーク上にある仮想マシンの間にも、企業の VPN ゲートウェイ間のトラフィックを暗号化するために業界標準の IPsec プロトコルを使用できます。

残りの部分にあるデータは、Azure では、AES の 256 のサポートなど、さまざまな暗号化オプション、ニーズに最適なデータ ストレージのシナリオを選択する柔軟性を提供します。データ暗号化が可能に自動的に[ストレージ ・ サービスの暗号化](https://docs.microsoft.com/azure/storage/storage-service-encryption)を使用して、Azure ストレージに書き込まれたときと、 [Azure のディスクの暗号化](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)を使用して、オペレーティング システムと仮想マシンで使用されるデータ ・ ディスクを暗号化できます。さらに、Azure ストレージ内のデータ オブジェクトへのアクセスを委任された[共有アクセス署名](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1)を使用して付与できます。Azure では、 [Azure の SQL データベースとデータ ウェアハウスの透過的なデータ暗号化](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)を使用して残りの部分でデータの暗号化も提供します。

Azure での暗号化の詳細については、 [Azure の暗号化の概要](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)と[Azure データ暗号化の保存](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest)を参照してください。

## <a name="azure-disk-encryption"></a>Azure のディスクの暗号化
[Azure ディスク暗号化](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)を使用すると、Windows と Linux のインフラストラクチャ サービス (IaaS) VM として暗号化ディスクです。Azure のディスクの暗号化は、Windows の BitLocker の機能とオペレーティング システムとデータ ・ ディスクのボリューム ・ レベルの暗号化を提供する Linux の Dm-crypt 機能を活用します。また、Azure ストレージの残りの部分にある VM ディスク上のすべてのデータを暗号化することも保証されます。Azure のディスクの暗号化は、制御、管理、および暗号化キーおよび秘密情報の使用を監査するための Azure キー ヴォールトに統合されています。

詳細については、 [Azure ディスク暗号化のため Windows と Linux の IaaS の Vm](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)を参照してください。

## <a name="azure-storage-service-encryption"></a>Azure ストレージ サービスの暗号化
[Azure ストレージ ・ サービスの暗号化](https://docs.microsoft.com/azure/storage/storage-service-encryption)では、Azure ストレージによって自動的に暗号化データを永続化する前に取得する前にデータを記憶し、復号化します。暗号化、解読、およびキー管理のプロセスは、ユーザーに対して完全に透過的です。[Azure のブロブ ストレージ](https://azure.microsoft.com/services/storage/blobs/)と[Azure のファイル](https://azure.microsoft.com/services/storage/files/)には、azure のストレージ ・ サービスの暗号化を使用できます。Azure ストレージ ・ サービスの暗号化を使用、Microsoft で管理される暗号化キーを使用することもできますか、独自の暗号化キーを使用することができます。独自のキーを使用する方法の詳細についてを参照してください[顧客を使用してストレージ ・ サービスの暗号化は、Azure のキーの保管場所にキーを管理](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys)します。Microsoft 管理キーを使用する方法の詳細については、参照[データのストレージ ・ サービスの暗号化](https://docs.microsoft.com/azure/storage/storage-service-encryption))。さらに、暗号化の使用を自動化することができます。などのプログラムでを有効にしたり、 [Azure のストレージ ・ リソース プロバイダー API を置くと](https://msdn.microsoft.com/library/azure/mt163683.aspx)、[ストレージ ・ リソース プロバイダーのクライアント ライブラリ](https://msdn.microsoft.com/library/azure/mt131037.aspx)、 [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)では、使用するストレージ アカウントのストレージ ・ サービスの暗号化を無効にするか、[Azure CLI](https://docs.microsoft.com/azure/storage/storage-azure-cli)です。

いくつかの Office 365 サービスでは、Azure を使用して、データを格納するためです。など、SharePoint Online およびビジネスのための OneDrive は、Azure Blob ストレージにデータを格納し、マイクロソフトのチームは、テーブル、blob、およびキュー内のチャット サービスのデータを格納します。さらに、サービスの信頼のポータルのコンプライアンス マネージャー機能は、 [Azure 世界 DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)、世界中に分散、複数モデルのデータベース (PaaS)、サービスとしてのプラットフォームでの暗号化された形式で格納されている顧客が入力したデータを格納します。Azure のストレージ ・ サービスの暗号化は、Azure のブロブ ストレージにし、テーブル内に格納されているデータを暗号化し、Azure のディスクの暗号化は、キューと同様に、オペレーティング システムのボリュームの暗号化を提供する Windows および IaaS 仮想マシン ・ ディスクとデータ ディスク内のデータを暗号化します。ソリューションにより、仮想マシンのディスク上のすべてのデータが、Azure ストレージの残りの部分で暗号化されています。[Azure 世界 DB の残りの部分での暗号化](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)を実装するには、セキュリティで保護されたキー記憶域システム、暗号化されたネットワークは、暗号化 Api など、いくつかのセキュリティ テクノロジを使用します。

## <a name="azure-key-vault"></a>Azure Key Vault
セキュリティで保護されたキー管理は、暗号化のベスト プラクティスのコアだけではありません。クラウドにデータを保護するために不可欠です。[Azure キー ヴォールト](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)を使用すると、キーとハードウェア セキュリティ モジュール (Hsm) に格納されているキーを使用するパスワードのような小規模の機密情報を暗号化することができます。Azure キー ヴォールトは、マイクロソフトの管理と、クラウド サービスで使用される暗号化キーへのアクセスを制御するための推奨される解決策です。キーにアクセスするアクセス許可は、サービス、または Azure Active Directory アカウントを持つユーザーに割り当てられます。Azure キー ヴォールトでは、組織を構成する、この修正プログラムを適用すると、Hsm、およびキーの管理ソフトウェアを管理する必要があるを緩和します。Azure キー ヴォールトでは、マイクロソフトのキーは表示されません、アプリケーションはそれらに直接アクセスがないです。管理を維持できます。インポートまたは Hsm にキーを生成することができますも Azure の情報保護を含むサブスクリプションを持つ組織では、Azure の情報保護のテナント (BYOK) を[独自のキーの表示](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions)を、お客様が管理キーを使用するを構成できます)、[のログ使用法](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)。
