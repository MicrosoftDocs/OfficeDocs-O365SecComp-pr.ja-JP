---
title: Office 365 の証明書チェーン
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 は、別の証明書のプロバイダーを利用しています。お客様が Office 365 にアクセスするときに発生可能性のある既知の Office 365 ルート証明書の完全な一覧を次に示します。証明書については、独自のインフラストラクチャのインストール、Office 365 のサード パーティの SSL 証明書の計画を参照してくださいする必要があります。次の証明書情報は、Office 365 のすべての国内世界的なクラウドのインスタンスに適用されます。
ms.openlocfilehash: 1dcc2dc38bb8e3239a3be3983791b0c60917dc5e
ms.sourcegitcommit: 13f40ff7c1799152bf45af2d8110f4f3235b770a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "25549761"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="b3f37-106">Office 365 の証明書チェーン</span><span class="sxs-lookup"><span data-stu-id="b3f37-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="b3f37-p102">Office 365 は、別の証明書のプロバイダーを利用しています。お客様が Office 365 にアクセスするときに発生可能性のある既知の Office 365 ルート証明書の完全な一覧を次に示します。証明書については、独自のインフラストラクチャをインストールする必要があります、 [Office 365 の SSL 証明書をサード ・ パーティの計画](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)を参照してください。次の証明書情報は、Office 365 のすべての国内世界的なクラウドのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b3f37-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="b3f37-111">**証明書の種類**</span><span class="sxs-lookup"><span data-stu-id="b3f37-111">**Certificate type**</span></span>|<span data-ttu-id="b3f37-112">**P7b ダウンロード**</span><span class="sxs-lookup"><span data-stu-id="b3f37-112">**P7b download**</span></span>|<span data-ttu-id="b3f37-113">**CRL の端点**</span><span class="sxs-lookup"><span data-stu-id="b3f37-113">**CRL Endpoints**</span></span>|<span data-ttu-id="b3f37-114">**OCSP の端点**</span><span class="sxs-lookup"><span data-stu-id="b3f37-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="b3f37-115">**AIA の端点**</span><span class="sxs-lookup"><span data-stu-id="b3f37-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b3f37-116">信頼関係のルート証明書の公開</span><span class="sxs-lookup"><span data-stu-id="b3f37-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="b3f37-117">Office 365 のルート証明書バンドル (P7B)</span><span class="sxs-lookup"><span data-stu-id="b3f37-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="b3f37-118">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="b3f37-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="b3f37-119">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="b3f37-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="b3f37-120">該当なし</span><span class="sxs-lookup"><span data-stu-id="b3f37-120">N/A</span></span>  <br/> |<span data-ttu-id="b3f37-121">該当なし</span><span class="sxs-lookup"><span data-stu-id="b3f37-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="b3f37-122">一般に中間証明書を信頼</span><span class="sxs-lookup"><span data-stu-id="b3f37-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="b3f37-123">Office 365 の中間証明書バンドル (P7B)</span><span class="sxs-lookup"><span data-stu-id="b3f37-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="b3f37-124">cdp1.public trust.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="b3f37-125">crl.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="b3f37-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="b3f37-126">crl.entrust.net</span><span class="sxs-lookup"><span data-stu-id="b3f37-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="b3f37-127">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="b3f37-128">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="b3f37-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="b3f37-129">crl.identrust.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="b3f37-130">crl.thawte.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="b3f37-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="b3f37-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="b3f37-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="b3f37-134">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="b3f37-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="b3f37-135">isrg.trustid.ocsp.identrust.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="b3f37-136">ocsp.digicert.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="b3f37-137">ocsp.entrust.net</span><span class="sxs-lookup"><span data-stu-id="b3f37-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="b3f37-138">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="b3f37-139">ocsp.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="b3f37-140">ocsp.startssl.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="b3f37-141">ocsp.thawte.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="b3f37-142">ocsp2.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="b3f37-143">ocspcnnicroot.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="b3f37-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="b3f37-144">ルート-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="b3f37-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="b3f37-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="b3f37-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="b3f37-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="b3f37-147">aia.startssl.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="b3f37-148">apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="b3f37-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="b3f37-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="b3f37-150">www.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="b3f37-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="b3f37-151">ルートと証明書プロバイダーに関する追加情報を参照してください次の中間のセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="b3f37-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="b3f37-152">Office 365 のルート証明書の詳細</span><span class="sxs-lookup"><span data-stu-id="b3f37-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="b3f37-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="b3f37-153"></span></span>

 <span data-ttu-id="b3f37-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="b3f37-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="b3f37-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="b3f37-155">|:-----|</span></span>
|<span data-ttu-id="b3f37-156">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="b3f37-157">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-157">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-158">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-158"></span></span>|
|<span data-ttu-id="b3f37-159">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-159">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-160">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-160"></span></span>|
|<span data-ttu-id="b3f37-161">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-162">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-162"></span></span>|
|<span data-ttu-id="b3f37-163">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-164">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-164"></span></span>|
|<span data-ttu-id="b3f37-165">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-165">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-166">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-166"></span></span>|
|<span data-ttu-id="b3f37-167">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-168">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-168"></span></span>|
|<span data-ttu-id="b3f37-169">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-170">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-170"></span></span>|
|<span data-ttu-id="b3f37-171">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-172">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-172"></span></span>|
|<span data-ttu-id="b3f37-173">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-174">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-174"></span></span>|
   
 <span data-ttu-id="b3f37-175">**CNNIC のルート**</span><span class="sxs-lookup"><span data-stu-id="b3f37-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-176">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-176">**Subject**</span></span>|
|<span data-ttu-id="b3f37-177">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-177"></span></span>|
|<span data-ttu-id="b3f37-178">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-178">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-179">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-179"></span></span>|
|<span data-ttu-id="b3f37-180">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-180">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-181">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-181"></span></span>|
|<span data-ttu-id="b3f37-182">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-183">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-183"></span></span>|
|<span data-ttu-id="b3f37-184">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-185">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-185"></span></span>|
|<span data-ttu-id="b3f37-186">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-186">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-187">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-187"></span></span>|
|<span data-ttu-id="b3f37-188">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-189">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-189"></span></span>|
|<span data-ttu-id="b3f37-190">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-191">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-191"></span></span>|
|<span data-ttu-id="b3f37-192">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-193">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-193"></span></span>|
|<span data-ttu-id="b3f37-194">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-195">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-195"></span></span>|
|<span data-ttu-id="b3f37-196">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-197">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-197"></span></span>|
   
 <span data-ttu-id="b3f37-198">**DigiCert のグローバル ルート CA**</span><span class="sxs-lookup"><span data-stu-id="b3f37-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-199">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-199">**Subject**</span></span>|
