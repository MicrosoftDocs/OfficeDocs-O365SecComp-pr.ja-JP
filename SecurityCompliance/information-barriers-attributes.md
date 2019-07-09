---
title: 情報バリアポリシーの属性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: この記事は、情報バリアポリシーで使用できるさまざまな属性の参照として使用します。
ms.openlocfilehash: 1e2e183da350308a57fa5d627b4867b9b3d30cee
ms.sourcegitcommit: a6f046f1529b0515f4f0e918a19ec83f4138b871
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2019
ms.locfileid: "35587066"
---
# <a name="attributes-for-information-barrier-policies"></a>情報バリアポリシーの属性

Azure Active Directory の特定の属性を使用して、ユーザーをセグメントにすることができます。 セグメントが定義されると、それらのセグメントは情報バリアポリシーのフィルターとして使用できます。 たとえば、部署を使用し**** て、組織内の部署別のユーザーのセグメントを定義することができます (2 つの部署に対して1人の従業員が同時に働くことは想定されていません)。 

この記事では、情報バリアで属性を使用する方法について説明し、使用できる属性の一覧を示します。 情報バリアの詳細については、以下のリソースを参照してください。
- [情報の障壁](information-barriers.md)
- [Microsoft Teams の情報障壁に関するポリシーを定義する](information-barriers-policies.md)
- [情報バリアポリシーの編集 (または削除)](information-barriers-edit-segments-policies.md.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>情報バリアポリシーで属性を使用する方法

この記事に記載されている属性は、ユーザーのセグメントを定義または編集するために使用できます。 定義済みのセグメントは、[情報バリアポリシー](information-barriers-policies.md)でパラメーター ( *usergroupfilter*値と呼ばれる) として機能します。

1. セグメントを定義するために使用する属性を決定します。 (この記事の[参照](#reference)セクションを参照してください)。

2. 手順1で選択した属性に対して、ユーザーアカウントに値が入力されていることを確認します。 ユーザーアカウントの詳細を表示し、必要に応じて、属性値を含めるようにユーザーアカウントを編集します。 

    - 複数のアカウントを編集する (または PowerShell を使用して1つのアカウントを編集する) には、「 [Office 365 powershell でユーザーアカウントのプロパティを構成](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)する」を参照してください。

    - 単一のアカウントを編集するには、「 [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)する」を参照してください。

3. 次の例に示すように、 [PowerShell を使用してセグメントを定義](information-barriers-policies.md#define-segments-using-powershell)します。

    |例  |コマンドレット  |
    |---------|---------|
    |Department 属性を使用して、Segment1 というセグメントを定義します。     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |MemberOf 属性を使用して SegmentA と呼ばれるセグメントを定義します (この属性には "BlueGroup" などのグループ名が含まれているとします)。     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |ExtensionAttribute1 を使用して、DayTraders という名前のセグメントを定義します (この属性には "Daytraders" のような役職が含まれているとします)。|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > セグメントを定義するときは、すべてのセグメントに同じ属性を使用します。 たとえば、*部門*を使用してセグメントを定義する場合、 *department*を使用してすべてのセグメントを定義します。 *部署*を使用したセグメントと、 *MemberOf*を使用しているセグメントを定義しないでください。 セグメントが重ならないようにします。各ユーザーは、1つのセグメントにのみ割り当てる必要があります。 

## <a name="reference"></a>リファレンス

次の表に、情報バリアで使用できる属性を示します。

|Azure Active Directory のプロパティ名<br/>(LDAP 表示名)  |Exchange のプロパティ名  |
|---------|---------|
|産品       | 産品        |
|Company     |Company         |
|Department     |Department         |
|ExtensionAttribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |CustomAttribute4  |
|ExtensionAttribute5 |CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|MSExchExtensionCustomAttribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |エイリアス |
|PhysicalDeliveryOfficeName |Office |
|郵便 |郵便 |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|メール   |WindowsEmailAddress    |
|説明    |説明    |
|所属   |MemberOfGroup  |

## <a name="related-topics"></a>関連項目

[Microsoft Teams の情報障壁に関するポリシーを定義する](information-barriers-policies.md)

[情報の障壁をトラブルシューティングする](information-barriers-troubleshooting.md)

[情報の障壁](information-barriers.md)



