---
title: Office 365 のアクセスポリシー Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: o365-administration
localization_priority: Normal
description: Office 365 cloud App Security アクセスポリシーを使用すると、ユーザー、場所、デバイス、およびアプリに基づいて、クラウドアプリへのアクセスをリアルタイムで監視し、制御することができます。クライアント証明書を管理対象デバイスに展開したり、サードパーティの MDM 証明書などの既存の証明書を使用したりすることによって、ドメインに参加していないデバイスや、Windows Intune によって管理されていないデバイスを含む、任意のデバイスのアクセスポリシーを作成できます。たとえば、クライアント証明書を管理対象デバイスに展開し、証明書を持たないデバイスからのアクセスをブロックすることができます。
ms.openlocfilehash: bb4404793647c65ab8addc148e6efe24242f3079
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2019
ms.locfileid: "30103312"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a>Office 365 のアクセスポリシー Cloud App Security

|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](group-your-ip-addresses-in-ocas.md) <br/> |[利用を開始する](utilization-activities-for-ocas.md) <br/> |

Office 365 cloud App Security アクセスポリシーを使用すると、ユーザー、場所、デバイス、およびアプリに基づいて、クラウドアプリへのアクセスをリアルタイムで監視し、制御することができます。クライアント証明書を管理対象デバイスに展開したり、サードパーティの MDM 証明書などの既存の証明書を使用したりすることによって、ドメインに参加していないデバイスや、Windows Intune によって管理されていないデバイスを含む、任意のデバイスのアクセスポリシーを作成できます。たとえば、クライアント証明書を管理対象デバイスに展開し、証明書を持たないデバイスからのアクセスをブロックすることができます。

セッション [ポリシー](ocas-session-policies.md) を使用して、アクセスを完全に許可またはブロックする代わりに、セッションを監視したり、特定のセッションアクティビティを制限したりすることができます。

## <a name="prerequisites-to-using-access-policies"></a>アクセスポリシーを使用するための前提条件

- Azure AD Premium P1 ライセンス

- 関連するアプリは、 [条件付きアクセスアプリコントロールを使用して展開](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)する必要があります。

- 以下の説明に従って、ユーザーを Office 365 Cloud App Security にリダイレクトする [Azure AD 条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) を設定する必要があります。

## <a name="create-an-azure-ad-conditional-access-policy"></a>Azure AD 条件付きアクセスポリシーを作成する

Azure Active Directory の条件付きアクセスポリシーと Cloud App Security セッションポリシーは、相互に連携して各ユーザーセッションを調べ、各アプリのポリシーを決定します。Azure AD で条件付きアクセスポリシーを設定するには、次の手順を実行します。

1. ユーザーまたはユーザーのグループ、および条件付きアクセスアプリコントロールを使用して制御するアプリの割り当てを使用して、 [Azure AD 条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) を構成します。<br>注:  [条件付きアクセスアプリコントロールを使用](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)して展開されたアプリのみ、このポリシーの影響を受けます。

2.  [ **条件付きアクセスアプリを使用する] コントロール**で [ **セッション**] を選択して、ユーザーを Office 365 Cloud App Security にルーティングします。

## <a name="create-a-cloud-app-security-access-policy"></a>クラウドアプリのセキュリティアクセスポリシーを作成する

新しいアクセスポリシーを作成するには、次の手順を実行します。

1. ポータルで、[ **コントロール** の後に **ポリシー**] を選択します。

2. [ **ポリシー** ] ページで、[ **ポリシー** の作成] をクリックし、[ **アクセスポリシー**] を選択します。

3. [ **アクセスポリシー** ] ウィンドウで、[管理されていない *デバイスからのアクセスをブロック*する] など、ポリシーの名前を割り当てます。

4.   **次のすべての**セクションに一致するアクティビティについては、[ **アクティビティソース**] の下で、ポリシーに適用する追加のアクティビティフィルターを選択します。フィルターには、次のオプションがあります。
    
    - **デバイスタグ**: 管理されていないデバイスを識別するには、このフィルターを使用します。
    
    - **場所**: このフィルターを使用して、不明 (つまり、危険) の場所を特定します。
    
    - **ip アドレス**: このフィルターを使用して、ip アドレスごとにフィルター処理するか、以前に割り当てられた ip アドレスタグを使用します。
    
    - **ユーザーエージェントタグ**: このフィルターを使用して、モバイルアプリとデスクトップアプリを識別するヒューリスティックを有効にします。このフィルターは、等しいまたは等しくないように設定できます。これらの値は、各クラウドアプリのモバイルアプリとデスクトップアプリに対してテストする必要があります。

5. [ **アクション**] で、次のいずれかのオプションを選択します。
    
    - **Allow**: 設定したポリシーフィルターに従って、アクセスを明示的に許可するには、このアクションを設定します。
    
    - **block**: 設定したポリシーフィルターに従ってアクセスを明示的にブロックするには、このアクションを設定します。

6.   **ポリシーの重要度を持つ各一致イベントに対して通知を作成**し、通知制限を設定して、警告を電子メールとして設定するか、またはその両方にするかを選択できます。

## <a name="next-steps"></a>次の手順

- [IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する](group-your-ip-addresses-in-ocas.md)