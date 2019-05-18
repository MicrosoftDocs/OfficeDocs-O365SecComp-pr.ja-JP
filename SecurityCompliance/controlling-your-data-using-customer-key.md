---
title: 顧客キーを使用して Office 365 でデータを制御する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: Exchange Online、Skype for Business、SharePoint Online、OneDrive for business で Office 365 の顧客キーを設定する方法について説明します。 顧客キーを使用して、組織の暗号化キーを制御し、Office 365 を使用して Microsoft のデータセンターで保存されているデータを暗号化するように構成します。
ms.openlocfilehash: 839d0b56b3748e2ab4ccecc30a084447f22131aa
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153719"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>顧客キーを使用して Office 365 でデータを制御する

顧客キーによって、組織の暗号化キーを制御し、Microsoft のデータ センターにある保存データの暗号化にそれを使用するよう Office 365 を構成できます。 言い換えると、顧客キーを使用すると、そのキーを使用して、ユーザーに属する暗号化の層を追加することができます。 保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。
  
Office 365 の顧客キーを使用するには、事前に Azure をセットアップする必要があります。 このトピックでは、必要な Azure リソースを作成して構成するために従う必要のある手順について説明し、Office 365 で顧客キーを設定する手順について説明します。 Azure のセットアップを完了した後、組織内のメールボックスとファイルに割り当てるポリシーとそのためのキーを決定します。 ポリシーを割り当てていないメールボックスとファイルでは、Microsoft によって制御および管理されている暗号化ポリシーが使用されます。 顧客キーの詳細、または一般的な概要については、「 [Office 365 FAQ」の顧客キー](service-encryption-with-customer-key-faq.md)を参照してください。
  
> [!IMPORTANT]
> このトピックのベストプラクティスに従うことを強くお勧めします。 これらは、 **TIP**と**重要**と呼ばれます。 顧客キーを使用すると、組織全体でスコープが大きくなる可能性があるルート暗号化キーを制御できます。 このため、これらのキーに誤りが発生しても、サービスが中断したり、データが irrevocable 失われたりする可能性があります。 
  
## <a name="before-you-begin-setting-up-customer-key"></a>顧客キーの設定を開始する前に
<a name="Beforeyoustart"> </a>

開始する前に、組織に適したライセンスを持っていることを確認してください。 Office 365 の顧客キーは、Office 365 E5 または Advanced コンプライアンス SKU で提供されます。
  
その後、このトピックの概念と手順を理解するには、 [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/)のマニュアルを参照してください。 また、「[テナント](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)」など、Azure で使用される用語について理解しておいてください。
  
ドキュメントなどの顧客キーに関するフィードバックを提供するために、アイデア、提案、視点を customerkeyfeedback@microsoft.com に送信します。
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>Office 365 の顧客キーの設定の概要
<a name="Overview"> </a>

顧客キーを設定するには、これらのタスクを完了します。 このトピックの残りの部分では、各タスクの詳細な手順を説明します。または、プロセスの各ステップに関する詳細情報へのリンクを示します。
  
**Azure と Microsoft FastTrack の場合:**
  
これらのタスクのほとんどは、Azure PowerShell にリモートで接続することで完了します。 最良の結果を得るには、Azure PowerShell のバージョン4.4.0 以降を使用します。
  
