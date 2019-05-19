---
title: 情報を保護する
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 情報を保護するためのランディングページ
ms.openlocfilehash: 77b4332ae4c5450f7464af660e3cda82ddbe18a5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157239"
---
# <a name="protect-information"></a>情報を保護する

Microsoft 365 および Office 365 には、情報を保護するために特定の種類のデータに適用できる機能が含まれています。


|**機能**|**詳細情報**|
|:-----|:-----|
|[機密ラベル](sensitivity-labels.md) <br/> |機密ラベルを使用すると、機密コンテンツを分類して保護することができます。 保護オプションには、ラベル、ウォーターマーク、暗号化が含まれます。 機密ラベルは Azure Information Protection を使用します。 Azure Information Protection ラベルを使用している場合は、移行が完了するまで、他の管理センターで新しいラベルを作成しないようにすることをお勧めします。 「 [Azure Information Protection migration](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels)」を参照してください。 <br/> [保持ラベル](retention-policies.md)は、機密ラベルとは異なります。 保持ラベルは、定義したポリシーに基づいてコンテンツを保持または削除するのに役立ちます。 これらは、組織が業界の規制や内部ポリシーに準拠していることを支援します。|
|[データ損失防止](data-loss-prevention-policies.md)鮮明  <br/> |DLP ポリシーを使用すると、Office 365 全体の機密情報を識別、監視、および自動保護することができます。 データ損失防止ポリシーでは、機密情報を識別するために機密情報の種類を使用できます。 <br/> |
|[機密情報の種類](what-the-sensitive-information-types-look-for.md) <br/> |Microsoft 365 には、DLP ポリシーで使用するのに適した機密情報の種類が多数含まれており、感度と保持ラベルを使用した自動分類が用意されています。 機密情報の種類を[Azure Information Protection スキャナー](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner)で使用して、オンプレミスのファイルを分類および保護することもできます。 機密情報の種類は、自動化プロセスが正常性サービス番号やクレジットカード番号などの特定の情報の種類を認識する方法を定義します。   <br/> |
|[Office 365 メッセージの暗号化](ome.md)OME  <br/> |Office 365 メッセージの暗号化では、組織内のユーザーと外部のユーザーとの間で暗号化された電子メールメッセージの送受信を行うことができます。 Office 365 メッセージの暗号化は、Outlook.com、Yahoo!、Gmail、その他の電子メールサービスで機能します。 電子メールメッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。 <br/> |
|[Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/)<br/> |Azure Information Protection (AIP とも呼ばれることもあります) は、組織がドキュメントとメールを分類、ラベル付けし、必要に応じて保護するのに役に立ちます。 管理者は、ルールと条件を定義して、ラベルを自動的に適用できます。 ユーザーは、ファイルとメールに手動でラベルを適用できます。 ラベルを適用するときに関する推奨事項をユーザーに提供することもできます。<br/> 機密ラベルまたは Office メッセージの暗号化を使用している場合は、既に分類と保護の機能を使用しています。 Office 365 に Azure Information Protection ラベルをまだ移行していない場合は、引き続き Azure Information Protection で管理します。  <br/>オンプレミスで[Azure Information Protection スキャナー](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner)を実行して、Windows Server、ネットワーク共有、および SharePoint server サイトとライブラリのファイルを分類して保護することができます。 これは、Office 365 に移行するデータを特定するための最初の手順となります。
|顧客管理暗号化キーを使用した Azure Information Protection <br/> |組織によっては、暗号化キーの制御を維持するために、ビジネスニーズやコンプライアンス要件があります。 これは一般的ではありません。 Azure Information Protection を使用すると、組織は独自のキー (BYOK) をサービスに取り込むことができます。 詳細については、「 [Azure Information Protection の独自のキーを取り込む (BYOK)](https://docs.microsoft.com/en-us/azure/information-protection/byok-price-restrictions)」を参照してください。 別のより複雑なオプションが提供されているお客様は、社内で暗号化キーを保持する必要があります。これは、独自のキーを保持する (HYOK) と呼ばれます。  詳細については、「[独自のキーを保持する (HYOK) Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-adrms-restrictions)」を参照してください。 <br/> |
    

