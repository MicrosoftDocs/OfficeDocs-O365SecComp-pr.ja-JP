---
title: Choose between MDM for Office 365 and Microsoft Intune
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c93d9ab9-efb2-4349-9b93-30c30562ee22
description: Microsoft Intune と Office 365 の組み込みのモバイル デバイスの管理、組織内のモバイル デバイスを管理する機能を提供します。このトピックで説明した、重要な違いがあります。
ms.openlocfilehash: 553d401179f82b0f119f9e7d929b4af7d3df0c4a
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014739"
---
# <a name="choose-between-mdm-for-office-365-and-microsoft-intune"></a>Choose between MDM for Office 365 and Microsoft Intune

Microsoft Intune と Office 365 の組み込みのモバイル デバイスの管理、組織内のモバイル デバイスを管理する機能を提供します。次の表に記載されているとする、主な相違点もあります。
  
> [!NOTE]
> ユーザーと同じ Office 365 テナントに Intune と Office 365 の両方を使用してモバイル デバイスを管理することができます。Intune と MDM の両方を設定するには、特定のユーザーとデバイスに最適なソリューションを決定することができます。両方のオプションが利用可能であれば、Office 365 またはより機能豊富な Intune ソリューションの MDM を持つユーザーのデバイスを管理するかどうかを選択できます。 
  
||||
|:-----|:-----|:-----|
|**機能領域** <br/> |**Office 365 用 MDM** <br/> |**Microsoft Intune** <br/> |
|Cost  <br/> |多くの Office 365 の商用サブスクリプションに含まれています。  <br/> |Microsoft Intune のサブスクリプションを購入する必要がありますか、エンタープライズ ・ モビリティ ・ スイートを購入することができます。  <br/> |
|デバイスを管理する方法  <br/> |使用してデバイスを管理する、 [Office 365 のセキュリティ&amp;コンプライアンス センター](https://protection.office.com) Office 365。  <br/> |Intune を単独で使用する場合は、Intune 管理コンソールを使用してデバイスを管理します。  <br/> 構成マネージャー コンソールを使用して、デバイスの設置型を管理するためにシステム センター構成マネージャーで 2012 Intune を統合する場合と、雲の中です。  <br/> |
|デバイスを管理することができます。  <br/> |IOS、Android、および Windows の管理のクラウド ・ ベースのデバイス  <br/> |クラウド ・ ベースの管理 iOS、Mac OS X、アプリ、Windows 8.1 の (電話と PC) と後で Windows 10 が含まれます。 <br/> |
|主な機能  <br/> |Office 365 の企業の電子メールやドキュメントを電話やタブレット、会社によって管理されていると、IT ポリシーに準拠しているのみにアクセスできることを確認に役立ちます。  <br/> 設定し、デバイス レベルの暗証番号 (pin) ロックは、jailbreak の検出、認証されていないユーザーが紛失または盗まれた場合、企業の電子メールとデバイス上のデータをアクセスすることを防ぐためと同様に、セキュリティ ポリシーを管理します。  <br/> 場所、個人データを残したまま、従業員のデバイスから Office 365 の会社データを削除します。  <br/> [Office 365 でモバイル デバイス管理の機能](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)には、詳細情報が含まれます。  <br/> |Office 365 の機能は MDM とします。  <br/> 証明書、Wifi、VPN、および電子メールのプロファイルを持つ企業のリソースに安全にアクセスするユーザーを支援します。  <br/> 登録し、ポリシーとアプリケーションの展開を簡素化、自社所有のデバイスのコレクションを管理します。  <br/> ユーザーに、社内の基幹業務アプリケーションとストア内のアプリケーションを展開します。  <br/> モバイルの Office を使用して企業の情報および行のビジネス アプリケーションが知っているをより安全にアクセスするユーザーを有効にする、制限することによってデータのセキュリティを確保しながらアクションなどのコピー、切り取り、貼り付け、Intune によって管理されているアプリケーションのみに名前を付けて保存します。  <br/> Intune 管理ブラウザー アプリケーションを使用して安全な web ブラウズを有効にします。  <br/> Intune を使用するために必要なインフラストラクチャはありませんが、クラウドから Pc を管理または Intune に構成マネージャーで管理するすべての Pc、Mac、Linux および UNIX を含むデバイスの接続サーバー、および 1 つの管理コンソールからのモバイル デバイスです。  <br/> Intune サブスクリプションでは、他のユーザーのデバイスは、Intune に登録されていない場合でも、Azure ポータルを使用して、MAM (モバイル アプリケーションの管理ポリシーを設定することもできます。[MAM のポリシーを使用するアプリケーション データを保護](https://go.microsoft.com/fwlink/?LinkId=825439)を参照してください。<br/> |


## <a name="related-topics"></a>関連項目
   
詳細については Microsoft Intune に関するビデオのトレーニング コースに[マイクロソフト クラウド サービス: Office 365 の管理および Intune](https://support.office.com/article/c1224e20-3d49-4f40-99ee-fd0991880376.aspx)、LinkedIn の学習で。
  

