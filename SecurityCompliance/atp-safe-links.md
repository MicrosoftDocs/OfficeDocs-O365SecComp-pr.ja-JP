---
title: Office 365 ATP の安全なリンク
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: '[安全なリンク] 機能を使用すると、Office ドキュメントや電子メールメッセージ内のハイパーリンクの時間を確認できます。 安全なリンクを使用して、フィッシングやその他の攻撃から組織を保護します。'
ms.openlocfilehash: 1be7db8ad96a5fd0b46500288e674946e763385a
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652530"
---
# <a name="office-365-atp-safe-links"></a>Office 365 ATP の安全なリンク

## <a name="overview-of-office-365-atp-safe-links"></a>Office 365 の ATP の安全なリンクの概要

> [!IMPORTANT]
> この記事は、 [Office 365 Advanced Threat Protection](office-365-atp.md)を使用しているビジネスのお客様を対象としています。 Outlook.com、Office 365 Home、または Office 365 Personal を使用していて、Outlook での安全なリンクに関する情報をお探しの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

Office 365 の ATP の安全なリンク ( [Advanced Threat Protection](office-365-atp.md)の一部) は、[電子メールメッセージ](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email)や[Office ドキュメント](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents)内の web アドレス (url) の確認時間を提供することにより、組織を保護するのに役立ちます。 保護は、Office 365 セキュリティチームによって設定された[ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)によって定義されます。
  
ATP の安全なリンクポリシーが確立されると、Office 365 のグローバル管理者、セキュリティ管理者、およびセキュリティ閲覧者は、 [Advanced Threat Protection のレポートを表示](view-reports-for-atp.md)できるようになります。 これらのレポートの情報は、セキュリティチームが組織を保護したり、セキュリティインシデントを研究したりするために、さらに手順を実行するのに役立ちます。

[新機能が atp に追加される](office-365-atp.md#new-features-in-office-365-atp)と、Office 365 セキュリティチームは、組織の Atp の[安全なリンクポリシー](set-up-atp-safe-links-policies.md)を追加または編集することができます。 また、新しく改訂された[警告ページ](atp-safe-links-warning-pages.md)や、Outlook でのネイティブリンクのレンダリングなどの変更と改善が見られることがあります。
         
## <a name="how-to-get-atp-safe-links-protection"></a>ATP の安全なリンク保護を取得する方法

**最初に、サブスクリプションに[Advanced Threat Protection](office-365-atp.md)が含まれていることを確認**します。 ATP は、 [microsoft 365 enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 Enterprise E5、office 365 エデュケーション A5 などのサブスクリプションに含まれています。Office 365 ATP を含まない Office 365 サブスクリプションが組織にある場合は、ATP をアドオンとして購入する可能性があります。 詳細については、以下を参照してください。 

- [Office 365 Advanced Threat Protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)

- [Office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
**次に、ATP の安全なリンクポリシーが定義**されていることを確認します。 (「 [Office 365 ATP 安全リンクポリシーを](set-up-atp-safe-links-policies.md)セットアップする」を参照してください)。ATP の安全なリンク機能は、次の場合にアクティブになります。
  
- ATP の安全なリンクポリシーは、電子メールと Office ドキュメント用に設定されています。 (「 [Office 365 で ATP の安全なリンクポリシーを設定](set-up-atp-safe-links-policies.md)する」を参照してください)。

- Office 365 クライアントアプリは、先進認証を使用するように構成されています (これは、Office ドキュメントの ATP の安全なリンク保護のためです)。 (「 [Office 2016 のモダン認証」を](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)参照してください)。 
    
- ユーザーが職場または学校のアカウントを使用して Office 365 にサインインしている。 (「 [Office または office 365 へのサインイン」を](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)参照してください)。
    
- 組織の電子メールは、Exchange Online Protection を通過します。  

**また、必要なアクセス許可があることを確認して**ください。 ATP ポリシーを定義 (または編集) するには、適切な役割が割り当てられている必要があります。 次の表では、いくつかの例について説明します。

|役割  |参照先/割り当て方法  |
|---------|---------|
|Office 365 グローバル管理者 |Office 365 の購入へのサインアップをする場合、既定ではグローバル管理者になります。詳細については、「[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。         |
|セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照してください) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>ATP の安全なリンク保護が適切であることを確認する方法

全体管理者またはセキュリティ管理者として、 [ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)を定期的に確認してください。 ATP の安全なリンクポリシーは、保護を電子メールメッセージのみのハイパーリンクに適用するか、Office ドキュメント内の Url にも適用するかを決定します。

ATP 安全なリンクポリシーが確立されると、組織のセキュリティチームは、 [Advanced Threat protection のレポートを表示](view-reports-for-atp.md)することによって、組織のために Atp の安全なリンク保護がどのように機能しているかを確認できます。 

## <a name="example-scenarios"></a>シナリオ例
  
次の表では、ATP の安全なリンク保護が適用される可能性がある、または導入されていない可能性があるシナリオの例を示します。 (これらすべての場合において、組織に Office 365 Enterprise E5 があると想定しています)。
  
|**シナリオ例**|**この場合、ATP の安全なリンク保護が適用されますか。**|
|:-----|:-----|
|田中は、電子メールおよび Office ドキュメント内の Url を対象とする、ATP の安全なリンクポリシーを持つグループのメンバーです。 田中は、他のユーザーが送信した PowerPoint プレゼンテーションを開き、プレゼンテーション内の URL をクリックします。  <br/> |はい。 定義されている ATP の安全なリンクポリシーは、田中のグループ、田中の電子メール、および Word、Excel、PowerPoint、または Visio ドキュメントに適用されるため、田中がサインインして、Windows、iOS、または Android デバイス上で Office 365 ProPlus を使用している場合に限ります。  <br/> |
|Chris の組織では、グローバルまたはセキュリティ管理者がまだ ATP の安全なリンクポリシーを定義していません。 Chris は、悪意のある web サイトへの URL を含む電子メールを受信します。 Chris は、URL が悪意があることを認識しないので、リンクをクリックします。  <br/> |いいえ。 組織内のすべてのユーザーの Url を対象とする既定のポリシーは、保護を確立するために定義する必要があります。  <br/> |
|Pat の組織では、グローバルまたはセキュリティ管理者は、まだ ATP の安全なリンクポリシーを定義または編集していません。 [Pat] Word 文書を開き、ファイル内の URL をクリックします。  <br/> |いいえ。 Office ドキュメントを含むポリシーは、保護を確立するために定義する必要があります。 「 [Set UP ATP Safe Links policies In Office 365」を](set-up-atp-safe-links-policies.md)参照してください。  <br/> |
|Lee の組織には、ブロック`http://tailspintoys.com`された web サイトとしてリストされている、ATP の安全なリンクポリシーがあります。 Lee は、の URL が含まれる電子メール`http://tailspintoys.com/aboutus/trythispage`メッセージを受信します。 Lee が URL をクリックします。  <br/> |これは、サイト全体とそのすべてのサブページがブロックする Url の一覧に含まれているかどうかによって決まります。 「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-wtih-atp.md)」を参照してください。  <br/> |
|田中の仕事仲間は、電子メールが悪意のある URL を含んでいることを知らずに、田中に電子メールを送信します。  <br/> |これは、組織内で送信される電子メールに ATP の安全なリンクポリシーが定義されているかどうかによって決まります。 「 [Set UP ATP Safe Links policies In Office 365」を](set-up-atp-safe-links-policies.md)参照してください。  <br/> |


  

