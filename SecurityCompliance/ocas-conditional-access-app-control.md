---
title: Office 365 Cloud App Security アプリの条件付きアクセス制御を使用してアプリを保護する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Office 365 Cloud App Security Conditional Access App Control を使用してリアルタイムで違反とリークを阻止します。
ms.openlocfilehash: d8370b1e02866db8f92ab7f6a46b06ddc3ed1055
ms.sourcegitcommit: 866d8cab6bcfdd124516a8369e47ec797bc7cf8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312104"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a>Office 365 Cloud App Security アプリの条件付きアクセス制御を使用してアプリを保護する

|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](ocas-deploy-conditional-access-app-control.md) <br/> |[利用を開始する](utilization-activities-for-ocas.md) <br/> |

今日の workplace では、多くの場合、実際のクラウド環境で何が起こっているかを知るのに十分ではありません。 従業員が意図的に、または誤ってデータや組織をリスクにさらされる前に、リアルタイムで違反とリークを阻止する必要があります。 組織内のユーザーがクラウドアプリでこれらのサービスとツールを利用できるようにして、自分のデバイスが動作するようにすることが重要です。 同時に、データ漏洩から、リアルタイムでデータの盗難から組織を保護するためのツールが必要です。 Azure Active Directory と共に、Office 365 Cloud app Security は、これらの機能を条件付きアクセスアプリコントロールを使用した総合的かつ統合された環境で提供します。

> [!IMPORTANT]
> Cloud app security Conditional Access App Control を使用するには、 [Azure active Directory P1 ライセンス](https://azure.microsoft.com/pricing/details/active-directory/) と、アクティブな[Office 365 Cloud App Security](office-365-cas-overview.md)サブスクリプションが必要です。

## <a name="how-it-works"></a>しくみ

条件付きアクセスアプリコントロールはリバースプロキシアーキテクチャを使用し、Azure AD 条件付きアクセスと一意に統合されています。 Azure AD 条件付きアクセスを使用すると、特定の条件に基づいて組織のアプリにアクセス制御を適用することができます。 条件は、 ** (ユーザーまたはユーザー ** のグループ) と、条件付きアクセスポリシーが適用される *場所* (場所とネットワーク) を定義します。 条件を決定した後、ユーザーを Office 365 Cloud app Security にルーティングすることができます。これには、access および session control を適用することによって、条件付きアクセスアプリを使用してデータを保護できます。

Conditional access App Control アクセスおよびセッションポリシーに基づいて、ユーザーのアプリのアクセスとセッションをリアルタイムで監視および制御することができます。 アクセスポリシーとセッションポリシーは、Cloud App Security ポータル内で使用され、フィルターをさらに絞り込み、ユーザーに対してアクションを実行するように設定します。 アクセスポリシーとセッションポリシーを使用すると、次のことができます。

- **ダウンロード時にブロック**する: 機密ドキュメントのダウンロードをブロックすることができます。 たとえば、管理されていないデバイスの場合です。

- **ダウンロード時の保護**: 機密ドキュメントのダウンロードをブロックする代わりに、ダウンロード時に暗号化によってドキュメントを保護するよう要求することができます。 この暗号化によって、信頼されていないデバイスにデータがダウンロードされた場合に、ドキュメントが保護され、ユーザーアクセスが認証されます。

- **低信頼ユーザーセッションを監視**する: アプリケーションがアプリにサインインするときに、危険性のあるユーザーが監視され、その操作がセッション内からログに記録されます。 ユーザーの行動を調査および分析して、状況を把握することができます。また、どのような状況でも、今後はセッションポリシーを適用する必要があります。

- **アクセスをブロック**する: 非管理対象デバイスまたは企業以外のネットワークから、特定のアプリへのアクセスを完全にブロックすることができます。

- **読み取り専用モードの作成**: アプリ内のカスタムアクティビティを監視およびブロックすることで、特定のユーザー用の特定のアプリに対して読み取り専用モードを作成できます。

- **ユーザーセッションを企業以外のネットワークから制限**する: 企業ネットワークの一部でない場所から保護されたアプリにアクセスするユーザーには、制限付きアクセスが許可されます。 機密マテリアルのダウンロードは、ブロックまたは保護されます。

### <a name="how-session-control-works"></a>セッションコントロールのしくみ

条件付きアクセスアプリコントロールを使用してセッションポリシーを作成すると、ユーザーをアプリに直接ではなくリバースプロキシ経由でリダイレクトすることによって、ユーザーセッションを制御できます。 その後、ユーザーの要求と応答は、アプリに直接ではなく、Office 365 Cloud App Security を経由して行われます。

ユーザーをセッション内に保持するには、アプリセッション内の関連するすべての url、Java スクリプト、および cookie が Office 365 Cloud app Security url に置き換えられます。 たとえば、アプリが myapp.com で終わるドメインのリンクを持つページを返した場合、リンクは次のようなドメインに置き換えられます。 myapp.com.us.cas.ms

この方法では、デバイスに何もインストールする必要はありません。 この方法は、管理されていないデバイスからセッションを監視する場合に最適です。

Office 365 Cloud App Security を介してセッションが指示されたら、次の操作を実行できます。

1. ユーザーアクティビティのトラフィックを検査する

2. Office 365 Cloud App Security Activity log で、識別されたアクティビティを表示する

3. トラフィックログを保存して分析する

4. 管理者がトラフィックログをエクスポートできるようにする

5. セッションにポリシーを適用する

## <a name="managed-device-identification"></a>管理対象デバイスの識別

Conditional Access App Control デバイスが管理されているかどうかを考慮したポリシーを作成できます。 デバイスが管理されているかどうかを確認するには、次の機能を使用します。

- 準拠しているデバイス

- ドメインに参加しているデバイス

- クライアント証明書の展開

### <a name="compliant-and-domain-joined-devices"></a>準拠しているデバイスとドメインに参加しているデバイス

Azure AD 条件付きアクセスを使用すると、準拠し、ドメインに参加しているデバイス情報を Office 365 Cloud App Security に直接渡すことができます。 そこから、デバイス状態をフィルターとして使用するアクセスポリシーまたはセッションポリシーを開発できます。 詳細については、「 [Azure Active Directory でのデバイス管理の概要](https://docs.microsoft.com/azure/active-directory/device-management-introduction)」を参照してください。

### <a name="client-certificate-authenticated-devices"></a>クライアント証明書の認証済みデバイス

デバイス識別メカニズムは、クライアント証明書を使用して、関連するデバイスからの認証を要求できます。 組織に既に展開されている既存のクライアント証明書を使用するか、新しいクライアント証明書を管理対象デバイスにロールアウトすることができます。 その証明書の存在を使用して、アクセスおよびセッションポリシーを設定します。 クライアント証明書を展開する方法については、「 [deploy Conditional Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md)」を参照してください。

## <a name="supported-apps-and-clients"></a>サポートされるアプリとクライアント

Office 365 の条件付きアクセスアプリコントロールは、次のおすすめアプリをサポートしています。

- Exchange Online (プレビュー)

- OneDrive for business (プレビュー)

- Power BI (プレビュー)

- SharePoint Online (プレビュー)

- Microsoft Teams (プレビュー)

- Yammer (プレビュー)

その他のアプリは、継続的に boarded control に送られます。

## <a name="next-steps"></a>次のステップ

- [Office 365 アプリ用のアプリの条件付きアクセス制御を展開する](ocas-deploy-conditional-access-app-control.md)

- [Office 365 Cloud App Security のセッションポリシーについて](ocas-session-policies.md)

- [Office 365 Cloud App Security のアクセスポリシーについて](ocas-access-policies.md) 