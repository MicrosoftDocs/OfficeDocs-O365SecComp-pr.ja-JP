---
title: 情報の障壁をトラブルシューティングする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: この記事は、情報の障壁をトラブルシューティングするためのガイドとして使用してください。
ms.openlocfilehash: 47549029ffbaa5ead028c18e97850b30f8072011
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230541"
---
# <a name="troubleshooting-information-barriers"></a>情報の障壁をトラブルシューティングする

[情報バリア](information-barriers.md)は、組織が法的な要件や業界の規制に準拠していることを支援します。 たとえば、情報バリアを使用すると、特定のユーザーグループ間の通信を制限して、利息やその他の問題の競合を回避できます。 (情報障壁の設定方法の詳細については、「 [Define policies for information バリア](information-barriers-policies.md)」を参照してください)。

情報の障壁が設定された後に予期しない問題が発生した場合は、それらの問題を解決するために実行できるいくつかの手順があります。 この記事をガイドとして使用します。

> [!IMPORTANT]
> この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。<br/>-Microsoft 365 エンタープライズグローバル管理者<br/>-Office 365 グローバル管理者<br/>-コンプライアンス管理者<br/>-IB コンプライアンス管理 (新しい役割)<p>情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。<p>[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>問題: ユーザーが予期せず Microsoft Teams の他のユーザーとの通信をブロックされている 

この場合、ユーザーは、Microsoft Teams の他のユーザーとの間で予期しない問題を報告しています。 例:
- ユーザーがを検索しましたが、Microsoft Teams の別のユーザーを検索できません。
- ユーザーは、Microsoft Teams の別のユーザーを検索できますが、選択できません。
- ユーザーは別のユーザーを表示できますが、Microsoft Teams 内の他のユーザーにメッセージを送信することはできません。

### <a name="what-to-do"></a>行うこと

ユーザーが情報バリアポリシーの影響を受けているかどうかを判断します。 ポリシーの構成方法によっては、情報の障壁が期待どおりに機能している可能性があります。 または、組織のポリシーを調整する必要がある場合があります。

1. Identity パラメーターを指定して**InformationBarrierRecipientStatus**コマンドレットを使用します。 

    |構文  |例  |
    |---------|---------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p>名前、エイリアス、識別名 (DN)、標準 DN、電子メールアドレス、GUID など、各受信者を一意に識別する任意の id 値を使用できます。     |`Get-InformationBarrierRecipientStatus -Identity meganb` <p>この例では、Identity パラメーターに alias (*meガント b*) を使用しています。 このコマンドレットは、ユーザーが情報バリアポリシーの影響を受けているかどうかを示す情報を返します。 (* ExoPolicyId: \<GUID> を検索します。)         |

    **ユーザーが情報バリアポリシーに含まれていない場合は、サポートにお問い合わせください**。 それ以外の場合は、次の手順に進んでください。

2. 情報バリアポリシーに含まれるセグメントを確認します。 これを行うには、 `Get-InformationBarrierPolicy` Identity パラメーターを指定したコマンドレットを使用します。 

    |構文  |例  |
    |---------|---------|
    |`Get-InformationBarrierPolicy` <p>前の手順で受信したポリシー GUID (ExoPolicyId) などの詳細を identity 値として使用します。     | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p>この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*を持つ情報バリアポリシーに関する詳細情報を取得しています。         |

    コマンドレットを実行した後、結果で**AssignedSegment**、 **SegmentsAllowed**、および**SegmentsBlocked**の値を検索します。

    たとえば、 `Get-InformationBarrierPolicy`コマンドレットを実行した後、結果の一覧で次のように表示されています。

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    この場合、情報バリアポリシーが [営業] および [リサーチ] セグメントにあるユーザーに影響を与えることがわかります。 この場合、営業担当者は研究中の人々とコミュニケーションすることができません。 
    
    これが正しいように思われる場合は、情報バリアが期待どおりに機能しています。 それ以外の場合は、次の手順に進みます。

4. セグメントが正しく定義されていることを確認してください。 これを行うには、 `Get-OrganizationSegment`コマンドレットを使用して、結果の一覧を確認します。 

    |構文  |例  |
    |---------|---------|
    |`Get-OrganizationSegment`<p>このコマンドレットを Identity パラメーターと共に使用します。     |`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p>この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントについての情報を取得しています。         |

    セグメントの詳細を確認します。 必要に応じて、[セグメントを編集](information-barriers-edit-segments-policies.md.md#edit-a-segment)してから、 `Start-InformationBarrierPoliciesApplication`コマンドレットを再度使用します。

    **情報バリアポリシーに問題がある場合は、サポートにお問い合わせください**。

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>問題: Microsoft Teams でブロックする必要があるユーザー間で通信が許可されている

この場合、情報バリアは定義、アクティブ、および適用されますが、相互に通信できないようにする必要があるユーザーは、Microsoft Teams で互いにチャットして通話することができます。

### <a name="what-to-do"></a>行うこと

該当するユーザーが情報バリアポリシーに含まれていることを確認します。 

1. Identity パラメーターを使用して**InformationBarrierRecipientStatus**コマンドレットを使用します。

    |構文  |例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。          |

    
    > [!TIP]
    > 1人のユーザーに対してこのコマンドレットを使用することもできます。`Get-InformationBarrierRecipientStatus -Identity <value>`
    
2. 結果を確認します。 **InformationBarrierRecipientStatus**コマンドレットでは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。 

    結果を確認し、次の表に示すように、次の手順を実行します。
    
    |結果  |次の操作  |
    |---------|---------|
    |選択したユーザーのセグメントが表示されません     |次のいずれかを実行します。<br/>-Azure Active Directory でユーザープロファイルを編集して、ユーザーを既存のセグメントに割り当てます。 (「 [Office 365 PowerShell を使用してユーザーアカウントのプロパティを構成する」を](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)参照してください)。<br/>-[情報バリアに対してサポートされている属性](information-barriers-attributes.md)を使用してセグメントを定義します。 次に、[新しいポリシーを定義](information-barriers-policies.md#part-2-define-information-barrier-policies)するか、[既存のポリシーを編集](information-barriers-edit-segments-policies.md.md#edit-a-policy)してそのセグメントを含めます。  |
    |セグメントは表示されますが、これらのセグメントに情報バリアポリシーが割り当てられていません     |次のいずれかを実行します。<br/>- 対象のセグメントごとに[新しい情報バリアポリシーを定義する](information-barriers-policies.md#part-2-define-information-barrier-policies)<br/>- [既存の情報バリアポリシーを編集](information-barriers-edit-segments-policies.md.md#edit-a-policy)して正しいセグメントに割り当てる         |
    |セグメントがリストされ、それぞれが情報バリアポリシーに含まれています。     |-コマンドレット`Get-InformationBarrierPolicy`を実行して、情報バリアポリシーがアクティブであることを確認します。<br/>- `Get-InformationBarrierPoliciesApplicationStatus`コマンドレットを実行してポリシーが適用されていることを確認する<br/>-すべての`Start-InformationBarrierPoliciesApplication`アクティブ情報バリアポリシーを適用するには、コマンドレットを実行します。          |
    

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>問題: 情報バリアポリシーから1人のユーザーを削除する必要がある

この場合、情報バリアポリシーが有効になっており、1人以上のユーザーが予期せず Microsoft Teams 内の他のユーザーとの通信をブロックされています。 情報バリアポリシーを完全に削除するのではなく、1人または複数の個別のユーザーを情報バリアポリシーから削除することができます。 

### <a name="what-to-do"></a>行うこと

情報バリアポリシーは、ユーザーのセグメントに割り当てられます。 セグメントは、[ユーザーアカウントプロファイルの特定の属性](information-barriers-attributes.md)を使用して定義されます。 単一のユーザーからポリシーを削除する必要がある場合は、そのユーザーのプロファイルを Azure Active Directory で編集することを検討してください。これは、ユーザーが情報障壁の影響を受けるセグメントに含まれなくなったことです。

1. Identity パラメーターを使用して**InformationBarrierRecipientStatus**コマンドレットを使用します。 このコマンドレットは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。

    |構文  |例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`<p>名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。          |
    |`Get-InformationBarrierRecipientStatus -Identity <value>` <p>ユーザーを一意に識別する任意の値 (名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など) を使用できます。|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p>この例では、Office 365: *jeanp*で1つのアカウントを参照します。 |

2. 結果を確認して、情報バリアポリシーが割り当てられているかどうか、およびユーザーが属するセグメントがどれかを確認します。 

3. 情報バリアの影響を受けるセグメントからユーザーを削除するには、 [Azure Active Directory でユーザーのプロファイル情報を更新](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)します。

4. FwdSync が実行されるまで30分間待機します。 または、コマンド`Start-InformationBarrierPoliciesApplication`レットを実行して、すべてのアクティブな情報バリアポリシーを適用します。

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>問題: 情報バリアアプリケーションプロセスで時間がかかりすぎています

**InformationBarrierPoliciesApplication**コマンドレットを実行した後、プロセスが完了するまでに長い時間がかかります。

### <a name="what-to-do"></a>行うこと

Policy application コマンドレットを実行すると、組織内のすべてのアカウントについて、情報バリアポリシーがユーザーごとに適用 (または削除) されることに注意してください。 ユーザー数が多い場合は、処理に時間がかかります。 (一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。

1. 最新のポリシーアプリケーションの状態を確認するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。

    |最新のポリシーアプリケーションを表示するには  |すべてのポリシーアプリケーションの状態を表示するには  |
    |---------|---------|
    |`Get-InformationBarrierPoliciesApplicationStatus`     |`Get-InformationBarrierPoliciesApplicationStatus -All $true`         |


    これにより、ポリシーの適用が完了したか、失敗したか、または進行中であるかに関する情報が表示されます。

2. 前の手順の結果に応じて、次のいずれかの手順を実行します。
  
    |状態  |次の手順  |
    |---------|---------|
    |**未開始**     |**InformationBarrierPoliciesApplication**コマンドレットが実行されてから45分以上経過している場合は、監査ログを調べて、ポリシー定義にエラーがないかどうか、またはアプリケーションが開始されていない理由を確認してください。 |
    |**失敗**     |アプリケーションに障害が発生した場合は、監査ログを確認します。 また、セグメントとポリシーも確認してください。 複数のセグメントに割り当てられているユーザーはいますか? セグメントに複数の poliicy が割り当てられているかどうか。 必要に応じて、[セグメントを編集](information-barriers-edit-segments-policies.md.md#edit-a-segment)するか、または[ポリシーを編集](information-barriers-edit-segments-policies.md.md#edit-a-policy)してから、 **InformationBarrierPoliciesApplication**コマンドレットを再度実行します。  |
    |**処理中**     |アプリケーションがまだ進行中の場合は、完了するのに時間を確保します。 数日経過した場合は、監査ログを収集し、サポートに連絡してください。 |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>問題: 情報バリアポリシーがまったく適用されていない

この例では、セグメントを定義し、情報のバリアポリシーを定義し、それらのポリシーを適用しようとしました。 ただし、 `Get-InformationBarrierPoliciesApplicationStatus`コマンドレットを実行すると、ポリシーアプリケーションが失敗したことを確認できます。

### <a name="what-to-do"></a>行うこと

組織に[Exchange アドレス帳ポリシー](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)が設定されていないことを確認します。 このようなポリシーにより、情報バリアポリシーが適用されなくなります。

1. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) に接続する 

2. [AddressBookPolicy](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/get-addressbookpolicy?view=exchange-ps)コマンドレットを実行し、結果を確認します。

    |結果  |次の手順  |
    |---------|---------|
    |Exchange アドレス帳ポリシーの一覧     |[アドレス帳ポリシーを削除する](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)         |
    |アドレス帳ポリシーが存在しません |ポリシーアプリケーションが失敗している理由を確認するには、監査ログを参照してください。 |

3. [ユーザーアカウント、セグメント、ポリシー、またはポリシーアプリケーションの状態を表示](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)します。

## <a name="related-topics"></a>関連項目

[Microsoft Teams の情報障壁に関するポリシーを定義する](information-barriers-policies.md)

[情報の障壁](information-barriers.md)



