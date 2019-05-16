---
title: 高度な電子情報開示でサポートされているファイルの種類
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
ms.openlocfilehash: d8e9689cb04929137787225579dcda17005c8bfe
ms.sourcegitcommit: 7be8617ce75909f0fa1a2f6e72749e2ef4bb2d3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2019
ms.locfileid: "34088810"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>高度な電子情報開示でサポートされているファイルの種類

高度な電子情報開示では、多くの種類のファイルをサポートしています。これについては、次の表で説明します。 この一覧は最終処理されていません。検証テストを続行するときに、新しいファイルの種類を追加します。 表は、ファイルの種類がテキスト抽出 (画像用 OCR) でサポートされているかどうかを示します。これは、ネイティブビューアーで表示できます。また、Advanced 電子情報開示の注釈ビューアーでもサポートされています。

## <a name="archive--container"></a>Archive/Container

| Mime の種類 | ファイルの識別 | メタデータ抽出 | コンテナーの抽出 | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |
| アプリケーション/x-7z-圧縮 | はい | はい | はい | . 7z |
| アプリケーション/x-rar 圧縮 | はい | はい | はい | rar |
| アプリケーション/x-tar | はい | はい | はい | tar |
| アプリケーション/zip | はい | はい | はい | .zip |
||||||||

## <a name="database"></a>データベース

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| アプリケーション/x-msaccess.exe | はい | はい | はい | いいえ | いいえ | .mdb |
||||||||

## <a name="email"></a>Email

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. ms-outlook | はい | はい | はい | はい | はい | .msg |
| message/rfc822 | はい | はい | はい | はい | はい | .eml |
| テキスト/vcard-連絡先 | はい | はい | はい | はい | はい | .vcf |
||||||||

## <a name="email-container"></a>メールコンテナー

| Mime の種類 | ファイルの識別 | メタデータ抽出 | コンテナーの抽出 | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |
| application/mbox | はい | はい | はい | mbox |
| application/vnd. ms-outlook-pst | はい | はい | はい | .pst |
||||||||

## <a name="html"></a>HTML

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/xhtml + xml | はい | はい | はい | はい | はい | xhtml |
| application/xml | はい | はい | はい | はい | はい | .xml |
| text/html | はい | はい | はい | はい | はい | .htm、.html、. shtml.dll |
||||||||

## <a name="image"></a>イメージ

| Mime の種類 | ファイルの識別 | メタデータ抽出 | OCR テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| image/bmp | はい | はい | はい | はい | はい | .bmp |
| イメージ/emf | はい | はい | はい | はい | はい | .emf |
| image/gif | はい | はい | はい | はい | はい | .gif |
| image/jpeg | はい | はい | はい | はい | はい | .jpeg、.jpg |
| image/png | はい | はい | はい | はい | はい | .png |
| image/svg + xml | はい | はい | はい | はい | いいえ | svg |
| image/tiff | はい | はい | はい | はい | はい | .tif |
| 画像/vnd. .dwg | はい | はい | はい | はい | はい | .dwg、dxf |
| image/wmf | はい | はい | はい | はい | はい | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. が application | はい | はい | はい | はい | はい | .dat; .xls |
| アプリケーション/vnd を有効にします。12 | はい | はい | はい | はい | いいえ | .xlsb |
| アプリケーション/vnd を有効にします。12 | はい | はい | はい | はい | はい | .xlsm |
| アプリケーション/が application を有効にします。12 | はい | はい | はい | いいえ | いいえ | 。 xltm |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | はい | はい | はい | はい | はい | .xlsx |
| application/vnd. openxmlformats-officedocument | はい | はい | はい | はい | はい | 。 xltx |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft Powerpoint

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. が application | はい | はい | はい | はい | はい | .pot; .pps; .ppt |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | はい | はい | はい | はい | はい | .pptx |
| openxmlformats-officedocument (アプリケーション/vnd) | はい | はい | はい | はい | はい | . ppsx |
| openxmlformats-officedocument (アプリケーション/vnd) | はい | はい | はい | はい | はい | . potx |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| アプリケーション/x-mspublisher | はい | はい | はい | はい | はい | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. ms-visio | はい | はい | はい | はい | いいえ |  |
| アプリケーション/vnd visio | はい | はい | はい | はい | はい | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/msword | はい | はい | はい | はい | はい | .dat; .doc |
| アプリケーション/rtf | はい | はい | はい | はい | はい | .doc; .rtf |
| アプリケーション/vnd を有効にします。12 | はい | はい | はい | はい | はい | .docm |
| アプリケーション/が application を有効にします。12 | はい | はい | はい | はい | はい | normal.dotm |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | はい | はい | はい | はい | はい | .docx |
| application/vnd. openxmlformats-officedocument | はい | はい | はい | はい | はい | .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. ms-works-ss | はい | はい | いいえ | いいえ | いいえ | wps |
| application/vnd-wp | はい | はい | いいえ | いいえ | いいえ | wps |
||||||||

## <a name="open-document-format"></a>開いているドキュメント形式

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. oasis | はい | はい | はい | はい | はい | odt |
||||||||

## <a name="other"></a>Other

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/json | はい | はい | はい | はい | はい | × |
| application/vnd. ms-graph | はい | はい | いいえ | いいえ | いいえ |  |
| application/winhlp | はい | はい | いいえ | いいえ | いいえ | .hlp |
| アプリケーション/x-tnef | はい | はい | いいえ | いいえ | いいえ |  |
||||||||

## <a name="plain-text"></a>プレーン テキスト

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| text/csv | はい | はい | はい | はい | はい | .csv |
| text/plain | はい | はい | はい | はい | はい | .. .css; .csv;... pl; .txt |
||||||||

## <a name="portable-document-format"></a>Portable Document Format

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/pdf | はい | はい | はい | はい | はい | .pdf |
||||||||

## <a name="word-perfect"></a>完全な単語

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd wordperfect;バージョン = 5.0 | はい | はい | はい | いいえ | いいえ | wpd |
| application/vnd wordperfect;バージョン = 5.1 | はい | はい | はい | いいえ | いいえ | wpd |
| application/vnd wordperfect;バージョン = 6. x | はい | はい | はい | いいえ | いいえ | wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. lotus-wordpro | はい | はい | いいえ | いいえ | いいえ | lwp |
||||||||