|<span data-ttu-id="b3f37-200">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-200"></span></span>|
|<span data-ttu-id="b3f37-201">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-201">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-202">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-202"></span></span>|
|<span data-ttu-id="b3f37-203">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-203">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-204">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-204"></span></span>|
|<span data-ttu-id="b3f37-205">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-206">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-206"></span></span>|
|<span data-ttu-id="b3f37-207">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-208">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-208"></span></span>|
|<span data-ttu-id="b3f37-209">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-209">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-210">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-210"></span></span>|
|<span data-ttu-id="b3f37-211">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-212">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-212"></span></span>|
|<span data-ttu-id="b3f37-213">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-214">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-214"></span></span>|
|<span data-ttu-id="b3f37-215">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-216">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-216"></span></span>|
|<span data-ttu-id="b3f37-217">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-218">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-218"></span></span>|
|<span data-ttu-id="b3f37-219">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-220">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-220"></span></span>|
   
 <span data-ttu-id="b3f37-221">**DigiCert 高保証 EV のルート CA**</span><span class="sxs-lookup"><span data-stu-id="b3f37-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-222">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-222">**Subject**</span></span>|
|<span data-ttu-id="b3f37-223">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-223"></span></span>|
|<span data-ttu-id="b3f37-224">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-224">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-225">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-225"></span></span>|
|<span data-ttu-id="b3f37-226">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-226">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-227">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-227"></span></span>|
|<span data-ttu-id="b3f37-228">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-229">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-229"></span></span>|
|<span data-ttu-id="b3f37-230">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-231">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-231"></span></span>|
|<span data-ttu-id="b3f37-232">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-232">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-233">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-233"></span></span>|
|<span data-ttu-id="b3f37-234">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-235">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-235"></span></span>|
|<span data-ttu-id="b3f37-236">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-237">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-237"></span></span>|
|<span data-ttu-id="b3f37-238">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-239">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-239"></span></span>|
|<span data-ttu-id="b3f37-240">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-241">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-241"></span></span>|
|<span data-ttu-id="b3f37-242">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-243">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-243"></span></span>|
   
 <span data-ttu-id="b3f37-244">**D 信頼ルート クラス 3 CA 2 2009**</span><span class="sxs-lookup"><span data-stu-id="b3f37-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-245">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-245">**Subject**</span></span>|
|<span data-ttu-id="b3f37-246">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-246"></span></span>|
|<span data-ttu-id="b3f37-247">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-247">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-248">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-248"></span></span>|
|<span data-ttu-id="b3f37-249">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-249">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-250">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-250"></span></span>|
|<span data-ttu-id="b3f37-251">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-252">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-252"></span></span>|
|<span data-ttu-id="b3f37-253">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-254">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-254"></span></span>|
|<span data-ttu-id="b3f37-255">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-255">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-256">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-256"></span></span>|
|<span data-ttu-id="b3f37-257">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-258">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-258"></span></span>|
|<span data-ttu-id="b3f37-259">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-260">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-260"></span></span>|
|<span data-ttu-id="b3f37-261">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-262">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-262"></span></span>|
|<span data-ttu-id="b3f37-263">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-264">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-264"></span></span>|
|<span data-ttu-id="b3f37-265">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-265">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-266">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-266"></span></span>|
   
 <span data-ttu-id="b3f37-267">**クラス 3 の D に信頼できるルート CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="b3f37-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-268">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-268">**Subject**</span></span>|
|<span data-ttu-id="b3f37-269">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-269"></span></span>|
|<span data-ttu-id="b3f37-270">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-270">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-271">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-271"></span></span>|
|<span data-ttu-id="b3f37-272">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-272">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-273">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-273"></span></span>|
|<span data-ttu-id="b3f37-274">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-275">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-275"></span></span>|
|<span data-ttu-id="b3f37-276">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-277">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-277"></span></span>|
|<span data-ttu-id="b3f37-278">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-278">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-279">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-279"></span></span>|
|<span data-ttu-id="b3f37-280">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-281">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-281"></span></span>|
|<span data-ttu-id="b3f37-282">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-283">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-283"></span></span>|
|<span data-ttu-id="b3f37-284">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-285">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-285"></span></span>|
|<span data-ttu-id="b3f37-286">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-287">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-287"></span></span>|
|<span data-ttu-id="b3f37-288">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-288">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-289">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-289"></span></span>|
   
 <span data-ttu-id="b3f37-290">**DST のルート CA X3**</span><span class="sxs-lookup"><span data-stu-id="b3f37-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-291">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-291">**Subject**</span></span>|
|<span data-ttu-id="b3f37-292">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-292"></span></span>|
|<span data-ttu-id="b3f37-293">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-293">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-294">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-294"></span></span>|
|<span data-ttu-id="b3f37-295">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-295">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-296">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-296"></span></span>|
|<span data-ttu-id="b3f37-297">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-298">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-298"></span></span>|
|<span data-ttu-id="b3f37-299">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-300">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-300"></span></span>|
|<span data-ttu-id="b3f37-301">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-301">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-302">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-302"></span></span>|
|<span data-ttu-id="b3f37-303">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-304">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-304"></span></span>|
|<span data-ttu-id="b3f37-305">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-306">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-306"></span></span>|
|<span data-ttu-id="b3f37-307">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-308">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-308"></span></span>|
|<span data-ttu-id="b3f37-309">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-310">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-310"></span></span>|
   
 <span data-ttu-id="b3f37-311">**ルート証明機関の G2 を委託します。**</span><span class="sxs-lookup"><span data-stu-id="b3f37-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-312">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-312">**Subject**</span></span>|
|<span data-ttu-id="b3f37-313">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-313"></span></span>|
|<span data-ttu-id="b3f37-314">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-314">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-315">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-315"></span></span>|
|<span data-ttu-id="b3f37-316">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-316">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-317">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-317"></span></span>|
|<span data-ttu-id="b3f37-318">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-319">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-319"></span></span>|
|<span data-ttu-id="b3f37-320">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-321">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-321"></span></span>|
|<span data-ttu-id="b3f37-322">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-322">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-323">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-323"></span></span>|
|<span data-ttu-id="b3f37-324">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-325">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-325"></span></span>|
|<span data-ttu-id="b3f37-326">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-327">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-327"></span></span>|
|<span data-ttu-id="b3f37-328">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-329">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-329"></span></span>|
|<span data-ttu-id="b3f37-330">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-331">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-331"></span></span>|
   
 <span data-ttu-id="b3f37-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-333">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-333">**Subject**</span></span>|
|<span data-ttu-id="b3f37-334">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-334"></span></span>|
|<span data-ttu-id="b3f37-335">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-335">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-336">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-336"></span></span>|
|<span data-ttu-id="b3f37-337">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-337">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-338">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-338"></span></span>|
|<span data-ttu-id="b3f37-339">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-340">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-340"></span></span>|
|<span data-ttu-id="b3f37-341">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-342">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-342"></span></span>|
|<span data-ttu-id="b3f37-343">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-343">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-344">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-344"></span></span>|
|<span data-ttu-id="b3f37-345">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-346">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-346"></span></span>|
|<span data-ttu-id="b3f37-347">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-348">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-348"></span></span>|
|<span data-ttu-id="b3f37-349">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-350">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-350"></span></span>|
|<span data-ttu-id="b3f37-351">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-352">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-352"></span></span>|
   
 <span data-ttu-id="b3f37-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="b3f37-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-354">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-354">**Subject**</span></span>|
