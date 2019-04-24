---
title: Office 365 で脅威から保護する
ms.author: tracyp
author: msfttracyp
manager: laurawi
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: この記事をガイドとして使用して、今すぐ脅威保護機能を構成します。
ms.openlocfilehash: 065071999130f209d63bcafc09ad72daceceac04
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261635"
---
# <a name="protect-against-threats-in-office-365"></a>Office 365 で脅威から保護する

Office 365 には、さまざまな脅威保護機能が含まれています。 ここでは、組織に対して脅威保護機能がセットアップされていることを確認するためのチェックリストとして使用できる、クイックスタートガイドを紹介します。 Office 365 の脅威保護機能を初めて使用する場合や、どこから始めるべきかがわからない場合は、次のガイドを出発点としてご利用ください。 

> [!IMPORTANT]
> **ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき**ます。 使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。

## <a name="requirements"></a>要件

### <a name="licenses"></a>ライセンス

脅威保護機能は、すべての Office 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションには、Office 365 advanced Threat Protection などの高度な機能が含まれています。 この記事では、各保護エリアのサブスクリプション要件を示します。

脅威保護機能と subsriptions の詳細については、以下のリソースを参照してください。
- [Office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
- [Exchange Online Protection サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)
- [Office 365 セキュリティ/コンプライアンス センター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

### <a name="roles-and-permissions"></a>ロールと権限

[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)でポリシーを構成するには、適切な役割が割り当てられている必要があります。 次の表は、いくつかの例を示しています。 

|役割または役割グループ  |詳細情報  |
|---------|---------|
|Office 365 グローバル管理者 |[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|セキュリティ管理者 |[Azure Active Directory での管理者の役割のアクセス許可](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織の管理 |[Exchange Online でのアクセス許可](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>and<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="part-1---anti-malware"></a>パート 1-マルウェア対策

[Exchange Online protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP) を含むサブスクリプションでは[、マルウェア対策保護](anti-malware-protection.md)を利用できます。 

1. [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > の**マルウェア対策**] を選択します。

2. [**既定**のポリシー] をダブルクリックし、[**設定**] を選択します。

3. 次の設定を指定します。
    
    - [**マルウェア検出の応答**] セクションで、既定の設定の [**いいえ**] をそのまま使用します。
   
    - [**一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。

4. **[保存]** をクリックします。

マルウェア対策ポリシーオプションの詳細については、「[マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。

## <a name="part-2---zero-day-protection"></a>パート 2-0 日の保護

ゼロ日の保護は、 [Office 365 Advanced Threat protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) を含むサブスクリプションで利用でき、 [atp の安全な添付ファイル](atp-safe-attachments.md)と[atp の安全なリンク](atp-safe-links.md)ポリシーによって設定されます。

### <a name="atp-safe-attachments-policies"></a>ATP の安全な添付ファイルポリシー

[atp の安全な添付ファイル](atp-safe-attachments.md)を設定するには、少なくとも1つの atp の安全な添付ファイルポリシーを定義する必要があります。 

1. [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP 安全添付ファイル**] を選択します。

2. [ **SharePoint、OneDrive、Microsoft Teams の ATP を有効にする**] オプションを選択します。

3. [**電子メールの添付ファイルを保護**する] セクションで**+**、プラス記号 () をクリックします。

4. 次の設定を指定します。

    - [**名前**] ボックスに「 `Block malware`」と入力します。

    - [応答] セクションで、[**ブロック**] を選択します。

    - [**添付ファイルのリダイレクト**] セクションで、[**リダイレクトを有効にする**] オプションを選択し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定します。

    - [**適用先**] セクションで、[**受信者ドメイン**] を選択します。 次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。

5. **[保存]** をクリックします。

6. (**推奨の追加手順**)グローバル管理者または SharePoint Online 管理者は、 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** コマンドレットを実行して、Office 365 環境の**DisallowInfectedFileDownload**パラメーターを*true*に設定します。 (これにより、ユーザーが悪意を持って検出されたファイルを開く、移動、コピー、または共有できなくなります)。  

詳細については、次を参照してください。 
- [Office 365 の ATP の安全な添付ファイルのポリシーを設定する](set-up-atp-safe-attachments-policies.md)
- [SharePoint、OneDrive、Microsoft Teams の Office 365 ATP を有効にする](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="atp-safe-links-policies"></a>ATP の安全なリンクポリシー

[ATP の安全なリンク](atp-safe-links.md)を設定するには、既定のポリシーを確認して編集し、特定のユーザーのポリシーを追加します。

1. [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP セーフリンク**] を選択します。

2. [**既定**のポリシー] をダブルクリックします。

3. [**安全なリンクの使用**] セクションで、[ **office 365 ProPlus、office for iOS**、および Android] オプションをオンにして、[**保存**] をクリックします。

4. [**特定の受信者に適用されるポリシー** ] セクションで、プラス**+** 記号 () をクリックします。

5. 次の設定を指定します。

    - [**名前**] ボックスに、などの名前を入力`Safe Links`します。

    - **[アクションの選択**] セクションで、[**オン**] を選択します。

    - 次のオプションを選択します。

        - **安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする** 

        - **組織内で送信される電子メールメッセージに安全なリンクを適用する**

        - **ユーザーが元の URL への安全なリンクをクリックできないようにする**

    - [**適用先**] セクションで、[**受信者ドメイン**] を選択します。 次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。

6. **[保存]** をクリックします。

詳細については、「 [Office 365 ATP 安全リンクポリシー](set-up-atp-safe-links-policies.md)のセットアップ」を参照してください。 

## <a name="part-3---anti-phishing"></a>パート 3-フィッシング対策 

[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションでは、[フィッシング対策保護](anti-phishing-protection.md)を利用できます。 高度なフィッシング対策を[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)で利用できます。 次の手順では、ATP のフィッシング対策ポリシーを構成する方法について説明します。 この手順は、(ATP を使用しない) フィッシング対策ポリシーの構成に似ています。

1. [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP のフィッシング対策**] を選択します。

2. [**既定のポリシー**] をクリックします。

3. [**偽装**] セクションで、[**編集**] をクリックし、次の設定を指定します。

    -  [**保護するユーザーの追加**] タブで、[保護] をオンにします。 次に、組織の取締役会のメンバー、CEO、CFO、その他のシニアリーダーなどのユーザーを追加します。 (個々の電子メールアドレスを入力するか、クリックしてリストを表示することができます。)

    - [**保護するドメインの追加**] タブで、**自分が所有しているドメインを自動的**に有効にします。 カスタムドメインがある場合は、それらも追加します。

    - [**操作**] タブで、[**受信者の迷惑メールフォルダーにメッセージを移動する**] を選択して、偽装されたユーザーと偽装ドメインの両方を選択し、安全のヒントを有効にします。

    - [**メールボックスインテリジェンス**] タブで、[メールボックスインテリジェンス] がオンになっていることを確認します。

    - [**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。

4. [**スプーフィング**] セクションで、[**編集**] をクリックし、次の設定を指定します。

    - [**スプーフィングフィルターの設定**] タブで、[スプーフィング対策] 保護が有効になっていることを確認します。

    - [**操作**] タブで、[受信者の迷惑メールフォルダーにメッセージを移動する] を選択します。

    - [**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。 (変更を行っていない場合は、[**キャンセル**] をクリックします)。

5. [既定のポリシー設定] ページを閉じます。

フィッシング対策ポリシーオプションの詳細については、「[フィッシング対策ポリシーの設定](set-up-anti-phishing-policies.md)」を参照してください。

## <a name="part-4---anti-spam"></a>パート 4-スパム対策

[スパム対策保護](anti-spam-protection.md)は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。

1. [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > のスパム**対策**] を選択します。

2. [**カスタム**] タブで、[**カスタム設定**] をオンにします。

3. [**既定のスパムフィルターポリシー**] を展開し、[**ポリシーの編集**] をクリックして、次の設定を指定します。

    - [**スパムと一括操作**] セクションで、しきい値を5または6に設定します。

    - [**許可するリスト**] セクションで、許可された送信者とドメインを確認し、必要に応じて編集します。

4. **[保存]** をクリックします。

スパム対策ポリシーオプションの詳細については、「[スパム対策](configure-the-anti-spam-policies.md)ポリシーを構成する」を参照してください。

## <a name="part-5---service-wide-settings"></a>パート 5-サービスレベルの設定

### <a name="zero-hour-auto-purge"></a>ゼロ時間自動削除

[ゼロ時間自動削除](zero-hour-auto-purge.md)(ZAP) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。 この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たす必要があります。

- スパム[対策ポリシー](anti-spam-protection.md)で、 **[迷惑メール] フォルダーにメッセージを移動**するように設定されています。

- ユーザーが既定の[迷惑メール設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持していて、迷惑メールの保護がオフになっていない。

詳細については、「[スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。

### <a name="audit-logging"></a>監査ログ

監査ログは、 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)を含むサブスクリプションで利用できます。 [セキュリティダッシュボード](security-dashboard.md)、[電子メールセキュリティレポート](view-email-security-reports.md)、[エクスプローラー](use-explorer-in-security-and-compliance.md)などの脅威保護レポートのデータを表示するには、組織に対して監査ログを有効にする必要があります。 詳細については、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。

## <a name="post-setup-tasks"></a>セットアップ後のタスク

### <a name="watch-for-new-features-and-service-updates"></a>新機能とサービス更新を見る

- [標準または対象指定リリースオプションを設定する](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)

- [メッセージセンターに移動して機能のアナウンスを表示する](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) 

- [新しい機能の状態を確認するには、Microsoft 365 ロードマップを参照してください。](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [Office 365 サービスの説明を確認する](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)

### <a name="see-how-threat-protection-features-are-working-for-your-organization"></a>組織に対して脅威保護機能がどのように機能しているかを確認する

- [セキュリティダッシュボードにアクセスする](security-dashboard.md)

- [Office 365 ATP](view-reports-for-atp.md)([エクスプローラー](use-explorer-in-security-and-compliance.md)を含む) のレポートを表示する

- [電子メールのセキュリティレポートを表示する](view-email-security-reports.md)

### <a name="periodically-review-and-revise-your-threat-protection-policies"></a>脅威保護ポリシーを定期的に見直し、改訂する

- [セキュリティで保護されたスコアを確認する](microsoft-secure-score.md)

- [セキュリティ&amp; /コンプライアンスセンターのスマートレポートと分析情報を使用する](reports-and-insights-in-security-and-compliance.md) 

- [Office 365 の脅威の調査と応答機能をユーザーに対して安全に保つ](keep-users-safe-with-office-365-ti.md) 
 