---
title: 'クイックスタート: Office 365 Advanced Threat Protection のセットアップ'
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 次のクイックスタートガイドを使用して、Office 365 Advanced Threat Protection (ATP) が組織に合わせて設定および構成されていることを確認できます。
ms.openlocfilehash: a071c626327aa7d0055df522e8fec5ebe41d6a83
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999400"
---
# <a name="quick-start-guide-set-up-office-365-advanced-threat-protection"></a>クイック スタート ガイド: Set up Office 365 Advanced Threat Protection のセットアップ

ここでは、Office 365 Advanced Threat Protection (ATP) が組織に対して設定されていることを確認するためのチェックリストとして使用できる、クイックスタートガイドを紹介します。 Office 365 で脅威を保護するのが初めての場合、またはどこから始めるべきかがわからない場合は、次のガイダンスを出発点としてご利用ください。 

> [!IMPORTANT]
> **ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき**ます。 使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。

## <a name="prerequisites"></a>前提条件

- 組織には、 [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を含むサブスクリプションが必要です。

- ATP 機能にアクセスするには、適切な役割が割り当てられている必要があります。 次の表は、いくつかの例を示しています。 

    |役割または役割グループ  |詳細情報  |
    |---------|---------|
    |Office 365 グローバル管理者 |[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
    |セキュリティ管理者 |[Azure Active Directory での管理者の役割のアクセス許可](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
    |Exchange Online 組織の管理 |[Exchange Online でのアクセス許可](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>および<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

    ( [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照してください)。

## <a name="part-1---anti-malware"></a>パート 1-マルウェア対策

1. [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > の**マルウェア対策**] を選択します。
2. [**既定**のポリシー] をダブルクリックし、[**設定**] を選択します。
3. 次の設定を指定します。
    - [**マルウェア検出の応答**] セクションで、既定の設定の [**いいえ**] をそのまま使用します。
    - [**一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。
4. [**保存**] をクリックします。

マルウェア対策ポリシーオプションの詳細については、「[マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。

## <a name="part-2---zero-day-protection"></a>パート 2-0 日の保護

ゼロ日の保護は、ATP の安全なリンクや安全な添付ファイルのポリシーなどのポリシーによって設定されます。

### <a name="atp-safe-attachments-policies"></a>ATP の安全な添付ファイルポリシー

1. [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP 安全添付ファイル**] を選択します。
2. [ **SharePoint、OneDrive、Microsoft Teams の ATP を有効にする**] オプションを選択します。
3. [**電子メールの添付ファイルを保護**する] セクションで**+**、プラス記号 () をクリックします。
4. 次の設定を指定します。
    - [**名前**] ボックスに「 `Block malware`」と入力します。
    - [応答] セクションで、[**ブロック**] を選択します。
    - [**添付ファイルのリダイレクト**] セクションで、[**リダイレクトを有効にする**] オプションを選択し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定します。
    - [**適用先**] セクションで、[**受信者ドメイン**] を選択します。 次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。
5. [**保存**] をクリックします。
6. (推奨の追加手順)グローバル管理者または SharePoint Online 管理者は、 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** コマンドレットを実行して、Office 365 環境の**DisallowInfectedFileDownload**パラメーターを*true*に設定します。 (これにより、ユーザーが悪意を持って検出されたファイルを開く、移動、コピー、または共有できなくなります)。  

詳細については、「 [office 365 の atp の安全な添付ファイルのポリシーをセットアップ](set-up-atp-safe-attachments-policies.md)する」および「 [SharePoint、OneDrive、Microsoft Teams 用の office 365 ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。

### <a name="atp-safe-links-policies"></a>ATP の安全なリンクポリシー

ATP の安全なリンクを設定するには、既定のポリシーを確認し、ポリシーを追加します。

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
6. [**保存**] をクリックします。

詳細については、「 [Office 365 ATP 安全リンクポリシー](set-up-atp-safe-links-policies.md)のセットアップ」を参照してください。 

## <a name="part-3---anti-phishing"></a>パート 3-フィッシング対策 

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

フィッシング対策ポリシーオプションの詳細については、「 [Office 365 の ATP のフィッシング対策およびフィッシング対策ポリシー](set-up-anti-phishing-policies.md)をセットアップする」を参照してください。

## <a name="part-4---anti-spam"></a>パート 4-スパム対策

1. [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > のスパム**対策**] を選択します。
2. [**カスタム**] タブで、[**カスタム設定**] をオンにします。
3. [**既定のスパムフィルターポリシー**] を展開し、[**ポリシーの編集**] をクリックして、次の設定を指定します。
    - [**スパムと一括操作**] セクションで、しきい値を5または6に設定します。
    - [**許可するリスト**] セクションで、許可された送信者とドメインを確認し、必要に応じて編集します。
4. [**保存**] をクリックします。

スパム対策ポリシーオプションの詳細については、「[スパム対策](configure-the-anti-spam-policies.md)ポリシーを構成する」を参照してください。

## <a name="part-5---service-wide-settings"></a>パート 5-サービスレベルの設定

### <a name="zero-hour-auto-purge"></a>ゼロ時間自動削除

ゼロ時間自動削除 (ZAP) は既定でオンになっています。ただし、次の条件を満たす必要があります。
- スパム対策ポリシーで、 **[迷惑メール] フォルダーにメッセージを移動**するように設定されています。
- ユーザーが既定の迷惑メール設定を保持していて、迷惑メールの保護がオフになっていない。

詳細については、「[スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。

### <a name="audit-logging"></a>監査ログ

[セキュリティダッシュボード](security-dashboard.md)や[エクスプローラー](use-explorer-in-security-and-compliance.md)などの脅威保護レポートのデータを表示するには、組織に対して監査ログを有効にする必要があります。

「 [Office 365 監査ログの検索をオンまたはオフにする」を](turn-audit-log-search-on-or-off.md)参照してください。

## <a name="post-setup-tasks"></a>セットアップ後のタスク

### <a name="watch-for-new-features-and-service-updates"></a>新機能とサービス更新を見る

- [Microsoft 365 ロードマップにアクセスする](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [Office 365 Advanced Threat Protection サービスの説明を参照してください。](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a>組織に対して ATP がどのように機能するかを確認する

- [Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)

- [セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a>ATP ポリシーの定期的なレビューと改訂

- [office 365 ユーザーの office 365 の脅威の調査と応答を安全に保つ](keep-users-safe-with-office-365-ti.md) 

- [Office 365 セキュリティ&amp; /コンプライアンスセンターのスマートレポートと分析情報を使用する](reports-and-insights-in-security-and-compliance.md) 