|<span data-ttu-id="b3f37-355">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-355"></span></span>|
|<span data-ttu-id="b3f37-356">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-356">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-357">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-357"></span></span>|
|<span data-ttu-id="b3f37-358">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-358">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-359">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-359"></span></span>|
|<span data-ttu-id="b3f37-360">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-361">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-361"></span></span>|
|<span data-ttu-id="b3f37-362">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-363">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-363"></span></span>|
|<span data-ttu-id="b3f37-364">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-364">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-365">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-365"></span></span>|
|<span data-ttu-id="b3f37-366">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-367">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-367"></span></span>|
|<span data-ttu-id="b3f37-368">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-369">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-369"></span></span>|
|<span data-ttu-id="b3f37-370">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-371">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-371"></span></span>|
|<span data-ttu-id="b3f37-372">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-373">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-373"></span></span>|
|<span data-ttu-id="b3f37-374">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-375">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-375"></span></span>|
|<span data-ttu-id="b3f37-376">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-376">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-377">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-377"></span></span>|
   
 <span data-ttu-id="b3f37-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="b3f37-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-379">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-379">**Subject**</span></span>|
|<span data-ttu-id="b3f37-380">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-380"></span></span>|
|<span data-ttu-id="b3f37-381">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-381">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-382">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-382"></span></span>|
|<span data-ttu-id="b3f37-383">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-383">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-384">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-384"></span></span>|
|<span data-ttu-id="b3f37-385">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-386">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-386"></span></span>|
|<span data-ttu-id="b3f37-387">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-388">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-388"></span></span>|
|<span data-ttu-id="b3f37-389">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-389">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-390">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-390"></span></span>|
|<span data-ttu-id="b3f37-391">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-392">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-392"></span></span>|
|<span data-ttu-id="b3f37-393">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-394">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-394"></span></span>|
|<span data-ttu-id="b3f37-395">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-396">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-396"></span></span>|
|<span data-ttu-id="b3f37-397">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-398">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-398"></span></span>|
   
 <span data-ttu-id="b3f37-399">**thawte プライマリ ルート CA の場合は、G3**</span><span class="sxs-lookup"><span data-stu-id="b3f37-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-400">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-400">**Subject**</span></span>|
|<span data-ttu-id="b3f37-401">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-401"></span></span>|
|<span data-ttu-id="b3f37-402">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-402">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-403">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-403"></span></span>|
|<span data-ttu-id="b3f37-404">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-404">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-405">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-405"></span></span>|
|<span data-ttu-id="b3f37-406">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-407">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-407"></span></span>|
|<span data-ttu-id="b3f37-408">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-409">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-409"></span></span>|
|<span data-ttu-id="b3f37-410">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-410">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-411">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-411"></span></span>|
|<span data-ttu-id="b3f37-412">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-413">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-413"></span></span>|
|<span data-ttu-id="b3f37-414">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-415">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-415"></span></span>|
|<span data-ttu-id="b3f37-416">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-417">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-417"></span></span>|
|<span data-ttu-id="b3f37-418">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-419">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-419"></span></span>|
   
 <span data-ttu-id="b3f37-420">**VeriSign クラス 3 の主な公共の証明機関の G5**</span><span class="sxs-lookup"><span data-stu-id="b3f37-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-421">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-421">**Subject**</span></span>|
|<span data-ttu-id="b3f37-422">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-422"></span></span>|
|<span data-ttu-id="b3f37-423">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-423">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-424">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-424"></span></span>|
|<span data-ttu-id="b3f37-425">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-425">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-426">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-426"></span></span>|
|<span data-ttu-id="b3f37-427">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-428">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-428"></span></span>|
|<span data-ttu-id="b3f37-429">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-430">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-430"></span></span>|
|<span data-ttu-id="b3f37-431">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-431">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-432">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-432"></span></span>|
|<span data-ttu-id="b3f37-433">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-434">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-434"></span></span>|
|<span data-ttu-id="b3f37-435">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-436">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-436"></span></span>|
|<span data-ttu-id="b3f37-437">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-438">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-438"></span></span>|
|<span data-ttu-id="b3f37-439">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-440">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="b3f37-441">Office 365 の中間の証明書の詳細</span><span class="sxs-lookup"><span data-stu-id="b3f37-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="b3f37-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="b3f37-442"></span></span>

 <span data-ttu-id="b3f37-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="b3f37-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-444">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-444">**Subject**</span></span>|
|<span data-ttu-id="b3f37-445">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-445"></span></span>|
|<span data-ttu-id="b3f37-446">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-446">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-447">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-447"></span></span>|
|<span data-ttu-id="b3f37-448">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-448">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-449">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-449"></span></span>|
|<span data-ttu-id="b3f37-450">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-450">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-451">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-451"></span></span>|
|<span data-ttu-id="b3f37-452">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-453">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-453"></span></span>|
|<span data-ttu-id="b3f37-454">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-455">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-455"></span></span>|
|<span data-ttu-id="b3f37-456">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-456">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-457">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-457"></span></span>|
|<span data-ttu-id="b3f37-458">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-459">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-459"></span></span>|
|<span data-ttu-id="b3f37-460">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-461">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-461"></span></span>|
|<span data-ttu-id="b3f37-462">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-463">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-463"></span></span>|
|<span data-ttu-id="b3f37-464">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-465">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-465"></span></span>|
|<span data-ttu-id="b3f37-466">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-467">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-467"></span></span>|
|<span data-ttu-id="b3f37-468">**AIA の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-468">**AIA URLs**</span></span>|
|<span data-ttu-id="b3f37-469">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-469"></span></span>|
|<span data-ttu-id="b3f37-470">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-470">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-471">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-471"></span></span>|
|<span data-ttu-id="b3f37-472">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-473">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-473"></span></span>|
   
 <span data-ttu-id="b3f37-474">**D 信頼 SSL クラス 3 CA 1 2009**</span><span class="sxs-lookup"><span data-stu-id="b3f37-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-475">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-475">**Subject**</span></span>|
