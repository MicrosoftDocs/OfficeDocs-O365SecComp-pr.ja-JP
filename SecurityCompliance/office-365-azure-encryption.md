---
title: Azure での Office 365 暗号化
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
description: '概要: Azure の暗号化について説明します。'
ms.openlocfilehash: 317fafe34c642d6c78cdf856e7391715770c1659
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219837"
---
# <a name="office-365-encryption-in-azure"></a>Azure での Office 365 暗号化

## <a name="introduction"></a>はじめに
暗号化された通信や運用プロセスなど、Azure の技術的な防護策は、データのセキュリティを維持するのに役立ちます。また、追加の暗号化機能を実装し、独自の暗号化キーを管理する柔軟性もあります。お客様の構成に関係なく、Microsoft は暗号化を適用して Azure の顧客データを保護します。Microsoft では、さまざまな高度なテクノロジを使用して Azure でホストされているデータを制御し、暗号化キーの暗号化、制御、および管理、およびデータへのアクセスの制御や監査を行うこともできます。さらに、Azure ストレージには、セキュリティ機能の包括的なセットが用意されているため、開発者はセキュリティで保護されたアプリケーションを構築できます。

Azure には、ある場所から別の場所に移動する際にデータを保護するためのさまざまなメカニズムが用意されています。Microsoft では、クラウドサービスと顧客の間を移動するときに、TLS を使用してデータを保護しています。Microsoft のデータセンターは、Azure サービスに接続するクライアントシステムとの TLS 接続をネゴシエートします。完全転送機密性 (PFS) は、顧客のクライアントシステムと Microsoft のクラウドサービスとの間の接続を一意のキーで保護します。また、接続は RSA ベースの2048ビット暗号化キーの長さも使用します。この組み合わせにより、送信中のデータを他のユーザーが傍受したり、アクセスしたりすることが困難になります。

