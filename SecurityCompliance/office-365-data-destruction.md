---
title: Office 365 データ破壊
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 datacenter ディスクドライブおよびサーバーのリサイクル、廃棄、または破壊に関する Microsoft のポリシーの概要。
ms.openlocfilehash: 638f1964be0573f5f053a95b1dfa475776dd7b25
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091089"
---
# <a name="office-365-data-destruction"></a>Office 365 データ破壊

## <a name="physical-data-destruction"></a>物理的なデータの破壊

Microsoft では、ディスクドライブのリサイクルと破棄に対処し、障害を発生させるか、サーバーを撤去する標準的なポリシーをデータ処理しています。Office 365 内のディスクドライブを再利用する前に、Microsoft は米国標準に準拠した物理的なサニタイズプロセスを実行します。また、技術専門の文書 800-88 ([NIST SP 800-88 のメディアのサニタイズのガイドライン](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf))).Office 365 のすべてのディスクドライブは、BitLocker ボリュームレベル暗号化を使用して暗号化されるため、実際には、NIST SP 800-88 に準拠した消去は必要ありません。しかし、Microsoft によって引き続き実行されています。

Office 365 データセンター内で使用されている障害が発生したディスクは、ISO プロセスによって物理的に破棄および監査されます。適切な廃棄方法は、資産の種類によって決まります。ワイプできないハードドライブの場合、Microsoft は廃棄プロセスを使用してメディア (disintegrates、incinerates など) を破棄し、情報の回復を不可能にします。また、破棄の記録はすべて保持します。Microsoft は、Office 365 内で再利用されているサーバーで同様のサニタイズプロセスを実行します。これらのガイドラインには、電子情報と物理的な校正の両方が含まれます。

再利用できないディスクドライブは、破棄されるディスクを含むデータセンター内のサイト上で実行される物理的な破壊プロセスを使用して廃棄されます。廃棄用に指定されたストレージメディアは、データセンターの各領域にある安全なビンに配置されます。各セキュリティで保護された bin ステーションは、ビデオ監視によって監視されます。廃棄ビンが約 50% の容量に達すると、サイトサービスチームは物理的なセキュリティチームに連絡して、その削除を調整します。サイトサービスの担当者は、escort の下にある破棄ビンを、セキュリティで保護されたストレージ領域に配置されるまで削除し、データの破棄を待機します。廃棄時のデータの処理を管理するポリシーと手順には、手順を含めて定期的にテストします。これにより、機械が破壊されることが承認されていることを確認できます。

データ破壊プロセスでは、まず、NIST 800-88 (可能な場合) に準拠した方法でディスクが消去され、それが工業シュレッダおよび物理的な demolished に置かれます。Microsoft は、NIST SP 800-88 の一貫した浄化/削除、アセットの破棄、暗号化、正確なインベントリ、追跡、およびトランスポート中の管理チェーンの保護を使用して、データセンターを離れる資産のアカウンタビリティを維持しています。このプロセスは、クローズドサーキットテレビで監視され、完了時に破棄の証明書が発行されます。

Microsoft では、[エクストリームプロトコルソリューション](http://www.enterprisedataerasure.com/)(EPS) のデータ消去ユニットを使用しています。EPS ソフトウェアは、クレンジングおよび削除/セキュリティで保護された消去に関する NIST SP 800-88 の要件をサポートしています。クレンジングまたは消滅する前に、Microsoft アセットマネージャーによってインベントリが作成されます。ベンダーが破壊に使用されている場合、ベンダーは、破棄された各アセットの証明書を提供します。これは、資産マネージャーによって検証されます。

## <a name="virtual-data-destruction"></a>仮想データの破棄

Microsoft では、データの効果的な仮想破壊に対処し、サービステナント間でデータが不適切に共有される可能性や、サービスでのハード削除後にアクセスできることを防止するためのデータ処理ポリシーと手順を備えています。1つのテナント内のサービスから削除されたデータは、同じ基になる物理記憶域の一部またはすべてが後で再割り当てされても、別のサービステナントからはアクセスできません。これは、仮想環境の拡張に使用される複数の仮想化とフラグメント化テクノロジ、各サービステナント内のアプリケーションのアクティブな削除動作 ([ページの解放](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)など)、および必要なメディアおよびアプリケーションコンテンツの暗号化プロセス。