|<span data-ttu-id="b3f37-476">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-476"></span></span>|
|<span data-ttu-id="b3f37-477">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-477">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-478">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-478"></span></span>|
|<span data-ttu-id="b3f37-479">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b3f37-480">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-480"></span></span>|
|<span data-ttu-id="b3f37-481">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-481">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-482">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-482"></span></span>|
|<span data-ttu-id="b3f37-483">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-483">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-484">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-484"></span></span>|
|<span data-ttu-id="b3f37-485">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-486">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-486"></span></span>|
|<span data-ttu-id="b3f37-487">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-488">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-488"></span></span>|
|<span data-ttu-id="b3f37-489">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-489">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-490">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-490"></span></span>|
|<span data-ttu-id="b3f37-491">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-492">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-492"></span></span>|
|<span data-ttu-id="b3f37-493">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-494">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-494"></span></span>|
|<span data-ttu-id="b3f37-495">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-496">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-496"></span></span>|
|<span data-ttu-id="b3f37-497">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-498">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-498"></span></span>|
|<span data-ttu-id="b3f37-499">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-500">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-500"></span></span>|
|<span data-ttu-id="b3f37-501">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-501">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-502">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-502"></span></span>|
|<span data-ttu-id="b3f37-503">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-504">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-504"></span></span>|
   
 <span data-ttu-id="b3f37-505">**D 信頼 SSL クラス 3 CA 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="b3f37-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-506">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-506">**Subject**</span></span>|
|<span data-ttu-id="b3f37-507">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-507"></span></span>|
|<span data-ttu-id="b3f37-508">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-508">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-509">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-509"></span></span>|
|<span data-ttu-id="b3f37-510">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b3f37-511">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-511"></span></span>|
|<span data-ttu-id="b3f37-512">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-512">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-513">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-513"></span></span>|
|<span data-ttu-id="b3f37-514">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-514">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-515">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-515"></span></span>|
|<span data-ttu-id="b3f37-516">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-517">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-517"></span></span>|
|<span data-ttu-id="b3f37-518">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-519">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-519"></span></span>|
|<span data-ttu-id="b3f37-520">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-520">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-521">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-521"></span></span>|
|<span data-ttu-id="b3f37-522">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-523">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-523"></span></span>|
|<span data-ttu-id="b3f37-524">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-525">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-525"></span></span>|
|<span data-ttu-id="b3f37-526">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-527">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-527"></span></span>|
|<span data-ttu-id="b3f37-528">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-529">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-529"></span></span>|
|<span data-ttu-id="b3f37-530">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-531">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-531"></span></span>|
|<span data-ttu-id="b3f37-532">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-532">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-533">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-533"></span></span>|
|<span data-ttu-id="b3f37-534">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-535">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-535"></span></span>|
   
 <span data-ttu-id="b3f37-536">**DigiCert のクラウド サービスの CA 1**</span><span class="sxs-lookup"><span data-stu-id="b3f37-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-537">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-537">**Subject**</span></span>|
|<span data-ttu-id="b3f37-538">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-538"></span></span>|
|<span data-ttu-id="b3f37-539">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-539">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-540">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-540"></span></span>|
|<span data-ttu-id="b3f37-541">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-541">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-542">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-542"></span></span>|
|<span data-ttu-id="b3f37-543">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-543">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-544">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-544"></span></span>|
|<span data-ttu-id="b3f37-545">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-546">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-546"></span></span>|
|<span data-ttu-id="b3f37-547">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-548">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-548"></span></span>|
|<span data-ttu-id="b3f37-549">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-549">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-550">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-550"></span></span>|
|<span data-ttu-id="b3f37-551">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-552">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-552"></span></span>|
|<span data-ttu-id="b3f37-553">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-554">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-554"></span></span>|
|<span data-ttu-id="b3f37-555">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-556">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-556"></span></span>|
|<span data-ttu-id="b3f37-557">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-558">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-558"></span></span>|
|<span data-ttu-id="b3f37-559">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-560">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-560"></span></span>|
|<span data-ttu-id="b3f37-561">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-561">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-562">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-562"></span></span>|
|<span data-ttu-id="b3f37-563">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-564">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-564"></span></span>|
   
 <span data-ttu-id="b3f37-565">**DigiCert SHA2 高保証サーバー CA**</span><span class="sxs-lookup"><span data-stu-id="b3f37-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-566">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-566">**Subject**</span></span>|
|<span data-ttu-id="b3f37-567">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-567"></span></span>|
|<span data-ttu-id="b3f37-568">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-568">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-569">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-569"></span></span>|
|<span data-ttu-id="b3f37-570">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-570">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-571">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-571"></span></span>|
|<span data-ttu-id="b3f37-572">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-572">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-573">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-573"></span></span>|
|<span data-ttu-id="b3f37-574">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-575">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-575"></span></span>|
|<span data-ttu-id="b3f37-576">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-577">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-577"></span></span>|
|<span data-ttu-id="b3f37-578">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-578">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-579">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-579"></span></span>|
|<span data-ttu-id="b3f37-580">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-581">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-581"></span></span>|
|<span data-ttu-id="b3f37-582">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-583">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-583"></span></span>|
|<span data-ttu-id="b3f37-584">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-585">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-585"></span></span>|
|<span data-ttu-id="b3f37-586">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-587">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-587"></span></span>|
|<span data-ttu-id="b3f37-588">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-589">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-589"></span></span>|
|<span data-ttu-id="b3f37-590">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-590">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-591">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-591"></span></span>|
|<span data-ttu-id="b3f37-592">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-593">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-593"></span></span>|
   
 <span data-ttu-id="b3f37-594">**DigiCert SHA2 セキュリティで保護されたサーバーの CA**</span><span class="sxs-lookup"><span data-stu-id="b3f37-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-595">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-595">**Subject**</span></span>|
|<span data-ttu-id="b3f37-596">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-596"></span></span>|
|<span data-ttu-id="b3f37-597">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-597">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-598">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-598"></span></span>|
|<span data-ttu-id="b3f37-599">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-599">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-600">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-600"></span></span>|
|<span data-ttu-id="b3f37-601">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-601">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-602">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-602"></span></span>|
|<span data-ttu-id="b3f37-603">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-604">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-604"></span></span>|
|<span data-ttu-id="b3f37-605">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-606">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-606"></span></span>|
|<span data-ttu-id="b3f37-607">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-607">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-608">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-608"></span></span>|
|<span data-ttu-id="b3f37-609">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-610">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-610"></span></span>|
|<span data-ttu-id="b3f37-611">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-612">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-612"></span></span>|
|<span data-ttu-id="b3f37-613">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-614">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-614"></span></span>|
|<span data-ttu-id="b3f37-615">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-616">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-616"></span></span>|
|<span data-ttu-id="b3f37-617">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-618">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-618"></span></span>|
|<span data-ttu-id="b3f37-619">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-619">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-620">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-620"></span></span>|
|<span data-ttu-id="b3f37-621">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-622">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-622"></span></span>|
   
 <span data-ttu-id="b3f37-623">**証明機関 - L1C を委託します。**</span><span class="sxs-lookup"><span data-stu-id="b3f37-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-624">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-624">**Subject**</span></span>|
