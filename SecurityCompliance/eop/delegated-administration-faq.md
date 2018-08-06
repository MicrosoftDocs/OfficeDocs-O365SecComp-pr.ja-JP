---
title: 代理管理の FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: このトピックでは、代理で Office 365 の管理タスクを実行する (他のテナント (企業) のために Exchange Online Protection (EOP) を管理する機能を含む) Microsoft パートナーとリセラーを対象に、よく寄せられる質問とその答えを取り上げます。
ms.openlocfilehash: b6096e835f90a0d5f22a39a5df76e52f1a25a79d
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027494"
---
# <a name="delegated-administration-faq"></a>代理管理の FAQ

このトピックでは、代理で Office 365 の管理タスクを実行する (他のテナント (企業) のために Exchange Online Protection (EOP) を管理する機能を含む) Microsoft パートナーとリセラーを対象に、よく寄せられる質問とその答えを取り上げます。
  
 **Q. わたしはリセラーで、お客様のテナントを管理する必要があります。どのようにしたらいいですか？**
  
A. Microsoft パートナーまたはリセラーが Microsoft アドバイザーとしてサインアップした場合、Office 365 管理センター内でカスタマーのテナントを管理する権限を要求できます。これを代理管理と呼びます。代理管理では、組織内の管理者と同等に (EOP 設定を含む) Office 365 テナントを管理できます。代理管理を実行するための手順は以下のとおりです。
  
1. [Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。
    
2. Office 365 の代理管理を行うためにサインアップします。カスタマーのアカウント管理を開始する前に、カスタマーから代理管理者としての承認を得る必要があります。承認を得るには、最初に[代理管理の提供をカスタマーに送ります](https://go.microsoft.com/fwlink/?LinkId=396829)。(後でカスタマーに代理管理を提供することもできます。) 
    
3. 「[代理管理者を追加または削除する](https://go.microsoft.com/fwlink/?LinkId=396831)」に記されている手順により、代理管理者アカウントを作成します。
    
Office 365 代理管理のセットアップ方法について詳しくは、「[パートナー: ビジネスを構築して Office 365 パートナー アカウントを管理する](https://go.microsoft.com/fwlink/?LinkId=301485)」を参照してください。 
  
 **Q. わたしはリセラーではなく顧客です。どのようにすれば、自分のサブ テナントの代理管理者をセットアップできますか？**
  
A. 現時点で、代理管理が行えるのはリセラーとパートナーのみです。しかし、サブ テナント (企業) に適用するのに役立つ Windows PowerShell のサンプル スクリプトが用意されています。詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。
  
 **Q. サブ テナント管理者がわたしのポリシーを変更できないようにすることができますか？**
  
A. 現在、Office 365 にその機能はありません。
  
 **Q. 自分のすべてのサブ テナントを統合したレポートを取得できますか？**
  
A. 現時点では、Office 365 管理センターのレポートで、自分が管理する企業を横断して統合レポートを作成することはできません。ただしこれは、リモート Windows PowerShell または[レポート Web サービス](https://go.microsoft.com/fwlink/?LinkId=279926)を使用すると実行できます。 
  

