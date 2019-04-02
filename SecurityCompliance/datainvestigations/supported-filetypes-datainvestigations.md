---
title: データ調査でサポートされているファイルの種類
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
ms.openlocfilehash: bec8c01b75d68249a335c4de48909ce50ab3bf97
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030281"
---
# <a name="supported-file-types-in-data-investigations"></a>データ調査でサポートされているファイルの種類


| Mime の種類 | File クラス (画像、アーカイブ、電子メール、Office Doc など) | ネイティブビューアー | テキスト | ビューアーに注釈を付ける | コンテナーの抽出 | 可能な拡張機能 |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | ドキュメント | はい | はい | はい | いいえ | .doc、.dat |
| application/pdf | ドキュメント | はい | はい | はい | いいえ | .pdf |
| アプリケーション/rtf | ドキュメント | はい | はい | はい | いいえ | .rtf;。.doc |
| application/vnd. が application | ドキュメント | はい | はい | はい | いいえ | .xls、.dat |
| アプリケーション/vnd を有効にします。12 | 生産性/オープンドキュメント形式 | はい | はい | いいえ | いいえ | .xlsb |
| アプリケーション/vnd を有効にします。12 | ドキュメント | はい | はい | はい | いいえ | .xlsm |
| アプリケーション/が application を有効にします。12 | 生産性/オープンドキュメント形式 | いいえ | はい | いいえ | いいえ | 。 xltm |
| application/vnd. ms-outlook | 生産性 | いいえ | いいえ | いいえ | いいえ | .msg |
| application/vnd. ms-outlook-pst | 生産性/コラボレーション | いいえ | いいえ | いいえ | はい | .pst |
| application/vnd. が application | ドキュメント | はい | はい | はい | いいえ | .ppt; .pps;。なべ |
| アプリケーション/vnd を有効にします。12 | ドキュメント | はい | はい | はい | いいえ | .docm |
| アプリケーション/が application を有効にします。12 | ドキュメント | はい | はい | はい | いいえ | normal.dotm |
| application/vnd. oasis | ドキュメント | はい | はい | はい | いいえ | odt  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | ドキュメント | はい | はい | はい | いいえ | .pptx |
| openxmlformats-officedocument (アプリケーション/vnd) | 生産性/オープンドキュメント形式 | はい | はい | はい | いいえ | . ppsx |
| openxmlformats-officedocument (アプリケーション/vnd) | ドキュメント | はい | はい | はい | いいえ | . potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | ドキュメント | はい | はい | はい | いいえ | .xlsx |
| application/vnd. openxmlformats-officedocument | ドキュメント | はい | はい | はい | いいえ | 。 xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | ドキュメント | はい | はい | はい | いいえ | .docx |
| application/vnd. openxmlformats-officedocument | ドキュメント | はい | はい | はい | いいえ | .dotx |
| アプリケーション/vnd visio | ドキュメント | はい | はい | はい | いいえ | .vsd |
| アプリケーション/x-7z-圧縮 | Archive/Container | いいえ | いいえ | いいえ | はい | . 7z |
| application/xhtml + xml | ドキュメント | はい | はい | はい | いいえ | xhtml |
| application/xml | ドキュメント | はい | はい | はい | いいえ | .xml |
| アプリケーション/x-msaccess.exe | ドキュメント | はい | はい | はい | いいえ | .mdb |
| アプリケーション/x-mspublisher | ドキュメント | はい | はい | はい | いいえ | .pub |
| アプリケーション/x-rar 圧縮 | Archive/Container | いいえ | いいえ | いいえ | はい | rar |
| アプリケーション/zip | Archive/Container | いいえ | いいえ | いいえ | はい | .zip |
| image/bmp | イメージ | はい | はい | はい | いいえ | .bmp |
| イメージ/emf | イメージ | はい | はい | はい | いいえ | .emf |
| image/gif | ドキュメント | はい | はい | はい | いいえ | .gif |
| image/jpeg | イメージ | はい | はい | はい | いいえ | .jpg、.jpeg、...jpgt |
| image/png | イメージ | はい | はい | はい | いいえ | .png |
| image/tiff | イメージ | はい | はい | はい | いいえ | .tif |
| 画像/vnd. .dwg | ドキュメント | はい | はい | はい | いいえ | .dwg;。dxf |
| image/wmf | ドキュメント | はい | はい | はい | いいえ | .wmf |
| message/rfc822 | 生産性/コラボレーション | いいえ | いいえ | いいえ | いいえ | .eml |
| text/csv | ドキュメント | はい | はい | はい | いいえ | .csv |
| text/html | ドキュメント | はい | はい | はい | いいえ | .html;。shtml.dll; .htm |
| text/plain | ドキュメント | はい | はい | はい | いいえ | .txt、.css、。con; pl; .csv; .dat |
| テキスト/vcard-連絡先 | ドキュメント | はい | はい | はい | いいえ | .vcf |