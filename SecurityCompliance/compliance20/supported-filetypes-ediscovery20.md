---
title: Advanced eDiscovery でサポートされているファイルの種類 (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8b5651e7e1f1e15aae34a3100b25564f0b84abb7
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296160"
---
# <a name="supported-file-types-in-advanced-ediscovery-preview"></a>Advanced eDiscovery でサポートされているファイルの種類 (プレビュー)


| Mime の種類 | File クラス (画像、アーカイブ、電子メール、Office Doc など) | ネイティブビューアー | テキスト | ビューアーに注釈を付ける | コンテナーの抽出 | 可能な拡張機能 |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | ドキュメント | はい | はい | Yes | なし | .doc、.dat |
| application/pdf | ドキュメント | はい | はい | Yes | なし | .pdf |
| アプリケーション/rtf | ドキュメント | はい | はい | Yes | なし | .rtf;。.doc |
| application/vnd. が application | ドキュメント | はい | はい | Yes | なし | .xls、.dat |
| アプリケーション/vnd を有効にします。12 | 生産性/オープンドキュメント形式 | はい | Yes | × | いいえ | .xlsb |
| アプリケーション/vnd を有効にします。12 | ドキュメント | はい | はい | Yes | なし | .xlsm |
| アプリケーション/が application を有効にします。12 | 生産性/オープンドキュメント形式 | いいえ | はい | × | いいえ | .xltm |
| application/vnd. ms-outlook | 生産性 | いいえ | いいえ | いいえ | いいえ | .msg |
| application/vnd. ms-outlook-pst | 生産性/コラボレーション | いいえ | いいえ | いいえ | はい | .pst |
| application/vnd. が application | ドキュメント | はい | はい | Yes | なし | .ppt; .pps;。なべ |
| アプリケーション/vnd を有効にします。12 | ドキュメント | はい | はい | Yes | なし | .docm |
| アプリケーション/が application を有効にします。12 | ドキュメント | はい | はい | Yes | なし | .dotm |
| application/vnd. oasis | ドキュメント | はい | はい | Yes | なし | odt  |
| openxmlformats-officedocument (アプリケーション/vnd) | ドキュメント | はい | はい | Yes | なし | .pptx |
| openxmlformats-officedocument (アプリケーション/vnd) | 生産性/オープンドキュメント形式 | はい | はい | Yes | なし | . ppsx |
| openxmlformats-officedocument (アプリケーション/vnd) | ドキュメント | はい | はい | Yes | なし | .potx |
| application/vnd。 spreadsheetml | ドキュメント | はい | はい | Yes | なし | .xlsx |
| application/vnd. openxmlformats-officedocument | ドキュメント | はい | はい | Yes | なし | .xltx |
| application/vnd. openxmlformats-officedocument. wordprocessingml | ドキュメント | はい | はい | Yes | なし | .docx |
| application/vnd. openxmlformats-officedocument | ドキュメント | はい | はい | Yes | なし | .dotx |
| アプリケーション/vnd visio | ドキュメント | はい | はい | Yes | なし | .vsd |
| アプリケーション/x-7z-圧縮 | Archive/Container | いいえ | いいえ | いいえ | はい | . 7z |
| application/xhtml + xml | ドキュメント | はい | はい | Yes | なし | xhtml |
| application/xml | ドキュメント | はい | はい | Yes | いいえ | .xml |
| アプリケーション/x-msaccess.exe | ドキュメント | はい | はい | Yes | なし | .mdb |
| アプリケーション/x-mspublisher | ドキュメント | はい | はい | Yes | なし | .pub |
| アプリケーション/x-rar 圧縮 | Archive/Container | いいえ | いいえ | いいえ | はい | rar |
| アプリケーション/zip | Archive/Container | いいえ | いいえ | いいえ | はい | .zip |
| image/bmp | イメージ | はい | はい | Yes | なし | .bmp |
| イメージ/emf | イメージ | はい | はい | Yes | なし | .emf |
| image/gif | ドキュメント | はい | はい | Yes | なし | .gif |
| image/jpeg | イメージ | はい | はい | Yes | なし | .jpg、.jpeg、...jpgt |
| image/png | イメージ | はい | はい | Yes | なし | .png |
| image/tiff | イメージ | はい | はい | Yes | いいえ | .tif |
| 画像/vnd. .dwg | ドキュメント | はい | はい | Yes | なし | .dwg;。dxf |
| image/wmf | ドキュメント | はい | はい | Yes | なし | .wmf |
| message/rfc822 | 生産性/コラボレーション | いいえ | いいえ | いいえ | いいえ | .eml |
| text/csv | ドキュメント | はい | はい | Yes | なし | .csv |
| text/html | ドキュメント | はい | はい | Yes | なし | .html;。shtml.dll; .htm |
| text/plain | ドキュメント | はい | はい | Yes | なし | .txt、.css、。con; pl; .csv; .dat |
| テキスト/vcard-連絡先 | ドキュメント | はい | はい | Yes | なし | .vcf |