[クライアント側の暗号化](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)、HTTPS、または SMB 3.0 を使用して、アプリケーションと Azure 間のデータ転送を保護することができます。独自の仮想マシン (vm) とユーザーの間のトラフィックに対して暗号化を有効にすることができます。[azure 仮想ネットワーク](https://azure.microsoft.com/services/virtual-network/)では、業界標準の IPsec プロトコルを使用して、企業の VPN ゲートウェイと Azure の間、および仮想ネットワーク上に配置された vm 間のトラフィックを暗号化することができます。

rest のデータについては、Azure では、256のサポートなど、さまざまな暗号化オプションが提供されており、ニーズに最も適したデータストレージのシナリオを選択することができます。[ストレージサービスの暗号化](https://docs.microsoft.com/azure/storage/storage-service-encryption)を使用して azure ストレージに書き込んだときに、データを自動的に暗号化することができます。また、vm で使用されるオペレーティングシステムとデータディスクは、 [azure ディスク暗号化](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)を使用して暗号化することができます。さらに、[共有アクセス署名](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1)を使用して、Azure ストレージ内のデータオブジェクトへの代理アクセスを許可できます。azure では[、azure SQL データベースとデータウェアハウスに透過的なデータ暗号化](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)を使用して、データの暗号化も行います。

azure での暗号化の詳細については、「 [azure 暗号化の概要](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)」と「 [azure データ暗号化 (Rest](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest))」を参照してください。

## <a name="azure-disk-encryption"></a>Azure ディスク暗号化
[Azure Disk Encryption](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)を使用すると、Windows および Linux インフラストラクチャをサービス (IaaS) VM ディスクとして暗号化できます。Azure ディスク暗号化では、Windows の BitLocker 機能と Linux の DM/Crypt 機能を活用して、オペレーティングシステムとデータディスクのボリュームレベルの暗号化を行います。また、VM ディスク上のすべてのデータは、Azure storage の rest で暗号化されるようになります。azure ディスク暗号化は、azure Key Vault と統合されており、暗号化キーとシークレットの使用を制御、管理、および監査するのに役立ちます。

詳細については、「 [Azure Disk Encryption for Windows and Linux IaaS vm](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)」を参照してください。

## <a name="azure-storage-service-encryption"></a>Azure Storage Service の暗号化
[azure ストレージサービスの暗号化](https://docs.microsoft.com/azure/storage/storage-service-encryption)では、データを保存する前に、azure ストレージが自動的にデータを暗号化し、データの暗号化を解除してからデータを解読します。暗号化、復号化、およびキー管理のプロセスは、ユーザーに対して完全に透過的です。azure ストレージサービスの暗号化は、azure [Blob ストレージ](https://azure.microsoft.com/services/storage/blobs/)と[azure ファイル](https://azure.microsoft.com/services/storage/files/)に使用できます。また、Microsoft によって管理されている暗号化キーを Azure Storage Service 暗号化と共に使用することも、独自の暗号化キーを使用することもできます。(独自のキーを使用する方法については、「 [Azure Key Vault での customer managed keys を使用したストレージサービスの暗号化](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys)」を参照してください。Microsoft 管理キーの使用の詳細については、「 [Rest でのデータのストレージサービス暗号化](https://docs.microsoft.com/azure/storage/storage-service-encryption)」を参照してください。さらに、暗号化の使用を自動化することができます。たとえば、ストレージアカウントのストレージサービスの暗号化をプログラムで有効または無効にするには、 [azure storage resource プロバイダ REST API](https://msdn.microsoft.com/library/azure/mt163683.aspx)、 [.net 用ストレージリソースプロバイダークライアントライブラリ](https://msdn.microsoft.com/library/azure/mt131037.aspx)、 [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)、またはのいずれかを使用します。[Azure CLI](https://docs.microsoft.com/azure/storage/storage-azure-cli)。

一部の Office 365 サービスでは、データの格納に Azure を使用します。たとえば、SharePoint Online と OneDrive for business のデータは Azure Blob ストレージに格納され、Microsoft Teams はそのチャットサービスのデータをテーブル、blob、およびキューに格納します。また、サービス信頼ポータルのコンプライアンスマネージャー機能は、 [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)で暗号化された形式で保存された顧客入力データを格納します。これは、サービス (PaaS)、グローバルに分散された複数モデルのデータベースとしてのプラットフォームです。azure storage Service 暗号化は、azure Blob ストレージとテーブルに格納されているデータを暗号化します。また、azure ディスク暗号化は、キュー内のデータを暗号化し、Windows および IaaS 仮想マシンのディスクを使用して、オペレーティングシステムとデータディスクのボリューム暗号化を提供します。このソリューションによって、仮想マシンのディスク上のすべてのデータが Azure ストレージ内の残りの部分で暗号化されるようになります。[Azure Cosmos DB での rest の暗号化](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)は、セキュリティで保護されたキーストレージシステム、暗号化されたネットワーク、暗号化 api など、いくつかのセキュリティテクノロジを使用して実装されます。

## <a name="azure-key-vault"></a>Azure Key Vault
セキュリティで保護されたキーの管理は、暗号化のベストプラクティスに中核を発揮するだけではありません。また、クラウド内のデータを保護するためにも重要です。[Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)は、ハードウェアセキュリティモジュール (hsm) に格納されているキーを使用するパスワードなどのキーと小規模な機密情報を暗号化することができます。Azure Key Vault は、クラウドサービスで使用される暗号化キーへのアクセスを管理および制御するための Microsoft に推奨されるソリューションです。キーへのアクセス許可は、サービスまたは Azure Active Directory アカウントを持つユーザーに割り当てることができます。Azure Key Vault は、hsm とキー管理ソフトウェアを構成、修正、および保守する必要がなくなります。Azure Key Vault を使用すると、Microsoft はキーを認識せず、アプリケーションに直接アクセスできません。制御を維持します。また、hsm でキーをインポートまたは生成することもできます。 azure information protection を含むサブスクリプションがある組織では、顧客管理キーを使用するように azure information protection テナントを構成できます。[独自のキー](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions) (byok) とログを取得する[その使用方法](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)。
