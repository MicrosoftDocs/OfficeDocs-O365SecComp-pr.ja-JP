---
title: Office 365 カスタマー ロックボックス要求
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 問題が発生したときに Microsoft サポートエンジニアがデータにアクセスする方法を制御するための、カスタマーロックボックス要求について説明します。
ms.openlocfilehash: f3cfdec6521cd5fe0bcb7007b27ce128ae3b2a1d
ms.sourcegitcommit: 62447503300376aa95dd05fb5276f93a9f6a20b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2019
ms.locfileid: "34927580"
---
# <a name="customer-lockbox-in-office-365"></a>Office 365 のカスタマーロックボックス

> [!NOTE]
> この記事では、現在使用可能な機能の展開と構成に関するガイダンスを提供します。この機能は、Microsoft 365 E5、Office 365 E5、情報の保護とコンプライアンス、または高度なコンプライアンスアドオンサブスクリプションを持つ組織でのみ利用できます。

カスタマーロックボックスを使用すると、明示的な承認なしにサービス操作を実行するために、Microsoft がコンテンツにアクセスできなくなります。 お客様のロックボックスによって、コンテンツにアクセスする要求の承認ワークフローに入ります。

Microsoft のエンジニアは、サポートプロセスでお客様から報告された問題のトラブルシューティングと修正に役立つ場合があります。 通常、問題は広範なテレメトリおよびデバッグツールによって Microsoft がサービスに適用されています。 ただし、場合によっては、Microsoft のエンジニアにお客様のコンテンツにアクセスして、根本的な原因を特定し、問題を修正する必要があります。 お客様のロックボックスには、エンジニアが承認ワークフローの最後の手順として顧客からのアクセスを要求する必要があります。 これにより、組織は、これらの要求を承認または拒否したり、顧客への直接アクセス制御を提供したりすることができます。

### <a name="customer-lockbox-overview-video"></a>顧客ロックボックスの概要ビデオ

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

