---
title: Office 365 アプリ用のアプリの条件付きアクセス制御を展開する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 次の手順に従って、office 365 Cloud App Security Conditional Access App Control によって制御されるように Azure AD Office 365 アプリを構成します。
ms.openlocfilehash: 72be95b3213b90cfe60d851d0852d465cdbe6ef9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263113"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a>Office 365 アプリ用のアプリの条件付きアクセス制御を展開する

|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](ocas-session-policies.md) <br/> |[利用を開始する](utilization-activities-for-ocas.md) <br/> |

次の手順に従って、office 365 Cloud App Security Conditional Access App Control によって制御されるように Azure AD Office 365 アプリを構成します。

**手順 1: [Azure AD 条件付きアクセステストポリシーを作成する](#step-1-create-an-azure-ad-conditional-access-test-policy)**

**手順 2: [アプリのポリシーをスコープとするユーザーを使用してサインイン](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)する**

**手順 3: Azure AD で組み込みの Cloud app Security ポリシーを選択しなかった場合、またはこのポリシーを非おすすめアプリに適用する場合は、 [cloud app security ポータルで高度なコントロールを構成](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)します。**

**手順 4:[展開をテストする](#step-4-test-the-deployment)**

> [!IMPORTANT]
> office 365 アプリ用の条件付きアクセスアプリコントロールを展開するには、office 365 Cloud App Security license に加えて、 [Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) の有効なライセンスが必要です。

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a>手順 1: Azure AD 条件付きアクセステストポリシーを作成する 

1. Azure Active Directory の [ **セキュリティ**] で、[ **条件付きアクセス**] をクリックします。

2. [ **新しいポリシー** ] をクリックし、新しいポリシーを作成します。

3. テストポリシーの [ **ユーザー**] で、初期サインオンと検証に使用できるテストユーザーまたはユーザーを割り当てます。

4. テストポリシーの [ **クラウドアプリ**] で、制御するアプリを条件付きアクセスアプリコントロールで割り当てます。

5. [ **セッション**] で、組み込みのポリシーのいずれかを使用するようにポリシーを設定するか、 **ダウンロード** **のみ** を監視します。 または、[ **カスタムポリシー** を使用する] を選択して、Cloud App Security ポータルで高度なポリシーを設定します。

6. 適用可能な **条件の割り当て** を追加するか、 **コントロール** を付与します (省略可能)。

> ![Azure AD 条件付きアクセス](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a>手順 2: アプリのポリシーをスコープとするユーザーを使用してサインインする 

ポリシーを作成したら、そのポリシーで構成されている各アプリにサインインします。 ポリシーに構成されたユーザーを使用してサインインしていることを確認してください。 最初に既存のセッションからサインアウトしてください。

Cloud App Security は、ログインする新しいアプリごとに、ポリシーの詳細をサーバーに同期します。 これには最大1分かかる場合があります。

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a>手順 3: Cloud App Security ポータルで高度なコントロールを構成する 

上記の手順により、おすすめのアプリの組み込みの Cloud App Security policy を Azure AD に直接作成することができました。

高度なポリシーを構成するには、Office 365 Cloud App Security ポータルで [アクセスポリシー](ocas-access-policies.md) または [セッションポリシー](ocas-session-policies.md) を作成します。

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a>クライアント証明書を使用してデバイスを識別する (オプション):

1. [設定] cog に移動し、[ **デバイス id**] を選択します。

2. 1つ以上のルートまたは中間証明書をアップロードします。

3. 証明書がアップロードされたら、 **デバイスタグ**と **有効なクライアント証明書**に基づいてアクセスポリシーとセッションポリシーを作成できます。

![条件付きアクセスアプリコントロールデバイス ID](media/image2.png)

> [!NOTE]
> 証明書は、セッションが有効なクライアント証明書フィルターを使用するポリシーと一致する場合にのみ、ユーザーから要求されます。
> 
## <a name="step-4-test-the-deployment"></a>手順 4: 展開をテストする 

1. 既存のセッションを最初にサインアウトします。 次に、正常に展開された各アプリにサインインします。 Azure AD で構成されているポリシーに一致するユーザーを使用してサインインします。

2. Cloud app Security portal で、[ **調査**] の [ **アクティビティログ**] を選択し、アプリごとにログインアクティビティがキャプチャされていることを確認します。

3. [ **詳細設定**] をクリックしてフィルター処理し、Source を使用してフィルター処理するには、 **アクセス制御**を使用します。

4. 管理対象および管理されていないデバイスからモバイルアプリおよびデスクトップアプリにサインインすることをお勧めします。 これは、アクティビティがアクティビティログに適切にキャプチャされることを確認するためのものです。 アクティビティが適切にキャプチャされたことを確認するには、アクティビティの引き出しを開くシングルサインオンログオンをクリックします。 デバイスがネイティブクライアント (モバイルアプリまたはデスクトップアプリのいずれか) であるか、またはデバイスが管理されたデバイス (準拠、ドメイン参加、または有効なクライアント証明書) であるかを、 **ユーザーエージェントタグ** が正しく反映していることを確認してください。

> [!NOTE]
> 展開後は、条件付きアクセスアプリのコントロールページからアプリを削除することはできません。 アプリにセッションまたはアクセスポリシーを設定しない限り、条件付きアクセスアプリコントロールはアプリの動作を変更しません。

## <a name="next-steps"></a>次のステップ

- [Office 365 Cloud App Security のセッションポリシーについて](ocas-session-policies.md)

- [Office 365 Cloud App Security のアクセスポリシーについて](ocas-access-policies.md) 

- [IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する](group-your-ip-addresses-in-ocas.md)