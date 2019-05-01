---
title: Office 365 の高度なメッセージの暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: office 365 の高度なメッセージ暗号化では、管理者が office 365 web ポータルを使用して暗号化された電子メールにアクセスを期限切れにし、取り消すことができるようになります。
ms.openlocfilehash: a775803a8d2678441f319c0145e96e7d19c26f7e
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506727"
---
# <a name="office-365-advanced-message-encryption"></a>Office 365 の高度なメッセージの暗号化

office 365 の高度なメッセージの暗号化は、特定のサブスクリプションの office 365 メッセージの暗号化の上で使用できます。 高度なメッセージ暗号化は、 [Microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、office 365 Enterprise e5、および Office 365 エデュケーション A5 に含まれています。 office 365 advanced message encryption を含まない office 365 サブスクリプションが組織にある場合は、advanced コンプライアンス SKU の E5 コンプライアンスを使用して、高度なメッセージ暗号化をアドオンとして購入できます。

この記事は、 [Office 365 メッセージの暗号化](ome.md)についてのより大きな一連の記事の一部です。

Office 365 の高度なメッセージ暗号化を使用すると、お客様は、外部の受信者により柔軟な制御と暗号化された電子メールへのアクセスを必要とするコンプライアンス義務を満たすことができます。 Office 365 の高度なメッセージ暗号化を使用すると、自動ポリシーにより、組織の外部で共有される機密メールを制御することができます。 これらのポリシーは、PII、財務、健康 id などの機密情報の種類を識別するために構成したり、保護を強化するためにキーワードを使用したりすることができます。 ポリシーを構成したら、ポリシーをカスタムのブランド化された電子メールテンプレートとペアにして、ポリシーに適合するメールの追加の制御の有効期限を追加します。 さらに、管理者は、いつでもメールへのアクセスを取り消すことにより、セキュリティで保護された web ポータルを介して外部からアクセスされる暗号化メールを制御できます。

外部の受信者に送信されたメールの有効期限を設定し、取り消すことはできません。

office 365 Advanced Message Encryption では、カスタムブランドを適用するたびに、office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。 また、有効期限は、カスタムブランド化が使用されている場合にのみ使用できます。 取り消すことができるのは、ポータル経由で受信したメッセージのみです。

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Office 365 Advanced Message Encryption の使用を開始する

次のトピックでは、高度なメッセージ暗号化の設定方法と使用方法について説明します。

組織には、Office 365 Advanced Message Encryption を含むサブスクリプションが必要です。 サポートされているサブスクリプションの詳細については、「[メッセージポリシーとコンプライアンスサービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)」を参照してください。

高度なメッセージ暗号化機能を活用するように設定されていない場合は、新しい Office 365 メッセージ暗号化機能をセットアップします。これにより、外部で共有される暗号化されたメッセージの上位に保護が追加されます。 office 365 メッセージの暗号化がセットアップされていない場合は、「 [office を新しい office 365 メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。

[Office 365 Advanced Message Encryption で暗号化された電子メールの有効期限日を設定](ome-advanced-expiration.md)します。 セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを期限切れにすることによって保護を強化する自動ポリシーを使用して、組織外で共有する機密メールを制御

[Office 365 の高度なメッセージ暗号化によって暗号化された電子メールを取り消し](revoke-ome-encrypted-mail.md)ます。 セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを取り消すことにより、組織の外部で共有される機密メールを制御し、保護を強化します。  