> [!NOTE]
> Customer ロックボックスは、Exchange Online、SharePoint Online、OneDrive for business のデータにアクセスするための要求をサポートしています。 他の Office 365 サービスのサポートを推奨するには、 [office 365 UserVoice](https://office365.uservoice.com/)で要求を送信してください。

## <a name="customer-lockbox-workflow"></a>顧客ロックボックスのワークフロー

次の手順では、Microsoft のエンジニアからカスタマーロックボックス要求が開始されたときの一般的なワークフローの概要を示します。

1. 組織内の誰かが Office 365 メールボックスに問題を持っている。

2. ユーザーが問題のトラブルシューティングを行った後、問題を修正できない場合は、Microsoft サポートにサポートリクエストを開きます。

3. サポートエンジニアがサービス要求を確認し、問題を修復するためにお客様の Exchange Online コンテンツにアクセスする必要があるかどうかを判断します。

4. サポートエンジニアは、Customer のロックボックス要求ツールにログインし、顧客のテナント名、サービス要求番号、およびデータへのアクセスが必要な見積もり期間を指定して、データアクセス要求を行います。

5. Microsoft サポートマネージャーが要求を承認した後、顧客のロックボックスは、Microsoft からの保留中のアクセス要求に関する電子メール通知をお客様の組織で指定された承認者に送信します。

    ![顧客のロックボックス電子メール通知の例](media/CustomerLockbox1.png)

   > [!NOTE]
   > Microsoft 365 管理センターで[カスタマーロックボックスアクセス承認](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)者の役割を割り当てられたすべてのユーザーは、顧客ロックボックス要求を承認できます。

7. 承認者は、Microsoft 365 管理センターにサインインし、要求を承認します。 この手順では、Office 365 監査ログの検索によって使用可能な監査レコードの作成が開始されます。 詳細については、「[ユーザーのロックボックス要求の監査](#auditing-customer-lockbox-requests)」セクションを参照してください。

   顧客が要求を拒否した場合、または要求が12時間以内に承認されなかった場合、要求は有効期限が切れ、Microsoft のエンジニアにはアクセス権が与えられません。

   > [!IMPORTANT]
   > Microsoft では、Office 365 にサインインする必要がある、カスタマーロックボックスの電子メール通知にリンクは含まれていません。

8. お客様が要求を承認した後、Microsoft エンジニアは承認メッセージを受け取り、Exchange Online にログインし、お客様の問題を修正します。 Microsoft のエンジニアは、要求された期間に、アクセスが自動的に取り消される前に問題を修正します。

> [!NOTE]
> Microsoft のエンジニアによって実行されるすべての操作は、Office 365 監査ログに記録されます。 これらの監査レコードを検索して確認し、検索して確認することができます。

## <a name="turn-customer-lockbox-requests-on-or-off"></a>カスタマーロックボックス要求を有効または無効にする

Office 365 管理者は、Microsoft 365 管理センターでカスタマーロックボックスコントロールをオンにすることができます。 カスタマーロックボックスがオンになっている場合は、そのコンテンツにアクセスする前に、組織の承認を取得する必要があります。

> [!NOTE]
> 次の手順を実行するには、Microsoft 365 または Office 365 組織の全体管理者であるか、**カスタマーロックボックスアクセス許可**の管理者ロールが割り当てられている必要があります。

1. [https://admin.microsoft.com](https://admin.microsoft.com) に移動し、職場または学校のアカウントでサインインします。

2. [設定] をクリックして **> セキュリティ & プライバシー**] をクリックします。

    ![管理センターでカスタマーロックボックスの設定を編集する](media/CustomerLockbox2.png)

3. [**顧客ロックボックス**] タイルで、[**編集**] をクリックし、トグルを **[オン**] または [**オフ**] に移動して、機能をオンまたはオフにします。

    ![Require approval for Customer Lockbox](media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>カスタマーロックボックス要求を承認または拒否する

> [!NOTE]
> 次の手順を実行するには、Microsoft 365 または Office 365 組織の全体管理者であるか、**カスタマーロックボックスアクセス許可**の管理者ロールが割り当てられている必要があります。

1. [https://admin.microsoft.com](https://admin.microsoft.com) に移動し、職場または学校のアカウントでサインインします。

2. [**カスタマーロックボックス要求のサポート >**] をクリックします。

    ![[サポート] をクリックし、[カスタマーロックボックス要求] をクリックします。](media/CustomerLockbox5.png)

    顧客のロックボックス要求の一覧が表示されます。

    ![顧客ロックボックス要求の一覧](media/CustomerLockbox6.png)

3. 顧客のロックボックス要求を選択し、[**承認**] または [**拒否**] をクリックします。

    ![カスタマーロックボックス要求を承認または拒否する](media/CustomerLockbox7.png)

    カスタマーロックボックス要求の承認に関する確認メッセージが表示されます。

    ![カスタマーロックボックス要求を承認または拒否する](media/CustomerLockbox8.png)

## <a name="auditing-customer-lockbox-requests"></a>顧客ロックボックス要求の監査 

カスタマーロックボックス要求に対応する監査レコードは、Office 365 監査ログに記録され、Office 365 セキュリティ & コンプライアンスセンターの[監査ログ検索ツール](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)を使用してアクセスできます。 顧客に関連するアクション (アクセス要求が承認された場合に、Microsoft のエンジニアによって実行された操作) を承諾または拒否すると、Office 365 監査ログに記録されます。 これらの監査レコードを検索して確認することができます。

> [!NOTE]
> Office 365 監査ログを検索するには、Exchange Online で [表示のみの監査ログまたは監査ログの役割が割り当てられている必要があります。 詳細については、「[Office 365 セキュリティ/コンプライアンス センターで監査ログを検索する](https://docs.microsoft.com/en-us/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)」を参照してください。

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>カスタマーロックボックス要求に関連するアクティビティの監査ログを検索する

次に、監査ログ検索クエリを作成して、顧客ロックボックスに関連する監査レコードを取得する方法を示します。

1. [https://protection.office.com](https://protection.office.com) に移動します。
  
2. 職場または学校のアカウントを使用して、Office 365 にサインインします。

3. セキュリティ センターとコンプライアンス センターの左側のウィンドウで、[**検索と調査**]  >  [**監査ログの検索**] の順にクリックします。

    [**監査ログの検索**] ページが表示されます。

    ![監査ログの検索ページ](media/auditlogsearch1.png)
  
4. 次の検索条件を設定します。

    a. **アクティビティ**-検索ですべてのアクティビティの監査レコードが返されるようにするには、このフィールドを空白のままにします。 これは、カスタマーロックボックス要求と、Microsoft のエンジニアによって実行される対応するアクティビティに関連する監査レコードを返すために必要です。

    b. **開始**日と**終了日**-その期間内に発生したイベントを表示する日付と時刻の範囲を選択します。

    c. **ユーザー** -このフィールドは空白のままにします。

    d. **ファイル、フォルダー、またはサイト** - このフィールドは空白のままにします。

5. [**検索**] をクリックして、設定した検索条件で検索を実行します。 

    検索結果が読み込まれ、しばらくすると、[**監査ログの検索**] ページの [**結果**] の下に表示されます。

6. [検索結果] ページで [**結果のフィルター処理**] をクリックし、次のいずれかの操作を行います。

   - 組織内の承認者に関連する監査レコードを表示するには、顧客のロックボックス要求を承認または拒否します。 [**アクティビティ**] 列の下のボックスに「 **AccessToCustomerDataRequest**」と入力します。

   - Microsoft のエンジニアに関連する監査レコードを表示するには、承認された顧客ロックボックス要求に対する処理を実行します。 [**ユーザー** ] 列の下のボックスに、「 **Microsoft Operator**」と入力します。 エンジニアによって実行されるアクションが [**アクティビティ**] 列に表示されることに注意してください。

      ![監査レコードを表示するには、"Microsoft Operator" のフィルターを適用します。](media/CustomerLockbox10.png)

7. 結果の一覧で、監査レコードをクリックして表示します。

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>カスタマーロックボックスのアクセス要求の監査レコード

組織内のユーザーがカスタマーロックボックス要求を承認または拒否すると、監査レコードが Office 365 監査ログに記録されます。 このレコードには、次の情報が含まれています。 

| Audit record プロパティ| 説明|
|:---------- |:----------|
| 日付       | 顧客のロックボックス要求が承認または拒否された日時。
| IP アドレス | 承認者が要求を承認または拒否するために使用したコンピューターの IP アドレス。 |
| ユーザー       | サービスアカウント BOXServiceAccount @\[\]prod.outlook.com。            |
| アクティビティ   | AccessToCustomerDataRequest;これは、顧客のロックボックス要求を承認または拒否するときに記録される監査アクティビティです。                                |
| 項目       | 顧客のロックボックス要求の Guid                             |

次のスクリーンショットは、承認された顧客ロックボックス要求に対応する監査ログレコードの例を示しています。 顧客のロックボックス要求が拒否された場合、 **Approvaldecision**パラメーターの値は**Deny**になります。

![承認された顧客ロックボックス要求の監査レコード](media/CustomerLockbox9.png)

> [!TIP]
> 監査レコードに詳細情報を表示するには、[**詳細情報**] をクリックします。

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>Microsoft のエンジニアによって実行されたアクションの監査レコード

前述のように、お客様のロックボックス要求が承認された後に Microsoft のエンジニアが実行した操作 (およびお客様のコンテンツへのアクセスが発生する可能性があります) は、監査ログに記録されます。 これらのレコードには、次の情報が含まれています。

| Audit record プロパティ| 説明|
|:---------- |:----------|
| 日付       | アクションが実行された日時。 この操作が実行された時間は、顧客のロックボックス要求が承認された4時間以内になることに注意してください。              |
| IP アドレス | Microsoft エンジニアが使用したコンピューターの IP アドレス。 |
| ユーザー       | Microsoft Operator;この値は、このレコードが顧客のロックボックス要求に関連付けられていることを示します。                                  |
| アクティビティ   | Microsoft エンジニアによって実行されたアクティビティの名前。|
| 項目       | \<必須\>                                             |


## <a name="frequently-asked-questions"></a>よく寄せられる質問

#### <a name="which-office-365-services-does-customer-lockbox-apply-to"></a>どの Office 365 サービスが顧客ロックボックスに適用されますか。

お客様のロックボックスは現在、Exchange Online、SharePoint Online、OneDrive for business でサポートされています。

#### <a name="is-customer-lockbox-available-to-all-office-365-customers"></a>お客様のロックボックスは、すべての Office 365 のお客様が利用できますか?

カスタマーロックボックスは、Microsoft 365 または Office 365 E5 サブスクリプションに含まれており、情報の保護とコンプライアンス、または高度なコンプライアンスアドオンサブスクリプションを使用して他のプランに追加できます。 詳細については [、「プランと価格](https://products.office.com/business/office-365-enterprise-e5-business-software) 」を参照してください。

#### <a name="what-is-customer-content"></a>顧客コンテンツとは

顧客コンテンツは、Office 365 サービスおよびアプリケーションのユーザーによって作成されたデータです。 顧客コンテンツの例は次のとおりです。

- 電子メール本文またはメールの添付ファイル

- SharePoint サイトのコンテンツ

- SharePoint ファイルの本文に含まれる情報

- Skype for Business プレゼンテーションファイルの本文

- インスタントメッセージ (IM) または音声会話

- ユーザーが生成した blob または構造化ストレージデータ (SQL コンテナーなど)

- 顧客が所有するセキュリティ情報 (証明書、暗号化キー、パスワードなど)

- お客様のコンテンツが残っている場合の推論、以降のすべての推論

Office 365 の顧客コンテンツの詳細については、「 [office 365 のセキュリティセンター](https://products.office.com/en-US/business/office-365-trust-center-privacy/)」を参照してください。

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>自分のコンテンツへのアクセスを要求された場合、だれに通知されますか。

グローバル管理者と、カスタマーロックボックスアクセス許可管理者役割に割り当てられているユーザーに通知します。 これらのユーザーは、顧客のロックボックス要求の承認を行うこともできます。

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>組織内でこれらの要求を承認または拒否できるユーザー

グローバル管理者と顧客ロックボックスアクセス許可管理者ロールに割り当てられたユーザーは、顧客ロックボックス要求を承認できます。 お客様は、組織内でこれらの役割の割り当てを制御します。

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>カスタマーロックボックスにオプトインするにはどうすればよいですか?

グローバル管理者は、Microsoft 365 または Microsoft 365 管理センターでカスタマーロックボックスを有効にして構成することができます。

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>カスタマーロックボックス要求を承認した場合、エンジニアは何をすることができますか。また、Microsoft のエンジニアが何をしたかを知る方法を教えてください。

カスタマーロックボックス要求を承認した後、Microsoft のエンジニアは、事前承認済みコマンドレットを使用して、お客様のコンテンツにアクセスするためにこれらの必要な権限を付与しました。 カスタマーロックボックスの要求に対応して Microsoft のエンジニアが実行するアクションは、Office 365 セキュリティ & コンプライアンスセンターの監査ログに記録され、アクセスできます。

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>Microsoft が承認プロセスに従うことをどのように確認できますか?

組織内の管理者および承認者に送信される電子メールの承認通知は、Microsoft 365 管理センターのカスタマーロックボックス要求の履歴と相互参照できます。

お客様のロックボックスは、最新の[SOC 1 SSAE 16 監査レポート](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)に含まれています。 詳細については、 [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)の最新レポートを参照してください。

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>Microsoft は、自分のテナントの承認者の一覧を変更できますか? そうでない場合は、どのような方法で回避できますか。

顧客のロックボックス要求を承認できるユーザーを指定できるのは、組織内のグローバル管理者のみです。 これは、Azure Active Directory の全体管理者グループのメンバーのみが、要求を承認できるユーザーを指定できることを意味します。 Azure Active Directory の全体管理者グループのメンバーシップは、組織によってのみ管理されます。

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>承認のためにコンテンツアクセス要求に関する詳細情報が必要な場合は、どうすればよいですか?

各顧客のロックボックス要求には、Office 365 サービスの要求番号が含まれています。 要求に関する詳細情報を取得するには、Microsoft サポートに連絡して、このサービス番号を参照してください。

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>顧客のロックボックス要求が承認されると、アクセス許可はどのくらいの期間有効になりますか。

現時点では、Microsoft のエンジニアに付与されるアクセス許可の最大期間は4時間です。 Microsoft のエンジニアは、短い期間を要求することもできます。

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>すべてのカスタマーロックボックス要求の履歴を取得するにはどうすればよいですか?

すべてのカスタマーロックボックス要求は、Microsoft 365 管理センターで表示されます。

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>コンテンツアクセス要求を関連する監査ログと関連付けるにはどうすればよいですか。

コンプライアンスセンターのアクティビティフィードには、顧客ロックボックスのログアクティビティが含まれています。 顧客は、受信した電子メール要求に対して、顧客のロックボックスログアクティビティをアクティビティフィードから相互参照できます。

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>お客様がお客様のロックボックス要求に応答しない場合はどうなりますか?

顧客のロックボックス要求の既定の期間は12時間です。 12時間以内に要求に応答しない場合、要求は有効期限が切れます。

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>顧客が顧客のロックボックス要求を拒否した場合、Microsoft は何を行いますか?

顧客が顧客のロックボックス要求を拒否した場合、顧客コンテンツへのアクセスは行われません。 この問題を解決するために Microsoft がお客様のコンテンツにアクセスする必要があるというサービスの問題が組織内のユーザーから引き続き発生する場合、サービスの問題が持続する可能性があり、Microsoft はそのことをユーザーに通知します。

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>カスタマーロックボックスは、法律執行機関または他のサードパーティからのデータ要求に対して保護されるものですか?

いいえ。 Microsoft は、お客様のデータに関するサードパーティの要求を真剣に引き受けます。 クラウドサービスプロバイダーとして、Microsoft はお客様のデータのプライバシーを常に重視しています。 召喚を受け取った場合、Microsoft は常にお客様に情報を取得するためにサードパーティのリダイレクトを試行します。 (行政スミスのブログ:[政府からのお客様データの保護](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 Microsoft が受け取る法的執行機関の要求に関する[詳細情報](https://www.microsoft.com/en-us/corporate-responsibility/lerr)を定期的に公開しています。

詳細については、「[オンラインサービス用語](https://www.microsoft.com/Licensing/product-licensing/products.aspx)」の「サードパーティのデータ要求に関する[Microsoft セキュリティセンター](https://www.microsoft.com/en-us/trustcenter/default.aspx) 」と「顧客データの開示」を参照してください。

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>Microsoft では、Office 365 アプリケーションの顧客コンテンツへの継続的なアクセス権を、スタッフのメンバーが持っているかどうかを確認する方法を教えてください。

Microsoft は、アクセス制御システムを使用して広範な予防措置を実装しており、これらのアクセス制御システムを回避する試みを識別して対処するための検出対策を行います。 Office 365 は、最小限の特権とジャストインタイムアクセスの原則を使用して操作します。 そのため、Microsoft の担当者は、継続的にお客様のコンテンツにアクセスするためのアクセス許可を持っていません。 アクセス許可が付与されている場合は、期間に制限があります。 

Office 365 は、*ロックボックス*と呼ばれるアクセス制御システムを使用して、サービス内で運用および管理機能を実行する機能を付与するアクセス許可に対する要求を処理します。 オペレーターは、ロックボックスを使用してユーザーのコンテンツへのアクセスを要求する必要があります。その後、アクセス許可が付与される前に、要求に対してアクションを実行する (たとえば、承認する) 必要があります。 この2番目のユーザーはリクエスターになることができず、顧客コンテンツへのアクセスを承認するように指定する必要があります。 要求が承認された場合にのみ、オペレーターは顧客コンテンツへの一時的なアクセス権を取得します。 昇格期間が過ぎると、ロックボックスはアクセスを取り消します。

Microsoft の一般的なセキュリティ対策の詳細については、[オンラインサービス](https://www.microsoft.com/licensing/product-licensing/products)の使用条件を参照してください。

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>Microsoft のエンジニアがコンテンツにアクセスする必要があるのはどのような状況ですか。

Microsoft のエンジニアがお客様のコンテンツへのアクセスを必要とする最も一般的なシナリオは、お客様がトラブルシューティングのためのアクセス権を必要とするサポート要求を行った場合です。 Office 365 の基本原則は、お客様のコンテンツに Microsoft がアクセスせずにサービスを運用することです。 Microsoft によって実行されるほとんどすべてのサービス操作は完全に自動化されており、人的関与はユーザーのコンテンツによって高度に制御および抽象化されています。 Office 365 の目標は、お客様が Microsoft access の特定の要求を承認するまで、サービスをサポートするためにお客様のコンテンツにアクセスすることです。

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>Microsoft クラウドでデータをセキュリティで保護したことが既に考えられていますが、なぜお客様のロックボックスが必要ですか?

カスタマーロックボックスは、サービス操作の明示的なアクセス承認を提供する機能をお客様に提供することによって、特別な制御層を提供します。 明示的なデータアクセス承認のためにプロシージャが配置されていることを示すことにより、お客様のロックボックスは、顧客が HIPAA、FEDRAMP などの特定のコンプライアンス義務を満たすのを支援します。
