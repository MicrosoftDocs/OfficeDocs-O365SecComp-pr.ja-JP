---
title: Office 365 Advanced Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 の高度なメッセージ暗号化では、管理者が Office 365 web ポータルを使用して暗号化された電子メールにアクセスを期限切れにし、取り消すことができるようになります。
ms.openlocfilehash: dcef5f861711acffb8359063373cd90d4b122d88
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157651"
---
# <a name="office-365-advanced-message-encryption"></a>Office 365 Advanced Message Encryption

Office 365 の高度なメッセージの暗号化は、特定のサブスクリプションの Office 365 メッセージの暗号化の上で使用できます。 高度なメッセージ暗号化は、 [Microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 Enterprise e5、および Office 365 エデュケーション A5 に含まれています。 Office 365 Advanced Message Encryption を含まない Office 365 サブスクリプションが組織にある場合は、Advanced コンプライアンス SKU の E5 コンプライアンスを使用して、高度なメッセージ暗号化をアドオンとして購入できます。

Office 365 の高度なメッセージ暗号化を使用すると、お客様は、外部の受信者により柔軟な制御と暗号化された電子メールへのアクセスを必要とするコンプライアンス義務を満たすことができます。 Office 365 の高度なメッセージ暗号化を使用すると、自動ポリシーにより、組織の外部で共有される機密メールを制御することができます。 これらのポリシーは、PII、財務、健康 Id などの機密情報の種類を識別するために構成したり、保護を強化するためにキーワードを使用したりすることができます。 ポリシーを構成したら、ポリシーをカスタムのブランド化された電子メールテンプレートとペアにして、ポリシーに適合する電子メールの追加の制御の有効期限を追加します。 また、管理者は、メールへのアクセスをいつでも取り消すことにより、セキュリティで保護された web ポータルを介して外部からアクセスされる暗号化メールを制御することもできます。

外部の受信者に送信される電子メールの有効期限は、失効日と設定のみを行うことができます。

Office 365 の高度なメッセージ暗号化では、カスタムブランド設定テンプレートを適用するたびに、Office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。 メッセージを失効させることができます。また、ユーザーがポータル経由で受信するメッセージに有効期限日を適用することもできます。 つまり、カスタムブランド化テンプレートが適用されている電子メール。

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Office 365 Advanced Message Encryption の使用を開始する

次のトピックでは、高度なメッセージ暗号化の設定方法と使用方法について説明します。

組織には、Office 365 Advanced Message Encryption を含むサブスクリプションが必要です。 サポートされているサブスクリプションの詳細については、「[メッセージポリシーとコンプライアンスサービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)」を参照してください。

Office 365 メッセージの暗号化が既にセットアップされていない場合は、「365 office の新しいメッセージの暗号化機能をセットアップする」を参照してください。

[Office 365 Advanced Message Encryption で暗号化された電子メールの有効期限日を設定](ome-advanced-expiration.md)します。 セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを期限切れにすることによって保護を強化する自動ポリシーを使用して、組織外で共有する機密メールを制御

[Office 365 の高度なメッセージ暗号化によって暗号化された電子メールを取り消し](revoke-ome-encrypted-mail.md)ます。 セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを取り消すことにより、組織の外部で共有される機密メールを制御し、保護を強化します。  