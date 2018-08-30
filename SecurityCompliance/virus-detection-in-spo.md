---
title: SharePoint Online のウイルス検出
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
description: Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。ファイルをアップロードすると、そのファイルがスキャンされてウイルスが検出されます。ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。
ms.openlocfilehash: 22e983d35283ff96e1469fdf913e25b8d1d1c485
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532405"
---
# <a name="virus-detection-in-sharepoint-online"></a>SharePoint Online のウイルス検出

Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。ファイルをアップロードすると、そのファイルがスキャンされてウイルスが検出されます。ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。
  
> [!IMPORTANT]
> SharePoint Online のウイルス対策機能は、ウイルスを封じ込める 1 つの方法にすぎません。これだけで、お客様の環境がマルウェアから保護されるわけではありません。すべてのお客様が、マルウェア対策保護を評価してさまざまなレイヤーに実装し、ベスト プラクティスを適用してエンタープライズ インフラストラクチャを保護することをお勧めします。戦略とベスト プラクティスの詳細については、「[Security best practices for Office 365](security-best-practices.md)」を参照してください。 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされたとき

Office 365 は、一般的なウイルス検出エンジンを使用します。エンジンでは、SharePoint Online では、内で非同期的に実行し、アップロードしたファイルをスキャンします。ウイルスを含むファイルが見つかった場合フラグ設定できるように、もう一度ダウンロードすることはできません。2018 年 4 月では、スキャンしたファイルの 25 MB の制限を削除しました。
  
動作は次のとおりです。
  
1. ユーザーがファイルを SharePoint Online にアップロードします。
    
2. ウイルス検出エンジンによってファイルがスキャンされます。
    
3. ウイルスが見つかると、ウイルス エンジンによって、感染していることを示すプロパティがファイルに設定されます。
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

SharePoint Online からファイルをダウンロードすることはできません。
  
動作は次のとおりです。
  
1. Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、
    
2. ウイルスが検出されたことがユーザーに警告され、ファイルをダウンロードするかどうかを選択でき、独自のウイルス ソフトを使用してクリーン アップが試行されます。
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

ファイルの同期を 新しい OneDrive の同期クライアント (OneDrive.exe) と前の OneDrive for Business 同期クライアント (Groove.exe) のどちらを使用して行っても、そのファイルにウイルスが含まれている場合には同期クライアントでダウンロードができません。ファイルを同期できないという通知が同期クライアントに表示されます。
  

