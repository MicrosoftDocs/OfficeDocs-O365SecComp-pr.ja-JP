---
title: 顧客キーを使用して Office 365 でデータを制御する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
description: ビジネス、SharePoint Online では、およびビジネスのための OneDrive の Exchange Online、Skype の Office 365 用の顧客のキーを設定する方法について説明します。顧客のキーを使用して、組織の暗号キーを制御し、マイクロソフトのデータ センターの残りの部分でデータの暗号化を使用する Office 365 を構成し、します。
ms.openlocfilehash: 3eeccd03b89aa5a79ceba536d3f13c7a881b6ca7
ms.sourcegitcommit: ef0bb05a0cf7974ae5083c7551ce3fe4ab7a9544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965611"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>顧客キーを使用して Office 365 でデータを制御する

顧客のキーを使用して、組織の暗号キーを制御し、マイクロソフトのデータ ・ センターの残りの部分でデータの暗号化を使用する Office 365 を構成し、します。不使用時のデータには、Exchange のオンラインと、メールボックス、および SharePoint Online に保存されているファイルに格納されているビジネス用の Skype とビジネスの OneDrive からのデータが含まれています。
  
Office 365 の顧客のキーを使用する前に、Azure を設定する必要があります。このトピックでは、作成し、必要な Azure リソースを構成するために必要な手順を説明し、Office 365 の顧客のキーを設定するための手順を提供します。Azure のセットアップが完了したら後、は、どのポリシーでは、およびそのため、メールボックス、および組織内のファイルに割り当てるには、どのキーを決定します。メールボックスと対象のポリシーを割り当てていないファイルの管理方法と Microsoft によって管理されている暗号化のポリシーを使用します。顧客のキーの詳細については、一般的な概要については、 [Office 365 のよく寄せられる質問の顧客のキー](service-encryption-with-customer-key-faq.md)を参照してください。
  
> [!IMPORTANT]
> ここでのベスト プラクティスに従うことを強くお勧めします。これらは、**ヒント**、**重要**とと呼びます。ルートの暗号化キーを持つスコープを制御するキーにより、顧客は、組織全体と同じ大きさにすることはできます。つまり、これらのキーの間違いが広範な影響を与えることができ、サービスの中断やデータの損失を取り消し不可能な可能性があります。 
  
## <a name="before-you-begin-setting-up-customer-key"></a>顧客キーの設定を開始する前に
<a name="Beforeyoustart"> </a>

作業を開始する前に、組織の適切なライセンスがあることを確認します。Office 365 の顧客のキーは、Office 365 の E5 や高度なコンプライアンス SKU で提供されています。
  
