---
title: Office 365 ATP の安全な添付ファイル
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/08/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
description: '[安全な添付ファイル] 機能を使用すると、電子メールの添付ファイルの確認時間を確認できます。安全な添付ファイルを使用して、ユーザーが電子メールで送受信する悪意のあるファイルから組織を保護します。'
ms.openlocfilehash: 25fbfba104694f7f7418fadb88d60b17ea3d1ae6
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357488"
---
# <a name="office-365-atp-safe-attachments"></a>Office 365 ATP の安全な添付ファイル

## <a name="overview-of-office-365-atp-safe-attachments"></a>Office 365 の ATP の安全な添付ファイルの概要

atp の安全な添付ファイル ( [atp の安全なリンク](atp-safe-links.md)と共に) は、 [Office 365 Advanced Threat Protection](office-365-atp.md) (atp) の一部です。ATP の安全な添付ファイル機能は、電子メールの添付ファイルが悪意のあるものがないかどうかを確認し、組織を保護するアクションを実行します。atp の安全な添付ファイル機能は、Office 365 グローバルまたはセキュリティ管理者によって設定された[atp の安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md)に従って組織を保護します。 
  
ATP の保護は、SharePoint Online、OneDrive for business、Microsoft Teams のファイルに拡張することもできます。詳細については、「 [Office 365 Advanced Threat Protection for SharePoint、OneDrive、Microsoft Teams](atp-for-spo-odb-and-teams.md)」を参照してください。

## <a name="how-it-works"></a>しくみ

ATP の安全な添付ファイル機能は、組織内のユーザーの電子メールの添付ファイルを確認します。atp の安全な添付ファイルポリシーが設定されている場合に、そのポリシーの対象となるユーザーが Office 365 で電子メールを表示すると、そのメール添付ファイルがチェックされ、ATP の安全な添付ファイルのポリシーに基づいて適切な操作が実行されます。ポリシーの定義によっては、悪意のあるファイルが送信されたことを知らなくても、ユーザーは作業を続けることができます。
  
次に、作業中の ATP の安全な添付ファイルの2つの例を示します。
  
- **例 1: 電子メールの添付ファイル**Lee が添付ファイル付きの電子メールメッセージを受信するとします。Lee のユーザー資格情報を盗もうとするように設計されたマルウェアが安全か実際に添付されているかは、Lee では明白ではありません。Lee の組織では、セキュリティ管理者が ATP の安全な添付ファイルポリシーを数日前に定義しています。ATP の安全な添付ファイル機能を使用すると、Lee が受信する前に、仮想環境で電子メール添付ファイルが開かれ、テストされます。添付ファイルが悪意があると判断された場合は、自動的に削除されます。添付ファイルが安全な場合は、Lee がクリックしたときに正常に開かれます。

- **例 2: SharePoint Online のファイル**田中がファイルを受信し、SharePoint Online のライブラリにアップロードしたとします。田中は、ファイルが実際に悪意があることを知らずに、そのファイルへのリンクを他のチームと共有します。幸いなことに、 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)は、悪意のあるファイルを検出してブロックしています。数日後に、Chris はドキュメントを開きます。chris はファイルを見ることはできますが、そのファイルを開いたり共有したりすることはできません。

