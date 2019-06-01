---
title: 情報バリアポリシーの属性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: この記事は、情報バリアポリシーで使用できるさまざまな属性の参照として使用します。
ms.openlocfilehash: e72e37950442974897de479c7c11f0053a578d1c
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668320"
---
# <a name="attributes-for-information-barrier-policies-preview"></a>情報バリアポリシーの属性 (プレビュー)

Azure Active Directory の特定の属性を使用して、ユーザーをセグメントにすることができます。 次に、セグメントが情報バリアポリシーのフィルターとして使用されます。 たとえば、部署を使用し**** て、組織内の部署別のユーザーのセグメントを定義することができます (2 つの部署に対して1人の従業員が同時に働くことは想定されていません)。 

この記事では、使用可能な属性の一覧を示します。 情報バリアの詳細については、以下のリソースを参照してください。
- [情報バリア (プレビュー)](information-barriers.md)
- [Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)](information-barriers-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>情報バリアポリシーで属性を使用する方法

この記事に記載されている属性を使用して、ユーザーのセグメントを定義 (または編集) することができます。 次の例に示すように、セグメントは情報バリアポリシーでパラメーター (UserGroupFilter) として使用されます。

|例  |コマンドレット  |
|---------|---------|
|Department 属性を使用して、Segment1 というセグメントを定義します。     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
|MemberOf 属性を使用して SegmentA と呼ばれるセグメントを定義します (この属性には "BlueGroup" などのグループ名が含まれているとします)。     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
|ExtensionAttribute1 を使用して、DayTraders という名前のセグメントを定義します (この属性には "Daytraders" のような役職が含まれているとします)。|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

セグメントを定義するときは、すべてのセグメントに同じ属性を使用します。 たとえば、*部門*を使用してセグメントを定義する場合、 *department*を使用してすべてのセグメントを定義します。 *部署*を使用したセグメントと、 *MemberOf*を使用しているセグメントを定義しないでください。 セグメントが重ならないようにします。各ユーザーは、1つのセグメントにのみ割り当てる必要があります。 

詳細については、「 [PowerShell を使用してセグメントを定義](information-barriers-policies.md#define-segments-using-powershell)する」を参照してください。

## <a name="reference"></a>リファレンス

次の表に、情報バリアで使用できる属性を示します。

|Azure Active Directory のプロパティ名 (LDAP 表示名)  |Exchange のプロパティ名  |
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

[Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)](information-barriers-policies.md)

[情報障壁のトラブルシューティング (プレビュー)](information-barriers-troubleshooting.md)

[情報バリア (プレビュー)](information-barriers.md)



