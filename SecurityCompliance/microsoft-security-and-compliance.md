---
title: Microsoft 365 のセキュリティとコンプライアンスの準備をする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/14/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: すべての新しい Microsoft 365 セキュリティセンターとコンプライアンスセンターの準備をする
ms.openlocfilehash: cdea0aabec39082ce9da0001cb148fe14454e5b7
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "30639054"
---
# <a name="get-ready-for-the-new-microsoft-365-security-center-and-microsoft-365-compliance-center"></a>新しい Microsoft 365 セキュリティ センターと Microsoft 365 コンプライアンス センターの準備を行う

マイクロソフト**は、すべての新しい[microsoft 365 セキュリティセンター](#microsoft-365-security-center)と[microsoft 365 コンプライアンスセンター](#microsoft-365-compliance-center)を発表することを嬉しくしています。展開は、2019年1月から2019年3月までに開始され**ます。 この記事を読むと、提供される内容、[予想](#what-to-expect)されること、および[必要なライセンスとアクセス許可](#required-licenses-and-permissions)の概要を知ることができます。

## <a name="microsoft-365-security-center"></a>Microsoft 365 セキュリティセンター

新しい Microsoft 365 セキュリティセンターには、id、データ、デバイス、アプリ、およびインフラストラクチャ全体のセキュリティを管理および監視するためのダッシュボードが含まれています。 また、すべての新しい Microsoft セキュリティスコア、新しいデバイス脅威レポート、新しい id 脅威レポート、および Cloud App Security レポートにも簡単にアクセスできます。 

![新しい Microsoft 365 セキュリティセンター](media/m365-security-center.png)

Microsoft 365 セキュリティセンターを初めて使用すると、開始するのに役立つ情報が画面の上部に表示されます。 また、探索に最も興味のあるセキュリティ機能に簡単に移動する方法についても説明します。

Microsoft 365 セキュリティセンターがテナントに対して有効になると、に[https://security.microsoft.com](https://security.microsoft.com)アクセスできるようになります。 

> [!NOTE]
> Microsoft 365 セキュリティセンターにアクセスするには、有効な Azure Active Directory の役割が割り当てられている必要があります。 詳細については、この記事の「[必要なライセンスとアクセス許可](#required-licenses-and-permissions)」セクションを参照してください。

## <a name="microsoft-365-compliance-center"></a>Microsoft 365 コンプライアンスセンター

新しい microsoft 365 コンプライアンスセンターでは、コンプライアンスの全体的な状況を反映した microsoft コンプライアンスマネージャーを参照できるようになり、複雑な法令遵守の義務を満たすように設定を構成するための推奨措置が提供されます。 秘密度と保持ラベルとポリシー、データ損失防止 (DLP)、データガバナンス、電子情報開示、データ主体要求 (dsrs)、ケース管理、および Cloud App Security に簡単にアクセスできます。 さらに、実践的な洞察を得て、インテリジェントな自動化を活用して、コンプライアンスのリスクを軽減し、デジタルスペースを保護することができます。 

![Microsoft 365 コンプライアンスセンター](media/m365-compliance-center.png)

Microsoft 365 コンプライアンスセンターを初めて使用すると、開始するのに役立つ情報が画面の上部に表示されます。 調査に最も興味のあるコンプライアンス機能に簡単に移動する方法について説明します。

テナントに対して Microsoft 365 コンプライアンスセンターが有効になったら、にアクセスすることが[https://compliance.microsoft.com](https://compliance.microsoft.com)できます。  

> [!NOTE]
> Microsoft 365 コンプライアンスセンターにアクセスするには、有効な Azure Active Directory の役割が割り当てられている必要があります。 詳細については、この記事の「[必要なライセンスとアクセス許可](#required-licenses-and-permissions)」セクションを参照してください。

## <a name="what-to-expect"></a>期待されること

### <a name="coming-soon"></a>準備中です。

新しい microsoft 365 セキュリティセンターと新しい microsoft 365 コンプライアンスセンターは、1月から年3月までの初期段階では展開されていません。 この期間内に、新しい microsoft 365 セキュリティセンターおよび microsoft 365 コンプライアンスセンターにアクセスできる必要があります。

### <a name="easy-access"></a>簡単なアクセス

向上したナビゲーション、統合されたソリューション、および合理化された操作性により、最も関心のある情報を表示してアクセスし、Microsoft 365 の強力なセキュリティおよびコンプライアンスソリューションを利用できるようになります。

### <a name="smooth-transition"></a>滑らかな移行

新しいセンターへのスムーズな移行を期待できます。 この変更が完全に展開された後、以前の Microsoft 365 Security & コンプライアンスセンター ([https://protection.microsoft.com](https://protection.microsoft.com)) を廃止する予定です。 管理者の環境は変更されますが、現在のセキュリティとコンプライアンスの構成に影響はありません。

この更新プログラムが展開された後、組織に Microsoft 365 Enterprise E3 または E5 がある場合、セキュリティ/コンプライアンス管理者は次のことを行うことができます。

- に[https://security.microsoft.com](https://security.microsoft.com)直接移動し[https://compliance.microsoft.com](https://compliance.microsoft.com)ます。 <br>または  
- microsoft 365 管理センターに移動し、新しい microsoft 365 セキュリティセンターと microsoft 365 コンプライアンスセンター (左側のナビゲーションウィンドウの [管理センター] の下にあるリンク) に移動します。

> [!TIP]
> office 365 security & コンプライアンスセンター ([https://protection.office.com](http://protection.office.com)) を使用している場合でも、既存の office 365 security & コンプライアンスセンター内で office 365 の設定を構成および管理することはできます。 構成は、既存の Office 365 security & コンプライアンスセンターに加えて、新しい microsoft 365 セキュリティセンターおよび microsoft 365 コンプライアンスセンターにも保持されます。  

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

### <a name="licenses"></a>ライセンス

新しい microsoft 365 セキュリティセンターと microsoft 365 コンプライアンスセンターを入手するには、組織に microsoft 365 E3 または e5 へのサブスクリプション、または (Office 365 Enterprise E3 または e5、enterprise Mobility + security で構成された) ボリュームライセンスが必要です。E3 または E5、Windows 10 Enterprise E3/E5。 これらのプランの詳細については、「 [Microsoft が適切な Microsoft 365 Enterprise ソリューションを見つける](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)」を参照してください。

### <a name="roles-and-permissions"></a>ロールと権限

新しい Microsoft 365 セキュリティセンターまたは microsoft 365 コンプライアンスセンターにアクセスするには、ユーザーに Azure Active Directory のグローバル管理者、コンプライアンス管理者、セキュリティ管理者、またはセキュリティリーダーの役割が割り当てられている必要があります。

- グローバル管理者はセキュリティセンターとコンプライアンスセンターの両方にアクセスできます。

- コンプライアンスセンターにアクセスできるコンプライアンス管理者

- セキュリティ管理者またはセキュリティ閲覧者は、セキュリティセンターにアクセスできます。

> [!NOTE]
> セキュリティオペレーターおよびコンプライアンスデータ管理者を含む追加の役割が近日中に公開されています。

次の表では、Azure、Office 365、および Windows でさまざまなポータルにアクセスできるユーザーを要約しています。

|向け  |Global<br/>管理者  |セキュリティ <br/>管理者<br>または<br>セキュリティ<br>Reader |コンプライアンス<br/>管理者  |
|---------|---------|---------|---------|
|[Office 365 Security & コンプライアンスセンター](https://protection.office.com) |はい |はい  |はい |
|[Microsoft 365 セキュリティセンター](https://security.microsoft.com) |はい  | はい  | いいえ        |
|[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com) | はい | いいえ | あり |
|[コンプライアンス マネージャー](https://aka.ms/compliancemanager) |はい | はい |はい  |
|[Azure Information Protection](https://docs.microsoft.com/azure/information-protection) |はい |はい |いいえ |
|[Azure Security Center](https://docs.microsoft.com/azure/security-center/)  |はい |はい |いいえ |
|[Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)  |はい |はい |いいえ |
|[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection?ocid=tia-260153000#windows-defender-atp) |はい |はい |いいえ |
|[id 保護](https://docs.microsoft.com/azure/active-directory/identity-protection)     |はい |はい |いいえ |
|[Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management)     |はい |はい |いいえ |
|[Intune](https://docs.microsoft.com/intune)     |はい |はい |はい |
|[Cloud App Security](https://docs.microsoft.com/cloud-app-security/)     |はい |はい |はい |
|[セキュリティ スコア](https://docs.microsoft.com/office365/securitycompliance/office-365-secure-score)     |はい |はい |いいえ |
|[Exchange](https://docs.microsoft.com/exchange/)     |はい |はい |はい |

## <a name="additional-resources"></a>その他のリソース

[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)