ATP の安全な添付ファイルのスキャンは、Office 365 データが存在する地域と同じ地域で行われます。データセンター地理の詳細については、「[データの保存場所](https://products.office.com/where-is-your-data-located?geo=All)」を参照してください。 

ATP の安全な添付ファイルポリシーは、組織内の特定のユーザーやグループ、またはドメイン全体に適用できます。また、ATP の安全な添付ファイルのポリシーでは、実際の添付ファイルがスキャンされている間は、プレースホルダーの添付ファイルを使用するように構成できます。詳細については、「 **[Office 365 で ATP の安全な添付ファイルのポリシーを設定](set-up-atp-safe-attachments-policies.md)** する」を参照してください。
  
## <a name="how-to-get-atp-safe-attachments"></a>ATP の安全な添付ファイルを取得する方法

最初に、サブスクリプションに[Advanced Threat Protection](office-365-atp.md)が含まれていることを確認します。ATP は、 [microsoft 365 enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 Enterprise E5、office 365 エデュケーション A5 などのサブスクリプションに含まれています。office 365 atp を含まない office 365 サブスクリプションが組織にある場合は、atp をアドオンとして購入する可能性があります。詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。 

次に、ATP の安全な添付ファイルポリシーが定義されていることを確認します。(「 [Office 365 ATP の安全な添付ファイルのポリシーを](set-up-atp-safe-attachments-policies.md)セットアップする」を参照してください)ATP の安全な添付ファイル機能は、次の場合にアクティブになります。
  
- ATP の安全な添付ファイルポリシーはセットアップされています。(「 [Office 365 で ATP の安全な添付ファイルのポリシーを設定](set-up-atp-safe-attachments-policies.md)する」を参照してください)。

- ユーザーが職場または学校のアカウントを使用して Office 365 にサインインしている。(「 [office または office 365 へのサインイン」を](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)参照してください)。

ATP ポリシーを定義 (または編集) するには、適切な役割が割り当てられている必要があります。次の表では、いくつかの例について説明します。

|役割  |参照先/割り当て方法  |
|---------|---------|
|Office 365 グローバル管理者 |Office 365 の購入へのサインアップをする場合、既定ではグローバル管理者になります。詳細については、「[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。         |
|セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照してください) |

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>ATP の安全な添付ファイルの保護が適切かどうかを確認する方法

[ATP の安全な添付ファイルポリシーを定義 (またはレビュー)](set-up-atp-safe-attachments-policies.md)した後、サービスがどのように機能しているかを確認するために、 [Advanced Threat Protection のレポートを表示](view-reports-for-atp.md)することをお勧めします。
  
次の表に、いくつかのシナリオの例を示します。これらのすべての場合において、高度な脅威保護を含む Office 365 サブスクリプションが組織にあると想定しています。
  
|**シナリオ例**|**この場合、ATP の安全な添付ファイルの保護が適用されますか。**|
|:-----|:-----|
|Pat の組織には Office 365 Enterprise E5 がありますが、ATP の安全な添付ファイルのポリシーが定義されていないものがまだあります。  <br/> |違います。この機能は使用できますが、atp の安全な添付ファイルの保護を有効にするためには、少なくとも1つの atp の安全な添付ファイルポリシーを定義する必要があります。  <br/> |
|Lee は、Contoso 社の販売部門の従業員です。Lee の組織には、財務部門の従業員にのみ適用される ATP の安全な添付ファイルポリシーがあります。  <br/> |違います。この場合、財務の従業員は ATP の安全な添付ファイルの保護を行いますが、販売部門を含むその他の従業員は、これらのグループを含むポリシーが定義されるまではありません。  <br/> |
|昨日、田中の組織の Office 365 管理者は、すべての従業員に適用される ATP の安全な添付ファイルポリシーを設定します。今日以前は、田中は添付ファイルを含む電子メールメッセージを受信しました。  <br/> |うん。この例では、田中に Advanced Threat Protection のライセンスがあり、田中を含む ATP の安全な添付ファイルポリシーが定義されています。通常、新しいポリシーがデータセンター間で有効になるまでには約30分かかります。このケースでは、1日以上経過しているため、ポリシーが有効になっている必要があります。  <br/> |
|Chris の組織は、組織内のすべてのユーザーに対して、ATP の安全な添付ファイルポリシーが設定された Office 365 Enterprise E5 を持っています。Chris は添付ファイルを持つ電子メールを受信し、組織外の他のユーザーにメッセージを転送します。  <br/> |ATP の安全な添付ファイルの保護は、Chris が受信するメッセージに対して行われます。受信者の組織が ATP の安全な添付ファイルポリシーを適切に設定している場合は、転送されたメッセージが到着したときに、小川が転送するメッセージはそのポリシーの対象となります。  <br/> |
|森さんの組織には、atp の安全な添付ファイルポリシーが設定されており、 [SharePoint、OneDrive、Microsoft Teams の atp](atp-for-spo-odb-and-teams.md)が有効になっています。久保田さんは、SharePoint Online のすべてのファイルがスキャンされており、開いているか、または安全であることを前提としています。<br/> |ATP の安全な添付ファイルの保護は、定義されているポリシーに従って行われます。ただし、これは、SharePoint Online、OneDrive for business、または Microsoft Teams のすべてのファイルがスキャンされるという意味ではありません。(詳細については、「 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)」を参照してください)。<br/> |

## <a name="submitting-files-for-malware-analysis"></a>マルウェア分析のためのファイルの送信

- Microsoft に分析を求めるファイルを受信した場合は、「[マルウェア分析用のファイルを送信](https://aka.ms/wdsi/submit)する」を参照してください。

- Microsoft に送信する電子メールメッセージ (添付ファイルの有無にかかわらず) を受信した場合は、[レポートメッセージアドイン](enable-the-report-message-add-in.md)を使用します。