|<span data-ttu-id="b3f37-625">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-625"></span></span>|
|<span data-ttu-id="b3f37-626">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-626">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-627">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-627"></span></span>|
|<span data-ttu-id="b3f37-628">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-628">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-629">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-629"></span></span>|
|<span data-ttu-id="b3f37-630">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-630">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-631">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-631"></span></span>|
|<span data-ttu-id="b3f37-632">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-633">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-633"></span></span>|
|<span data-ttu-id="b3f37-634">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-635">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-635"></span></span>|
|<span data-ttu-id="b3f37-636">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-636">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-637">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-637"></span></span>|
|<span data-ttu-id="b3f37-638">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-639">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-639"></span></span>|
|<span data-ttu-id="b3f37-640">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-641">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-641"></span></span>|
|<span data-ttu-id="b3f37-642">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-643">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-643"></span></span>|
|<span data-ttu-id="b3f37-644">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-645">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-645"></span></span>|
|<span data-ttu-id="b3f37-646">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-647">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-647"></span></span>|
|<span data-ttu-id="b3f37-648">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-648">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-649">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-649"></span></span>|
|<span data-ttu-id="b3f37-650">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-651">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-651"></span></span>|
   
 <span data-ttu-id="b3f37-652">**証明機関 - L1K を委託します。**</span><span class="sxs-lookup"><span data-stu-id="b3f37-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-653">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-653">**Subject**</span></span>|
|<span data-ttu-id="b3f37-654">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-654"></span></span>|
|<span data-ttu-id="b3f37-655">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-655">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-656">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-656"></span></span>|
|<span data-ttu-id="b3f37-657">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-657">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-658">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-658"></span></span>|
|<span data-ttu-id="b3f37-659">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-659">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-660">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-660"></span></span>|
|<span data-ttu-id="b3f37-661">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-662">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-662"></span></span>|
|<span data-ttu-id="b3f37-663">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-664">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-664"></span></span>|
|<span data-ttu-id="b3f37-665">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-665">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-666">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-666"></span></span>|
|<span data-ttu-id="b3f37-667">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-668">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-668"></span></span>|
|<span data-ttu-id="b3f37-669">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-670">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-670"></span></span>|
|<span data-ttu-id="b3f37-671">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-672">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-672"></span></span>|
|<span data-ttu-id="b3f37-673">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-674">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-674"></span></span>|
|<span data-ttu-id="b3f37-675">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-676">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-676"></span></span>|
|<span data-ttu-id="b3f37-677">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-677">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-678">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-678"></span></span>|
|<span data-ttu-id="b3f37-679">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-680">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-680"></span></span>|
   
 <span data-ttu-id="b3f37-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="b3f37-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-682">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-682">**Subject**</span></span>|
|<span data-ttu-id="b3f37-683">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-683"></span></span>|
|<span data-ttu-id="b3f37-684">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-684">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-685">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-685"></span></span>|
|<span data-ttu-id="b3f37-686">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-686">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-687">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-687"></span></span>|
|<span data-ttu-id="b3f37-688">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-688">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-689">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-689"></span></span>|
|<span data-ttu-id="b3f37-690">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-691">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-691"></span></span>|
|<span data-ttu-id="b3f37-692">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-693">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-693"></span></span>|
|<span data-ttu-id="b3f37-694">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-694">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-695">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-695"></span></span>|
|<span data-ttu-id="b3f37-696">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-697">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-697"></span></span>|
|<span data-ttu-id="b3f37-698">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-699">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-699"></span></span>|
|<span data-ttu-id="b3f37-700">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-701">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-701"></span></span>|
|<span data-ttu-id="b3f37-702">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-703">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-703"></span></span>|
|<span data-ttu-id="b3f37-704">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-705">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-705"></span></span>|
|<span data-ttu-id="b3f37-706">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-706">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-707">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-707"></span></span>|
|<span data-ttu-id="b3f37-708">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-709">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-709"></span></span>|
   
 <span data-ttu-id="b3f37-710">**GlobalSign の CA の SHA256 の G2 の検証の拡張**</span><span class="sxs-lookup"><span data-stu-id="b3f37-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-711">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-711">**Subject**</span></span>|
|<span data-ttu-id="b3f37-712">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-712"></span></span>|
|<span data-ttu-id="b3f37-713">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-713">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-714">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-714"></span></span>|
|<span data-ttu-id="b3f37-715">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-715">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-716">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-716"></span></span>|
|<span data-ttu-id="b3f37-717">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-717">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-718">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-718"></span></span>|
|<span data-ttu-id="b3f37-719">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-720">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-720"></span></span>|
|<span data-ttu-id="b3f37-721">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-722">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-722"></span></span>|
|<span data-ttu-id="b3f37-723">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-723">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-724">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-724"></span></span>|
|<span data-ttu-id="b3f37-725">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-726">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-726"></span></span>|
|<span data-ttu-id="b3f37-727">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-728">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-728"></span></span>|
|<span data-ttu-id="b3f37-729">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-730">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-730"></span></span>|
|<span data-ttu-id="b3f37-731">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-732">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-732"></span></span>|
|<span data-ttu-id="b3f37-733">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-734">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-734"></span></span>|
|<span data-ttu-id="b3f37-735">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-735">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-736">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-736"></span></span>|
|<span data-ttu-id="b3f37-737">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-738">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-738"></span></span>|
   
 <span data-ttu-id="b3f37-739">**GlobalSign の CA の SHA256 の G3 の検証の拡張**</span><span class="sxs-lookup"><span data-stu-id="b3f37-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-740">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-740">**Subject**</span></span>|
|<span data-ttu-id="b3f37-741">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-741"></span></span>|
|<span data-ttu-id="b3f37-742">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-742">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-743">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-743"></span></span>|
|<span data-ttu-id="b3f37-744">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-744">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-745">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-745"></span></span>|
|<span data-ttu-id="b3f37-746">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-746">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-747">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-747"></span></span>|
|<span data-ttu-id="b3f37-748">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-749">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-749"></span></span>|
|<span data-ttu-id="b3f37-750">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-751">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-751"></span></span>|
|<span data-ttu-id="b3f37-752">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-752">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-753">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-753"></span></span>|
|<span data-ttu-id="b3f37-754">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-755">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-755"></span></span>|
|<span data-ttu-id="b3f37-756">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-757">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-757"></span></span>|
|<span data-ttu-id="b3f37-758">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-759">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-759"></span></span>|
|<span data-ttu-id="b3f37-760">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-761">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-761"></span></span>|
|<span data-ttu-id="b3f37-762">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-763">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-763"></span></span>|
|<span data-ttu-id="b3f37-764">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-764">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-765">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-765"></span></span>|
|<span data-ttu-id="b3f37-766">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-767">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-767"></span></span>|
   
 <span data-ttu-id="b3f37-768">**GlobalSign 組織検証の CA の SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="b3f37-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-769">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-769">**Subject**</span></span>|
