---
title: 情報障壁の概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/26/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 情報バリアを使用して、組織内の Microsoft Teams を使用して通信のコンプライアンスを確保します。
ms.openlocfilehash: 6565fc28d70ac6ff9a6f4df6edc75b89d19ae29a
ms.sourcegitcommit: 1c254108c522d0cb44023565268b5041d07748aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2019
ms.locfileid: "35279475"
---
# <a name="information-barriers-preview"></a>情報バリア (プレビュー)

## <a name="overview"></a>概要

Microsoft クラウドサービスには、強力なコミュニケーションとコラボレーションの機能が含まれています。 しかし、2つのグループ間の通信を制限して、組織内での利息の競合を回避する必要があるとします。 または、内部情報を保護するために、組織内の特定のユーザー間の通信を制限する必要がある場合があります。 Microsoft 365 は、グループと組織間での通信とコラボレーションを可能にするため、必要に応じて特定のユーザーグループ間の通信を制限する方法がありますか。 情報バリアを使用して、できることはありません。 

情報バリアは、Microsoft Teams から始めて、今すぐプレビュー段階にあります。 これらの機能が組織で使用可能な場合、コンプライアンス管理者または情報障壁管理者は、Microsoft Teams のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。 情報バリアポリシーは、次のような状況で使用できます。

- 1日の販売者は、マーケティングチームで他のユーザーを呼び出すことはできません
- 機密企業情報に従事している財務担当者は、組織内の特定のグループからの通話を受信できません
- 組織内の特定のグループに属するユーザーとの通信を行うことができません。
- 研究チームは、製品開発チームとの通話またはオンラインチャットのみを行うことができます。

これらのすべてのシナリオ例 (およびその他) については、Microsoft Teams での通信を禁止または許可するように情報バリアポリシーを定義できます。 このようなポリシーを使用すると、ユーザーが不要な通話やチャットを行うことができなくなり、Microsoft Teams 内の特定のグループとのみ通信できるようになります。 情報バリアポリシーが有効になっていると、そのポリシーの対象となっているユーザーが Microsoft Teams 内の他のユーザーと通信しようとするたびに、チェックが行われて、通信 (情報バリアポリシーによって定義されている) を回避 (または許可) します。 情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。

> [!NOTE]
> 情報バリアは、SharePoint Online または OneDrive を使用した電子メール通信やファイル共有には適用されません。 さらに、情報バリアは、[コンプライアンスの境界](set-up-compliance-boundaries.md)から独立しています。

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

**現時点では、情報バリア機能はプライベートプレビューに**あります。 これらの機能が一般公開されると、次のようなサブスクリプションに含まれます。

- Microsoft 365 E5
- Office 365 E5
- Office 365 Advanced Compliance
- Microsoft 365 E5 情報の保護とコンプライアンス

詳細については、「[コンプライアンスソリューション](https://products.office.com/business/security-and-compliance/compliance-solutions)」を参照してください。

[情報バリアポリシーを定義または編集](information-barriers-policies.md)するには、次のいずれかの役割が割り当てられている必要があります。

- Microsoft 365 グローバル管理者
- Office 365 グローバル管理者
- コンプライアンス管理者
- 情報障壁管理者

情報バリアポリシーを定義、検証、または編集するには、PowerShell コマンドレットを熟知している必要があります。 [How to 情報](information-barriers-policies.md)には PowerShell コマンドレットの例がいくつか用意されていますが、パラメーターなどの追加の詳細については、組織のために知っておく必要があります。

## <a name="concepts-of-information-barrier-policies"></a>情報バリアポリシーの概念

情報バリアポリシーの基礎概念を理解しておくと役に立ちます。

- **ユーザーアカウントの属性**は、Azure Active Directory (または Exchange Online) で定義されます。 これらの属性には、部署、役職、場所、チーム名、その他のジョブプロファイルの詳細を含めることができます。 

- **セグメント**とは、Office 365 セキュリティ & コンプライアンスセンターで、選択した**ユーザーアカウント属性**を使用して定義された一連のユーザーのことです。 ([サポートされている属性の一覧](information-barriers-attributes.md)を参照してください)。 

- **情報バリアポリシー**では、通信制限または制限を決定します。 情報バリアポリシーを定義するときは、次の2種類のポリシーから選択します。
    - "Block" ポリシーは、あるセグメントが別のセグメントと通信できないようにします。
    - [許可] ポリシーでは、1つのセグメントが特定の他のセグメントのみと通信できるようにします。

- **ポリシーアプリケーション**は、すべての情報バリアポリシーが定義された後に実行され、組織に適用する準備が整っています。

## <a name="next-steps"></a>次のステップ

- [Microsoft Teams の情報障壁の詳細を知る](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [情報バリアポリシーに使用できる属性を参照してください。](information-barriers-attributes.md)
- [情報バリアのポリシーを定義する](information-barriers-policies.md) 

