---
title: 情報バリアポリシーを編集または削除する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/24/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 情報バリアのポリシーを編集または削除する方法について説明します。
ms.openlocfilehash: e6bed4df2329d426f86bd4cde07bdc7d1a2792cd
ms.sourcegitcommit: 7c48ce016fa9f45a3813467f7c5a2fd72f9b8f49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35215650"
---
# <a name="edit-or-remove-information-barrier-policies-preview"></a>情報バリアポリシーの編集または削除 (プレビュー)

## <a name="overview"></a>概要

[情報バリアポリシーを定義](information-barriers-policies.md)した後、[トラブルシューティング](information-barriers-troubleshooting.md)の一環として、または定期的な保守の一環として、これらのポリシーまたはユーザーセグメントに変更を加える必要がある場合があります。 この記事をガイドとして使用します。

> [!IMPORTANT]
> この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。<br/>-Microsoft 365 エンタープライズグローバル管理者<br/>-Office 365 グローバル管理者<br/>-コンプライアンス管理者<br/>-IB コンプライアンス管理 (新しい役割)<p>情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。<p>[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。

## <a name="edit-user-account-attributes"></a>ユーザーアカウントの属性を編集する

ユーザーのセグメント化に使用される属性を編集するには、以下の手順を使用します。 

たとえば、Department 属性を使用していて、1つまたは複数のユーザーアカウントで Department の値がリストされていない場合は、それらのユーザーアカウントを編集して部署情報を含める必要があります。 

ユーザーアカウント属性は、情報バリアポリシーを割り当てることができるように、セグメントを定義するために使用されます。

1. 属性値、割り当てられたセグメントなど、特定のユーザーアカウントの詳細を表示するには、Identity パラメーターを指定して**InformationBarrierRecipientStatus**コマンドレットを使用します。 

   文`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` 
    
   名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 
    
   例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` 
    
   この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。 
    
   (1 人のユーザーに対してこのコマンドレットを`Get-InformationBarrierRecipientStatus -Identity <value>`使用することもできます。) 
    
2. ユーザーアカウントプロファイルに対してどの属性を編集するかを決定します。 詳細については、 [「情報バリアポリシーの属性 (プレビュー)](information-barriers-attributes.md) 」を参照してください。 

3. 1つ以上のユーザーアカウントを編集して、前の手順で選択した属性の値を含めます。 これを行うには、次のいずれかの手順を使用します。

    - 単一のアカウントを編集するには、「 [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)する」を参照してください。

    - 複数のアカウントを編集する (または PowerShell を使用して1つのアカウントを編集する) には、「 [Office 365 powershell でユーザーアカウントのプロパティを構成](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)する」を参照してください。

## <a name="edit-a-segment"></a>セグメントを編集する

この手順を使用して、ユーザーセグメントの定義を編集します。 たとえば、セグメントの名前を変更したり、セグメントに含まれている人物を特定するために使用するフィルターを変更したりすることができます。

1. 既存のすべてのセグメントを表示するには、コマンドレットの**取得**を使用します。
    
    文`Get-OrganizationSegment`

    セグメントの種類、UserGroupFilter 値、作成者または最終更新日時、GUID など、セグメントと詳細の一覧が表示されます。

    > [!TIP]
    > 後で参照するために、セグメントのリストを印刷または保存します。 たとえば、セグメントを編集する場合は、その名前を知っているか、値を識別する必要があります (これは Identity パラメーターと共に使用されます)。

2. セグメントを編集するには、 **Identity**パラメーターと関連する詳細情報を使用して、**グループ**化コマンドレットを使用します。 

    文`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`

    例: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`

    この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントに対して、部署名を "hrdept" に更新しました。

組織のセグメントの編集が終了したら、情報バリアポリシーの[定義](information-barriers-policies.md#part-2-define-information-barrier-policies)または[編集](#edit-a-policy)を行うことができます。

## <a name="edit-a-policy"></a>ポリシーを編集する

1. 現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。

    文`Get-InformationBarrierPolicy`

    結果の一覧で、変更するポリシーを特定します。 ポリシーの GUID と名前をメモします。

2. **InformationBarrierPolicy**コマンドレットを**Identity**パラメーターと共に使用して、必要な変更を指定します。

    例: ポリシーが定義されていて、*リサーチ*セグメントが*販売*および*マーケティング*セグメントとの通信をブロックするとします。 このポリシーは、このコマンドレットを使用して定義されています。`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`
    
    *研究*セグメント内のユーザーが*HR*セグメント内のユーザーとのみ通信できるように変更するとします。 この変更を行うには、次のコマンドレットを使用します。`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    この例では、"SegmentsBlocked" を "SegmentsAllowed" に変更し、 *HR*セグメントを指定しました。

3. ポリシーの編集が終了したら、変更内容を適用してください。 ([情報バリアポリシーの適用](information-barriers-policies.md#part-3-apply-information-barrier-policies)を参照してください)。

## <a name="set-a-policy-to-inactive-status"></a>ポリシーを非アクティブな状態に設定する

1. 現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。

    文`Get-InformationBarrierPolicy`

    結果の一覧で、変更する (または削除する) ポリシーを特定します。 ポリシーの GUID と名前をメモします。

2. ポリシーの状態を非アクティブに設定するには、Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用し、State パラメーターを inactive に設定します。

    文`Set-InformationBarrierPolicy -Identity GUID -State Inactive`

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247*を非アクティブな状態に設定する情報バリアポリシーを設定します。

3. 変更を適用するには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。

    文`Start-InformationBarrierPoliciesApplication`

    組織の変更がユーザーごとに適用されます。 組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。 (一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。

この時点で、1つまたは複数の情報バリアポリシーが非アクティブ状態に設定されます。 ここから、次のいずれかの操作を実行できます。
- そのまま保持する (非アクティブな状態に設定されたポリシーはユーザーに影響しません)
- [ポリシーを編集する](#edit-a-policy) 
- [ポリシーを削除する](#remove-a-policy)

## <a name="remove-a-policy"></a>ポリシーを削除する

1. 現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。

    文`Get-InformationBarrierPolicy`

    結果の一覧で、削除するポリシーを特定します。 ポリシーの GUID と名前をメモします。 ポリシーが非アクティブの状態に設定されていることを確認します。

2. Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用します。

    文`Remove-InformationBarrierPolicy -Identity GUID`

    例: GUID が*43c37853-ea10-4b90-a23d-ab8c93772471*のポリシーを削除するとします。 これを行うには、次のコマンドレットを使用します。
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    メッセージが表示されたら、変更を確認します。

3. 削除するポリシーごとに、手順1-2 を繰り返します。

4. ポリシーの削除が終了したら、変更内容を適用します。 これを行うには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。

    文`Start-InformationBarrierPoliciesApplication`

    組織の変更がユーザーごとに適用されます。 組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。

## <a name="stop-a-policy-application"></a>ポリシーアプリケーションを停止する

情報バリアポリシーの適用を開始した後で、これらのポリシーの適用を停止するには、次の手順を使用します。 プロセスが開始されるまで約30-35 分かかることに注意してください。

1. 最新の情報バリアポリシーアプリケーションの状態を表示するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。

    文`Get-InformationBarrierPoliciesApplicationStatus`

    アプリケーションの GUID をメモします。

2. Identity パラメーターを指定して**InformationBarrierPoliciesApplication**コマンドレットを使用します。

    文`Stop-InformationBarrierPoliciesApplication -Identity GUID`

    例: `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`

    この例では、情報バリアポリシーの適用を停止しています。

## <a name="related-articles"></a>関連記事

[情報障壁の概要を理解する](information-barriers.md)

[情報バリアのポリシーを定義する (プレビュー)](information-barriers-policies.md)

[Microsoft Teams の情報障壁の詳細を知る](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[情報バリアポリシーの属性 (プレビュー)](information-barriers-attributes.md)

[情報障壁のトラブルシューティング (プレビュー)](information-barriers-troubleshooting.md)
