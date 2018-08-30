---
title: Office 365 Enterprise で暗号化を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Office 365 では、いくつかの暗号化機能は既定でオンにします。その他の機能は、特定のコンプライアンスや法的な要件を満たすように構成できます。
ms.openlocfilehash: 80deced80283ac36d82ac15cee9af6d390c4749a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531898"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Office 365 Enterprise で暗号化を設定する

暗号化では、権限のないユーザーによって読み取られるから、コンテンツを保護できます。[Office 365 で暗号化](encryption.md)を行うことができますのでさまざまなテクノロジやメソッドを使用して、1 つ 1 つの場所を有効にするまたは暗号化を設定した位置がないです。この資料を設定したり、情報保護戦略の一部として暗号化を構成する各種の方法についての情報を提供します。 
  
> [!TIP]
> 暗号化についての技術的な詳細を検索する場合は、[テクニカル リファレンスの詳細については、Office 365 での暗号化](technical-reference-details-about-encryption.md)を参照してください。 
  
Office 365 では、いくつかの暗号化機能はデフォルトで使用可能です。追加の暗号化機能は、特定のコンプライアンスや法的な要件を満たすように構成できます。次の表では、さまざまなシナリオのいくつかの暗号化方法について説明します。
  
|**シナリオ**|**暗号化方法**|
|:-----|:-----|
|Windows コンピューターにファイルが保存されます。  <br/> |コンピューター レベルでの暗号化を実行する Windows デバイスで BitLocker を使用します。エンタープライズ管理者または IT プロフェッショナルは、マイクロソフト展開 Toolkit (MDT) を使用してこれを設定できます。[MDT BitLocker のセットアップ](https://go.microsoft.com/fwlink/?linkid=849282)を参照してください。<br/> |
|モバイル デバイスでファイルが保存されます。  <br/> |モバイル デバイスの種類によっては、既定でこれらのデバイスに保存されているファイルを暗号化します。[Office 365 でモバイル デバイス管理の機能](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)を備えたモバイル デバイスから Office 365 のデータへのアクセスを許可するかどうかを決定するポリシーを設定できます。たとえば、Office 365 のデータにアクセスするコンテンツの暗号化デバイスのみを許可するポリシーを設定できます。参照してください[を作成するデバイスのセキュリティ ポリシーを展開し、](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。<br/> Office 365 との対話をモバイル デバイスに対する追加のコントロールは、 [Microsoft Intune](https://aka.ms/qzln04)を追加することを検討することができます。[Office 365 の MDM と Microsoft Intune との間の選択](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22)を参照してください。<br/> |
|マイクロソフトのデータ センターでデータを暗号化するために使用する暗号化キーを制御する必要があります。  <br/> | Office 365 管理者は、組織の暗号化キーを制御し、マイクロソフトのデータ ・ センターの残りの部分でデータの暗号化を使用する Office 365 を構成できます。  <br/> [顧客キーを使用して Office 365 でデータを制御する](controlling-your-data-using-customer-key.md) <br/> [Office 365 のよく寄せられる質問の顧客のキー](service-encryption-with-customer-key-faq.md) <br/> |
|人は、電子メール (Exchange Online) 経由で通信しています。  <br/> | Exchange Online 管理者は、電子メールの暗号化を構成するためのいくつかのオプションがあります。これらは次のとおりです。<br/>  Azure 著作権管理 (Azure RMS) で[Office 365 のメッセージの暗号化 (ホーム)](set-up-new-message-encryption-capabilities.md)を使用して、組織の内外に暗号化されたメッセージを送信するユーザーを有効にするには  <br/>  [秒/MIME メッセージの署名と暗号化のため](https://aka.ms/c6dozg)を使用して暗号化し、電子メール メッセージにデジタル署名するには  <br/>  TLS を使用して[別の組織とセキュリティで保護されたメール フローにコネクタを設定](https://aka.ms/hs809p)するのには <br/>  [Office 365 で電子メールの暗号化](https://aka.ms/hic3f7)を参照してください。  <br/> |
|チーム サイトやドキュメント ライブラリ (ビジネスまたは SharePoint Online の OneDrive) からファイルにアクセス  <br/> |人がビジネスまたは SharePoint Online の OneDrive に保存されているファイルで作業している場合は、TLS 接続が使用されます。これは、Office 365 に自動的に構築します。[ビジネスとオンラインの SharePoint の OneDrive でのデータの暗号化](https://go.microsoft.com/fwlink/?linkid=526379)を参照してください。<br/> |
|オンライン会議および IM 会話 (ビジネス オンラインの Skype) でファイルを共有します。  <br/> |人は、オンライン ビジネスの Skype を使用してファイルを使用する、接続に TLS が使用されます。これは、Office 365 に自動的に構築します。[セキュリティとアーカイブ (オンラインでビジネス用の Skype)](https://aka.ms/nuq4ws)を参照してください。<br/> |
   
## <a name="additional-information"></a>追加情報

暗号化オプションを含むファイルの保護ソリューションの詳細については、 [Office 365 の保護ソリューションのファイル](https://www.microsoft.com/en-us/download/details.aspx?id=55523)を参照してください。
  

