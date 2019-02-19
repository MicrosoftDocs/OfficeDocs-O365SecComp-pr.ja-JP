---
title: Office 365 の ATP のフィッシング詐欺対策機能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP のフィッシング対策は、Office 365 Advanced Threat Protection の一部です。ATP のフィッシング対策は、一連の機械学習モデルを受信メッセージに適用して、市販およびスピアーフィッシング攻撃に対する保護を提供します。すべてのメッセージは、フィッシングメッセージを検出するために訓練された広範な一連の機械学習モデルと共に、さまざまなユーザーおよびドメイン偽装攻撃から保護するための一連の高度なアルゴリズムと共に適用されます。
ms.openlocfilehash: 3cd786de403bd2fe4fcdd5d53f3f825c6e4e8a40
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2019
ms.locfileid: "29889250"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Office 365 の ATP のフィッシング詐欺対策機能

ATP のフィッシング対策は、 [Office 365 Advanced Threat Protection](office-365-atp.md)の一部です。ATP のフィッシング対策は、一連の機械学習モデルを受信メッセージに適用して、市販およびスピアーフィッシング攻撃に対する保護を提供します。すべてのメッセージは、フィッシングメッセージを検出するために訓練された広範な一連の機械学習モデルと共に、さまざまなユーザーおよびドメイン偽装攻撃から保護するための一連の高度なアルゴリズムと共に適用されます。ATP のフィッシング対策は、Office 365 グローバルまたはセキュリティ管理者によって設定されたポリシーに従って組織を保護します。
  
詳細については、「 [Office 365 でフィッシング対策ポリシーをセットアップ](set-up-anti-phishing-policies.md)する」を参照してください。
  
> [!NOTE]
> ATP のフィッシング対策は、Advanced Threat Protection でのみ利用できます。これは、 [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 Enterprise E5、office 365 エデュケーション A5 などのサブスクリプションに含まれています。office 365 atp を含まない office 365 サブスクリプションが組織にある場合は、atp をアドオンとして購入する可能性があります。詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。

## <a name="how-atp-anti-phishing-works"></a>ATP のフィッシング対策のしくみ

ATP のフィッシング対策は、メッセージがフィッシングである可能性があることを示すインジケーターの受信メッセージをチェックします。ユーザーが ATP ポリシー (「安全な添付ファイル」、「安全なリンク」、または「フィッシング詐欺対策」) に該当する場合、受信メッセージは、メッセージを分析する複数のマシン学習モデルによって評価され、ポリシーがメッセージに適用されているかどうかを判断し、適切なアクションを実行します。構成済みのポリシーに基づいて実行されます。
  
ATP のフィッシング対策では、Office 365 の全体管理者またはセキュリティ管理者が、ユーザーまたはドメインの偽装を含むフィッシング攻撃に対する保護を提供するポリシーを定義できます。(または両方)。Office 365 全体管理者またはセキュリティ管理者は、ユーザーまたはドメインの固定リストまたはメールボックスインテリジェンスを使用して、偽装攻撃から保護する必要があるユーザーとドメインをポリシー内で定義します。メールボックスインテリジェンスは、ユーザーのメール習慣と個人用連絡先を高度に理解しています。ATP は、個々のユーザーが組織の内部および外部の他のユーザーと通信し、これらの関係のマップを構築する方法を学習します。このマップを使用すると、適切なメッセージを偽装として識別する方法の詳細を ATP で理解できます。
  
ATP のフィッシング対策ポリシーは、組織内の特定のユーザーまたはグループ、またはドメイン全体またはすべてのカスタムドメインに適用できます。詳細については、「 [Office 365 でフィッシング対策ポリシーをセットアップ](set-up-anti-phishing-policies.md)する」を参照してください。
  
## <a name="how-to-get-atp-anti-phishing"></a>ATP のフィッシング対策を取得する方法

ATP のフィッシング対策機能は、 [Advanced Threat Protection](office-365-atp.md)の一部です。ただし、フィッシング対策ポリシーが定義されている場合は、ATP のフィッシング対策保護が適用されます。(1 つの例は、偽装ベースのポリシーです。)「 [Office 365 でフィッシング対策ポリシーをセットアップ](set-up-anti-phishing-policies.md)する」を参照してください。
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>ATP のフィッシング対策が実施されているかどうかを確認する方法

保護を有効にするためには、ATP のフィッシング対策ポリシーを定義する必要があります。保護が適切に行われていることを確認するために、最初に確認してください。

さらに、組織に対してサービスがどのように機能しているかを示すレポートを使用できます。詳細については、「 [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md)」を参照してください。

特定のユーザーに対して、atp のフィッシング対策のコンピューターの学習モデルをアクティブにするには、定義済みの[atp の安全な添付ファイル](atp-safe-attachments.md)、 [atp の安全なリンク](atp-safe-links.md)、または atp のフィッシング対策ポリシーの一部である必要があります。 

次の表に、いくつかのシナリオの例を示します。これらの各例では、組織は Office 365 Enterprise E5 を使用しています。これには Advanced Threat Protection が含まれています。
  
|**シナリオ例**|**この場合、ATP のフィッシング対策が適用されますか。**|
|:-----|:-----|
|Pat の組織には Office 365 Enterprise E5 がありますが、atp の安全な添付ファイル、atp の安全なリンク、または atp の高度なフィッシングのポリシーは定義されていません。|違います。この機能は使用できますが、atp コンピューターの学習モデルを動作させるには、少なくとも1つの atp ポリシーを定義する必要があります。偽装の場合は、ATP のフィッシング対策ポリシーも設定する必要があります。|
|Lee は、Contoso 社の販売部門の従業員です。Lee の組織には、財務の従業員のみに適用される ATP のフィッシング対策ポリシーがあります。|違います。この場合、ATP のフィッシング対策 (コンピューターモデルと偽装保護) は財務担当従業員に適用されますが、販売部門を含むその他の従業員になることはありません。|
|昨日、田中の組織の Office 365 管理者は、すべての従業員に適用される ATP のフィッシング対策ポリシーを設定します。今日以前は、田中は、ポリシーによってカバーされる偽装を含む電子メールメッセージを受信しました。|うん。この例では、田中に Advanced Threat Protection のライセンスがあり、田中を含む ATP のフィッシング対策ポリシーが定義されています。通常、新しいポリシーがデータセンター間で有効になるまでには約30分かかります。このケースでは、1日以上経過しているため、ポリシーが有効になっている必要があります。|

## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Office 365 でのフィッシング対策保護](anti-phishing-protection.md)
  
[Office 365 でフィッシング対策ポリシーを設定する](set-up-anti-phishing-policies.md)
  
[Office 365 の ATP の安全なリンク](atp-safe-links.md)
  
[Office 365 で ATP の安全なリンクポリシーを設定する](set-up-atp-safe-links-policies.md)
  
[Office 365 での ATP の安全な添付ファイル](atp-safe-attachments.md)
  
[Office 365 で ATP の安全な添付ファイルポリシーを設定する](set-up-atp-safe-attachments-policies.md)
  
[Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)