- [2つの新しい Azure サブスクリプションを作成する](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [Azure サブスクリプションを登録して必須の保持期間を使用する](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    登録には 1 ~ 5 営業日かかります。
    
- [Office 365 の顧客キーを有効にするための要求を送信する](controlling-your-data-using-customer-key.md#FastTrack)
    
    2つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされている web フォームに入力して、適切な顧客キー提示要求を送信する必要があります。 **FastTrack チームは、顧客キーについてサポートを提供していません。Office では、FastTrack ポータルを使用**してフォームを送信することができます。また、顧客キーの関連する提供を追跡するのに役立ちます。
  
カスタマーキーオファーを送信すると、Microsoft は要求を確認し、残りのセットアップタスクを続行できる場合に通知します。 このプロセスには最大5営業日かかることがあります。
    
- [各サブスクリプションにプレミアム Azure キーコンテナーを作成する](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [各キーコンテナーにアクセス許可を割り当てる](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [キーコンテナーでの論理削除を有効にして、確認します。](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [キーを作成またはインポートすることによって、各キーコンテナーにキーを追加する](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [キーの回復レベルを確認する](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [Azure Key Vault のバックアップ](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [Azure Key Vault 構成設定を検証する](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [各 Azure Key Vault キーの URI を取得する](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**Office 365:**
  
Exchange Online と Skype for Business:
  
- [Exchange Online と Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [メールボックスに DEP を割り当てる](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [メールボックスの暗号化を検証する](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online と OneDrive for Business:
  
- [SharePoint Online と OneDrive for business の各 geo にデータ暗号化ポリシー (DEP) を作成する](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [グループサイト、チームサイト、および OneDrive for Business の暗号化を検証する](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Azure Key Vault のタスクを完了し、顧客キーの Microsoft FastTrack を管理する
<a name="AzureSteps"> </a>

Office 365 の顧客キーを設定するために、Azure Key Vault でこれらのタスクを完了します。 これらの手順は、Exchange Online と Skype for business、SharePoint Online と OneDrive for business、または Office 365 でサポートされているすべてのサービスに対して、顧客キーを設定するかどうかにかかわらず実行する必要があります。
  
### <a name="create-two-new-azure-subscriptions"></a>2つの新しい Azure サブスクリプションを作成する
<a name="Create2newsubs"> </a>

顧客キーには、2つの Azure サブスクリプションが必要です。 ベストプラクティスとして、Microsoft では、顧客キーと共に使用するために新しい Azure サブスクリプションを作成することをお勧めします。 Azure Key Vault キーは、同じ Azure Active Directory (AAD) テナント内のアプリケーションに対してのみ承認できます。この新しいサブスクリプションは、DEPs が割り当てられている Office 365 組織で使用されているものと同じ Azure AD テナントを使用して作成する必要があります。 たとえば、Office 365 組織のグローバル管理者特権を持つ職場または学校のアカウントを使用します。 詳細な手順については、「[組織としての Azure へのサインアップ](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)」を参照してください。
  
> [!IMPORTANT]
> 顧客キーには、データ暗号化ポリシー (DEP) ごとに2つのキーが必要です。 これを実現するためには、2つの Azure サブスクリプションを作成する必要があります。 ベストプラクティスとして、組織のメンバーごとに、各サブスクリプションで1つのキーを構成することをお勧めします。 さらに、これらの Azure サブスクリプションは、Office 365 の暗号化キーを管理するためにのみ使用してください。 これにより、オペレーターのいずれかが偶然、故意、または悪意によって削除された場合や、自分が責任を持つキーを誤って管理した場合に、組織が保護されます。 <br/> 顧客キーで使用するために Azure Key Vault リソースの管理にのみ使用される新しい Azure サブスクリプションをセットアップすることをお勧めします。 組織に対して作成できる Azure サブスクリプションの数に実際に制限はありません。 これらのベストプラクティスに従うことで、顧客キーによって使用されるリソースの管理を支援しながら、人的エラーの影響を最小限に抑えることができます。 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Office 365 の顧客キーを有効にするための要求を送信する
<a name="FastTrack"> </a>

Azure の手順を完了したら、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)で提供要求を提出する必要があります。 FastTrack web ポータルを通じて要求を送信すると、Microsoft は、提供された Azure Key Vault 構成データと連絡先情報を検証します。 組織の承認済みの担当者に関する提供フォームで行う選択は、重要であり、顧客のキーの登録を完了するために必要です。 フォームで選択する組織の責任者は、顧客キーデータ暗号化ポリシーで使用されているすべてのキーを取り消して破棄するためのすべての要求の信頼性を確保するために使用されます。 この手順を1回実行する必要があります。これを行うには、Exchange Online と Skype for business の使用をサポートするための顧客キーを有効にし、SharePoint Online と OneDrive for business の顧客キーを再度アクティブにします。
  
顧客キーを有効にするオファーを提出するには、次の手順を実行します。
  
1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)にログインします。
    
2. ログインしたら、**ダッシュボード**を参照します。
    
3. [**提供**] を選択し、現在のサービスの一覧を確認します。
    
4. 適用するオファーの詳細については、「**詳細情報**」を選択します。 
    
  - **Exchange Online と Skype For business:**「 **Exchange サービスの顧客キー** 」で、[**詳細情報**] を選択します。 
    
  - **SharePoint Online と OneDrive For business:**「 **SharePoint および OneDrive For business のお客様キー** 」を**参照**してください。 
    
5. [**提供の詳細**] ページで、[**要求の作成**] を選択します。
    
6. 提供フォームで該当するすべての詳細と要求された情報を記入します。 暗号化キーとデータを永続的に、元に戻れないように承認する組織の責任者に対して、特定の選択について特に注目してください。 フォームが完成したら、[**送信**] を選択します。
    
    このプロセスは、Microsoft が要求を通知した後、最大5営業日かかることがあります。
    
7. 以下の必須の [保持期間] に進みます。
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure サブスクリプションを登録して必須の保持期間を使用する
<a name="RegisterSubsforMRP"> </a>

ルート暗号化キーが一時的または完全に失われると、非常に破壊的または重大な操作によってデータが失われる可能性があります。 このため、顧客キーで使用されるリソースには強力な保護が必要です。 顧客キーと共に使用されるすべての Azure リソースは、既定の構成を超える保護メカニズムを提供します。 Azure サブスクリプションは、即時および irrevocable のキャンセルを防止するようにタグ付けまたは登録することができます。 これは、必須の保持期間の登録と呼ばれます。 必須の保持期間に Azure サブスクリプションを登録するために必要な手順は、Office 365 チームとの共同作業が必要です。 このプロセスには、1 ~ 5 営業日かかることがあります。 以前は、これは「キャンセルしない」と呼ばれることがありました。
  
Office 365 チームに連絡する前に、顧客キーで使用する各 Azure サブスクリプションに対して次の手順を実行する必要があります。
  
1. Azure PowerShell を使用して Azure サブスクリプションにログインします。 手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)してログインする」を参照してください。
    
2. AzureRmProviderFeature コマンドレットを実行して、必須の保持期間を使用するようにサブスクリプションを登録します。
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. プロセスを完了させるために、Microsoft にお問い合わせください。 SharePoint および OneDrive for Business チームについては、 [spock@microsoft.com](mailto:spock@microsoft.com)にお問い合わせください。 Exchange Online と Skype for Business の場合は、 [exock@microsoft.com](mailto:exock@microsoft.com)にお問い合わせください。 このプロセスを完了するためのサービスレベル契約 (SLA) は、Microsoft が事前通知 (および検証) した後で、サブスクリプションを必須の保持期間を使用するように登録した後、5営業日です。 メールに次のものを含めます。
    
    **件名**: \<*テナントの完全修飾ドメイン名*の顧客キー\> 
    
    **本文**: 必須の保持期間を最終処理するサブスクリプション id。 
    
4. 登録が完了したことを Microsoft から通知されたら、次のように AzureRmProviderFeature コマンドレットを実行して、登録の状態を確認します。
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. AzureRmProviderFeature コマンドレットの**登録状態**プロパティが [**登録済み**] の値を返すことを確認した後、次のコマンドを実行してプロセスを完了します。
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>各サブスクリプションにプレミアム Azure キーコンテナーを作成する
<a name="CreateKeyVault"> </a>

キーコンテナーを作成する手順については、「azure[キーコンテナー](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)の概要」で説明されています。このガイドでは、azure PowerShell のインストールと起動、azure サブスクリプションへの接続、リソースグループの作成、およびその場所でのキーコンテナーの作成を実行する方法について説明します。リソースグループ。
  
キーコンテナーを作成する場合、SKU: Standard または Premium のどちらかを選択する必要があります。 標準 SKU を使用すると、Azure Key Vault キーがソフトウェアで保護されます。ハードウェアセキュリティモジュール (HSM) キー保護はありません。また、Premium SKU では、重要な資格情報のキーを保護するために Hsm を使用することができます。 顧客キーは、いずれかの SKU を使用するキーコンテナーを受け入れますが、Microsoft は Premium SKU のみを使用することを強くお勧めします。 どちらの種類のキーを使用する操作のコストも同じであるため、コストの唯一の違いは、各 HSM で保護されたキーの月ごとのコストです。 詳細については、「[主要な資格情報](https://azure.microsoft.com/pricing/details/key-vault/)」を参照してください。 
  
> [!IMPORTANT]
> プレミアム SKU キーコンテナーおよび HSM で保護された、運用データ用のキーを使用して、テストおよび検証の目的で標準的な SKU キーボルトとキーのみを使用します。 
  
顧客キーを使用する Office 365 サービスごとに、作成した2つの Azure サブスクリプションのそれぞれにキーコンテナーを作成します。 たとえば、Exchange Online と Skype for business のみ、または SharePoint Online と OneDrive for business の場合のみ、ボルトのペアを1つだけ作成します。 Exchange Online と SharePoint Online の両方で顧客キーを有効にするには、キーコンテナーの2つのペアを作成します。
  
資格を与えるために使用する DEP の使用目的を反映する、キーコンテナーの名前付け規則を使用します。 命名規則の推奨事項については、以下の「ベストプラクティス」セクションを参照してください。
  
各データ暗号化ポリシーに対して、独立したコンテナーのセットを作成します。 Exchange Online の場合、データ暗号化ポリシーの範囲は、そのポリシーをメールボックスに割り当てるときに選択されます。 メールボックスに割り当てることのできるポリシーは1つだけで、最大50のポリシーを作成できます。 SharePoint Online では、ポリシーの範囲として、組織内のすべてのデータが地理的な場所または geo に含まれます。
  
キーコンテナーの作成には、Azure リソースグループの作成も必要です。これは、キーコンテナーにはストレージ容量が必要です (非常に小さい)。また、キーヴォールトログが有効になっている場合は、保存されたデータも生成します。 ベストプラクティスとして、Microsoft では、個別の管理者を使用して各リソースグループを管理することをお勧めします。管理者は、関連するすべての顧客キーリソースを管理する一連の管理者と連携しています。
  
> [!IMPORTANT]
> 可用性を最大限にするには、Office 365 サービスの近くにある地域にキーコンテナーが存在する必要があります。 たとえば、北米に Exchange Online 組織がある場合は、北アメリカにキーコンテナーを配置します。 Exchange Online 組織がヨーロッパの場合は、重要な資格を欧州に配置します。<br/>キーコンテナーに共通のプレフィックスを使用します。また、重要な資格情報の使用およびスコープの省略形を含めることもできます (たとえば、コンテナーが北米に配置される Contoso SharePoint サービスの場合は、名前のペアが O365SP-NA-VaultA1 となり、Contoso-O365SP-VaultA2。 コンテナー名は Azure 内のグローバルに一意の文字列なので、目的の名前が他の Azure のお客様によって既に要求されている場合は、目的の名前のバリエーションを試す必要があります。 2017年7月の資格情報を変更することはできません。そのため、セットアップに関する計画を作成し、2番目のユーザーを使用して計画が正常に実行されることを確認することをお勧めします。<br/>可能な場合は、ペアになっていない地域にコンテナーを作成します。 ペアになっている Azure 領域は、サービス障害ドメイン間で高可用性を提供します。 そのため、地域のペアは、互いのバックアップ地域と考えることができます。 これは、1つの領域に配置されている Azure リソースが、ペア化された領域を通じて自動的にフォールトトレランスを獲得することを意味します。 このため、地域がペアになっている場合に、DEP で使用される2つの資格情報領域を選択することは、2つの空き領域が使用されていることを意味します。 ほとんどの地域には2つの地域があるため、ペアになっていない地域を選択することはまだできません。 可能であれば、DEP で使用する2つのコンテナーに対して2つのペアでない地域を選択します。 これは、合計4つの可用性の領域からメリットを得られます。 詳細については、「 [Business 継続性と障害復旧 (BCDR)](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 」を参照してください。現在の地域のペアの一覧については、「Azure ペアリング領域」を参照してください。 
  
### <a name="assign-permissions-to-each-key-vault"></a>各キーコンテナーにアクセス許可を割り当てる
<a name="KeyVaultPerms"> </a>

各キーコンテナーについて、お客様の実装に応じて、顧客キーに対して3つの個別のアクセス許可セットを定義する必要があります。 たとえば、次のいずれかのアクセス許可のセットを定義する必要があります。
  
- 組織のために主要な資格情報コンテナーの日常の管理を実行する**主要な資格情報コンテナー管理者**。 これらのタスクには、backup、create、get、import、list、restore があります。 
    
    > [!IMPORTANT]
    > キーコンテナー管理者に割り当てられているアクセス許可のセットには、キーを削除するためのアクセス許可は含まれていません。 これは意図的で重要な手法です。 暗号化キーの削除は、通常、データを完全に破棄するため、通常は行われません。 ベストプラクティスとして、既定では、このアクセス許可を主要な資格情報管理者に付与しないでください。 その代わりに、主要な資格情報投稿者に対してこれを予約し、その結果を明確に理解した後に、短い期間のみ管理者に割り当てるようにしてください。 
  
    Office 365 組織のユーザーにこれらのアクセス許可を割り当てるには、azure PowerShell を使用して Azure サブスクリプションにログインします。 手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)してログインする」を参照してください。
    
- 必要なアクセス許可を割り当てるには、AzureRmKeyVaultAccessPolicy コマンドレットを実行します。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  次に例を示します。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- Azure Key Vault 自体に対する権限を変更できる**重要な資格情報投稿**者。 これらのアクセス許可を変更する必要があるのは、従業員がチームを脱退するか、チームに参加するか、重要な資格情報管理者がキーを削除または復元するためのアクセス許可を必要とする非常にまれな状況です。 この一連の主要なコンテナー投稿者は、キーコンテナーに対して**投稿者**の役割を付与する必要があります。 この役割は、Azure リソースマネージャーを使用して割り当てることができます。 詳細な手順については、「[役割ベースのアクセス制御を使用して Azure サブスクリプションリソースへのアクセスを管理する](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)」を参照してください。 サブスクリプションを作成する管理者は、このアクセス権と、他の管理者を共同作成者の役割に割り当てることができます。
    
- Exchange Online と Skype for business で顧客キーを使用する場合は、Office 365 に Exchange Online と Skype for business の代わりにキーヴォールトを使用するためのアクセス許可を付与する必要があります。 同様に、SharePoint Online と OneDrive for business で顧客キーを使用する場合は、SharePoint Online と OneDrive for business の代わりにキーコンテナーを使用するために Office 365 にアクセス許可を追加する必要があります。 Office 365 にアクセス許可を付与するには、次の構文を使用して**AzureRmKeyVaultAccessPolicy**コマンドレットを実行します。 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    詳細は次のとおりです。
    
  - *vaultname*は、作成したキーのコンテナーの名前です。 
    
  - Exchange Online と Skype for Business の場合は、 *Office 365 appID*をに置き換えます。`00000002-0000-0ff1-ce00-000000000000`
    
  - SharePoint Online と OneDrive for business の場合は、 *Office 365 appID*をに置き換えます。`00000003-0000-0ff1-ce00-000000000000`
    
  例: Exchange Online と Skype for Business のアクセス許可を設定する:
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  例: SharePoint Online と OneDrive for business の権限を設定する
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>キーコンテナーでの論理削除を有効にして、確認します。
<a name="SoftDelete"> </a>

キーをすばやく回復できると、偶然または悪意によって削除されたキーによってサービスの停止が発生する可能性が低くなります。 ユーザーキーでキーを使用する前に、この構成を (ソフト削除と呼ばれる) 有効にする必要があります。 ソフト削除を有効にすると、バックアップからの復元を行わずに、削除から90日以内にキーまたは資格を回復できます。
  
キーコンテナーでの論理削除を有効にするには、次の手順を実行します。
  
1. Windows Powershell を使用して、Azure サブスクリプションにログインします。 手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してログインする」を参照してください。
    
2. [AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault)コマンドレットを実行します。 この例では、 *vaultname*は、回復可能な削除を有効にするキーコンテナーの名前です。 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. **AzureRmKeyVault**コマンドレットを実行して、重要なコンテナーに対して論理削除が構成されていることを確認します。 重要な資格情報コンテナーに対して論理削除が適切に構成されている場合は、回復可能な削除を有効にしますか。プロパティは**True**の値を返します。 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>キーを作成またはインポートすることによって、各キーコンテナーにキーを追加する
<a name="AddKeystoKeyVault"> </a>

Azure Key Vault にキーを追加するには、2つの方法があります。キーを直接キーコンテナーに作成することも、キーをインポートすることもできます。 キーコンテナーに直接キーを作成することは、より単純な方法ですが、キーのインポートでは、キーの生成方法を完全に制御できます。
  
キーコンテナーに直接キーを作成するには、次のように[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)コマンドレットを実行します。 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

詳細は次のとおりです。
  
-  *vaultname*は、キーを作成するキーコンテナーの名前です。 
    
-  *keyname*は、新しいキーを指定する名前です。 
    
    > [!TIP]
    > キーコンテナーの場合と同様の命名規則を使用して、名前付きキーを指定します。 このようにすると、キー名のみを表示するツールでは、文字列が自己記述されます。 
  
- キーを HSM で保護する場合は、 _Destination_パラメーターの値として**hsm**を指定する必要があります。そうでない場合は、**ソフトウェア**を指定します。
    
For example,
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

キーを直接キーコンテナーにインポートするには、Thales nShield ハードウェアセキュリティモジュールを用意する必要があります。
  
一部の組織では、キーの機能を確立するためにこの方法をお勧めします。また、この方法では、次の機能も提供されます。
  
- インポートに使用されるツールセットには、Thales からの構成証明が含まれています。生成するキー交換キー (KEK) はエクスポート可能ではないため、Thales によって製造された正規の HSM の内部で生成されます。
    
- ツールセットには、Thales からの構成証明が含まれています。これは、Azure Key Vault セキュリティ world が Thales で製造された正規の HSM でも生成されたことです。 この構成証明は、Microsoft が正規の Thales ハードウェアを使用していることを証明します。
    
セキュリティグループに確認して、上記の attestations が必要かどうかを確認してください。 オンプレミスのキーを作成してキーコンテナーにインポートする詳細な手順については、「 [Azure Key vault 用に HSM で保護されたキーを生成して転送する方法](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)」を参照してください。 各キーコンテナーにキーを作成するには、Azure の手順を使用します。
  
### <a name="check-the-recovery-level-of-your-keys"></a>キーの回復レベルを確認する
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 では、Azure Key Vault サブスクリプションがキャンセルされないように設定されている必要があります。また、顧客キーで使用されるキーには、ソフト削除が有効になっています。 このことを確認するには、キーの回復レベルを参照してください。
  
キーの復旧レベルを確認するには、Azure PowerShell で、次のように AzureKeyVaultKey コマンドレットを実行します。
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

_回復レベル_プロパティが、回復**可能 + ProtectedSubscription**以外の値を返す場合は、このトピックを確認して、サブスクリプションをキャンセル不可リストに追加するすべての手順を実行していることを確認してください。各キーボルトに対して、ソフト削除が有効になっていること。
  
### <a name="backup-azure-key-vault"></a>Azure Key Vault のバックアップ
<a name="BackupAzureKeyVaultkeys"> </a>

作成またはキーへの変更の直後に、バックアップを実行し、オンラインとオフラインの両方でバックアップとストアのコピーを行います。 オフラインコピーは、物理的な安全または商用ストレージ機能などのネットワークに接続することはできません。 バックアップの少なくとも1つは、障害が発生した場合にアクセスできる場所に格納する必要があります。 バックアップ blob はキーマテリアルを復元するための唯一の手段です。キーコンテナーキーを完全に破棄するか、またはその他の方法で操作できないようにする必要があります。 Azure key vault の外部にあるキーは、キーを使用するために必要なメタデータが外部キーに存在しないため、バックアップとして認定されません。 顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。 したがって、キーをアップロードまたは作成した後に、Azure Key Vault のバックアップを作成することが重要です。
  
Azure Key Vault キーのバックアップを作成するには、次のように[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey)コマンドレットを実行します。
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

出力ファイルがサフィックス`.backup`を使用していることを確認します。
  
このコマンドレットから得られる出力ファイルは暗号化されており、Azure Key Vault の外部では使用できません。 バックアップは、バックアップが実行された Azure サブスクリプションにのみ復元できます。
  
> [!TIP]
> 出力ファイルに対して、コンテナー名とキー名の組み合わせを選択します。 これにより、ファイル名が自己記述されます。 バックアップファイルの名前が競合しないようにすることもできます。 
  
次に例を示します。
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault 構成設定を検証する
<a name="Validateconfiguration"> </a>

DEP でキーを使用する前に検証を実行することはオプションですが、強くお勧めします。 特に、手順を使用して、このトピックで説明されているもの以外のキーとボルトを設定する場合は、顧客キーを構成する前に、Azure Key Vault のリソースの状態を検証する必要があります。
  
キーに get、wrapKey、および unwrapKey 操作が有効になっていることを確認するには、次の操作を行います。
  
[AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault)コマンドレットを次のように実行します。 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

出力で、必要に応じて、アクセスポリシーと Exchange Online id (GUID) または SharePoint Online id (GUID) を探します。 上記の3つのアクセス許可のすべてを [キーへのアクセス許可] の下に表示する必要があります。
  
アクセスポリシーの構成が正しくない場合は、次のように AzureRmKeyVaultAccessPolicy コマンドレットを実行します。
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

たとえば、Exchange Online と Skype for Business の場合は次のようになります。
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

たとえば、SharePoint Online と OneDrive for business の場合は次のようになります。
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

キーの有効期限が設定されていないことを確認するには、 [AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey)コマンドレットを次のように実行します。 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

期限切れのキーを顧客キーで使用することはできず、期限切れのキーを使用して実行しようとした操作は失敗し、サービスが停止する可能性があります。 顧客キーと一緒に使用するキーに有効期限がないことを強くお勧めします。 有効期限日を設定すると、削除することはできませんが、別の日付に変更することができます。 有効期限日が設定されているキーを使用する必要がある場合は、有効期限の値を12/31/9999 に変更します。 有効期限が12/31/9999 以外の日付に設定されているキーは、Office 365 検証に合格しません。
  
12/31/9999 以外の値に設定されている有効期限を変更するには、 [AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute)コマンドレットを次のように実行します。 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 顧客キーで使用する暗号化キーに有効期限を設定しないようにします。 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>各 Azure Key Vault キーの URI を取得する
<a name="GetKeyURI"> </a>

キーコンテナーを設定してキーを追加するために Azure のすべての手順を完了したら、次のコマンドを実行して、各キーコンテナーのキーの URI を取得します。 後で各 DEP を作成して割り当てるときにこれらの Uri を使用する必要があるので、この情報は安全な場所に保存しておいてください。 このコマンドは、キーヴォールトごとに1回実行してください。
  
Azure PowerShell の場合:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Exchange Online と Skype for Business の顧客キーの設定
<a name="AzureSteps"> </a>

開始する前に、Azure Key Vault をセットアップするために必要なタスクを完了していることを確認してください。 詳細については[、「Azure Key Vault でタスクを完了する」および「Microsoft FastTrack For Customer key](controlling-your-data-using-customer-key.md#AzureSteps) 」を参照してください。 
  
Exchange Online と Skype for Business の顧客キーを設定するには、Windows PowerShell を使用して Exchange Online にリモートで接続することにより、これらの手順を実行する必要があります。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する
<a name="CreateDEP4EXOSkype"> </a>

DEP は、Azure Key Vault に格納されているキーのセットに関連付けられています。 Office 365 で、メールボックスに DEP を割り当てます。 Office 365 は、ポリシーで識別されたキーを使用して、メールボックスを暗号化します。 DEP を作成するには、前の手順で取得したキーの資格情報 Uri が必要です。 手順については[、「Azure Key Vault キーごとに URI を取得](controlling-your-data-using-customer-key.md#GetKeyURI)する」を参照してください。 
  
念頭! DEP を作成するときには、2つの異なる Azure キーボルトに存在する2つのキーを指定します。 これらのキーが、地理的冗長性を確保するために2つの独立した Azure 領域に配置されていることを確認します。
  
DEP を作成するには、次の手順を実行します。
  
1. ローカルコンピューターで、Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell を開いて次のコマンドを実行して、 [Exchange Online powershell に接続](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)します。 
    
   ```
   $UserCredential = Get-Credential
   ```

2. [Windows PowerShell 資格情報の要求] ダイアログボックスで、職場または学校のアカウント情報を入力し、[ **OK**] をクリックして、次のコマンドを入力します。 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. 次のコマンドを実行します。
    
   ```
   Import-PSSession $Session
   ```

4. DEP を作成するには、次のコマンドを入力して、新しい-DataEncryptionPolicy コマンドレットを使用します。
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   詳細は次のとおりです。
    
   -  *PolicyName*は、ポリシーに使用する名前です。 名前にスペースを含めることはできません。 たとえば、USA_mailboxes のようになります。 
    
   -  *PolicyDescription*は、ポリシーの目的を記憶するのに役立つユーザーフレンドリな説明です。 説明にはスペースを含めることができます。 たとえば、USA およびその領土のメールボックスのルートキー。 
    
   -  *KeyVaultURI1*は、ポリシー内の最初のキーの URI です。 たとえば、https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01 などです。 
    
   -  *KeyVaultURI2*は、ポリシーの2番目のキーの URI です。 たとえば、https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02 などです。 2つの Uri をコンマとスペースで区切ります。 
    
   例:
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>メールボックスに DEP を割り当てる
<a name="assignDEPtomailbox"> </a>

メールボックスの設定コマンドレットを使用して、メールボックスに DEP を割り当てます。 ポリシーを割り当てた後、Office 365 は DEP で指定されたキーを使用してメールボックスを暗号化できます。
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

ここで、 *MailboxIdParameter*はメールボックスを指定します。 メールボックスの設定コマンドレットの詳細については、「[メールボックスの設定](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)」を参照してください。
  
### <a name="validate-mailbox-encryption"></a>メールボックスの暗号化を検証する
<a name="validatemailboxencryption"> </a>

メールボックスを暗号化するには、しばらく時間がかかることがあります。 最初にポリシーを割り当てる場合、メールボックスは、サービスがメールボックスを暗号化する前に、あるデータベースから別のデータベースへの移動も完了する必要があります。 DEP を変更した後、または初めてメールボックスに DEP を割り当てるときに、暗号化の検証を試行する前に、72時間待つことをお勧めします。
  
メールボックスが暗号化されているかどうかを確認するには、Get-mailboxstatistics コマンドレットを使用します。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted プロパティは、メールボックスが暗号化されている場合は**true**の値を返し、メールボックスが暗号化されていない場合は**false**の値を返します。 

メールボックスの移動が完了するまでの時間は、最初に DEP を割り当てるメールボックスの数、およびメールボックスのサイズによって異なります。 DEP を割り当てたときから1週間後にメールボックスが暗号化されていない場合は、New-moverequest コマンドレットを使用して、暗号化されていないメールボックスのメールボックスの移動を開始します。

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: SharePoint Online と OneDrive for business の顧客キーの設定
<a name="AzureSteps"> </a>

開始する前に、Azure Key Vault をセットアップするために必要なタスクを完了していることを確認してください。 詳細については[、「Azure Key Vault でタスクを完了する」および「Microsoft FastTrack For Customer key](controlling-your-data-using-customer-key.md#AzureSteps) 」を参照してください。 
  
SharePoint Online と OneDrive for business の顧客キーを設定するには、Windows PowerShell を使用して SharePoint Online にリモートで接続することにより、これらの手順を実行する必要があります。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>SharePoint Online と OneDrive for business の各 geo にデータ暗号化ポリシー (DEP) を作成する
<a name="CreateDEP4SPOODfB"> </a>

DEP は、Azure Key Vault に格納されているキーのセットに関連付けられています。 1つの地理的な場所 (geo とも呼ばれます) 内のすべてのデータに DEP を適用します。 Office 365 の複数地域機能を使用している場合 (現在プレビュー中)、geo ごとに1つの DEP を作成できます。 複数地域を使用していない場合は、SharePoint Online と OneDrive for business で使用するために、1つの DEP を Office 365 で作成できます。 Office 365 は、DEP で識別されたキーを使用して、その地域のデータを暗号化します。 DEP を作成するには、前の手順で取得したキーの資格情報 Uri が必要です。 手順については[、「Azure Key Vault キーごとに URI を取得](controlling-your-data-using-customer-key.md#GetKeyURI)する」を参照してください。 
  
念頭! DEP を作成するときには、2つの異なる Azure キーボルトに存在する2つのキーを指定します。 これらのキーが、地理的冗長性を確保するために2つの独立した Azure 領域に配置されていることを確認します。
  
DEP を作成するには、Windows PowerShell を使用して SharePoint Online にリモートで接続する必要があります。
  
1. ローカルコンピューターで、Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [SharePoint Online Powershell に接続](https://technet.microsoft.com/library/fp161372.aspx)します。
    
2. Microsoft SharePoint Online 管理シェルで、 [get-spodataencryptionpolicy](https://technet.microsoft.com/library/mt843950.aspx)コマンドレットを次のように実行します。 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   DEP を登録すると、暗号化は geo のデータに対して開始されます。 これには、しばらく時間がかかることがあります。
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>グループサイト、チームサイト、および OneDrive for Business の暗号化を検証する
<a name="validateencryptionSPO"> </a>

Get-spodataencryptionpolicy コマンドレットを次のように実行して、暗号化の状態を確認できます。
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

このコマンドレットの出力には次のものが含まれます。
  
- 主キーの URI。
    
- セカンダリキーの URI。
    
- Geo の暗号化の状態。 次の状態が考えられます。
    
  - **未登録:** 顧客キーの暗号化はまだ適用されていません。 
    
  - **登録:** 顧客キーの暗号化が適用され、ファイルが暗号化されています。 Geo がこの状態にある場合は、暗号化の進行状況を監視できるように、地域内のサイトの割合がどれだけ完了しているかに関する情報も表示されます。 
    
  - **登録済み:** 顧客キーの暗号化が適用され、すべてのサイトのすべてのファイルが暗号化されました。 
    
  - **ローリング:** キーロールが進行中です。 Geo がこの状態にある場合は、進行状況を監視できるように、キーロール操作を完了したサイトの割合に関する情報も表示されます。 
    
## <a name="managing-customer-key-for-office-365"></a>Office 用の顧客キーの管理365
<a name="ManageCustomerKey"> </a>

Office 365 の顧客キーを設定した後、これらの追加の管理タスクを実行できます。
  
- [Azure Key Vault キーを復元する](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [顧客キーと共に使用する Azure Key Vault でキーをローリングまたは回転する](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [キーコンテナーのアクセス許可を管理する](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [メールボックスに割り当てられた DEP を決定する](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>Azure Key Vault キーを復元する
<a name="RestoreAzureKeyVaultKeys"> </a>

復元を実行する前に、ソフト削除で提供される回復機能を使用します。 ユーザーキーで使用されるすべてのキーは、ソフト削除を有効にするために必要です。 ソフト削除は、ごみ箱と同じように動作し、復元する必要がなくても最大90日の復旧が可能です。 復元は、キーまたはキーの保管が失われた場合など、極端または異常な状況でのみ必要になります。 顧客キーと一緒に使用するためにキーを復元する必要がある場合は、Azure PowerShell で、AzureKeyVaultKey コマンドレットを次のように実行します。
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

次に例を示します。
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

同じ名前を持つキーがキーコンテナーに既に存在する場合、復元操作は失敗します。 AzureKeyVaultKey は、キーの名前を含むキーのすべてのキーバージョンとすべてのメタデータを復元します。
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>顧客キーと共に使用する Azure Key Vault でキーをローリングまたは回転する
<a name="RollCKkey"> </a>

キーのローリングは、Azure Key Vault または顧客キーでは必要ありません。 さらに、HSM で保護されているキーは、実質的には危険にさらすことは不可能です。 ルートキーが悪意のある出演者に所有されている場合でも、Office 365 コードのみがその使用方法を認識しているため、これを使用してデータの暗号化を解除することはできません。 ただし、キーのロールは顧客キーでサポートされています。
  
> [!CAUTION]
> お客様キーと一緒に使用する暗号化キーをロールするのは、明確な技術的理由が存在するか、コンプライアンスの要件によってキーをロールする必要がある場合のみにしてください。 また、ポリシーに関連付けられている、またはポリシーに関連付けられていたキーは削除しないでください。 キーをロールすると、以前のキーを使用してコンテンツが暗号化されます。 たとえば、アクティブなメールボックスは頻繁に再暗号化されますが、非アクティブ、切断済み、および無効になったメールボックスは、以前のキーで暗号化されたままになります。 SharePoint Online は復元と回復のためにコンテンツのバックアップを実行するので、古いキーを使用してアーカイブされたコンテンツが残っている場合があります。 <br/> データの安全性を確保するために、SharePoint Online では一度に1つのキーロール操作を実行することはできません。 キーコンテナーで両方のキーをロールバックする場合は、最初のキーロール操作が完全に完了するまで待機する必要があります。 重要な役割の操作をさまざまな間隔でずらして、これが問題にならないようにすることをお勧めします。 
  
キーをロールすると、既存のキーの新しいバージョンが要求されます。 既存のキーの新しいバージョンを要求するために、最初にキーを作成したときと同じ構文を使用して、同じコマンドレット[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)を使用します。
  
次に例を示します。
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

この例では、 **VaultA1-Key001**という名前のキーが O365EX に既に存在して**** いるため、新しいキーバージョンが作成されます。 操作によって新しいキーバージョンが追加されます。 この操作では、以前のキーバージョンがキーのバージョン履歴で保持されるため、以前にキーを使用して暗号化されたデータを復号化することができます。 DEP に関連付けられているキーのすべてのロールアウトを完了したら、追加のコマンドレットを実行して、顧客キーが新しいキーを使用するようにする必要があります。 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Azure Key Vault でキーをロールまたは回転した後、Exchange Online と Skype for Business が新しいキーを使用できるようにする

Exchange Online と Skype for Business で使用される DEP に関連付けられている Azure キーヴォールトキーのいずれかをロールバックする場合は、次のコマンドを実行して DEP を更新し、Office 365 を有効にして新しいキーの使用を開始する必要があります。
  
Office 365 でメールボックスを暗号化するために新しいキーを使用するよう顧客キーに指示するには、次のように、Set-DataEncryptionPolicy コマンドレットを実行します。
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

48時間以内に、このポリシーを使用して暗号化されたアクティブなメールボックスは、更新されたキーに関連付けられます。 「[メールボックスに対して DEP が割り当てられているかどうかを判断](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)する」の手順を使用して、メールボックスの DataEncryptionPolicyID プロパティの値を確認します。 更新したキーが適用されると、このプロパティの値が変更されます。 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Azure Key Vault でキーをロールまたは回転した後、SharePoint Online と OneDrive for Business で新しいキーを使用できるようにする

SharePoint Online と OneDrive for business で使用される DEP に関連付けられている Azure キーヴォールトキーのいずれかをロールする場合は、 [get-spodataencryptionpolicy](https://technet.microsoft.com/library/mt843948.aspx)コマンドレットを実行して dep を更新し、Office 365 を有効にして新しいキーの使用を開始する必要があります。 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

これにより、SharePoint Online と OneDrive for business のキーロール操作が開始されます。 このアクションは、すぐには実行されません。 キーロール操作の進行状況を確認するには、次のように Get-spodataencryptionpolicy コマンドレットを実行します。
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>キーコンテナーのアクセス許可を管理する
<a name="Managekeyvaultperms"> </a>

いくつかのコマンドレットを使用して、重要な資格情報のアクセス許可を表示および削除できます。 たとえば、従業員がチームを離れるときにアクセス許可を削除する必要がある場合があります。
  
重要な資格情報コンテナーのアクセス許可を表示するには、AzureRmKeyVault コマンドレットを実行します。
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

次に例を示します。
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

管理者のアクセス許可を削除するには、AzureRmKeyVaultAccessPolicy コマンドレットを実行します。
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

次に例を示します。
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>メールボックスに割り当てられた DEP を決定する
<a name="DeterminemailboxDEP"> </a>

メールボックスに割り当てられている DEP を特定するには、Get-mailboxstatistics コマンドレットを使用します。 コマンドレットは、一意の識別子 (GUID) を返します。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

ここで、 *GeneralMailboxOrMailUserIdParameter*はメールボックスを指定します。 Get-mailboxstatistics コマンドレットの詳細については、「 [get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)」を参照してください。
  
GUID を使用して、次のコマンドレットを実行して、メールボックスが割り当てられている DEP のフレンドリ名を検索します。
  
```
Get-DataEncryptionPolicy <GUID>
```

ここで、 *guid*は、前の手順で get-mailboxstatistics コマンドレットによって返される guid です。 
  