|<span data-ttu-id="b3f37-770">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-770"></span></span>|
|<span data-ttu-id="b3f37-771">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-771">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-772">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-772"></span></span>|
|<span data-ttu-id="b3f37-773">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-773">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-774">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-774"></span></span>|
|<span data-ttu-id="b3f37-775">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-775">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-776">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-776"></span></span>|
|<span data-ttu-id="b3f37-777">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-778">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-778"></span></span>|
|<span data-ttu-id="b3f37-779">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-780">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-780"></span></span>|
|<span data-ttu-id="b3f37-781">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-781">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-782">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-782"></span></span>|
|<span data-ttu-id="b3f37-783">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-784">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-784"></span></span>|
|<span data-ttu-id="b3f37-785">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-786">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-786"></span></span>|
|<span data-ttu-id="b3f37-787">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-788">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-788"></span></span>|
|<span data-ttu-id="b3f37-789">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-790">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-790"></span></span>|
|<span data-ttu-id="b3f37-791">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-792">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-792"></span></span>|
|<span data-ttu-id="b3f37-793">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-793">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-794">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-794"></span></span>|
|<span data-ttu-id="b3f37-795">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-796">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-796"></span></span>|
   
 <span data-ttu-id="b3f37-797">**GlobalSign 組織検証の CA の SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="b3f37-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-798">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-798">**Subject**</span></span>|
|<span data-ttu-id="b3f37-799">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-799"></span></span>|
|<span data-ttu-id="b3f37-800">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-800">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-801">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-801"></span></span>|
|<span data-ttu-id="b3f37-802">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-802">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-803">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-803"></span></span>|
|<span data-ttu-id="b3f37-804">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-804">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-805">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-805"></span></span>|
|<span data-ttu-id="b3f37-806">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-807">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-807"></span></span>|
|<span data-ttu-id="b3f37-808">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-809">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-809"></span></span>|
|<span data-ttu-id="b3f37-810">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-810">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-811">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-811"></span></span>|
|<span data-ttu-id="b3f37-812">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-813">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-813"></span></span>|
|<span data-ttu-id="b3f37-814">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-815">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-815"></span></span>|
|<span data-ttu-id="b3f37-816">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-817">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-817"></span></span>|
|<span data-ttu-id="b3f37-818">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-819">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-819"></span></span>|
|<span data-ttu-id="b3f37-820">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-821">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-821"></span></span>|
|<span data-ttu-id="b3f37-822">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-822">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-823">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-823"></span></span>|
|<span data-ttu-id="b3f37-824">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-825">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-825"></span></span>|
   
 <span data-ttu-id="b3f37-826">**機関 X3 を暗号化してみましょう**</span><span class="sxs-lookup"><span data-stu-id="b3f37-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-827">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-827">**Subject**</span></span>|
|<span data-ttu-id="b3f37-828">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-828"></span></span>|
|<span data-ttu-id="b3f37-829">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-829">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-830">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-830"></span></span>|
|<span data-ttu-id="b3f37-831">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-831">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-832">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-832"></span></span>|
|<span data-ttu-id="b3f37-833">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-833">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-834">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-834"></span></span>|
|<span data-ttu-id="b3f37-835">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-836">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-836"></span></span>|
|<span data-ttu-id="b3f37-837">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-838">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-838"></span></span>|
|<span data-ttu-id="b3f37-839">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-839">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-840">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-840"></span></span>|
|<span data-ttu-id="b3f37-841">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-842">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-842"></span></span>|
|<span data-ttu-id="b3f37-843">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-844">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-844"></span></span>|
|<span data-ttu-id="b3f37-845">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-846">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-846"></span></span>|
|<span data-ttu-id="b3f37-847">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-848">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-848"></span></span>|
|<span data-ttu-id="b3f37-849">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-850">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-850"></span></span>|
|<span data-ttu-id="b3f37-851">**AIA の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-851">**AIA URLs**</span></span>|
|<span data-ttu-id="b3f37-852">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-852"></span></span>|
|<span data-ttu-id="b3f37-853">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-853">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-854">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-854"></span></span>|
|<span data-ttu-id="b3f37-855">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-856">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-856"></span></span>|
   
 <span data-ttu-id="b3f37-857">**Microsoft IT の SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="b3f37-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-858">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-858">**Subject**</span></span>|
|<span data-ttu-id="b3f37-859">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-859"></span></span>|
|<span data-ttu-id="b3f37-860">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-860">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-861">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-861"></span></span>|
|<span data-ttu-id="b3f37-862">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-862">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-863">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-863"></span></span>|
|<span data-ttu-id="b3f37-864">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-864">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-865">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-865"></span></span>|
|<span data-ttu-id="b3f37-866">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-867">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-867"></span></span>|
|<span data-ttu-id="b3f37-868">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-869">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-869"></span></span>|
|<span data-ttu-id="b3f37-870">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-870">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-871">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-871"></span></span>|
|<span data-ttu-id="b3f37-872">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-873">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-873"></span></span>|
|<span data-ttu-id="b3f37-874">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-875">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-875"></span></span>|
|<span data-ttu-id="b3f37-876">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-877">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-877"></span></span>|
|<span data-ttu-id="b3f37-878">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-879">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-879"></span></span>|
|<span data-ttu-id="b3f37-880">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-881">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-881"></span></span>|
|<span data-ttu-id="b3f37-882">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-882">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-883">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-883"></span></span>|
   
 <span data-ttu-id="b3f37-884">**Microsoft IT の SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="b3f37-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-885">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-885">**Subject**</span></span>|
|<span data-ttu-id="b3f37-886">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-886"></span></span>|
|<span data-ttu-id="b3f37-887">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-887">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-888">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-888"></span></span>|
|<span data-ttu-id="b3f37-889">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-889">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-890">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-890"></span></span>|
|<span data-ttu-id="b3f37-891">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-891">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-892">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-892"></span></span>|
|<span data-ttu-id="b3f37-893">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-894">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-894"></span></span>|
|<span data-ttu-id="b3f37-895">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-896">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-896"></span></span>|
|<span data-ttu-id="b3f37-897">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-897">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-898">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-898"></span></span>|
|<span data-ttu-id="b3f37-899">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-900">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-900"></span></span>|
|<span data-ttu-id="b3f37-901">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-902">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-902"></span></span>|
|<span data-ttu-id="b3f37-903">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-904">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-904"></span></span>|
|<span data-ttu-id="b3f37-905">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-906">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-906"></span></span>|
|<span data-ttu-id="b3f37-907">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-908">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-908"></span></span>|
|<span data-ttu-id="b3f37-909">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-909">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-910">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-910"></span></span>|
|<span data-ttu-id="b3f37-911">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-912">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-912"></span></span>|
   
 <span data-ttu-id="b3f37-913">**Microsoft IT の TLS の CA 1**</span><span class="sxs-lookup"><span data-stu-id="b3f37-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-914">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-914">**Subject**</span></span>|