次に、このトピックの手順と概念を理解するのに[Azure キー ヴォールト](https://azure.microsoft.com/en-us/documentation/services/key-vault/)のマニュアルを確認します。また、Azure では、[テナント](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)などで使われる用語に精通のようになります。
  
顧客キーを文書などに関するフィードバックを提供するには、customerkeyfeedback@microsoft.com に、アイデア、提案、分析視点を送信します。
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>Office 365 の顧客のキーの設定の概要
<a name="Overview"> </a>

顧客キーを設定するには、これらのタスクを完了します。このトピックの残りの部分には、各タスクまたはプロセスの各手順の詳細についてをリンクする詳細な手順が用意されています。
  
**Azure および Microsoft FastTrack。**
  
Azure PowerShell にリモートで接続することによって、これらのタスクのほとんどを完了します。最良の結果を使用してバージョン 4.4.0 や Azure PowerShell の後で。
  
- [2 つの新しい Azure サブスクリプションを作成します。](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [必須の保持期間を使用するのには Azure サブスクリプションを登録します。](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    登録は、1 ~ 5 営業日かかります。
    
- [Office 365 の顧客のキーをアクティブ化する要求を送信します。](controlling-your-data-using-customer-key.md#FastTrack)
    
    2 つの新しい Azure サブスクリプションを作成した後は、適切な顧客キーの提供要求を送信するには、Microsoft FastTrack ポータルでホストされている web フォームに入力する必要があります。Fasttrack というチームは、顧客のキーを使用して、アシスタンスを提供していません。Office は、単を使用すると、フォームを送信してのに、顧客キーに関連するサービスを追跡するために FastTrack ポータルを使用します。
  
顧客キーの提供を送信すると、Microsoft は、要求をレビューし、セットアップ タスクの残りの部分を行うときに通知します。最大 5 営業日をかかることができます。
    
- [サブスクリプションごとにプレミアムの Azure キー ヴォールトを作成します。](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [各キーのボルトにアクセス許可を割り当てる](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [有効にして、キー、ボルトのソフトの削除を確認](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [各キーのボルトにするか、作成またはキーをインポートすることでキーを追加します。](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [キーの回復レベルを確認します。](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [Azure キー ヴォールトをバックアップ](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [Azure キーの格納域の構成の設定を検証します。](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [各 Azure キー ヴォールト ・ キーの URI を取得します。](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**Office 365。**
  
Exchange のオンライン ビジネスの Skype.
  
- [ビジネスの Exchange Online と Skype を使用するためのデータ暗号化のポリシー (DEP) の作成します。](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [DEP をメールボックスに割り当てる](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [メールボックスの暗号化を確認します。](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint のオンライン ビジネスのための OneDrive.
  
- [各 SharePoint Online および OneDrive のビジネス地域のデータの暗号化ポリシー (DEP) を作成します。](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [グループ サイト、チーム サイト、およびビジネスのための OneDrive の暗号化を確認します。](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Azure キー ヴォールトおよび顧客キー用の Microsoft FastTrack でタスクを完了
<a name="AzureSteps"> </a>

Office 365 の顧客のキーを設定するのには、Azure のキーの保管場所にこれらのタスクを完了します。かどうかを設定する顧客のキーを Exchange Online と Skype のビジネスまたは SharePoint Online と OneDrive のビジネスのまたは Office 365 のサポートされているすべてのサービスに関係なく、次の手順を完了する必要があります。
  
### <a name="create-two-new-azure-subscriptions"></a>2 つの新しい Azure サブスクリプションを作成します。
<a name="Create2newsubs"> </a>

Azure の 2 つのサブスクリプションは、お客様のキーの必要があります。最善の方法としては、顧客のキーを使用するための新しい Azure サブスクリプションを作成することをお勧めします。Azure のキーのヴォールト ・ キーは同じ Azure Active Directory (AAD) テナントのアプリケーションの承認のみことができます、DEPs を割り当てられる Office 365 の組織で使用される同じ Azure AD テナントを使用して新しいサブスクリプションを作成する必要があります。たとえば、職場、学校、Office 365 の組織のグローバル管理者特権を持つアカウントを使用しています。詳細な手順は、[組織としての Azure にサインアップする](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)を参照してください。
  
> [!IMPORTANT]
> 顧客キーには、ポリシーごとにデータの暗号化 (DEP) の 2 つのキーが必要です。これを行うには、Azure サブスクリプションの 2 つを作成する必要があります。最善の方法としては、サブスクリプションごとに 1 つのキーを構成する組織の別のメンバーがあることをお勧めします。さらに、これら Azure サブスクリプションは、Office 365 の暗号化キーの管理にのみ使用してください。誤って、意図的に、または悪意のある削除、またはそれ以外の場合、担当するキーを mismanages、演算子のいずれかの場合に、組織を保護します。<br/> 顧客キーを使用してキー ヴォールトの Azure リソースを管理するためだけに使用されている新しい Azure サブスクリプションを設定することをお勧めします。組織の作成することができます Azure サブスクリプションの数には事実上制限はありません。これらのベスト プラクティスに従うと、顧客キーによって使用されるリソースを管理しながらヒューマン エラーの影響を最小限は。 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Office 365 の顧客のキーをアクティブ化する要求を送信します。
<a name="FastTrack"> </a>

Azure の手順を完了したら、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)のサービス リクエストを送信する必要があります。FastTrack web ポータルを通じて要求を送信した後マイクロソフトが提供した Azure キー ヴォールトの構成データおよび連絡先情報を確認します。組織の権限のある役員に関する提案フォームでの選択は重要な顧客キー登録の完了に必要です。フォームで選択した組織の責任者は失効し、顧客のキー データの暗号化ポリシーで使用されるすべてのキーを破棄するための要求の信頼性を保証するために使用されます。Exchange Online と Skype ビジネスと 2 回目の SharePoint Online およびビジネスのための OneDrive の顧客のキーをアクティブにするのには顧客のキーをアクティブにするのには、この手順を 1 回する必要があります。
  
顧客キーをアクティブにするという申し出を送信するには、この手順を完了します。
  
1. 大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)にログインします。
    
2. ログオンしていることと**ダッシュ ボード**を参照します。
    
3. **用意されています**が、選択し、現在のサービスの一覧を確認します。
    
4. 該当する提供サービスの**詳細**を選択します。 
    
  - **オンラインの Exchange およびビジネス用の Skype:****Exchange の顧客のキー**の提供の**詳細**を選択します。 
    
  - **オンラインの SharePoint とビジネスの OneDrive:****SharePoint およびビジネスのための OneDrive の顧客のキー**の提供の**詳細**を選択しました。 
    
5. **特別提供の詳細**] ページで、**要求の作成**を選択します。
    
6. すべての該当する詳細情報と必要な情報提供のフォームに記入します。暗号化キーとデータの元に戻すこと、永続的な破壊を承認する承認する、選択した項目にする責任者の組織の特定の注意を払います。フォームが完了したら、**送信**を選択します。
    
    処理が完了するまでの 5 営業日後、Microsoft は、要求が通知されています。
    
7. 必須の保持期間以下のセクションに進みます。
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>必須の保持期間を使用するのには Azure サブスクリプションを登録します。
<a name="RegisterSubsforMRP"> </a>

暗号化キーのルートの一時的または永続的な損失は、支障をきたすまたはサービスの操作にも壊滅的なことができ、データの損失が発生することができます。このため、顧客のキーで使用するリソースには、強力な保護が必要があります。顧客キーで使用されているすべての Azure リソースは、既定の構成以外の保護メカニズムを提供します。Azure サブスクリプションは、タグ付けまたは即時かつ取消不能なキャンセルを回避する方法で登録できます。これは必須の保持期間の登録と呼ばれます。必須の保持期間の Azure サブスクリプションを登録するための手順には、Office 365 チームとの共同作業が必要です。このプロセスは、1 ~ 5 営業日かかることができます。以前は、これとも呼ば [キャンセルの操作を行います] です。
  
Office 365 チームに問い合わせる前に顧客のキーを使用する Azure サブスクリプションごとに次の手順を行う必要があります。
  
1. Azure PowerShell で Azure サービスにログインします。手順については、 [Azure の PowerShell を使用してログイン](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)を参照してください。
    
2. 必須の保持期間を使用するのには、サブスクリプションを登録するのにはレジスタ AzureRmProviderFeature コマンドレットを実行します。
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. プロセスを終了するのには Microsoft に問い合わせてください。SharePoint およびビジネスのチームの OneDrive は、 [spock@microsoft.com](mailto:spock@microsoft.com)をにお問い合わせください。Exchange Online は、ビジネスの Skype [exock@microsoft.com](mailto:exock@microsoft.com)をにお問い合わせください。サービス レベル契約 (SLA) 必須の保持期間を使用するのには、サブスクリプションを登録するこのプロセスの完了には、マイクロソフトが通知を受け取る (および検証された) した後、5 営業日以内にします。電子メールに次のとおりです。
    
    **件名**: 顧客のキーの\< *、テナントの完全修飾ドメイン名*\> 
    
    **本文**: 必須の保持期間の終了するサブスクリプションの Id です。 
    
4. 登録が完了しているマイクロソフトからの通知が表示されたら、次のように Get AzureRmProviderFeature コマンドレットを実行することによって、登録の状態を確認します。
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. Get AzureRmProviderFeature コマンドレットの**登録の状態**プロパティが**登録されている**の値を返すことを確認した後、プロセスを完了するのには次のコマンドを実行します。
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>サブスクリプションごとにプレミアムの Azure キー ヴォールトを作成します。
<a name="CreateKeyVault"> </a>

キーのボルトを作成する手順は、 [Azure のキーのボルトを使うにあたって](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)をインストールして Azure PowerShell を起動する、Azure サブスクリプションに接続する、リソース グループを作成するおよび主要ボルトを作成することでに記載されていますリソース グループです。
  
SKU を選択する必要があります主要ボルトを作成する場合: 標準またはプレミアムのいずれかです。標準の SKU のハードウェア セキュリティ モジュール (HSM) キーの保護はありません - ソフトウェアで保護する Azure キー ヴォールト ・ キーを使うと、プレミアム SKU キー ヴォールト ・ キーの保護に Hsm を使用できます。プレミアム SKU のみを使用することを強くお勧めしているにもかかわらず、顧客キーはいずれかの SKU を使用するキーのボルトを受け入れます。いずれかの種類のキー操作のコストは、コストの唯一の違いが HSM で保護されたキーはごとに 1 か月あたりのコストであるためです。詳細については、[キーのボルトの価格](https://azure.microsoft.com/pricing/details/key-vault/)を参照してください。 
  
> [!IMPORTANT]
> プレミアム SKU キー ボルトと HSM で保護されたキーを使用して、本番データとだけ標準的な SKU キー ボルトとキーを使用して、テストと検証のために。 
  
顧客キーを使用すると、Office 365 サービスごとに作成した 2 つの Azure サブスクリプションの各主要ボルトを作成します。たとえば、Exchange Online とはビジネスのみまたは SharePoint Online の Skype とビジネスだけの OneDrive、ボルトの 1 つだけのペアを作成します。Exchange Online と SharePoint Online の両方の顧客のキーを有効にするのには、キーの貯蔵庫の 2 つのペアを作成します。
  
関連付けるボルト DEP の使用目的を表すキーのボルトの名前付け規則を使用します。命名規則に関する推奨事項はベスト ・ プラクティスの項を参照してください。
  
1 組の独立した一連のデータの暗号化ポリシーごとにボルトを作成します。オンラインの Exchange のメールボックスにポリシーを割り当てるとしてデータの暗号化ポリシーのスコープが選択されます。メールボックスが割り当てられている 1 つだけのポリシーを持つことができ、50 台までのポリシーを作成することができます。SharePoint Online には、ポリシーのスコープは、地理的位置、または地域で組織内のデータのすべてです。
  
ボルトのキーの作成は、(ただし、非常に小さい)、キーのボルトがストレージ容量を必要し、ログイン、キーのボルトが有効な場合も生成保存されているデータなので、Azure のリソース グループの作成が必要です。ベスト プラクティスとしては、一連の関連するすべての顧客キー リソースを管理する管理者の配置の管理と、各リソース グループを管理するために個別の管理者を使用してをお勧めします。
  
> [!IMPORTANT]
> 可用性を最大化するのには、Office 365 サービスに近い地域でキー、ボルトがあります。たとえば、Exchange Online 組織は、北アメリカでは、北米でのキー、ボルトを配置します。Exchange Online 組織は、ヨーロッパでは場合、は、ヨーロッパのキー、ボルトを配置します。<br/>キーのボルトに共通のプレフィックスを使用し、使用の省略形およびボルトのキーとキーの範囲が含まれます (contoso 社の SharePoint サービスが可能な 1 組の名前の北米でのボルトの位置は、Contoso O365SP NA VaultA1 用など、Contoso O365SP-「na」と VaultA2。ボルトの名前は、目的の名前は既に Azure の他の顧客が要求している場合に、目的の名前のバリエーションを実行する必要がありますので、Azure 内のグローバル一意識別の文字列です。2017年 7 月年ヴォールト ・名前は変更できません、ため、セットアップを記述した計画があり、プランが正しく実行されたことを確認するのには 2 番目のユーザーを使用するが最適です。<br/>可能な場合は、ペアになっていない地域で、ボルトを作成します。Azure の一対の領域は、サービスの障害ドメイン間で高可用性を提供します。したがって、地域のペアは互いのバックアップ領域として。これは、1 つの領域に配置される Azure のリソースが自動的にペアリングされている地域によってフォールト トレランスを獲得することを意味します。このため、場所、地域では、ペアは、可用性の 2 つの領域の合計のみを使用していることを意味する DEP で使用される 2 つのボルトの領域を選択します。ほとんどの地域では、まだ非対応の地域を選択することがないために 2 つの領域をあるだけです。可能な場合、dep が原因で使用される 2 つのボルトの 2 つのペアになっていない領域を選択します。可用性の 4 つの領域の合計からこれを利用できます。詳細についてを参照してください[ビジネス継続性/災害復旧 (BCDR): Azure 対応の地域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)の地域のペアの現在のリストです。 
  
### <a name="assign-permissions-to-each-key-vault"></a>各キーのボルトにアクセス許可を割り当てる
<a name="KeyVaultPerms"> </a>

各キーのボルトの実装によって、お客様のキーのアクセス許可の 3 つの異なるセットを定義する必要があります。たとえば、次の各アクセス許可の 1 つのセットを定義する必要があります。
  
- 組織のキー、ボルトの日常的な管理を実行する**キー ヴォールトの管理者**です。これらのタスクのバックアップ、作成、取得、] ボックスの一覧をインポートします。 および復元します。 
    
    > [!IMPORTANT]
    > キー ヴォールトの管理者に割り当てられたアクセス許可のセットでは、キーを削除するアクセス許可は含まれません。これは意図的なものと、重要なプラクティスです。暗号化キーを削除する通常行わないと、データが破壊されるため永続的に行うためです。最善の方法としてはこのアクセス権を付与キー ヴォールトの管理者に既定でします。キー ヴォールトの貢献者にこれを予約し、のみに割り当てることを短期的に管理者の影響を明確に理解を理解するとします。 
  
    Office 365 組織内のユーザーにこれらのアクセス許可を割り当てるには Azure PowerShell で Azure サービスにログインします。手順については、 [Azure の PowerShell を使用してログイン](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)を参照してください。
    
- 必要なアクセス許可を割り当てるセット AzureRmKeyVaultAccessPolicy コマンドレットを実行するには。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  次に例を示します。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- 自体ように Azure キー ボルトへのアクセス許可が変更可能な**キーのボルトの貢献者**。従業員のままにして、チームに参加、または非常にまれな状況で、キーのヴォールティング管理者正当に必要があることを削除するか、キーを復元するためのアクセス許可と、これらのアクセス許可を変更する必要があります。この一連のキー ヴォールト ・投稿者のニーズがキー、ボルト、**寄稿者**の役割を与えられます。Azure のリソース マネージャーを使用して、このロールを割り当てることができます。詳細な手順は、 [Use Role-Based、Azure サブスクリプションのリソースへのアクセスを管理するためのアクセス制御](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)を参照してください。サブスクリプションを作成した管理者は、寄稿者の役割を他の管理者を割り当てる機能だけでなく暗黙的に、このアクセス権を持ちます。
    
- Exchange Online と Skype をビジネスの顧客キーを使用する場合は、Exchange Online と Skype のためのキーのボルトを使用して、ビジネスのために Office 365 にアクセス権を付与する必要があります。同様に、SharePoint Online および OneDrive とビジネスの顧客キーを使用する場合は、SharePoint Online と OneDrive のためのキーのボルトを使用して、ビジネスのために Office 365 にアクセス許可を追加する必要があります。Office 365 にアクセス許可を与える、次の構文を使用して**セット AzureRmKeyVaultAccessPolicy**コマンドレットを実行します。 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    詳細は次のとおりです。
    
  - *vaultname*は、作成したキーのボルトの名前です。 
    
  - Exchange Online は、ビジネスの Skype と*Office 365 の appID*が置き換えられること`00000002-0000-0ff1-ce00-000000000000`
    
  - SharePoint Online をビジネスのための OneDrive と*Office 365 の appID*が置き換えられる`00000003-0000-0ff1-ce00-000000000000`
    
  例: は、Exchange のオンラインおよびビジネス用の Skype のアクセス許可を設定します。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  例: SharePoint Online およびビジネスのための OneDrive のアクセス許可を設定します。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>有効にして、キー、ボルトのソフトの削除を確認
<a name="SoftDelete"> </a>

キーをすばやく回復できますが、ときに、誤ってまたは悪意のある削除されたキーのための拡張サービス障害が発生する可能性は低くしています。呼ばれるソフト削除では、お客様のキーを使用して、キーを使用する前に、この構成を有効にする必要があります。ソフト削除の有効化を使用すると、削除の 90 日以内にバックアップから復元することがなくキーまたはボルトを回復します。
  
キー、ボルトのソフトの削除を有効にするには、これらの操作を行います。
  
1. Windows Powershell で Azure サービスにログインします。手順については、 [Azure の PowerShell を使用してログイン](https://docs.microsoft.com/powershell/azure/authenticate-azureps)を参照してください。
    
2. [Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault)コマンドレットを実行します。この例では、 *vaultname*は、ソフトの削除を有効にするキーのボルトの名です。 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. ソフト削除は**Get AzureRmKeyVault**コマンドレットを実行してキーのボルトの構成を確認します。ソフトの削除が正しく設定されてキーのボルトの場合、ソフトは有効を削除しますか。プロパティは、 **True**の値を返します。 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>各キーのボルトにするか、作成またはキーをインポートすることでキーを追加します。
<a name="AddKeystoKeyVault"> </a>

Azure キーのボルトにキーを追加するのには 2 つの方法があります。キーを作成するにはキーのボルトで直接、またはキーをインポートすることができます。キーの保管場所に直接キーを作成する方が、簡単なキーを生成する方法を完全に制御を提供するキーをインポートするときに。
  
キーをボルトに直接キーを作成するには、次のように[追加 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)コマンドレットを実行します。 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

詳細は次のとおりです。
  
-  *vaultname*は、主キーを作成するボルトの名前です。 
    
-  *キー名*は、新しいキーを指定する名前です。 
    
    > [!TIP]
    > 前述のキーの貯蔵庫のような名前付け規則を使用して、キーの名前を指定します。この方法では、キーの名前のみを表示するツールでは、文字列は、自己言及的な。 
  
- HSM にキーを保護する場合は、**ソフトウェア**を指定することは、 **HSM**を_コピー先_のパラメーターの値として指定を確認します。
    
たとえば、次のように使用します。
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

キーをボルトに直接には、キーをインポートするには、Thales nShield ハードウェア セキュリティ モジュールがある必要があります。
  
組織によっては、キーと、この provenance を確立するには、このアプローチを選択する方法には、次も用意されています。
  
- インポートに使用するツールセットは、Thales を生成するキーの暗号化に使用されるキー交換キー (KEK) がエクスポート可能ではないことの証明が含まれています、Thales によって製造された正規品である HSM 内で生成されるが。
    
- ツールセットには、Thales の Thales 製の正規品である HSM にキー ヴォールトの Azure のセキュリティ環境が生成されたもの証明が含まれています。この証明は、マイクロソフトが本物である Thales のハードウェアを使用しても自分に証明します。
    
上記の attestations が必要なかどうかを決定するセキュリティ グループを確認します。キーの設置型を作成し、キー、ボルトにインポートする手順の詳細を[生成し、Azure キー ヴォールト用の HSM で保護されたキーを転送する方法](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)を参照してください。各キーの保管場所にキーを作成するのにには、Azure の手順を使用します。
  
### <a name="check-the-recovery-level-of-your-keys"></a>キーの回復レベルを確認します。
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 では、キー ヴォールトの Azure サブスクリプションをキャンセルしないでに設定されていると、お客様のキーに使用するキーがあるソフトの削除が有効になっている必要があります。これを確認するには、キーの回復レベルを見る。
  
Azure の PowerShell で、キーの回復レベルを確認するのには次のように Get AzureKeyVaultKey コマンドレットを実行します。
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

_リカバリ ・ レベル_のプロパティには、**回復可能な + ProtectedSubscription**の値以外の値が返された場合は、このトピックを参照し、すべてのサブスクリプションをキャンセルしないでリストに配置する手順を従っていることを確認する必要があり、あるソフト削除の各キー、ボルトの上を有効にします。
  
### <a name="backup-azure-key-vault"></a>Azure キー ヴォールトをバックアップ
<a name="BackupAzureKeyVaultkeys"> </a>

すぐ後に作成または変更しても、キーをバックアップを実行し、バックアップ、オンラインとオフラインの両方のコピーを格納します。オフライン コピーする必要があります接続されていないネットワークなど、安全または商用ストレージの物理的な施設にします。バックアップのコピーを少なくとも 1 つは、災害発生時にアクセスできる場所に格納されている必要があります。バックアップの blob は、キーのヴォールト ・ キーまたはする必要が完全に破棄しなくなる場合それ以外の場合、キー マテリアルを復元する唯一の手段です。Azure キー ボルトの外部に、Azure のキーのボルトにインポートされたキーの対象とならないバックアップとして外部キーを使用して顧客のキー、キーを使用するのに必要なメタデータが存在しないためです。顧客キーを使用して、リストア ・ オペレーションの Azure キー ヴォールトから作成されたバックアップのみを使用できます。したがって、キーをアップロードまたは作成したら、Azure キー ヴォールトのバックアップが行われることが重要です。
  
Azure キー ヴォールト ・ キーのバックアップを作成するには、次のように[バックアップ AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey)コマンドレットを実行します。
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

出力ファイルがサフィックスを使用することを確認`.backup`。
  
このコマンドレットの結果の出力ファイルは暗号化されており、Azure キー ヴォールト以外では使用できません。バックアップは、バックアップが行われた Azure サブスクリプションにのみ復元できます。
  
> [!TIP]
> 出力ファイルでは、ボルトの名前とキーの名前の組み合わせを選択します。これにより、ファイル名は自己記述形式します。それも使用すれば、バックアップ ファイル名が競合していないこと。 
  
次に例を示します。
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure キーの格納域の構成の設定を検証します。
<a name="Validateconfiguration"> </a>

キーを使用して、DEP で前に検証を実行することはオプションですが、強くお勧めです。具体的には、このトピックで説明されていないその他のキーとボルトを設定する手順を使用する場合、顧客のキーを構成する前に、Azure キー ヴォールト ・ リソースの稼働状態を検証する必要があります。
  
キーがある、wrapKey、および unwrapKey の操作が有効になっていることを確認するには。
  
次のように、 [Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault)コマンドレットを実行します。 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

出力では、適切なアクセス ポリシーおよび Exchange のオンライン id (GUID) または SharePoint Online id (GUID) を確認します。上のアクセス許可の 3 つのすべてはする必要がありますキーを [アクセス許可表示されます。
  
アクセス ポリシーの構成が正しくない場合、次のようにセット AzureRmKeyVaultAccessPolicy コマンドレットを実行します。
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

たとえば、Exchange Online とビジネス用の Skype。
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

たとえば、SharePoint Online およびビジネスのための OneDrive。
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

次のように、 [Get AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey)コマンドレットを実行する、キーの有効期限が設定されていないことを確認します。 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

顧客キーで、有効期限の切れたキーを使用することはできませんし、有効期限の切れたキーを使用して実行しようとする操作は失敗し、サービスの停止が発生する可能性があります。顧客キーに使用されるキーに有効期限がないことを強くお勧めします。有効期限の日付、セット、削除することはできませんが、別の日付に変更することができます。キーを使用する有効期限を設定する場合は、12/31/9999 に有効期限の値を変更します。有効期限の日付を使用してキーは、12/31/9999 が Office 365 の検証を通過しない以外の日付に設定します。
  
12/31/9999 以外の値に設定されている有効期限の日付を変更するには、次のように[セット AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute)コマンドレットを実行します。 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 顧客キーで使用する暗号化キーの有効期限を設定しません。 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>各 Azure キー ヴォールト ・ キーの URI を取得します。
<a name="GetKeyURI"> </a>

キー、ボルトを設定するのには Azure 内のすべての手順を完了すると、キーを追加、各キーの保管場所にキーの URI を取得するのには次のコマンドを実行します。これらを使用する必要があります。 Uri を作成して後で、それぞれの DEP を割り当てるときは、安全な場所でこの情報を保存するようにします。各キーのボルトには、このコマンドを実行することを忘れないでください。
  
Azure PowerShell: の
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Exchange のオンラインであり、ビジネス用の Skype の顧客のキーを設定します。
<a name="AzureSteps"> </a>

作業を開始する前に、Azure キー ヴォールトを設定するために必要なタスクを完了したことを確認します。については、 [Azure キー ヴォールトおよび顧客キー用の Microsoft FastTrack でタスクの実行](controlling-your-data-using-customer-key.md#AzureSteps)を参照してください。 
  
Exchange オンラインであり、ビジネスの Skype の顧客のキーを設定するには、Windows PowerShell を Exchange Online にリモートで接続して、次の手順を実行する必要があります。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>ビジネスの Exchange Online と Skype を使用するためのデータ暗号化のポリシー (DEP) の作成します。
<a name="CreateDEP4EXOSkype"> </a>

DEP は、Azure のキーの保管場所に保存されているキーのセットに関連付けられます。DEP は、Office 365 にメールボックスを割り当てます。Office 365 メールボックスを暗号化するために、ポリシーで指定されたキーが使用されます。DEP を作成するには、キーのボルトの Uri が以前のバージョンを取得する必要があります。手順については、[各 Azure キー ヴォールト ・ キーの URI を取得](controlling-your-data-using-customer-key.md#GetKeyURI)を参照してください。 
  
忘れないでください!DEP を作成するときは、2 つの異なる Azure キー ヴォールト内に存在する 2 つのキーを指定します。これらのキーは、geo の冗長性を確保するのには 2 つの独立した Azure 領域に配置されていることを確認します。
  
DEP を作成するには、次の手順を実行します。
  
1. 職場または学校のアカウントを Office 365 組織で Windows PowerShell を開き、次のコマンドを実行している[Exchange のオンライン PowerShell への接続](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)をグローバル管理者のアクセス許可を持つを使用して、ローカル コンピューター上です。 
    
   ```
   $UserCredential = Get-Credential
   ```

2. Windows PowerShell の資格情報の要求] ダイアログ ボックスで、作業時間を入力またはアカウント情報の学校 **[ok]** を次のコマンドを入力します。 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. 次のコマンドを実行します。
    
   ```
   Import-PSSession $Session
   ```

4. DEP を作成するには、次のコマンドを入力して新規 DataEncryptionPolicy コマンドレットを使用します。
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   詳細は次のとおりです。
    
   -  *グループ*は、ポリシーを使用する名前です。名は、スペースを含めることはできません。たとえば、USA_mailboxes です。 
    
   -  *許可*を忘れないように、ポリシーのポリシーのユーザー フレンドリな説明です。説明にスペースを含めることができます。たとえば、アメリカ合衆国およびその領土内のメールボックス用のキーをルートします。 
    
   -  *KeyVaultURI1*は、URI のポリシーでは、最初のキーです。たとえば、 https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。 
    
   -  *KeyVaultURI2*は、ポリシーでは、2 番目のキーの URI です。たとえば、 https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。コンマとスペース 2 つの Uri を分離します。 
    
   例:
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>DEP をメールボックスに割り当てる
<a name="assignDEPtomailbox"> </a>

セット-メールボックス コマンドレットを使用して、DEP をメールボックスに割り当てます。ポリシーを割り当てると、Office 365 が、DEP. で指定したキーを使用してメールボックスを暗号化できます。
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

場所*MailboxIdParameter*は、メールボックスを指定します。セット-メールボックス コマンドレットの詳細については、[一連のメールボックス](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)を参照してください。
  
### <a name="validate-mailbox-encryption"></a>メールボックスの暗号化を確認します。
<a name="validatemailboxencryption"> </a>

メールボックスを暗号化すると、時間がかかることができます。時間ポリシーの割り当て、最初のメールボックスする必要がありますも移動を完了 1 つのデータベースから別にサービスが、メールボックスを暗号化する前にします。DEP を変更するか、最初の時間を割り当てる、DEP のメールボックスに、暗号化を検証しようとする前に、72 時間を待機することをお勧めします。
  
Get MailboxStatistics コマンドレットを使用すると、メールボックスが暗号化されているかを判断できます。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

暗号化されたチャレンジ プロパティは、メールボックスが暗号化されていない場合の値**は true**メールボックスが暗号化されている場合と**false**の値を返します。 

メールボックスの移動を完了するには、メールボックスのサイズと同様に、最初に、DEP を割り当てるためのメールボックスの数によって異なります。DEP が割り当てられた時間から 1 週間後、メールボックスが暗号化されていない場合、新規 MoveRequest コマンドレットを使用して暗号化されていないメールボックスに対するメールボックスの移動を開始します。

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: SharePoint Online およびビジネスのための OneDrive の顧客のキーを設定します。
<a name="AzureSteps"> </a>

作業を開始する前に、Azure キー ヴォールトを設定するために必要なタスクを完了したことを確認します。については、 [Azure キー ヴォールトおよび顧客キー用の Microsoft FastTrack でタスクの実行](controlling-your-data-using-customer-key.md#AzureSteps)を参照してください。 
  
SharePoint Online およびビジネスのための OneDrive の顧客のキーを設定するには、SharePoint Online では、Windows PowerShell にリモートで接続することによって、次の手順を実行する必要があります。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>各 SharePoint Online および OneDrive のビジネス地域のデータの暗号化ポリシー (DEP) を作成します。
<a name="CreateDEP4SPOODfB"> </a>

DEP は、Azure のキーの保管場所に保存されているキーのセットに関連付けられます。地域とも呼ばれる 1 つの地理的位置にあるデータのすべてに、DEP を適用するとします。(プレビュー) では現在、複数地域の機能 Office 365 を使用する場合は、地域ごとの 1 つの DEP を作成できます。複数地域を使用していない場合は、ビジネスの SharePoint Online と OneDrive を使用する Office 365 の DEP の 1 つを作成できます。Office 365 は、その地域のデータを暗号化するのには、DEP で識別されるキーが使用されます。DEP を作成するには、キーのボルトの Uri が以前のバージョンを取得する必要があります。手順については、[各 Azure キー ヴォールト ・ キーの URI を取得](controlling-your-data-using-customer-key.md#GetKeyURI)を参照してください。 
  
忘れないでください!DEP を作成するときは、2 つの異なる Azure キー ヴォールト内に存在する 2 つのキーを指定します。これらのキーは、geo の冗長性を確保するのには 2 つの独立した Azure 領域に配置されていることを確認します。
  
DEP を作成するには、Windows PowerShell を使用して、SharePoint Online にリモートで接続する必要があります。
  
1. ローカル コンピューター上には、グローバル管理者アクセス許可を持つ[SharePoint オンライン Powershell への接続](https://technet.microsoft.com/library/fp161372.aspx)、Office 365 の組織で職場または学校のアカウントを使用してください。
    
2. Microsoft SharePoint オンライン管理シェルで次のように[レジスタ SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx)コマンドレットを実行します。 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   DEP を登録する場合、地域内のデータの暗号化を開始します。これにより、時間がかかることができます。
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>グループ サイト、チーム サイト、およびビジネスのための OneDrive の暗号化を確認します。
<a name="validateencryptionSPO"> </a>

次のように Get SPODataEncryptionPolicy コマンドレットを実行して、暗号化の状態をチェックできます。
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

このコマンドレットからの出力は次のとおりです。
  
- プライマリ ・ キーの URI。
    
- セカンダリ ・ キーの URI。
    
- Geo の暗号化の状態です。可能な状態は次のとおりです。
    
  - **未登録:** 顧客キー暗号方式はまだ適用されていません。 
    
  - **の登録:** 顧客キーの暗号化が適用されているし、ファイルが暗号化されています。地域がこの状態である場合も表示されます情報を地域内のサイトの割合は、完全な暗号化の進行状況を監視することができます。 
    
  - **登録:** 顧客キーの暗号化が適用されている、およびすべてのサイト内のすべてのファイルが暗号化されています。 
    
  - **ローリング:** キーのロールは、実行中です。地域がこの状態である場合も表示されます情報のサイトの何パーセント完了キー操作の進行状況を監視できるようにします。 
    
## <a name="managing-customer-key-for-office-365"></a>Office 365 の顧客のキーを管理します。
<a name="ManageCustomerKey"> </a>

Office 365 の顧客のキーを設定したら後、は、これらの余分な管理作業を行うことができます。
  
- [Azure キー ヴォールト ・ キーを復元します。](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [ロールまたは顧客のキーを使用した Azure キーの保管場所にキーを回転させる](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [ヴォールトのキーのアクセス許可を管理します。](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [DEP のメールボックスに割り当てられているを決定します。](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>Azure キー ヴォールト ・ キーを復元します。
<a name="RestoreAzureKeyVaultKeys"> </a>

リストアを実行する前に、ソフトの削除が提供するリカバリ機能を使用します。顧客キーで使用されるすべてのキーは、ソフトの削除を有効にする必要があります。ソフトの削除、ごみ箱のように動作でき、回復を 90 日間を復元する必要はありません。復元は、極端なまたは異常な状況は、たとえば、キーまたはキーのボルトが失われた場合にのみ必要する必要があります。顧客のキーを使用するキーを復元する必要がある場合 Azure の PowerShell のコマンドレットを実行、復元 AzureKeyVaultKey 次のように。
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

次に例を示します。
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

キーの保管場所に同じ名前のキーが既に存在する場合、復元操作は失敗します。復元 AzureKeyVaultKey は、キーのすべてのバージョンおよびキーの名前を含むキーのすべてのメタデータを復元します。
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>ロールまたは顧客のキーを使用した Azure キーの保管場所にキーを回転させる
<a name="RollCKkey"> </a>

キーのロールでは、いずれかの Azure キー ヴォールト、顧客キーは必要ありません。さらに、HSM で保護されているキーは侵害することは事実上不可能ではありません。ルート キーが悪意のあるアクターに所持されていた場合でも、Office 365 のコードのみを使用する方法を知っているので、データを復号化に使用する際の実現可能な対策はありません。ただし、キーのローリングでは顧客のキーです。
  
> [!CAUTION]
> チェック ボックスをオフに技術的な理由が存在するか、規則の遵守要件の規定があるか、キーを展開するときに、お客様のキーを使用してに使用する暗号化キーのロールのみです。さらに、またはポリシーに関連付けられていたすべてのキーを削除できません。ありますが、キーをロールバックすると、コンテンツは暗号化以前のキーで。などのアクティブなメールボックス再暗号化される多くの場合、非アクティブなときにメールボックスが切断された場合、および無効になっている可能性がありますまだ暗号化以前のキーで。SharePoint のオンライン ・ バックアップを実行コンテンツの復元と回復のためにアーカイブされたコンテンツが古いキーを使用してありますので。<br/> データの安全を確保するには、SharePoint Online は操作を許可する複数のキーのロールを同時に実行されています。キーのロールの最初の操作が待機する必要がありますキーの両方をキーの保管場所にロールバックする場合は、完全に完了します。推奨は、さまざまな間隔で、キーのロールの操作をずらすようにこれは問題ではありません。 
  
キーをロールバックするときは、既存のキーの新しいバージョンを要求しています。既存のキーの新しいバージョンを要求するために、まずキーの作成に使用した同じ構文を使用して[追加 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)、同じコマンドレットを使用します。
  
次に例を示します。
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

この例では、 **Contoso O365EX NA VaultA1** vault の**contoso 社の O365EX-ナ-VaultA1-Key001**を既にという名前のキーが存在するため、新しいキー バージョン作成されます。操作は、新しいキー バージョンを追加します。以前にそのキーで暗号化されたデータが暗号化を解除できるように、この操作は、以前のキー、キーのバージョン履歴では、バージョンを保持します。DEP に関連付けられている任意のキーのローリングを完了すると、顧客キーは新しいキーの使用を開始することを確認するのには追加のコマンドレットを実行してください。 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Exchange オンラインで Skype のビジネス ロールまたは Azure キーの保管場所にキーを回転した後、新しいキーを使用するを有効にします。

いずれかに移動すると、DEP に関連付けられている Azure キー ヴォールトのキーを使用と、Exchange オンライン Skype ビジネス、DEP を更新し、新しいキーを使用する Office 365 を有効にするには、次のコマンドを実行する必要があります。
  
顧客キーを暗号化するために新しいキーを使用するように指示するのには、Office 365 のメールボックスは、セット DataEncryptionPolicy コマンドレットをとおり実行します。
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

48 時間以内は、このポリシーを使用して暗号化のアクティブなメールボックスが更新されたキーに関連付けられているになります。メールボックスの DataEncryptionPolicyID プロパティの値を確認するのには[特定のメールボックスに割り当てられている DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)で手順を使用します。更新キーが適用された後、このプロパティの値が変更されます。 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>SharePoint Online およびビジネスのための OneDrive ロールまたは Azure キーの保管場所にキーを回転した後、新しいキーを使用するを有効にします。

いずれかに移動すると、DEP に関連付けられている Azure キー ヴォールトのキーを使用し、OneDrive、SharePoint Online でビジネス、DEP を更新し、新しいキーを使用する Office 365 を有効にする[更新プログラム SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx)コマンドレットを実行する必要があります。 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

SharePoint Online およびビジネスのための OneDrive のキー操作を開始します。この操作は即時ではありません。キーの操作をロールバックの進行状況を表示するには、次のように、Get SPODataEncryptionPolicy コマンドレットを実行します。
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>ヴォールトのキーのアクセス許可を管理します。
<a name="Managekeyvaultperms"> </a>

利用できるいくつかのコマンドレットを表示し、必要であれば、ボルトのキーのアクセス許可を削除することができます。従業員がチームを離れたときなど、アクセス許可を削除する必要があります。
  
ヴォールトのキーのアクセス許可を表示するには、Get AzureRmKeyVault コマンドレットを実行します。
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

次に例を示します。
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

管理者のアクセス許可を削除するには、削除 AzureRmKeyVaultAccessPolicy コマンドレットを実行します。
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

次に例を示します。
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>DEP のメールボックスに割り当てられているを決定します。
<a name="DeterminemailboxDEP"> </a>

DEP のメールボックスに割り当てられているを確認するのには、Get MailboxStatistics コマンドレットを使用します。コマンドレットでは、一意の識別子 (GUID) を返します。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

場所*GeneralMailboxOrMailUserIdParameter*は、メールボックスを指定します。Get MailboxStatistics コマンドレットの詳細については、 [Get MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)を参照してください。
  
メールボックス割り当てられている次のコマンドレットを実行して、DEP のフレンドリ名を検索するのには、GUID を使用します。
  
```
Get-DataEncryptionPolicy <GUID>
```

*GUID*は、前の手順で Get MailboxStatistics コマンドレットによって返される GUID です。 
  

