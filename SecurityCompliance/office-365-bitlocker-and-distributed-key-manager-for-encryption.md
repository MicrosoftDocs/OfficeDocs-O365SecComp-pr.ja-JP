---
title: Office 365 の暗号化用 BitLocker
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
description: '概要: クラウドでの暗号化の BitLocker に関する情報。'
ms.openlocfilehash: 77de478899591be54bdaf7c3ac9e7d591dd418b1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212907"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker とDistributed Key Manager (DKM) による暗号化
Office 365 サーバーは BitLocker を使用して、顧客保存データが含まれるディスク ドライブをボリューム レベルで暗号化します。BitLocker 暗号化は、Windows に組み込まれているデータ保護機能です。BitLocker は、顧客データが含まれるディスクに何者かが物理的にアクセスできるようになりかねない過失がプロセスや制御 (アクセス制御またはハードウェアのリサイクルなど) で生じた場合に、脅威から安全に保護するために使用されるテクノロジの 1 つです。その場合、BitLocker は、コンピューターやディスクの紛失、盗難、または不適切な廃棄によるデータの盗難や漏洩などの脅威の可能性を低減します。

BitLocker は、Exchange online、SharePoint Online、Skype for business の顧客データが格納されているディスク上に、Advanced encryption Standard (AES) 256 ビット暗号化を使用して展開されます。ディスクセクターは、完全なボリューム暗号化キー (FVEK) で暗号化され、ボリュームマスターキー (VMK) を使用して暗号化されます。これは、サーバーのトラステッドプラットフォームモジュール (TPM) にバインドされます。VMK は FVEK を直接保護するため、VMK を保護することが重要になります。次の図は、特定のサーバー (この場合は Exchange Online server を使用) に対する BitLocker キー保護チェーンの例を示しています。

次の表は、特定のサーバー (この場合は Exchange Online server) に対する BitLocker キー保護チェーンを示しています。

| キーの保護機能 | 性 | 生成方法 | 保存される場所 | 保護 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256-ビット外部キー | サーバーごと | BitLocker api | TPM またはシークレットセーフ | ロックボックス/アクセス制御 |
|  |  |  | メールボックスサーバーのレジストリ | TPM 暗号化 |
| 48桁の数字のパスワード | ディスクあたり | BitLocker api | Active Directory | ロックボックス/アクセス制御 |
| x.509 証明書をデータ回復エージェント (DRA) として公開キー保護機能とも呼びます。 | 環境 (Exchange Online マルチテナントなど) | Microsoft CA | ビルドシステム | 秘密キーへの完全なパスワードを持っているユーザーはいません。パスワードは、[物理的な保護] の下にあります。 |


BitLocker キーの管理 Office 365 データセンターで暗号化されたディスクのロック解除/回復に使用する回復キーの管理を行います。Office 365 は、セキュリティで保護された共有にマスターキーを格納します。これは、自分がスクリーン化および承認した個人のみがアクセスできます。キーの資格情報は、アクセス制御データ ("secret store" と呼ばれる) に対するセキュリティで保護されたリポジトリに格納されます。これには、高度な昇格と、ジャストインタイムのアクセス昇格ツールを使用してアクセスするための管理承認が必要です。

BitLocker は、2つの管理カテゴリに分類されるキーをサポートします。
- 通常、サーバーまたは特定のディスクにインストールされているオペレーティングシステムのインスタンスの有効期間が短時間で、BitLocker で管理されているキー。これらのキーは、サーバーの再インストール時またはディスクのフォーマット時に削除され、リセットされます。
- bitlocker の外部で管理されているが、ディスクの復号化に使用される bitlocker 回復キー。BitLocker は、オペレーティングシステムが再インストールされ、暗号化されたデータディスクが既に存在するシナリオで、回復キーを使用します。回復キーは、応答側がディスクのロックを解除する必要がある Exchange Online の管理された可用性監視プローブによっても使用されます。

BitLocker で保護されたボリュームは、完全なボリューム暗号化キーを使用して暗号化されます。これは、ボリュームマスターキーで暗号化されます。BitLocker は FIPS に準拠したアルゴリズムを使用して、暗号化キーが暗号化されずに保存または送信されることがないようにします。お客様のデータを保存する Office 365 の実装は、既定の BitLocker 実装から逸脱したものではありません。