|<span data-ttu-id="b3f37-915">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-915"></span></span>|
|<span data-ttu-id="b3f37-916">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-916">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-917">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-917"></span></span>|
|<span data-ttu-id="b3f37-918">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-918">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-919">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-919"></span></span>|
|<span data-ttu-id="b3f37-920">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-920">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-921">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-921"></span></span>|
|<span data-ttu-id="b3f37-922">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-923">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-923"></span></span>|
|<span data-ttu-id="b3f37-924">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-925">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-925"></span></span>|
|<span data-ttu-id="b3f37-926">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-926">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-927">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-927"></span></span>|
|<span data-ttu-id="b3f37-928">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-929">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-929"></span></span>|
|<span data-ttu-id="b3f37-930">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-931">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-931"></span></span>|
|<span data-ttu-id="b3f37-932">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-933">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-933"></span></span>|
|<span data-ttu-id="b3f37-934">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-935">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-935"></span></span>|
|<span data-ttu-id="b3f37-936">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-937">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-937"></span></span>|
|<span data-ttu-id="b3f37-938">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-938">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-939">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-939"></span></span>|
|<span data-ttu-id="b3f37-940">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-941">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-941"></span></span>|
   
 <span data-ttu-id="b3f37-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="b3f37-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-943">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-943">**Subject**</span></span>|
|<span data-ttu-id="b3f37-944">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-944"></span></span>|
|<span data-ttu-id="b3f37-945">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-945">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-946">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-946"></span></span>|
|<span data-ttu-id="b3f37-947">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-947">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-948">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-948"></span></span>|
|<span data-ttu-id="b3f37-949">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-949">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-950">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-950"></span></span>|
|<span data-ttu-id="b3f37-951">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-952">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-952"></span></span>|
|<span data-ttu-id="b3f37-953">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-954">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-954"></span></span>|
|<span data-ttu-id="b3f37-955">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-955">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-956">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-956"></span></span>|
|<span data-ttu-id="b3f37-957">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-958">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-958"></span></span>|
|<span data-ttu-id="b3f37-959">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-960">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-960"></span></span>|
|<span data-ttu-id="b3f37-961">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-962">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-962"></span></span>|
|<span data-ttu-id="b3f37-963">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-964">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-964"></span></span>|
|<span data-ttu-id="b3f37-965">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-966">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-966"></span></span>|
|<span data-ttu-id="b3f37-967">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-967">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-968">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-968"></span></span>|
|<span data-ttu-id="b3f37-969">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-970">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-970"></span></span>|
   
 <span data-ttu-id="b3f37-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="b3f37-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-972">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-972">**Subject**</span></span>|
|<span data-ttu-id="b3f37-973">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-973"></span></span>|
|<span data-ttu-id="b3f37-974">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-974">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-975">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-975"></span></span>|
|<span data-ttu-id="b3f37-976">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-976">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-977">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-977"></span></span>|
|<span data-ttu-id="b3f37-978">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-978">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-979">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-979"></span></span>|
|<span data-ttu-id="b3f37-980">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-981">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-981"></span></span>|
|<span data-ttu-id="b3f37-982">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-983">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-983"></span></span>|
|<span data-ttu-id="b3f37-984">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-984">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-985">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-985"></span></span>|
|<span data-ttu-id="b3f37-986">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-987">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-987"></span></span>|
|<span data-ttu-id="b3f37-988">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-989">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-989"></span></span>|
|<span data-ttu-id="b3f37-990">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-991">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-991"></span></span>|
|<span data-ttu-id="b3f37-992">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-993">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-993"></span></span>|
|<span data-ttu-id="b3f37-994">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-995">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-995"></span></span>|
|<span data-ttu-id="b3f37-996">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-996">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-997">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-997"></span></span>|
|<span data-ttu-id="b3f37-998">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-999">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-999"></span></span>|
   
 <span data-ttu-id="b3f37-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-1001">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1001">**Subject**</span></span>|
|<span data-ttu-id="b3f37-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1002"></span></span>|
|<span data-ttu-id="b3f37-1003">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1003">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1004"></span></span>|
|<span data-ttu-id="b3f37-1005">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1005">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1006"></span></span>|
|<span data-ttu-id="b3f37-1007">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1008"></span></span>|
|<span data-ttu-id="b3f37-1009">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1010"></span></span>|
|<span data-ttu-id="b3f37-1011">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1012"></span></span>|
|<span data-ttu-id="b3f37-1013">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1014"></span></span>|
|<span data-ttu-id="b3f37-1015">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1016"></span></span>|
|<span data-ttu-id="b3f37-1017">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1018"></span></span>|
|<span data-ttu-id="b3f37-1019">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1020"></span></span>|
|<span data-ttu-id="b3f37-1021">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1022"></span></span>|
|<span data-ttu-id="b3f37-1023">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1024"></span></span>|
|<span data-ttu-id="b3f37-1025">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1026"></span></span>|
|<span data-ttu-id="b3f37-1027">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1028"></span></span>|
   
 <span data-ttu-id="b3f37-1029">**Symantec クラス 3 の EV SSL CA G3**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-1030">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1030">**Subject**</span></span>|
|<span data-ttu-id="b3f37-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1031"></span></span>|
|<span data-ttu-id="b3f37-1032">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1032">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1033"></span></span>|
|<span data-ttu-id="b3f37-1034">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b3f37-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1035"></span></span>|
|<span data-ttu-id="b3f37-1036">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1036">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1037"></span></span>|
|<span data-ttu-id="b3f37-1038">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1039"></span></span>|
|<span data-ttu-id="b3f37-1040">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1041"></span></span>|
|<span data-ttu-id="b3f37-1042">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1043"></span></span>|
|<span data-ttu-id="b3f37-1044">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1045"></span></span>|
|<span data-ttu-id="b3f37-1046">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1047"></span></span>|
|<span data-ttu-id="b3f37-1048">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1049"></span></span>|
|<span data-ttu-id="b3f37-1050">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1051"></span></span>|
|<span data-ttu-id="b3f37-1052">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1053"></span></span>|
|<span data-ttu-id="b3f37-1054">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1055"></span></span>|
|<span data-ttu-id="b3f37-1056">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1057"></span></span>|
|<span data-ttu-id="b3f37-1058">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1059"></span></span>|
   
 <span data-ttu-id="b3f37-1060">**Symantec クラス 3 セキュリティで保護されたサーバー CA - 第 4 世代**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-1061">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1061">**Subject**</span></span>|
|<span data-ttu-id="b3f37-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1062"></span></span>|
|<span data-ttu-id="b3f37-1063">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1063">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1064"></span></span>|
|<span data-ttu-id="b3f37-1065">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b3f37-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1066"></span></span>|
|<span data-ttu-id="b3f37-1067">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1067">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1068"></span></span>|
|<span data-ttu-id="b3f37-1069">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1070"></span></span>|
|<span data-ttu-id="b3f37-1071">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1072"></span></span>|
|<span data-ttu-id="b3f37-1073">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1074"></span></span>|
|<span data-ttu-id="b3f37-1075">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1076"></span></span>|
|<span data-ttu-id="b3f37-1077">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1078"></span></span>|
|<span data-ttu-id="b3f37-1079">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1080"></span></span>|
|<span data-ttu-id="b3f37-1081">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1082"></span></span>|
|<span data-ttu-id="b3f37-1083">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1084"></span></span>|
|<span data-ttu-id="b3f37-1085">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1086"></span></span>|
|<span data-ttu-id="b3f37-1087">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1088"></span></span>|
|<span data-ttu-id="b3f37-1089">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1090"></span></span>|
   
 <span data-ttu-id="b3f37-1091">**thawte SHA256 SSL CA**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-1092">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1092">**Subject**</span></span>|
