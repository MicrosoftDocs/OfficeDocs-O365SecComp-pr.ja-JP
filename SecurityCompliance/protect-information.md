---
title: 情報を保護する
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 情報を保護するためのランディングページ
ms.openlocfilehash: 1c673c2417b399c57ca7ac7e5c5a7b7351de1edd
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "33473146"
---
# <a name="protect-information"></a>情報を保護する

Microsoft 365 および Office 365 には、情報を保護するために特定の種類のデータに適用できる機能が含まれています。 


|**機能**|**詳細情報**|
|:-----|:-----|
|[機密ラベル](sensitivity-labels.md) <br/> |機密ラベルを使用すると、機密コンテンツを分類して保護することができます。 保護オプションには、ラベル、ウォーターマーク、暗号化が含まれます。 機密ラベルは Azure Information Protection を使用します。 Azure Information Protection ラベルを使用している場合は、移行が完了するまで、他の管理センターで新しいラベルを作成しないようにすることをお勧めします。 「 [Azure Information Protection migration](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels)」を参照してください。 <br/> [保持ラベル](retention-policies.md)は、機密ラベルとは異なります。 保持ラベルは、定義したポリシーに基づいてコンテンツを保持または削除するのに役立ちます。 これらは、組織が業界の規制や内部ポリシーに準拠していることを支援します。|
|[データ損失防止](data-loss-prevention-policies.md)鮮明  <br/> |DLP ポリシーを使用すると、Office 365 全体の機密情報を識別、監視、および自動保護することができます。 データ損失防止ポリシーでは、機密情報を識別するために機密情報の種類を使用できます。 <br/> |
|[機密情報の種類](what-the-sensitive-information-types-look-for.md)  <br/> |dlp には、dlp ポリシーで使用できる、多くの機密情報の種類が含まれています。 機密情報の種類は、自動化プロセスが正常性サービス番号やクレジットカード番号などの特定の情報の種類を認識する方法を定義します。   <br/> |
|[Office 365 メッセージの暗号化](ome.md)OME  <br/> |Office 365 メッセージの暗号化では、組織内のユーザーと外部のユーザーとの間で暗号化された電子メールメッセージの送受信を行うことができます。 Office 365 メッセージの暗号化は、Outlook.com、yahoo!、Gmail、その他の電子メールサービスで機能します。 電子メールメッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。  <br/> |
|[Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/)<br/> |機密ラベルまたは Office メッセージの暗号化を使用している場合は、既に Azure Information Protection を使用しています。 まだ azure information protection ラベルを Office 365 に移行していない場合は、引き続き azure information protection で管理します。  <br/>[Azure Information Protection スキャナー](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner)をオンプレミスで実行して、Windows Server、ネットワーク共有、および SharePoint server サイトとライブラリのファイルを分類し、保護することができます。 これは、Office 365 に移行するデータを特定するための最初の手順となります。
|byok または HYOK ソリューションを使用した Azure Information Protection <br/> |一部の組織では、社内またはクラウドでの encyption キーの管理を維持するために、ビジネスニーズまたはコンプライアンス要件があります。 これは一般的ではありません。 詳細については、「[独自のキーを保持する (HYOK) (azure information protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-adrms-restrictions) )」および「[独自のキーを作成する (byok)](https://docs.microsoft.com/en-us/azure/information-protection/byok-price-restrictions)」を参照してください。 <br/> |
    

