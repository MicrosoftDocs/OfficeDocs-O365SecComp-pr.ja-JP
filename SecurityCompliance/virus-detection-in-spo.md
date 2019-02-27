---
title: SharePoint Online のウイルス検出
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/14/2019
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。ファイルをアップロードすると、そのファイルがスキャンされてウイルスが検出されます。ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。
ms.openlocfilehash: d4f18c84935d9c6e1d3f135bbda6c40737956ae7
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276237"
---
# <a name="virus-detection-in-sharepoint-online"></a>SharePoint Online のウイルス検出

Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。ファイルをアップロードすると、そのファイルがスキャンされてウイルスが検出されます。ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。
  
> [!IMPORTANT]
> SharePoint Online のウイルス対策機能は、ウイルスを封じ込める 1 つの方法にすぎません。これだけで、お客様の環境がマルウェアから保護されるわけではありません。すべてのお客様が、マルウェア対策保護を評価してさまざまなレイヤーに実装し、ベスト プラクティスを適用してエンタープライズ インフラストラクチャを保護することをお勧めします。戦略とベスト プラクティスの詳細については、「[Security best practices for Office 365](security-best-practices.md)」を参照してください。 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされたとき

Office 365 は、一般的なウイルス検出エンジンを使用します。エンジンは SharePoint Online 内で非同期に実行され、アップロード後にファイルをスキャンします。ファイルにウイルスが含まれていることが検出されると、再度ダウンロードできないようにフラグが付けられます。2018年4月に、スキャンされたファイルの 25 MB の制限を削除しました。
  
動作は次のとおりです。
  
1. ユーザーがファイルを SharePoint Online にアップロードします。
    
2. ウイルス検出エンジンによってファイルがスキャンされます。
    
3. ウイルスが見つかると、ウイルス エンジンによって、感染していることを示すプロパティがファイルに設定されます。
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

SharePoint Online からファイルをダウンロードすることはできません。
  
動作は次のとおりです。
  
1. Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、
    
2. ウイルスが検出されたという警告がユーザーに提示されます。ユーザーには、ファイルをダウンロードして、独自のウイルスソフトウェアを使用して駆除を試行するオプションが与えられます。

> [!NOTE]
> set-spotenant コマンドレットを**DisallowInfectedFileDownload**パラメーターと共に使用して、ウイルス対策の警告ウィンドウであっても、検出されたファイルをダウンロードできないようにすることができます。「[DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)」を参照してください。
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

ファイルの同期を 新しい OneDrive の同期クライアント (OneDrive.exe) と前の OneDrive for Business 同期クライアント (Groove.exe) のどちらを使用して行っても、そのファイルにウイルスが含まれている場合には同期クライアントでダウンロードができません。ファイルを同期できないという通知が同期クライアントに表示されます。
  

