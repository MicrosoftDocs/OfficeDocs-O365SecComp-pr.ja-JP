---
title: iOS デバイス用の APNs 証明書を作成する
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: Office 365 のモバイルデバイス管理で iPad や iphones などの iOS デバイスを管理するには、最初に APNs 証明書を作成するために、次の手順を実行します。
ms.openlocfilehash: 5f82690f0add5f1aae95a089d9cdfc0b320ae596
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220457"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>iOS デバイス用の APNs 証明書を作成する

 Office 365 のモバイルデバイス管理で iPad や iphones などの iOS デバイスを管理するには、APNs 証明書を作成する必要があります。 
  
これを行うには、ポータルページの [**設定**] リンクからの手順を実行します。( ** &amp;セキュリティコンプライアンスセンター** \>の**セキュリティポリシー** \>に移動し、**デバイス管理** \>の**設定を管理**します。)
  
![モバイルデバイス管理をセットアップする必要があり、推奨される手順](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. [ **iOS デバイス用の APNs 証明書の構成**] の横にある [**設定**] を選択します。
    
2. [ **CSR ファイルをダウンロード**し、証明書の署名要求をコンピューター上のどこかに保存します] を選択します。 
    
    ![[APN 証明書のインストール] ダイアログボックス](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. [ **次へ**] を選びます。
    
4. APN 証明書を作成します。
    
  - apple **APNS portal**を選択して、apple プッシュ証明書ポータルを開きます。 
    
    ![Apple APNS ポータルが選択されている状態で APN 通知証明書ダイアログをインストールする](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Apple ID でサインインします。
    
    > [!IMPORTANT]
    > アカウントを管理するユーザーが残っている場合でも、組織との間で使用される電子メールアカウントに関連付けられている会社の Apple ID を使用します。この id は、証明書の更新時に同じ id を使用する必要があるため、保存します。 
  
  - [**証明書を作成**し、**使用条件**に同意します] を選択します。
    
  - Office 365 からコンピューターにダウンロードした証明書の署名要求を**参照**し、[**アップロード**] を選択します。
    
  - Apple プッシュ証明書ポータルによって作成された APN 証明書をコンピューターに**ダウンロード**します。 
    
    > [!TIP]
    > 証明書のダウンロードで問題が発生した場合は、ブラウザーを更新します。 
  
5. Office 365 に戻り、[**次**へ] を選択して、[ **APNS 証明書のアップロード**] ページに移動します。 
    
6. Apple プッシュ証明書ポータルからダウンロードした APN 証明書に移動します。
    
    ![[参照] ボタンをクリックして Apple からダウンロードした APNS 証明書を選択します。](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. [**完了**] を選択します。
    
**セキュリティ&amp; /コンプライアンスセンター** \> **のセキュリティポリシー** \>に戻る**デバイス管理** \> **設定を管理**してセットアップを完了します。 
  