|<span data-ttu-id="b3f37-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1093"></span></span>|
|<span data-ttu-id="b3f37-1094">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1094">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1095"></span></span>|
|<span data-ttu-id="b3f37-1096">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b3f37-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1097"></span></span>|
|<span data-ttu-id="b3f37-1098">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1098">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1099"></span></span>|
|<span data-ttu-id="b3f37-1100">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1101"></span></span>|
|<span data-ttu-id="b3f37-1102">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1103"></span></span>|
|<span data-ttu-id="b3f37-1104">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1105"></span></span>|
|<span data-ttu-id="b3f37-1106">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1107"></span></span>|
|<span data-ttu-id="b3f37-1108">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1109"></span></span>|
|<span data-ttu-id="b3f37-1110">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1111"></span></span>|
|<span data-ttu-id="b3f37-1112">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1113"></span></span>|
|<span data-ttu-id="b3f37-1114">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1115"></span></span>|
|<span data-ttu-id="b3f37-1116">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1117"></span></span>|
|<span data-ttu-id="b3f37-1118">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1119"></span></span>|
|<span data-ttu-id="b3f37-1120">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1121"></span></span>|
   
 <span data-ttu-id="b3f37-1122">**Verizon akamai 社 SureServer CA G14-SHA2**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b3f37-1123">**件名**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1123">**Subject**</span></span>|
|<span data-ttu-id="b3f37-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1124"></span></span>|
|<span data-ttu-id="b3f37-1125">**発行者**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1125">**Issuer**</span></span>|
|<span data-ttu-id="b3f37-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1126"></span></span>|
|<span data-ttu-id="b3f37-1127">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1127">**Serial Number**</span></span>|
|<span data-ttu-id="b3f37-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1128"></span></span>|
|<span data-ttu-id="b3f37-1129">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="b3f37-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1130"></span></span>|
|<span data-ttu-id="b3f37-1131">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b3f37-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1132"></span></span>|
|<span data-ttu-id="b3f37-1133">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="b3f37-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1134"></span></span>|
|<span data-ttu-id="b3f37-1135">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="b3f37-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1136"></span></span>|
|<span data-ttu-id="b3f37-1137">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1138"></span></span>|
|<span data-ttu-id="b3f37-1139">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b3f37-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1140"></span></span>|
|<span data-ttu-id="b3f37-1141">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b3f37-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1142"></span></span>|
|<span data-ttu-id="b3f37-1143">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1144"></span></span>|
|<span data-ttu-id="b3f37-1145">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b3f37-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1146"></span></span>|
|<span data-ttu-id="b3f37-1147">**AIA の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="b3f37-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1148"></span></span>|
|<span data-ttu-id="b3f37-1149">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="b3f37-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1150"></span></span>|
|<span data-ttu-id="b3f37-1151">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="b3f37-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="b3f37-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="b3f37-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="b3f37-1153">追加の証明書のパス</span><span class="sxs-lookup"><span data-stu-id="b3f37-1153">Additional certificate paths</span></span>
<span data-ttu-id="b3f37-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="b3f37-1154"></span></span>

<span data-ttu-id="b3f37-1155">次には、上は含まれていないし、時間の経過と共に上のリストと結合されている従来の証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3f37-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
```
evsecure-aia.verisign.com
sa.symcb.com
sd.symcb.com
*.omniroot.com
*.verisign.com
*.symcb.com
*.symcd.com
*.verisign.net
*.geotrust.com
*.entrust.net
*.public-trust.com
EVIntl-ocsp.verisign.com
EVSecure-ocsp.verisign.com
isrg.trustid.ocsp.identrust.com
ocsp.digicert.com
ocsp.entrust.net
ocsp.globalsign.com/ExtendedSSLSHA256CACross
ocsp.globalsign.com/rootr1
ocsp.globalsign.com/rootr2
ocsp2.globalsign.com/rootr3
ocsp.int-x3.letsencrypt.org/
ocsp.msocsp.com
ocsp.omniroot.com/baltimoreroot
ocsp2.globalsign.com/gsextendvalsha2g3r3
ocsp2.globalsign.com/gsorganizationvalsha2g2
ocsp2.globalsign.com/gsorganizationvalsha2g3
ocsp2.globalsign.com/rootr3
ocspx.digicert.com
s2.symcb.com
sr.symcd.com
su.symcd.com
vassg142.ocsp.omniroot.com
cdp1.public-trust.com/CRL/Omniroot2025.crl
crl.entrust.net/2048ca.crl
crl.entrust.net/g2ca.crl
crl.entrust.net/level1k.crl
crl.entrust.net/rootca1.crl
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl
crl.globalsign.com/gsorganizationvalsha2g3.crl
crl.globalsign.com/root.crl
crl.globalsign.net/root-r2.crl
crl.globalsign.com/root-r3.crl
crl.globalsign.net/root.crl
crl.identrust.com/DSTROOTCAX3CRL.crl
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl3.digicert.com/DigiCertGlobalRootCA.crl
crl3.digicert.com/sha2-ev-server-g1.crl
crl3.digicert.com/sha2-ha-server-g5.crl
crl3.digicert.com/ssca-sha2-g5.crl
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl4.digicert.com/DigiCertGlobalRootCA.crl
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl
crl4.digicert.com/sha2-ev-server-g1.crl
crl4.digicert.com/sha2-ha-server-g5.crl
crl4.digicert.com/ssca-sha2-g5.crl
EVIntl-crl.verisign.com/EVIntl2006.crl
EVSecure-crl.verisign.com/pca3-g5.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl
s1.symcb.com/pca3-g5.crl
sr.symcb.com/sr.crl
su.symcb.com/su.crl
vassg142.crl.omniroot.com/vassg142.crl
aia.entrust.net/l1k-chain256.cer
apps.identrust.com/roots/dstrootcax3.p7c
https://cacert.a.omniroot.com/vassg142.crt
https://cacert.a.omniroot.com/vassg142.der
https://cacert.omniroot.com/baltimoreroot.crt
https://cacert.omniroot.com/baltimoreroot.der
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt
cert.int-x3.letsencrypt.org/
EVIntl-aia.verisign.com/EVIntl2006.cer
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt
sr.symcb.com/sr.crt
su.symcb.com/su.crt
https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt
https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt
www.microsoft.com/pki/mscorp/msitwww1.crt
www.microsoft.com/pki/mscorp/msitwww2.crt

```


