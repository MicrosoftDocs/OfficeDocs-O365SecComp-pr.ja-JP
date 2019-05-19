---
title: 'AD RMS による Exchange Online のメールの暗号化 '
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
description: 必要に応じて、社内の Active Directory Rights Management サービス (AD RMS) を使用するように Exchange Online IRM を構成し、組織の要件を満たすようにすることができます。 これは一般的ではありません。 AD RMS を使用するための要件がない場合は、代わりに Office メッセージの暗号化を使用します。
ms.openlocfilehash: f5611ca7efeae0ab60ef90ebf4f8a225ea1332e7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154269"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>AD RMS による Exchange Online のメールの暗号化 

情報漏洩を防止するために、Exchange Online には、電子メール メッセージおよび添付ファイルをオンラインおよびオフラインで保護する Information Rights Management (IRM) 機能が搭載されています。 必要に応じて、社内の Active Directory Rights Management サービス (AD RMS) を使用するように Exchange Online IRM を構成し、組織の要件を満たすようにすることができます。 これは一般的ではありません。 AD RMS を使用するための要件がない場合は、代わりに[Office 365 メッセージの暗号化](ome.md)を使用します。 

IRM 保護は、ユーザーが Microsoft Outlook や Outlook on the web で適用したり、管理者がトランスポート保護ルールや Outlook の保護ルールを使用して適用したりできます。 IRM を使用すると、管理者とユーザーは、電子メールに含まれている機密性の高いデータのアクセス、転送、印刷、コピーをだれに許可するかを管理できるようになります。
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>IRM と Office 365 Message Encryption (OME) および Azure Active Directory が協働する方法に関する変更点

2017 年 9 月以後、組織で Office 365 Message Encryption の新機能をセットアップすると、IRM を Azure Rights Management (Azure RMS) と使用するためのセットアップも行われます。IRM および Azure RMS を別個にセットアップすることはなくなりました。そのセットアップなしで、OME とアクセス権管理がシームレスに協働します。新機能の詳細については、「[Office 365 Message Encryption のよくあるご質問](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)」を参照してください。組織内で OME 新機能を使用する準備ができたら、「[Azure Information Protection の上に構築された Office 365 Message Encryption の新機能をセットアップする](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)」を参照してください。
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>IRM が Exchange Online および Active Directory Rights Management サービスと協働する方法

Exchange Online IRM では、Windows Server 2008 以降の情報保護テクノロジであるオンプレミスの Active Directory Rights Management サービス (AD RMS) が使用されます。IRM 保護を電子メールに適用するには、AD RMS 権利ポリシー テンプレートを電子メール メッセージに適用します。権限はメッセージ自体に添付されているため、オンラインとオフラインの両方、および組織のファイアウォールの内外両方で保護が有効になります。
  
ユーザーは、電子メール メッセージにテンプレートを適用して、メッセージに対する受信者のアクセス許可を制御できます。転送、メッセージからの情報の抽出、メッセージの保存、メッセージの印刷などの操作を制御するには、AD RMS 権利ポリシーをメッセージに適用します。
  
Windows Server 2008 以降を実行している AD RMS サーバーを使用するよう IRM を構成できます。 この AD RMS サーバーは、クラウドベースの組織の AD RMS 権利ポリシー テンプレートを管理するために使用できます。 Outlook では、ユーザーが IRM 保護を送信メッセージに適用できるようにする目的にも AD RMS サーバーが使用されます。 詳細については、「[オンプレミスの AD RMS サーバーを使用するように IRM を構成する](configure-irm-to-use-an-on-premises-ad-rms-server.md)」を参照してください。 
  
有効になっていれば、次のように、IRM 保護をメッセージに適用できます。
  
- **ユーザーが Outlook と Outlook on the web を使用して手動でテンプレートを適用する** ユーザーは、 **[アクセス許可の設定]** リストからテンプレートを選択して、AD RMS 権利ポリシー テンプレートを電子メール メッセージに適用できます。ユーザーが IRM 保護メッセージを送信するときは、サポートされている形式を使用している添付ファイルもメッセージと同じ IRM 保護の対象となります。IRM 保護は、Word、Excel、PowerPoint に関連付けられたファイルだけでなく, .xps ファイルや添付された電子メール メッセージにも適用されます。 
    
- **管理者がトランスポート保護ルールを使用して Outlook と Outlook on the web の両方に IRM 保護を自動的に適用する** 管理者は、メッセージを IRM で保護するためのトランスポート保護ルールを作成できます。ルール条件を満たすメッセージに AD RMS 権利ポリシー テンプレートを適用するように、トランスポート保護ルールの処理を構成します。IRM を有効にすると、 **メッセージに権利保護を適用する**というトランスポート保護ルールの処理で組織の AD RMS 権利ポリシー テンプレートを使用できるようになります。
    
- **管理者が Outlook 保護ルールを作成する** Outlook 保護ルールは、送信者の部署、メッセージの送信先、受信者が組織内か組織外かなどのメッセージの条件に基づいて、IRM 保護を Outlook 2010 (Outlook on the web ではない) のメッセージに自動的に適用します。詳細については、「 [Create an Outlook Protection Rule](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx)」を参照してください。
    

